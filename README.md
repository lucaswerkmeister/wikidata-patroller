wikidata-patroller
==================

A [Wikidata][wd] patroller bot.

This bot is intended to automatically patrol two kinds of changes which frequently pollute the [list of unpatrolled recent changes][rc] and can be checked automatically:

1. “Page moved from [Xwiki:A] to [Xwiki:B]”: Patrol if Xwiki:A is now a redirect to Xwiki:B.
2. “Page on [Xwiki] deleted: A”: Patrol if Xwiki:A doesn’t exist.

Current status
--------------

Development of this bot is discontinued; I will instead use a [Wikidata user script](https://www.wikidata.org/wiki/User:DSGalaktos/checkMoveDiff.js) to verify the edits before I *manually* patrol them.

Feel free to use it yourself, but be aware that [not everyone agrees that these edits should be automatically patrolled](https://www.wikidata.org/wiki/Wikidata:Bot_requests#Patrol_page_moves_and_deletes).

Patrolling of page moves (1) is implemented on Wikipedias (wikisources etc. missing), patrolling of page deletions (2) isn’t.

Usage
-----

Create a new file named `auth` and put your username and password in it, separated by a space:

    AzureDiamond hunter2

(This should still work if your password contains spaces, though I haven’t tested it. If your _username_ contains spaces, you’ll have to solve the problem yourself – sorry.)

Then you can simply run the bot:

    ./wikidata-patroller

Dependencies
------------

- `bash` (uses Bash specific syntax, other shells probably won’t work)
- `curl`
- `sed` (POSIX-compliant should suffice – tested with GNU `sed`)
- `tr` (POSIX-compliant should suffice – tested with GNU `coreutils` version)
- `date` (POSIX-compliant will *not* suffice, needs GNU `coreutils`’ `-d` option)
- [`jq`][jq]

License
-------

The content of this repository is released under the GNU GPLv3 as provided in the LICENSE file that accompanied this code.

By submitting a “pull request” or otherwise contributing to this repository, you agree to license your contribution under the license mentioned above.

[wd]: https://www.wikidata.org/wiki/Wikidata:Main_Page
[rc]: https://www.wikidata.org/w/index.php?title=Special:RecentChanges&hidepatrolled=1
[jq]: https://stedolan.github.io/jq/
