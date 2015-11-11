## September 4 2015 (1.0.10)

  Minor fix release.

  * **Fixes**:

    * Fixes Node.Refresh logic.

    * Fixes an issue with dead connections that would cause an infinite loop.

## Augest 11 2015 (1.0.9)

  Minor fix release.

  * **Fixes**:

    * Sends the original key value to the server for all relevant commands, including `operate` and `execute_udf`

## July 23 2015 (1.0.8)

  Minor fix release.

  * **Improvements**:

    * Adds 'Filter.to_s'. Thanks to [Ángel M](https://github.com/Angelmmiguel)

  * **Fixes**:

    * Fixes an issue in write policy that would use an undefined variable if `:send_key` isn't `nil`.

    * Fixes an issue in cluster.closed logic.

    * Fixes an issue with including the `statement.rb` in the manifest. Thanks to [Ángel M](https://github.com/Angelmmiguel)

## May 15 2015 (1.0.7)

  Minor fixes.

  NOTICE: All LDTs on server other than LLIST have been deprecated, and will be removed in the future. As Such, all API regarding those features are considered deprecated and will be removed in tandem.

  * **Improvements**:

    * Removed workaround in `BatchGet`. Bins are filtered on server now.

    * Added New Error Codes. Fixes Issues #17 and #18

    * Node validator won't lookup hostsif an IP is passed as a seed to it.

  * ** Other Changes **

    * Removed deprecated `ReplaceRoles()` method.

    * Removed deprecated `SetCapacity()` and `GetCapacity()` methods for LDTs.

## April 2 2015 (1.0.6)

  Minor fixes.

  * **New Features**:

    * Fixed running a stream query without parameters to the function.

## March 25 2015 (1.0.5)

  Minor improvements.

  * **New Features**:

    * Added `:execute_udf_on_query` method to `Aerospike::Client`

## March 24 2015 (1.0.4)

  Hot fix.

  * **Fixes**:

    * Close a socket if connection raises an exception to avoid leaking the file descriptor.

## March 24 2015 (1.0.3)

  Minor fixes and improvements.

  * **New Features**:

    * Symbols are now accepted as key values. Keep in mind that symbols are converted to string automatically, and type information is lost.

  * **Fixes**:

    * Wait for a good connection on `socket.connect_nonblock` to prevent infinite loops on read/write operations.


## March 14 2015 (1.0.2)

  Minor improvements.

  * **New Features**:

    * Added `:new_many` method to `Aerospike::Client`

## Jan 28 2015 (1.0.1)

  Hot fix.

  * **Fixes**:

    * Added `bcrypt` to the gem dependencies.

## Jan 26 2015 (1.0.0)

  Major release. With this release, Ruby client graduates to version 1.

  * **Breaking Changes**:

    * All `policy` initialize signatures have changed. Using policies was not documented, so it shouldn't affect most code. It will however, break any code initializing policies.
    * Removed `Record.dups` and `GenerationPolicy::DUPLICATE`

  * **New Features**:

    * Added Security Features: Please consult [Security Docs](https://www.aerospike.com/docs/guide/security.html) on Aerospike website.
      
      * `ClientPolicy.User`, `ClientPolicy.Password`
      * `Client.CreateUser()`, `Client.DropUser()`, `Client.ChangePassword()`
      * `Client.GrantRoles()`, `Client.RevokeRoles()`, `Client.ReplaceRoles()`
      * `Client.QueryUser()`, `Client.QueryUsers`

  * **Fixes**:

    * fixed size returned from `BytesValue.write`

## Dec 28 2014 (0.1.6)

  Minor features added, minor fixes and improvements.

  * **New Features**:

    * Added `Policy.consistency_level`
    * Added `WritePolicy.commit_level`

  * **Fixes**

    * Fixed setting timeout on connection
    * Fixed exception handling typo for Connection#write 

## Dec 8 2014 (0.1.5)

  Major features added, minor fixes and improvements.

  * **New Features**:

    * Added `Client.scan_node`, `Client.scan_all`
    * Added `Client.query`

  * **Fixes**

    * Fixed getting back results only for specified bin names.

## Oct 27 2014 (0.1.3)

  Minor fix.

  * **Changes**:

    * Fixed LDT bin and module name packing.

## Oct 25 2014 (0.1.2)

  Minor fix.

  * **Changes**:

    * Fixed String unpacking for single byte strings.

## Oct 25 2014 (0.1.1)

  Minor fixes.

  * **Changes**:

    * Fixed String packing header in Hash and Array.
    * #find on LDTs returns `nil` instad of raising an exception if the item is not found.

## Oct 14 2014 (0.1.0)

  * Initial Release.
