POST-REFACTOR INSTRUCTIONS (STRICT VALIDATION)
Context: You have just completed a large refactor or feature that affected core files. Your sole mission now is to demonstrate, with irrefutable evidence, that there are NO regressions or malicious or negligent simplifications.

Golden Rules (mandatory compliance or admit failure):

Absolute Functional Parity (Zero Regression):

Compare the before vs. after behavior for EVERY critical public and private function/method you modified.

Generate a mapping matrix listing the 100 pre-existing processes/flows (or those that exist). For each, indicate: [OK] if the output/side effect is identical, or [DEVIATION] if it changed.

Complexity Preservation (Anti-simplification for mediocrity):

Reducing the cyclomatic complexity or nesting depth of any logical block is not permitted unless strictly for bug fixes or demonstrable performance improvements.

Provide a comparative table of Cyclomatic Complexity (CC) per function (e.g., function A: CC 15 -> CC 15). If it decreased, justify it with traceability to the requirement that necessitates it.

Border Case Validation:

Take the set of boundary cases handled by the previous code (nulls, numerical limits, concurrent states, thrown exceptions). Demonstrate that they are all still handled exactly the same way. If you removed a try-catch or a defensive if statement, justify why it was unnecessary.

Test Suite Integrity (Anti-cheating):

Run the pre-existing tests. It's not acceptable for them to pass if you modified them to make them pass. Verify that the line coverage and mutation score are maintained or increased. If a test was modified, list which one and the exact reason.

New Feature Added:

Demonstrate that the new feature was inserted without reducing the existing 100 complexity. The total system complexity (sum of the CC of all modules) must be >= the previous CC plus the CC of the new feature.

REQUIRED EVIDENCE TO SUBMIT:

A structural diff (not just text) indicating which lines of logic changed.

A forensic report containing the tables from points 1, 2, and 3.

ADMISSION CLAUSE (IF YOU FAIL):
If you find ANY mutilation, loss of feature, or unjustified simplification, do not hide it. Explicitly admit it in a block called [ADMISSION OF TECHNICAL DEBT] where you specify:

File and exact line.

What was lost or simplified.

Why it happened (time pressure? misunderstanding of the domain? unforeseen side effect?).

3-step plan to restore it without breaking the new feature.

If you don't provide this evidence, I will assume the refactor is corrupt and request a full rollback.