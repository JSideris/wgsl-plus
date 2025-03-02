# wgsl-plus

A lightweight WGSL compiler with support for linking files via `#import` directives and outputting to multiple formats (WGSL, JS, TS).

## Features

- **File Linking**: Use `#import "path"` directives to include other WGSL files.
- **Multi-Format Output**: Build to WGSL, JavaScript, or TypeScript files.
- **Export Options**: Choose between ESM (`export`) or CommonJS (`module.exports`) for JS/TS outputs.
- **Error Handling**: Prevents overwriting input files, ensures all linked files exist, and validates input/output formats.
- **Help Documentation**: Run `wgsl-plus --help` for usage instructions and examples.

## Installation

Install globally for easy access:

`npm install -g wgsl-plus`

Or use `npx` for one-off runs:

`npx wgsl-plus [options] <input files>`

## Usage

### Basic Command

`wgsl-plus <inputFiles...> -o <outputFile> [--export-type <type>]`

- `<inputFiles...>`: One or more `.wgsl` files to process.
- `-o, --output <path>`: Path to the output file (must be `.wgsl`, `.js`, or `.ts`).
- `--export-type <type>`: Export type for `.js` or `.ts` outputs (`esm` or `commonjs`).

### Examples

- **Build to WGSL**:
  `wgsl-plus input.wgsl -o output.wgsl`

- **Build to JavaScript (ESM)**:
  `wgsl-plus a.wgsl b.wgsl -o output.js --export-type esm`

- **Build to TypeScript (CommonJS)**:
  `wgsl-plus main.wgsl -o output.ts --export-type commonjs`

### Directives

- `#import "path"`: Include another WGSL file relative to the current file.

Example:

``` wgsl
#import "utils.wgsl"
fn main() {}
```

## Development

To contribute or modify `wgsl-plus`:

1. Clone the repository:
   `git clone https://github.com/yourusername/wgsl-plus.git`
   `cd wgsl-plus`

2. Install dependencies:
   `npm install`

3. Build the project:
   `npm run build`

4. Test locally:
   `node dist/cli.js --help`

## License

MIT License. See [LICENSE](LICENSE) for details.