# release-it + wireit

Working demo/prototype to use release-it with wireit in a monorepo setup.

```
npm install
WIREIT_PARALLEL=1 npm run release
```

Note that this currently uses a patched version of wireit to spawn the child
process using `stdio: 'inherit'`. Also, `WIREIT_PARALLEL=1` is required to run
the release-it processes in sequence.
