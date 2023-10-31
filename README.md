# Nx 17.0.2 build error reproduction

If `outputPath` starts with `../source/` then build fails:

```
$ cd test-repo
$ pnpm build

> @test-repo/source@0.0.0 build /home/user/projects/tmp/NxCacheErrorRepro/test-repo
> nx build test-repo


> nx run test-repo:build:production

✔ Browser application bundle generation complete.
✔ Copying assets complete.
✔ Index html generation complete.

Initial Chunk Files           | Names         |  Raw Size | Estimated Transfer Size
main.1bbff18d881dbd28.js      | main          | 111.97 kB |                32.26 kB
polyfills.17fcc834a0cb8fcf.js | polyfills     |  33.03 kB |                10.63 kB
runtime.4a236d66b86ed93e.js   | runtime       | 896 bytes |               510 bytes
styles.ef46db3751d8e999.css   | styles        |   0 bytes |                       -

                              | Initial Total | 145.87 kB |                43.39 kB

Build at: 2023-10-31T17:45:50.112Z - Hash: 976dace513b0324e - Time: 1613ms

 ———————————————————————————————————————————————————————————————————————————————————————

 >  NX   Ran target build for project test-repo (7s)

    ✖    0/0 failed
    ✔    0/0 succeeded [0 read from cache]


 >  NX   EISDIR: illegal operation on a directory, open '/home/user/projects/tmp/NxCacheErrorRepro/test-repo/.nx/cache/13495886819029245579/source'

   Pass --verbose to see the stacktrace.

 ELIFECYCLE  Command failed with exit code 1.

```
