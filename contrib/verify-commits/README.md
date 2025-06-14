Tooling for verification of PGP signed commits
----------------------------------------------

* ["pre-push-hook.sh"](pre-push-hook.sh)
  * allows
    * ensure that their OWN commits -- are -- PGP signed
  * uses
    * maintainers 
* ["gpg.sh"](gpg.sh)
  * TODO:

Using verify-commits.sh
------------------------------

* ❌if you checkout & run `verify-commits.sh` -- against -- `HEAD` -> NOT safe❌ 
  * Reason: 🧠`verify-commits.sh`'s versions could be backdoored🧠

* steps to take
  * ⚠️BEFORE checkout, use a trusted version of verify-commits⚠️
    * Reason: 🧠make sure you're checking out ONLY code / signed by trusted keys
    ```
    git fetch origin && \
        ./contrib/verify-commits/verify-commits.sh origin/master && \
        git checkout origin/master
    ```
