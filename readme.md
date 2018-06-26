# Issue building Realm.js from source on Windows

## Steps to reproduce
- git clone this repo `https://github.com/jozsefm/realm-windows-build.git` 
- cd into it  
- execute `yarn`

## Remarks
- This is likely a regression or breaking change as it doesn't happen with versions earlier than `2.3.0`
- I use electron-builder only to automatically start the rebuild. It has nothing to do with the issue itself.

## Environment
- Windows 10
- Node 9.9.0
- VS 2017 Community

## The error:
~~~~
$ install-app-deps
  • please use as subcommand: electron-builder install-app-deps
  • electron-builder version=20.16.2
  • loaded configuration file=package.json ("build" field)
  • rebuilding native production dependencies platform=win32 arch=x64
  • rebuilding native dependency name=realm
Error: C:\Program Files\nodejs\node.exe exited with code 1
Output:
yarn run v1.7.0
$ node-pre-gyp install --fallback-to-build

C:\work\realm-windows-build\node_modules\realm>if not defined npm_config_node_gyp (node "C:\Program Files\nodejs\node_modules\npm\bin\node-gyp-bin\\..\..\node_modules\node-gyp\bin\node-gyp.js" clean )  else (node "" clean ) 

C:\work\realm-windows-build\node_modules\realm>if not defined npm_config_node_gyp (node "C:\Program Files\nodejs\node_modules\npm\bin\node-gyp-bin\\..\..\node_modules\node-gyp\bin\node-gyp.js" configure --fallback-to-build --module=C:\work\realm-windows-b
uild\node_modules\realm\compiled\electron-v2.0_win32_x64\realm.node --module_name=realm --module_path=C:\work\realm-windows-build\node_modules\realm\compiled\electron-v2.0_win32_x64 --python=C:\Users\joco-\.windows-build-tools\python27\python.exe --msvs_v
ersion=2015 )  else (node "" configure --fallback-to-build --module=C:\work\realm-windows-build\node_modules\realm\compiled\electron-v2.0_win32_x64\realm.node --module_name=realm --module_path=C:\work\realm-windows-build\node_modules\realm\compiled\electr
on-v2.0_win32_x64 --python=C:\Users\joco-\.windows-build-tools\python27\python.exe --msvs_version=2015 ) 
Warning: Missing input files:
C:\work\realm-windows-build\node_modules\realm\build\..\scripts\test.sh
C:\work\realm-windows-build\node_modules\realm\build\..\src\object-store\src\util\compiler.hpp
C:\work\realm-windows-build\node_modules\realm\build\..\lib\browser\util.jsscripts\build-node-pre-gyp.ps1
C:\work\realm-windows-build\node_modules\realm\build\..\scripts\changelog-header.sh
C:\work\realm-windows-build\node_modules\realm\build\..\src\object-store\src\descriptor_ordering.hpp
C:\work\realm-windows-build\node_modules\realm\build\..\scripts\set-version.sh
C:\work\realm-windows-build\node_modules\realm\build\..\scripts\publish.sh

C:\work\realm-windows-build\node_modules\realm>if not defined npm_config_node_gyp (node "C:\Program Files\nodejs\node_modules\npm\bin\node-gyp-bin\\..\..\node_modules\node-gyp\bin\node-gyp.js" build --fallback-to-build --module=C:\work\realm-windows-build
\node_modules\realm\compiled\electron-v2.0_win32_x64\realm.node --module_name=realm --module_path=C:\work\realm-windows-build\node_modules\realm\compiled\electron-v2.0_win32_x64 )  else (node "" build --fallback-to-build --module=C:\work\realm-windows-bui
ld\node_modules\realm\compiled\electron-v2.0_win32_x64\realm.node --module_name=realm --module_path=C:\work\realm-windows-build\node_modules\realm\compiled\electron-v2.0_win32_x64 ) 
Building the projects in this solution one at a time. To enable parallel build, please add the "/m" switch.
  download-realm
  Resolved requirements: { CORE_SERVER_FOLDER: 'core/v5.4.0/windows/x64/nouwp/Release',
    CORE_ARCHIVE: 'realm-core-Release-v5.4.0-Windows-x64-devel.tar.gz' }
  No lockfile found at the target, proceeding.
  Download url: https://static.realm.io/downloads/core/v5.4.0/windows/x64/nouwp/Release/realm-core-Release-v5.4.0-Windows-x64-devel.tar.gz
  Extracting realm-core-Release-v5.4.0-Windows-x64-devel.tar.gz => C:\work\realm-windows-build\node_modules\realm\vendor\realm-win-x64
  Success
  binding_callback_thread_observer.cpp
  collection_notifications.cpp
  index_set.cpp
  list.cpp
  object.cpp
  placeholder.cpp
  object_schema.cpp
  object_store.cpp
  results.cpp
  schema.cpp
  shared_realm.cpp
  thread_safe_reference.cpp
  collection_change_builder.cpp
  collection_notifier.cpp
  list_notifier.cpp
  object_notifier.cpp
  primitive_list_notifier.cpp
  realm_coordinator.cpp
  results_notifier.cpp
  transact_log_handler.cpp
  weak_realm_notifier.cpp
  uuid.cpp
  external_commit_helper.cpp
  win_delay_load_hook.cc
  object-store.vcxproj -> C:\work\realm-windows-build\node_modules\realm\build\Release\\object-store.lib
  js_realm.cpp
  node_init.cpp
  platform.cpp
  win_delay_load_hook.cc
     Creating library C:\work\realm-windows-build\node_modules\realm\build\Release\realm.lib and object C:\work\realm-windows-build\node_modules\realm\build\Release\realm.exp
node_init.obj : error LNK2001: unresolved external symbol "public: enum realm::ComputedPrivileges __cdecl realm::Realm::get_privileges(void)" (?get_privileges@Realm@realm@@QEAA?AW4ComputedPrivileges@2@XZ) [C:\work\realm-windows-build\node_modules\realm\bu
ild\realm.vcxproj]
node_init.obj : error LNK2001: unresolved external symbol "public: enum realm::ComputedPrivileges __cdecl realm::Realm::get_privileges(class realm::StringData)" (?get_privileges@Realm@realm@@QEAA?AW4ComputedPrivileges@2@VStringData@2@@Z) [C:\work\realm-wi
ndows-build\node_modules\realm\build\realm.vcxproj]
node_init.obj : error LNK2001: unresolved external symbol "public: enum realm::ComputedPrivileges __cdecl realm::Realm::get_privileges(class realm::BasicRowExpr<class realm::Table>)" (?get_privileges@Realm@realm@@QEAA?AW4ComputedPrivileges@2@V?$BasicRowEx
pr@VTable@realm@@@2@@Z) [C:\work\realm-windows-build\node_modules\realm\build\realm.vcxproj]
C:\work\realm-windows-build\node_modules\realm\build\Release\realm.node : fatal error LNK1120: 3 unresolved externals [C:\work\realm-windows-build\node_modules\realm\build\realm.vcxproj]
Failed to execute 'node-gyp.cmd build --fallback-to-build --module=C:\work\realm-windows-build\node_modules\realm\compiled\electron-v2.0_win32_x64\realm.node --module_name=realm --module_path=C:\work\realm-windows-build\node_modules\realm\compiled\electro
n-v2.0_win32_x64' (1)
info Visit https://yarnpkg.com/en/docs/cli/run for documentation about this command.

Error output:
node-pre-gyp info it worked if it ends with ok
node-pre-gyp info using node-pre-gyp@0.6.39
node-pre-gyp info using node@9.9.0 | win32 | x64
node-pre-gyp http GET https://static.realm.io/node-pre-gyp/2.3.0/realm-v2.3.0-electron-v2.0-win32-x64.tar.gz
node-pre-gyp http 404 https://static.realm.io/node-pre-gyp/2.3.0/realm-v2.3.0-electron-v2.0-win32-x64.tar.gz
node-pre-gyp ERR! Tried to download(404): https://static.realm.io/node-pre-gyp/2.3.0/realm-v2.3.0-electron-v2.0-win32-x64.tar.gz 
node-pre-gyp ERR! Pre-built binaries not found for realm@2.3.0 and electron@2.0.3 (electron-v2.0 ABI, unknown) (falling back to source compile with node-gyp) 
node-pre-gyp http 404 status code downloading tarball https://static.realm.io/node-pre-gyp/2.3.0/realm-v2.3.0-electron-v2.0-win32-x64.tar.gz 
gyp info it worked if it ends with ok
gyp info using node-gyp@3.6.2
gyp info using node@9.9.0 | win32 | x64
gyp info ok 
gyp info it worked if it ends with ok
gyp info using node-gyp@3.6.2
gyp info using node@9.9.0 | win32 | x64
gyp info spawn C:\Users\joco-\.windows-build-tools\python27\python.exe
gyp info spawn args [ 'C:\\Program Files\\nodejs\\node_modules\\npm\\node_modules\\node-gyp\\gyp\\gyp_main.py',
gyp info spawn args   'binding.gyp',
gyp info spawn args   '-f',
gyp info spawn args   'msvs',
gyp info spawn args   '-G',
gyp info spawn args   'msvs_version=2015',
gyp info spawn args   '-I',
gyp info spawn args   'C:\\work\\realm-windows-build\\node_modules\\realm\\build\\config.gypi',
gyp info spawn args   '-I',
gyp info spawn args   'C:\\Program Files\\nodejs\\node_modules\\npm\\node_modules\\node-gyp\\addon.gypi',
gyp info spawn args   '-I',
gyp info spawn args   'C:\\Users\\joco-\\.electron-gyp\\iojs-2.0.3\\common.gypi',
gyp info spawn args   '-Dlibrary=shared_library',
gyp info spawn args   '-Dvisibility=default',
gyp info spawn args   '-Dnode_root_dir=C:\\Users\\joco-\\.electron-gyp\\iojs-2.0.3',
gyp info spawn args   '-Dnode_gyp_dir=C:\\Program Files\\nodejs\\node_modules\\npm\\node_modules\\node-gyp',
gyp info spawn args   '-Dnode_lib_file=C:\\Users\\joco-\\.electron-gyp\\iojs-2.0.3\\<(target_arch)\\iojs.lib',
gyp info spawn args   '-Dmodule_root_dir=C:\\work\\realm-windows-build\\node_modules\\realm',
gyp info spawn args   '-Dnode_engine=v8',
gyp info spawn args   '--depth=.',
gyp info spawn args   '--no-parallel',
gyp info spawn args   '--generator-output',
gyp info spawn args   'C:\\work\\realm-windows-build\\node_modules\\realm\\build',
gyp info spawn args   '-Goutput_dir=.' ]
gyp info ok 
gyp info it worked if it ends with ok
gyp info using node-gyp@3.6.2
gyp info using node@9.9.0 | win32 | x64
gyp info spawn msbuild
gyp info spawn args [ 'build/binding.sln',
gyp info spawn args   '/clp:Verbosity=minimal',
gyp info spawn args   '/nologo',
gyp info spawn args   '/p:Configuration=Release;Platform=x64' ]
gyp ERR! build error 
gyp ERR! stack Error: `msbuild` failed with exit code: 1
gyp ERR! stack     at ChildProcess.onExit (C:\Program Files\nodejs\node_modules\npm\node_modules\node-gyp\lib\build.js:258:23)
gyp ERR! stack     at ChildProcess.emit (events.js:180:13)
gyp ERR! stack     at Process.ChildProcess._handle.onexit (internal/child_process.js:209:12)
gyp ERR! System Windows_NT 10.0.17134
gyp ERR! command "C:\\Program Files\\nodejs\\node.exe" "C:\\Program Files\\nodejs\\node_modules\\npm\\node_modules\\node-gyp\\bin\\node-gyp.js" "build" "--fallback-to-build" "--module=C:\\work\\realm-windows-build\\node_modules\\realm\\compiled\\electron-
v2.0_win32_x64\\realm.node" "--module_name=realm" "--module_path=C:\\work\\realm-windows-build\\node_modules\\realm\\compiled\\electron-v2.0_win32_x64"
gyp ERR! cwd C:\work\realm-windows-build\node_modules\realm
gyp ERR! node -v v9.9.0
gyp ERR! node-gyp -v v3.6.2
gyp ERR! not ok 
node-pre-gyp ERR! build error 
node-pre-gyp ERR! stack Error: Failed to execute 'node-gyp.cmd build --fallback-to-build --module=C:\work\realm-windows-build\node_modules\realm\compiled\electron-v2.0_win32_x64\realm.node --module_name=realm --module_path=C:\work\realm-windows-build\node
_modules\realm\compiled\electron-v2.0_win32_x64' (1)
node-pre-gyp ERR! stack     at ChildProcess.<anonymous> (C:\work\realm-windows-build\node_modules\node-pre-gyp\lib\util\compile.js:83:29)
node-pre-gyp ERR! stack     at ChildProcess.emit (events.js:180:13)
node-pre-gyp ERR! stack     at maybeClose (internal/child_process.js:936:16)
node-pre-gyp ERR! stack     at Process.ChildProcess._handle.onexit (internal/child_process.js:220:5)
node-pre-gyp ERR! System Windows_NT 10.0.17134
node-pre-gyp ERR! command "C:\\Program Files\\nodejs\\node.exe" "C:\\work\\realm-windows-build\\node_modules\\node-pre-gyp\\bin\\node-pre-gyp" "install" "--fallback-to-build"
node-pre-gyp ERR! cwd C:\work\realm-windows-build\node_modules\realm
node-pre-gyp ERR! node -v v9.9.0
node-pre-gyp ERR! node-pre-gyp -v v0.6.39
node-pre-gyp ERR! not ok 
error Command failed with exit code 1.

    at ChildProcess.childProcess.once.code (C:\work\realm-windows-build\node_modules\builder-util\src\util.ts:251:14)
    at Object.onceWrapper (events.js:272:13)
    at ChildProcess.emit (events.js:180:13)
    at maybeClose (internal/child_process.js:936:16)
    at Process.ChildProcess._handle.onexit (internal/child_process.js:220:5)
From previous event:
    at runCallback (timers.js:763:18)
    at tryOnImmediate (timers.js:734:5)
    at processImmediate (timers.js:716:5)
From previous event:
    at C:\work\realm-windows-build\node_modules\electron-builder-lib\src\util\yarn.ts:150:27
From previous event:
    at rebuild (C:\work\realm-windows-build\node_modules\electron-builder-lib\out\util\yarn.js:234:18)
    at C:\work\realm-windows-build\node_modules\electron-builder-lib\src\util\yarn.ts:20:11
From previous event:
    at installOrRebuild (C:\work\realm-windows-build\node_modules\electron-builder-lib\out\util\yarn.js:68:17)
    at C:\work\realm-windows-build\node_modules\electron-builder\src\cli\install-app-deps.ts:56:9
    at Generator.next (<anonymous>)
    at runCallback (timers.js:763:18)
    at tryOnImmediate (timers.js:734:5)
    at processImmediate (timers.js:716:5)
From previous event:
    at installAppDeps (C:\work\realm-windows-build\node_modules\electron-builder\out\cli\install-app-deps.js:174:17)
    at main (C:\work\realm-windows-build\node_modules\electron-builder\src\cli\install-app-deps.ts:65:10)
    at Object.<anonymous> (C:\work\realm-windows-build\node_modules\electron-builder\src\cli\install-app-deps.ts:70:3)
    at Module._compile (module.js:649:30)
    at Object.Module._extensions..js (module.js:660:10)
    at Module.load (module.js:561:32)
    at tryModuleLoad (module.js:501:12)
    at Function.Module._load (module.js:493:3)
    at Function.Module.runMain (module.js:690:10)
    at startup (bootstrap_node.js:194:16)
    at bootstrap_node.js:666:3
error Command failed with exit code 1.
info Visit https://yarnpkg.com/en/docs/cli/install for documentation about this command.
~~~~
