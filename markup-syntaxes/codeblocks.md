# Inline `code` h1

## Inline `code` h2

More inline `code` and `code`

Block 1

```js
if (!useOrgFeatureEnabled(ENABLE_ASSISTANCE_CENTER)) {
  return;
}

const { workspaceId } = Template.currentData();
const workspace = getWorkspace(workspaceId, {
  fields: {
    event_id: 1,
    "view_state.page": 1,
    visitors: 1,
    "view_state.follow": 1,
    needAssistance: 1
  }
});
const isFollowingPresenter = !!workspace.view_state.follow;
const isWatchingOwnLab =
  workspace.view_state.page === PAGE_VIEW_STATE.LAB && !isFollowingPresenter;
const isWorkspaceBeingVisitedOldValue = this.isWorkspaceBeingVisited;
const isWorkspaceBeingVisitedNewValue = !!workspace.visitors?.length;
const isAskingForAssistanceOldValue = this.isAskingForAssistance;
const {
  status: isAskingForAssistanceNewValue,
  changedBy: assistanceStatusChangedBy
} = workspace.needAssistance || {};
const wasChangedByCurrentWorkspace = assistanceStatusChangedBy === workspaceId;

// The learner is changing the assistance request
if (wasChangedByCurrentWorkspace) {
  this.isAskingForAssistance = isAskingForAssistanceNewValue;
  this.isWorkspaceBeingVisited = isWorkspaceBeingVisitedNewValue;

  return;
}
```

Block 2

```js
const shouldShowDialog =
  isAskingForAssistanceOldValue &&
  !isWatchingOwnLab &&
  !isWorkspaceBeingVisitedOldValue &&
  isWorkspaceBeingVisitedNewValue;

if (shouldShowDialog) {
  openDialog(dialogs.labIsBeingVisited, {
    visitingWorkspaceProfiles: workspace.visitors,
    higherPriorityDialogs: allDialogs,
    dismissOverlayClick: false,
    onApply: () => {
      workspace.followPresenter(false);
      workspace.setViewState("page", "lab");
    }
  });
  this.isAskingForAssistance = false;
}
```

Block 3

```js
this.isWorkspaceBeingVisited = isWorkspaceBeingVisitedNewValue;
```

Block 4

```sh
cd ~
mkdir source
cd source
cp ~/.zshrc .
```

```zsh
cd ~
mkdir source
cd source
cp ~/.zshrc .
```

```bash
cd ~
mkdir source
cd source
cp ~/.zshrc .
```

```shell
cd ~
mkdir source
cd source
cp ~/.zshrc .
```
