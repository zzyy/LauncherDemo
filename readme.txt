https://github.com/zzyy/LauncherDemo

1. LauncherProvider����, ��ʼ��provider, ����DatabaseHelper, ������Ӧ�����ݿ��
2. LauncherApplication extends Application, ��ʼ�� LauncherAppState
3. LauncherAppState �г�ʼ�� LauncherModel
4. ����Launcher �� onCreate

���ݼ���
1. LauncherModel.loadWorkspace
	LauncherProvider.loadDefaultFavoritesIfNecessary -> mOpenHelper.loadFavorites
2. LauncherModel.loadAllApps

LauncherModel
	����Thread  sWorkThread����Ӧ��Handler sWorker
	����main thread �� handler ����
	
	1.sBgWorkspaceItems		1.appinfo shortcut��������(container)����folder; 2.folderInfo
	2.sBgAppWidgets		
	3.sBgFolders 	1.folder��id�Ͷ�Ӧ��folderInfo�ļ�ֵ��
	4.sBgDbIconCache:	the set of ItemInfos that need to have their icons updated in the databas
	5.sBgWorkspaceScreens

HashMap<Long, ItemInfo> sBgItemsIdMap = id(_id)��itemInfo�ļ�ֵ��

ͼ��: BubbleTextView	layout/application	��Ӧ��style: WorkspaceIcon
folderͼ��:	FolderIcon	layou/folder_icon	����һ��ImageView(����ͼƬ) ��һ�� BubbleTextView

workspace cellLayout:	workspace_screen

1.����shortcut����:  ��Ӧ��style: WorkspaceIcon
2.folder��2��:	DynamicGrid����	folderCellHeightPx
3.AllApps����͸����: 	AppsCustomizeTabHost.onTabChangedEnd(ContentType)
