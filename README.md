
# my *tiny* LuaJIT 2.1 fork

## Overview

I've worked in order to fill the compatibility gap between LuaJIT 2.1 and Lua 5.2/5.3.

Some of my Pull Requests were merged upstream by Mike Pall.

My unmerged work is available in the branch `tiny_fork` on <https://github.com/fperrad/LuaJIT>.
It contains:

  - [PR#269](https://github.com/LuaJIT/LuaJIT/pull/269) : backport string.\*pack\* from 5.3
  - [PR#327](https://github.com/LuaJIT/LuaJIT/pull/327) : backport lua\_rawlen, lua\_len & luaL\_len from 5.2
  - [PR#364](https://github.com/LuaJIT/LuaJIT/pull/364) : patterns better compatibility with 5.2 ('\0' in pattern)

## Pull Requests

- [PR#265](https://github.com/LuaJIT/LuaJIT/pull/265) : backport package.searchers from 5.2

    status : Merged in v2.1.0-beta3

- [PR#266](https://github.com/LuaJIT/LuaJIT/pull/266) : io:read compat with 5.3

    status : Merged in v2.1.0-beta3

- [PR#267](https://github.com/LuaJIT/LuaJIT/pull/267) : backport table.move from 5.3

    status : Merged in v2.1.0-beta3 (fully reworked by Mike Pall)

- [PR#268](https://github.com/LuaJIT/LuaJIT/pull/268) : backport coroutine.isyieldable from 5.3

    status : Merged in v2.1.0-beta3

- [PR#269](https://github.com/LuaJIT/LuaJIT/pull/269) : backport string.\*pack\* from 5.3

    status : Rejected / Included in my fork

- [PR#270](https://github.com/LuaJIT/LuaJIT/pull/270) : backport utf8 library from 5.3

    status : Rejected (At this time, I think the module [luautf8](https://github.com/starwing/luautf8) is a better alternative)

- [PR#273](https://github.com/LuaJIT/LuaJIT/pull/273) : refactor table.maxn with LJLIB_LUA

    status : Rejected

- [PR#302](https://github.com/LuaJIT/LuaJIT/pull/302) : remove compatibility with Lua 5.0

    status : Merged in v2.1.0-beta3

- [PR#307](https://github.com/LuaJIT/LuaJIT/pull/307) : remove old compatibility macros

    status : Merged in v2.1.0-beta3

- [PR#309](https://github.com/LuaJIT/LuaJIT/pull/309) : package/module better compatibility with Lua 5.2

    status : Merged in v2.1.0-beta3

- [PR#312](https://github.com/LuaJIT/LuaJIT/pull/312) : backport operators from 5.3

    status : Pending (huge change, break bytecode compatibility, waiting for v2.2)

- [PR#313](https://github.com/LuaJIT/LuaJIT/pull/313) : backport math.type and math.tointeger from 5.3

    status : Rejected (incompatible numeric model)

- [PR#314](https://github.com/LuaJIT/LuaJIT/pull/314) : backport some C/API from 5.2/5.3

    status : Merged in v2.1.0-beta3

- [PR#315](https://github.com/LuaJIT/LuaJIT/pull/315) : extract lib\_coro from lib\_base

    status : Rejected (break binary compatibility)

- [PR#317](https://github.com/LuaJIT/LuaJIT/pull/317) : add 5.3 operators as syntax sugar

    status : Bugged / needs some rework

- [PR#327](https://github.com/LuaJIT/LuaJIT/pull/327) : backport lua\_rawlen, lua\_len & luaL\_len from 5.2

    status : Pending / Included in my fork

- [PR#364](https://github.com/LuaJIT/LuaJIT/pull/364) : patterns better compatibility with 5.2 ('\0' in pattern)

    status : Pending / Included in my fork

## Build / Install Instructions

From source, like with LuaJIT, see <http://luajit.org/install.html>.

Note: [hererocks](https://github.com/mpeterv/hererocks) could be used like this :

```
$ hererocks somewhere --luajit https://github.com/fperrad/LuaJIT.git@tiny_fork --compat 5.2
```

## TODO

- Fix [PR#317](https://github.com/LuaJIT/LuaJIT/pull/317) : add 5.3 operators as syntax sugar
