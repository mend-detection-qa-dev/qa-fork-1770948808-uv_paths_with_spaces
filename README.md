# Test: Paths with Spaces

## Objective
Verify that the dependency tree builder correctly handles project paths containing spaces.

## What This Tests
- Parsing projects in directories with spaces
- File path resolution with spaces
- Cross-platform space handling
- Command-line argument parsing with spaces

## Test Structure
```
paths_with_spaces/
└── path with spaces/
    └── project/
        ├── pyproject.toml
        └── uv.lock
```

## Expected Behavior
- Tool should handle space-containing paths gracefully
- Should properly quote paths when needed
- Should work on Windows, macOS, and Linux
- Should not fail with "file not found" errors

## Common Issues
- Shell argument parsing issues
- Path concatenation bugs
- Missing quotes around paths
- Platform-specific path handling

## Error Scenarios to Test
1. ✅ Space in parent directory
2. ✅ Space in project directory name
3. ✅ Multiple spaces in path
4. ✅ Leading/trailing spaces
5. ✅ Tab characters mistaken for spaces

## Success Criteria
- No crashes when scanning paths with spaces
- Correct file detection
- Accurate dependency tree output
- Same results as paths without spaces
