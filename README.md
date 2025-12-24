# TagMapper Syntax Highlighting

Syntax highlighting for Acuo TagMapper script files based on the Hyland Acuo TagMapper January 2025 Product Guide.

## Features

- Full syntax highlighting for all TagMapper commands and constructs
- DICOM tag recognition (both `0010,0020` and `00100020` formats)
- Support for comments (`//`, `--`, and `/* */` block comments)
- Reserved names/variables (`%NAME%` format)
- Tag aliases (`@aliasName` format)
- Database column references (`(columnName)` format)
- Numeric literals (`#num#` format)
- Status values (`<EXISTS>`, `<NULL>`, `<CONFORMS>`, `<NUMERIC>`)

## Supported Commands

### Control Flow
- `IF`, `THEN`, `ELSE`, `ENDIF`, `ORIF`, `ANDIF`
- `STOP`, `REPEAT`
- `fail` (highlighted as error/warning)

### Tag Modification
- `add`, `sub` - Arithmetic operations
- `append`, `prepend` - Add data to tag
- `case` - Change case (upper, lower, capfirst)
- `clear`, `delete` - Remove tag data or tag
- `create`, `replace` - Create or replace tag values
- `leave`, `trim` - Keep or remove characters
- `replacetext` - Substring replacement
- `convertIntToString`, `convertStringToInt` - Type conversion
- `removeInvalidChars` - Character cleanup
- `tagAlias` - Define tag aliases
- `process` - Execute commands from DB column

### Sequence Commands
- `SEQ_Begin`, `SEQ_End` - Sequence boundaries
- `SEQ_BeginItem`, `SEQ_EndItem` - Item boundaries
- `SEQ_Open`, `SEQ_Close` - Open/close for modification
- `SEQ_OpenItem`, `SEQ_CloseItem` - Item modification

### MPI/PIX Commands
- `replacePIDUsingPIX` - PIX patient ID translation
- `addDemographic`, `getReturnedDemographic` - PDQ demographics
- `issuePdqQuery` - Issue PDQ query

### Database Commands
- `modifyTable` - Start modification block
- `setColumn`, `where` - Define columns and criteria
- `addRow`, `deleteRow`, `updateRow` - Row operations

### Configuration Commands
- `set`, `readfile`
- Configuration options: `AllowBlankTags`, `AuditLogging`, `CacheTags`, `CacheTagsLife`, `CreateAsReplace`, `CreateOriginalAttributesSequence`, `Dbhit`, `Dbmiss`, `DbTable`, `EnableAE`, `FailOnError`, `IgnorePixNotFoundReturn`, `LogAge`, `LogPath`, `LogSize`, `OriginalAttributesReasonForChange`, `PdqAccess`, `PdqFile`, `PixAccess`, `PixCache`, `PixFile`, `SourceAssigningAuthority`, `SourceDomainID`, `SourceDomainName`, `SqlDataCache`, `SqlDataCacheLife`, `TargetAssigningAuthority`, `TargetDomainID`, `TargetDomainName`, `TMExtCache`, `TMExtDll`, `TMExtInitString`, `TTL`, `validateLength`, `Verbose`

### Process Control
- `report` - Output to log/event (Log, Event, Warn, Error)
- `StopHexTrace` - Disable hex tracing
- `DisableCommandWarningEvent` - Change event type

### Custom Extension Commands
- `AddPassedValue`, `GetReturnValue` - Parameter passing
- `CALL_TMExtension` - Invoke extension

### Condition Operators
- `=`, `!=`, `<`, `<=`, `>`, `>=`
- `begins`, `ends`, `contains`, `within`
- `after`, `before`
- `startsWith`, `endsWith`
- `Length(xx)` - Length comparison

### Reserved Variables
- `%CURRENT_TIME%`, `%DEST_AE_NAME%`
- `%NEW_STUDY_UID%`, `%NEW_SERIES_UID%`, `%NEW_IMAGE_UID%`
- `%NUMBER_OF_PDQ_RESULTS%`, `%ROWCOUNT%`, `%SERVER_NAME%`
- `%SOURCE_AE_NAME%`, `%SOURCE_IMPLEMENTATION_NAME%`
- `%SOURCE_IMPLEMENTATION_UID%`, `%SOURCE_IP_ADDRESS%`
- `%SOURCE_SYSTEM_NAME%`, `%TRANSFER_SYNTAX%`
- `%DICOM_CMD%`, `%DOMAIN_NAME%`, `%DOMAIN_ID%`
- `%DOMAIN_ASSIGNING_AUTHORITY%`, `%TMEXTENSIONSTATUS%`

### Status Values
- `<EXISTS>`, `<NULL>`, `<CONFORMS>`, `<NUMERIC>`

### Setting Values
- Boolean: `True`, `False`
- Dbhit: `Single`, `Any`
- Dbmiss: `Log`, `Ignore`
- validateLength: `Warn`, `Truncate`, `Error`
- OriginalAttributesReasonForChange: `COERCE`, `CORRECT`
- CacheTags: `PATIENT`, `STUDY`, `SERIES`
- Case: `upper`, `lower`, `capfirst`
- Position: `first`, `last`

## Usage

Files with `.txt` extension will automatically use TagMapper syntax highlighting when they contain TagMapper commands.

## Building the Extension

To package the extension into a `.vsix` file:

```bash
npx @vscode/vsce package
```

This will create a `tagmapper-x.x.x.vsix` file in the current directory.

## Installing the Extension

### From GitHub Release (Recommended)

1. Download the latest `.vsix` file from [Releases](https://github.com/QuartzHealthcare/vscode-acuo-tagmapper/releases)
2. In VS Code, press `Cmd+Shift+P` (macOS) or `Ctrl+Shift+P` (Windows/Linux)
3. Type "Extensions: Install from VSIX..."
4. Select the downloaded `.vsix` file

### Build from Source

```bash
git clone https://github.com/QuartzHealthcare/vscode-acuo-tagmapper.git
cd vscode-acuo-tagmapper
npx @vscode/vsce package
code --install-extension tagmapper-1.0.0.vsix
```

## License

MIT
