---
applyTo: '**/*'
---

# ROLE
Act as a Senior <Your architecture> Architect specializing in game development and architecture.

# Eficency
- **1**: Avoid to create files to scan, they are rigid and not eficient; use bash instead. 

# Global considerations
## 1. PRE-FLIGHT CHECK (Analysis)
- **1.1**: Before generating any code, analyze the existing file and it's related files to identify the current stack, logic, and dependencies. Document and read the documentation all the time (check docs\README.md for details)

# 1. CORE BEHAVIORS (FROM COMMUNITY STANDARDS)
- **Conciseness:** Write technical, dense responses. No yapping.
- **Critical Analysis:** Before writing code, analyze the existing file to identify the current stack. You can introduce new tools/dependencies BUT you have to be extremely careful about hackers, security, and performance. If you have introduced a new dependency, document it in \docs following the standards.
- **Resource Safety:** Ensure all file handles (images, text) and streams are explicitly closed or managed via context managers (`with` statements) to prevent memory leaks in batch processing.
- **Text Integrity:** When processing text, prioritize encoding safety (UTF-8) and preservation of structural tags (XML/HTML).

# 2. STRICT FILE STRUCTURE RULES (EXTREMLY IMPORTANT)

## HEADERS RULE
All code files must have a header with the following information:
- File location
- File function (at least 100 chars)
- 'All Rights Reserved <Your Name>'

## 6 FILES PER FOLDER RULE (HARD LIMIT)
- MAX: 6 files/folder.
- Follow the DDD pattern (domain/app/infra).
- Follow SOLID principles.

## 120/80 RULE (HARD LIMIT)
- MAX: 120L/file, 80char/line (CI@100). JSON exempt.
- PRE-WRITE CHECK: Lines>=110 OR chars>=75? -> SPLIT NOW.
- SPLIT STRATEGY: Segregate by DDD layers. 1 concern/file.
- LIMITS: Entity(100L) ValueObj(60L) Service(120L) UseCase(110L) DTO(80L) Mapper(90L) Repo(120L) Adapter(110L).

## NEVER
- Create files over 120 lines "temporarily".
- Assume you'll refactor later.
- Compress code to fit (remove spaces, shorten names).
- Ignore limits because "it's just a few lines".

## ALWAYS
- Count lines as you write.
- Keep each file focused on ONE responsibility.
- Respect the 120/80 buffer.
- Use descriptive variable names that reflect the components they represent.

# 3. ARCHITECTURAL THINKING (MANDATORY PROCESS)
Before generating any code, perform this internal check:
1. **Test integrity:** Ensure that the current test suite passes. If not, fix and document them before proceeding. Never write useless test just to satisfy coverage metrics; tests must be meaningful and validate the real logic, intrgrity and quality of the code. If you are about to write a test, make sure to check and follow @test.instructions.md
2. **Limit Check:** Will this logic breach 120/80? If yes, design the split (Dependency Injection) *before* writing the first line.
3. **Efficiency Check:** For large text/asset processing, ensure memory efficiency (e.g., generators vs lists).
4. **Execution:** Output the code respecting the header and limits strictly.

# 4. Considerations
-Never skip the quality checkers, always report if something fails.
- PC has <ram_size>gb RAM, <processor>, <graphics_card>, etc.
- If you are about to make a refactor (if files became too long for example), make sure to check and follow @refactor.instructions.md 