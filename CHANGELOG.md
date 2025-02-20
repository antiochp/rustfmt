# Changelog

## [Unreleased]

## [0.3.2] 2017-12-15

### Changed

- Warn when unkown configuration option is used.

### Fixed

- Rustup to `rustc 1.24.0-nightly (0077d128d 2017-12-14)`.

## [0.3.1] 2017-12-11

### Added

- Add `error_on_unformatted` configuration option.
- Add `--error-on-unformatted` command line option.

### Changed

- Do not report formatting errors on comments or strings by default.
- Rename `error_on_line_overflow_comments` to `error_on_unformatted`.

### Fixed

- Fix formatting bugs.
- Fix adding a trailing whitespace inside code block when `wrap_comments = true`.

## [0.3.0] 2017-12-11

### Added

- Support nested imports.

### Changed

- Do not report errors on skipped items.
- Do not format code block inside comments when `wrap_comments = true`.
- Keep vertical spaces between items within range.
- Format `format!` and its variants using compressed style.
- Format `write!` and its variants using compressed style.
- Format **simple** array using compressed style.

### Fixed

- Fix `rustfmt --package package_name` not working properly.
- Fix formatting bugs.

## [0.2.17] 2017-12-03

### Added

- Add `blank_lines_lower_bound` and `blank_lines_upper_bound` configuration options.

### Changed

- Combine configuration options related to width heuristic into `width_heuristic`.
- If the match arm's body is `if` expression, force to use block.

### Fixed

- Fix `cargo fmt --all` being trapped in an infinite loop.
- Fix many formatting bugs.

### Removed

- Remove legacy configuration options.

## [0.2.16] 2017-11-21

### Added

- Remove empty lines at the beginning of the file.
- Soft wrapping on doc comments.

### Changed

- Break before `|` when using multiple lines for match arm patterns.
- Combine `control_style`, `where_style` and `*_indent` config options into `indent_style`.
- Combine `item_brace_style` and `fn_brace_style` config options into `brace_style`.
- Combine config options related spacing around colons into `space_before_colon` and `space_after_colon`.

### Fixed

- Fix many bugs.

## [0.2.15] 2017-11-08

### Added

- Add git-fmt tool
- `where_single_line` configuration option.

### Changed

- Rename `chain_one_line_max` to `chain_width`.
- Change the suffix of indent-related configuration options to `_indent`.

## [0.2.14] 2017-11-06

### Fixed

- Rustup to the latest nightly.

## [0.2.13] 2017-10-30

### Fixed

- Rustup to the latest nightly.

## [0.2.12] 2017-10-29

### Fixed

- Fix a bug that `cargo fmt` hangs forever.

## [0.2.11] 2017-10-29

### Fixed

- Fix a bug that `cargo fmt` crashes.

## [0.2.10] 2017-10-28

## [0.2.9] 2017-10-16

## [0.2.8] 2017-09-28

## [0.2.7] 2017-09-21

### Added

- `binop_separator` configuration option (#1964).

### Changed

- Use horizontal layout for function call with a single argument.

### Fixed

- Fix panicking when calling `cargo fmt --all` (#1963).
- Refactorings & faster rustfmt.

## [0.2.6] 2017-09-14

### Fixed

- Fix a performance issue with nested block (#1940).
- Refactorings & faster rustfmt.

## [0.2.5] 2017-08-31

### Added

- Format and preserve attributes on statements (#1933).

### Fixed

- Use getters to access `Span` fields (#1899).

## [0.2.4] 2017-08-30

### Added

- Add support for `Yield` (#1928).

## [0.2.3] 2017-08-30

### Added

- `multiline_closure_forces_block` configuration option (#1898).
- `multiline_match_arm_forces_block` configuration option (#1898).
- `merge_derives` configuration option (#1910).
- `struct_remove_empty_braces` configuration option (#1930).
- Various refactorings.

### Changed

- Put single-lined block comments on the same line with list-like structure's item (#1923).
- Preserve blank line between doc comment and attribute (#1925).
- Put the opening and the closing braces of enum and struct on the same line, even when `item_brace_style = "AlwaysNextLine"` (#1930).

### Fixed

- Format attributes on `ast::ForeignItem` and take max width into account (#1916).
- Ignore empty lines when calculating the shortest indent width inside macro with braces (#1918).
- Handle tabs properly inside macro with braces (#1918).
- Fix a typo in `compute_budgets_for_args()` (#1924).
- Recover comment between keyword (`impl` and `trait`) and `{` which used to get removed (#1925).
