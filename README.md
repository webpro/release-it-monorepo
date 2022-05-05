# release-it + wireit

Working demo/prototype to use release-it with wireit in a monorepo setup.

```
npm install
WIREIT_PARALLEL=1 npm run release
```

- Uses a patched version of wireit to spawn the child process using
  `stdio: ['inherit', 'pipe', 'pipe']`
- Uses a patched version of release-it to filter the `git log` for each package.
- Requires `WIREIT_PARALLEL=1` to run the release-it processes in sequence.

Example output:

```
❯ WIREIT_PARALLEL=1 npm run release

> monorepo@1.0.0 release
> wireit

🏃 [packages/mol:release] Running command "release-it --npm.skipChecks --no-git.requireCleanWorkingDir"
🏃 [packages/bravo:release] Running command "release-it --npm.skipChecks --no-git.requireCleanWorkingDir"
🏃 [packages/zen:release] Running command "release-it --npm.skipChecks --no-git.requireCleanWorkingDir"

🚀 Let's release mol (currently at 1.0.0)


Changelog:
* Disable clean working dir requirement (since it's dirty after first package release) (26ab265)
* Add release-it config to mol package (ac4cf6a)

? Select increment (next version): minor (1.1.0)
? Publish mol to npm? No
🏁 Done (in 5s.)
✅ [packages/mol:release] Executed successfully

🚀 Let's release zen (currently at 1.0.0)


Changelog:
* Disable clean working dir requirement (since it's dirty after first package release) (26ab265)
* Add release-it config to zen package (0992d11)

? Select increment (next version): minor (1.1.0)
? Publish zen to npm? No
🏁 Done (in 3s.)
✅ [packages/zen:release] Executed successfully

🚀 Let's release bravo (currently at 1.0.0)


Changelog:
* Disable clean working dir requirement (since it's dirty after first package release) (26ab265)
* Add release-it config to bravo package (56c9325)

? Select increment (next version): minor (1.1.0)
? Publish bravo to npm? No
🏁 Done (in 3s.)
✅ [packages/bravo:release] Executed successfully
🏃 [release] Running command "release-it --no-npm --no-git.requireCleanWorkingDir"

🚀 Let's release release-it-monorepo (currently at 1.0.0)


Changelog:
* Disable clean working dir requirement (since it's dirty after first package release) (26ab265)
* Add patch for release-it (9370806)
* Add release command to repo itself (4e0fa2b)
* Add release-it config to zen package (0992d11)
* Add release-it config to mol package (ac4cf6a)
* Add release-it config to bravo package (56c9325)

? Select increment (next version): minor (1.1.0)

Changeset:
 M packages/bravo/package.json
 M packages/mol/package.json
 M packages/zen/package.json

? Commit (Release 1.1.0)? Yes
? Tag (1.1.0)? Yes
? Push? Yes
🏁 Done (in 14s.)
✅ [release] Executed successfully
```
