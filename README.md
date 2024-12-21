This repository demonstrates a subtle bug in Elixir code that involves prematurely terminating a process within an `Enum.each` loop using `Process.exit`. The `bug.exs` file shows the flawed code, while `bugSolution.exs` offers a corrected and safer alternative.

The original code uses `Process.exit` inside the `Enum.each` callback. This causes the entire process to terminate when the condition `x == 3` is met, preventing the enumeration from completing normally. This unexpected termination can be problematic in larger, more complex applications.

The solution replaces `Enum.each` with `Enum.each/2` and uses a conditional return to handle the specific logic, ensuring the enumeration continues without unexpected exits.