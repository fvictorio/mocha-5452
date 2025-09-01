# Repro Mocha issue 5452

Run `npm install && npx mocha test.ts`. You'll get an error like `Exception during run: Error [ERR_INTERNAL_ASSERTION]: Unexpected status of a module that is imported again after being required. Status = 0`. This is caused by https://github.com/mochajs/mocha/issues/5411, which was already fixed. But using the [11.7.2 version of mocha](https://github.com/mochajs/mocha/pull/5398) still results in an error, just with a better message: `Exception during run: SyntaxError: The requested module './foo.js' does not provide an export named 'Foo'`.
