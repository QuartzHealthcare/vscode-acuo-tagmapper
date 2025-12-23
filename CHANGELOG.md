# Change Log

## [1.0.0] - 2025-12-24

### Added
- Full syntax highlighting support based on the January 2025 TagMapper Product Guide
- All tag modification commands (add, sub, leave, replacetext, convertIntToString, convertStringToInt, removeInvalidChars, tagAlias, process)
- Sequence commands (SEQ_Begin, SEQ_End, SEQ_BeginItem, SEQ_EndItem, SEQ_Open, SEQ_Close, SEQ_OpenItem, SEQ_CloseItem)
- MPI/PIX commands (replacePIDUsingPIX, addDemographic, getReturnedDemographic, issuePdqQuery)
- Database table modification commands (modifyTable, setColumn, where, addRow, deleteRow, updateRow)
- Custom extension commands (AddPassedValue, GetReturnValue, CALL_TMExtension)
- Reserved names/variables (%NAME% format)
- All configuration options (AllowBlankTags, AuditLogging, CacheTags, etc.)
- Process control commands (report, StopHexTrace, DisableCommandWarningEvent)
- Condition operators (begins, ends, contains, within, after, before, startsWith, endsWith, Length())
- Support for `--` double-dash line comments
- Support for `/* */` block comments
- Numeric literals (`#num#` format)
- Column name references (`(columnName)` format)
- Tag aliases (`@aliasName` format)
- Additional status values (`<CONFORMS>`, `<NUMERIC>`)
- Setting values (Single, Any, Log, Ignore, Warn, Truncate, Error, COERCE, CORRECT, PATIENT, STUDY, SERIES)
- Support for unframed DICOM tag format (8 hex characters without comma)

## [0.0.1] - Initial Release

### Added
- Basic syntax highlighting for TagMapper commands
- Control keywords (IF, THEN, ELSE, ENDIF, ORIF, ANDIF, STOP, REPEAT)
- Basic operations (Prepend, Replace, Create, Case, Append, Trim, Delete, Clear, Set)
- Constants (UPPER, EXISTS, NULL, TRUE, FALSE)
- DICOM tag recognition (0010,0020 format)
- Double-quoted strings
- Line comments (//)
