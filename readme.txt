1.sBgWorkspaceItems		1.appinfo shortcut并且容器(container)不是folder; 2.folderInfo
2.sBgAppWidgets		
3.sBgFolders 	1.folder的id和对应的folderInfo的键值对
4.sBgDbIconCache
5.sBgWorkspaceScreens

HashMap<Long, ItemInfo> sBgItemsIdMap = id(_id)和itemInfo的键值对

图标: BubbleTextView	layout/application	对应的style: WorkspaceIcon
folder图标:	FolderIcon	layou/folder_icon	包含一个ImageView(背景图片) 和一个 BubbleTextView

workspace cellLayout:	workspace_screen