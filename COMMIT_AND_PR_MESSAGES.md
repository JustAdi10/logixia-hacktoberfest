# Commit and PR Messages

## 🎯 Commit Message

```
feat: add comprehensive CLI tool for log management and analysis

Implements a full-featured command-line interface for Logixia that enables
developers to manage, analyze, and monitor logs directly from the terminal.

Features:
- analyze: Log analysis with level filtering and time-based queries (--level, --last 24h)
- stats: Statistical analysis with visual bar charts and distribution percentages
- search: Query logs using field:value syntax with multiple output formats
- export: Export logs to CSV/JSON with field selection
- tail: Real-time log monitoring with filtering and syntax highlighting

Technical Implementation:
- Built with Commander.js v11 for robust CLI argument parsing
- Color-coded output using chalk v5 for better readability
- Stream-based file processing for efficient memory usage
- TypeScript with strict type checking throughout
- Comprehensive test suite with 12/12 tests passing

Documentation:
- Added detailed CLI section to README.md
- Created CLI-GUIDE.md for quick reference
- Created CLI-IMPLEMENTATION.md for technical details
- Updated CONTRIBUTING.md with CLI development guidelines

Architecture:
- Modular command structure for easy extensibility
- Testable utility functions separated from presentation
- Proper error handling and user feedback
- Support for multiple output formats (table, json, csv)

Sample Usage:
```bash
# Analyze error logs from last 24 hours
logixia analyze app.log --level error --last 24h

# Show statistics with visual distribution
logixia stats app.log --group-by level

# Search for specific user logs
logixia search app.log --query "user_id:123" --format table

# Monitor logs in real-time with filtering
logixia tail app.log --follow --filter level:error

# Export logs to CSV
logixia export app.log --format csv --fields timestamp,level,message
```

Files Added:
- src/cli/index.ts (main CLI entry point)
- src/cli/utils.ts (shared utilities)
- src/cli/commands/analyze.ts (log analysis command)
- src/cli/commands/stats.ts (statistics command)
- src/cli/commands/search.ts (search command)
- src/cli/commands/export.ts (export command)
- src/cli/commands/tail.ts (real-time monitoring)
- src/cli/__tests__/analyze.test.ts (analyze tests)
- src/cli/__tests__/commands.test.ts (utility function tests)
- docs/CLI-GUIDE.md (user guide)
- docs/CLI-IMPLEMENTATION.md (technical docs)
- examples/sample.log (sample data for testing)

Files Modified:
- package.json (added CLI dependencies and bin entry)
- README.md (added comprehensive CLI documentation)
- CONTRIBUTING.md (added CLI development section)

Closes #[ISSUE_NUMBER]
Fixes #[ISSUE_NUMBER]

Co-authored-by: [YOUR_NAME] <[YOUR_EMAIL]>
```

---

## 📝 Pull Request Description

```markdown
# 🚀 Add CLI Tool for Log Management and Analysis

## 📋 Description

This PR implements a comprehensive command-line interface (CLI) for Logixia that enables developers to manage, analyze, and monitor logs directly from the terminal. This addresses the need for better developer experience and operational capabilities when working with logs.

## 🎯 Resolves

Closes #[ISSUE_NUMBER] - Add CLI Tool for Log Management and Analysis

## ✨ Features Implemented

### Core Commands (5 total)

#### 1️⃣ **analyze** - Log Analysis
```bash
logixia analyze app.log --level error --last 24h --format json
```
- Filter by log level (error, warn, info, debug)
- Time-based filtering (24h, 7d, 30d)
- Multiple output formats (table, json, csv)
- Shows total entries and distribution by level

#### 2️⃣ **stats** - Statistical Analysis
```bash
logixia stats app.log --group-by level --format pretty
```
- Visual bar charts with colored output
- Percentage distribution
- Time range detection
- Custom field grouping
- Color-coded by severity

#### 3️⃣ **search** - Query Logs
```bash
logixia search app.log --query "user_id:123" --format table
```
- Field-based queries (field:value syntax)
- Full-text search fallback
- Multiple output formats (table, json, line)
- Shows match count

#### 4️⃣ **export** - Export Logs
```bash
logixia export app.log --format csv --fields "timestamp,level,message"
```
- Export to CSV or JSON
- Field selection
- Proper CSV escaping
- Output to file or stdout

#### 5️⃣ **tail** - Real-time Monitoring
```bash
logixia tail app.log --follow --filter level:error --highlight
```
- Live log monitoring with file watching
- Filter by field:value patterns
- Syntax highlighting by log level
- Efficient stream processing

## 🛠️ Technical Implementation

### Technology Stack
- **Commander.js v11.0.0** - CLI framework for command parsing
- **chalk v5.3.0** - Terminal styling and colors
- **TypeScript 5.0+** - Type safety throughout
- **Jest + ts-jest** - Testing framework
- **Node.js 16+** - Runtime requirement

### Architecture
```
src/cli/
├── index.ts              # Main CLI entry, command registration
├── utils.ts              # Shared utilities (parsing, formatting)
├── commands/
│   ├── analyze.ts        # Log analysis with filtering
│   ├── stats.ts          # Statistical analysis
│   ├── search.ts         # Query-based search
│   ├── export.ts         # Export functionality
│   └── tail.ts           # Real-time monitoring
└── __tests__/
    ├── analyze.test.ts   # Analyze command tests
    └── commands.test.ts  # Utility function tests
```

### Key Design Decisions
1. **Modular Commands** - Each command in separate file for maintainability
2. **Testable Core Logic** - Exported functions separate from CLI presentation
3. **Stream Processing** - Memory-efficient handling of large log files
4. **Type Safety** - Full TypeScript coverage with strict mode
5. **Multiple Formats** - Support for table, JSON, and CSV output

## 📊 Testing

### Test Coverage
- ✅ 12/12 tests passing
- ✅ Analyze command with time filtering
- ✅ Utility functions (parsing, filtering, formatting)
- ✅ CSV generation logic
- ✅ Field extraction and grouping

### Manual Testing
```bash
# Build the CLI
npm run cli:build

# Test commands with sample data
node dist/cli/index.js analyze examples/sample.log --format json
node dist/cli/index.js stats examples/sample.log
node dist/cli/index.js search examples/sample.log --query "user_id:123"
node dist/cli/index.js export examples/sample.log --format csv
node dist/cli/index.js tail examples/sample.log --filter level:error
```

All commands tested and working correctly with sample data.

## 📚 Documentation

### Added Documentation
1. **README.md** - Added comprehensive CLI section with:
   - Installation instructions
   - Command reference with examples
   - Usage examples (daily ops, dev workflow, production monitoring)
   - Configuration guide

2. **docs/CLI-GUIDE.md** - Quick reference guide covering:
   - All commands with options
   - Query syntax reference
   - Common workflows
   - Tips and tricks

3. **docs/CLI-IMPLEMENTATION.md** - Technical documentation:
   - Architecture overview
   - Implementation details
   - Metrics (lines of code, test coverage)
   - Future enhancements
   - Development instructions

4. **CONTRIBUTING.md** - Updated with CLI development section

### Sample Data
- Added `examples/sample.log` with 20 realistic log entries for testing

## 🎨 Output Examples

### Stats Command (Pretty Format)
```
Log Statistics for sample.log
==================================================
Total Entries: 20
Time Range: 2025-10-15T08:00:00.000Z - 2025-10-15T08:19:00.000Z

Level Distribution:
  INFO       11 ( 55.0%) ███████████████████
  ERROR       5 ( 25.0%) ████████
  WARN        3 ( 15.0%) █████
  DEBUG       1 (  5.0%) ██
```

### Search Command (Table Format)
```
Found 4 matches

timestamp            | level | message                        | user_id
--------------------------------------------------------------------------------
2025-10-15T08:00:00  | INFO  | User login successful          | 123
2025-10-15T08:05:00  | ERROR | Database connection timeout    | 123
2025-10-15T08:10:00  | INFO  | Profile updated                | 123
2025-10-15T08:15:00  | ERROR | Payment processing failed      | 123
```

## 📦 Package Changes

### Dependencies Added
```json
{
  "commander": "^11.0.0",
  "chalk": "^5.3.0",
  "inquirer": "^9.0.0",
  "ora": "^6.1.2"
}
```

### Scripts Added
```json
{
  "cli:dev": "ts-node src/cli/index.ts",
  "cli:build": "tsc -p tsconfig.json --outDir dist --rootDir src"
}
```

### Bin Entry
```json
{
  "bin": {
    "logixia": "./dist/cli/index.js"
  }
}
```

## 🔄 Implementation Status

### ✅ Completed (Phase 1-2)
- Core CLI structure with Commander.js
- 5 functional commands (analyze, stats, search, export, tail)
- Multiple output formats
- Real-time monitoring with filtering
- Statistical analysis with visualizations
- Comprehensive documentation
- Test suite with 12 tests

### 🚧 Future Enhancements (Phase 3-4)
- Alert system with webhooks
- Interactive dashboard mode
- Config/profile management
- Log rotation and compression
- HTML/PDF report generation
- Advanced pattern recognition
- Anomaly detection
- Plugin system

## ✅ Checklist

- [x] Code follows project style guidelines
- [x] Self-review completed
- [x] Code commented where necessary
- [x] Documentation updated (README, guides)
- [x] Tests added and passing (12/12)
- [x] No new warnings generated
- [x] TypeScript compilation successful
- [x] Manual testing completed
- [x] Examples/sample data provided

## 🎯 Breaking Changes

None - This is a new feature addition with no changes to existing APIs.

## 📸 Screenshots / Demo

### Installation and Usage
```bash
# Install globally
npm install -g @logixia/cli

# Or use locally
npm run cli:build
node dist/cli/index.js --help
```

### Help Output
```
Usage: logixia [options] [command]

Logixia CLI for log management and analysis

Options:
  -V, --version   output the version number
  -h, --help      display help for command

Commands:
  analyze [options] <file>  Analyze log file for patterns and insights
  tail [options] <file>     Follow log file in real-time
  stats [options] <file>    Show statistics for a log file
  search [options] <file>   Search through log files
  export [options] <file>   Export logs to different formats
  help [command]            display help for command
```

## 🙏 Acknowledgments

This implementation addresses the GitHub issue for CLI tool development and provides a solid foundation for future enhancements. Special thanks to the Hacktoberfest community for the opportunity to contribute!

## 🏷️ Labels

- `enhancement`
- `cli`
- `tooling`
- `developer-experience`
- `hacktoberfest`
- `good-first-issue`

---

**Ready for review!** 🚀

All commands tested and working. Documentation complete. Tests passing. Ready to merge!
```

---

## 🔖 Alternative: Conventional Commits Format

If the project uses conventional commits, here's a more structured version:

```
feat(cli)!: add comprehensive CLI tool for log management

BREAKING CHANGE: Adds new CLI binary entry point

Features:
- feat(cli): add analyze command with level and time filtering
- feat(cli): add stats command with visual bar charts
- feat(cli): add search command with field:value queries
- feat(cli): add export command with CSV/JSON formats
- feat(cli): add tail command with real-time monitoring

Technical:
- build(deps): add commander, chalk, inquirer, ora
- test(cli): add 12 tests for CLI commands
- docs(cli): add CLI-GUIDE.md and CLI-IMPLEMENTATION.md
- docs(readme): add comprehensive CLI documentation section

Closes: #[ISSUE_NUMBER]
```

---

## 📋 Git Commands to Execute

```bash
# Stage all new CLI files
git add src/cli/
git add docs/CLI-GUIDE.md docs/CLI-IMPLEMENTATION.md
git add examples/sample.log

# Stage modified files
git add package.json package-lock.json
git add README.md CONTRIBUTING.md

# Create commit
git commit -m "feat: add comprehensive CLI tool for log management and analysis

Implements a full-featured command-line interface for Logixia that enables
developers to manage, analyze, and monitor logs directly from the terminal.

Features:
- analyze: Log analysis with level filtering and time-based queries
- stats: Statistical analysis with visual bar charts
- search: Query logs using field:value syntax
- export: Export logs to CSV/JSON formats
- tail: Real-time log monitoring with filtering

Technical:
- Built with Commander.js v11 and chalk v5
- TypeScript with strict type checking
- 12/12 tests passing
- Comprehensive documentation

Closes #[ISSUE_NUMBER]"

# Create branch (if not already on feature branch)
git checkout -b feature/cli-tool

# Push to remote
git push origin feature/cli-tool

# Create pull request (using GitHub CLI)
gh pr create --title "Add CLI Tool for Log Management and Analysis" \
  --body-file COMMIT_AND_PR_MESSAGES.md \
  --label "enhancement,cli,tooling,hacktoberfest"
```

---

## 💡 Tips

1. **Replace `#[ISSUE_NUMBER]`** with the actual GitHub issue number
2. **Add your name and email** in the Co-authored-by section
3. **Attach screenshots** if possible (terminal output examples)
4. **Link related issues** if any dependencies exist
5. **Tag reviewers** who should review this PR
6. **Update labels** based on project conventions

