Near term
─────────
Merge conflict resolution strategy
  → currently throws, needs user-facing resolution flow

UI status refresh
  → after SessionSyncWorker commits/pulls, app UI should
    reflect new file statuses without user manually opening app

Windows plugin HTTP
  → plugin already has desktop console.log path
  → swap for fetch() to Ktor local server in desktopMain

Medium term
───────────
vaultId → vault path mapping
  → plugin sends vaultId, app needs to resolve which local path

Multi-vault support
  → each vault gets its own plugin instance and vaultId

Token refresh in workers
  → current workers use stored token but don't refresh on expiry


- [ ] multi-vault support - we need to know from the plugin if user created new vault, or changed the vault, we need to have one github repository for one vault, so we can track them independently with different vault id, can we make sure windows and android are on same vault? can we have some kind of settings.md where we store the current vault info of windows and android, if we have different we can warn user that mobile and desktop vaults are different make sure u are on same vault to have the sync it doens't matter right? like everything is going to github and if user is on different vaults they don't see the changes as it'll be different repository and when they are in same it will sync, how do we warn the users? when they change the vault?? like notfiication? or banner? in our obsync app?
- [ ] what happens when user will delete a vault from obsidian vault? should we show that vault has been deleted in the obisidan app, and have user option to delete it on github has well? if user is tracking that vault on windows how we will know? our app is multi-platform sync itseems!! we need to spend some time on vault and github repo creation, deletion
- [ ] what if user already have lots of vaults before our plugin and app has been installed, are we syning all? should we show an option in plugin that what vaults are tracked and what are not? start tracking existing vaults? give user option to pick the vaults to track?
- [ ] when creating a github repo for a vault we can have a naming convention like user-named-vault-obsync-android or something to know that user is tracking some vaults, let's say on onbaording the user or somewhere we can list the current github repositres user have which are tracking the vaults do we really need this?? i was thinking to help user pick the repository if they want the same vault in windows, let's say user created the vault in mobile and wants that vaults in windows and vice versa,
- [ ] merge conflict resolving - We will use merge resolve editor like vscode has, just viewing the diff and giving options like accept incoming, accept yours, accept both kind of thing, we need a good mechanism for resolving merge conflicts Vscode terminology for merge editorVscode terminology for merge editor there are 3 section in a single screen, the screen is split in 2 section top and bottom top one shows incoming changes in the left side and current changes in the right side (horizontal split). And at the bottom there is a result section which shows after resolving the conflicts, i see accept current and accept combination button in the current changes section, there are double tick button in the top right side of the section to accept all, and below the section it showsn conflicts remaining count and a undo or revert the current accepted change button, complete merge button in the bottom right side of the screen, until the merge conflict has been resolved it won't sync that file, and we will have a merge resolve screen poped up from our obsync app where user will resolve it. we need to force our obsync merge resovler screen to user, or atleast a notification, or banner on our app
 
