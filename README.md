# NAME

Unqlite - Perl bindings for Unqlite

# SYNOPSIS

    use Unqlite;

    my $db = Unqlite->open('foo.db');
    $db->kv_store('foo', 'bar');
    say $db->kv_fetch('foo'); # => bar
    $db->kv_delete('foo');
    undef $db; # close database

# DESCRIPTION

UnQLite is a in-process software library which implements a self-contained, serverless, zero-configuration, transactional NoSQL database engine. UnQLite is a document store database similar to MongoDB, Redis, CouchDB etc. as well a standard Key/Value store similar to BerkeleyDB, LevelDB, etc.  

This module is Perl5 binding for Unqlite.

If you want to know more information about Unqlite, see [http://unqlite.org/](http://unqlite.org/).

Current version of Unqlite.pm supports only some `kv_*` methods. Patches welcome.

# METHODS

- `my $db = Unqlite->open('foo.db'[, $mode]);`

    Open the database.

- `$db->kv_store($key, $value);`

    Store the entry to database.

- `$db->kv_fetch($key);`

    Fetch data from database.

- `$db->kv_delete($key);`

    Delte ` $key ` from database.

- `$db->rc();`

    Return code from unqlite. It may updates after any Unqlite API call.

- `$db->errstr()`

    This API returns stringified version of `$db->rc()`. It's not human readable but it's better than magic number.

# LICENSE

Copyright (C) tokuhirom.

This library is free software; you can redistribute it and/or modify
it under the same terms as Perl itself.

# AUTHOR

tokuhirom <tokuhirom@gmail.com>
