https://github.com/zzyy/LauncherDemo

1. LauncherProvider加载, 初始化provider, 创建DatabaseHelper, 创建相应的数据库表
2. LauncherApplication extends Application, 初始化 LauncherAppState
3. LauncherAppState 中初始化 LauncherModel
4. 加载Launcher 的 onCreate

数据加载
1. LauncherModel.loadWorkspace
	LauncherProvider.loadDefaultFavoritesIfNecessary -> mOpenHelper.loadFavorites
2. LauncherModel.loadAllApps

LauncherModel
	创建Thread  sWorkThread及对应的Handler sWorker
	创建main thread 的 handler 对象
	
	1.sBgWorkspaceItems		1.appinfo shortcut并且容器(container)不是folder; 2.folderInfo
	2.sBgAppWidgets		
	3.sBgFolders 	1.folder的id和对应的folderInfo的键值对
	4.sBgDbIconCache:	the set of ItemInfos that need to have their icons updated in the databas
	5.sBgWorkspaceScreens

HashMap<Long, ItemInfo> sBgItemsIdMap = id(_id)和itemInfo的键值对

图标: BubbleTextView	layout/application	对应的style: WorkspaceIcon
folder图标:	FolderIcon	layou/folder_icon	包含一个ImageView(背景图片) 和一个 BubbleTextView

workspace cellLayout:	workspace_screen

1.桌面shortcut两行:  对应的style: WorkspaceIcon
2.folder中2行:	DynamicGrid设置	folderCellHeightPx
3.AllApps背景透明度: 	AppsCustomizeTabHost.onTabChangedEnd(ContentType)
