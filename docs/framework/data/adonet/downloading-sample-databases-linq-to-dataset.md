---
title: Herunterladen von Beispieldatenbanken (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: eb42a7af-d410-4b7f-b4a8-13c72ce6fd09
ms.openlocfilehash: f0fc3e8d447f82c89b3b558d95b45120db0a876d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573333"
---
# <a name="downloading-sample-databases-linq-to-dataset"></a><span data-ttu-id="8d4ec-102">Herunterladen von Beispieldatenbanken (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="8d4ec-102">Downloading Sample Databases (LINQ to DataSet)</span></span>
<span data-ttu-id="8d4ec-103">Die Beispiele und exemplarischen Vorgehensweisen in der [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Dokumentation verwenden die AdventureWorks-Beispieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-103">The samples and walkthroughs in the [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] documentation use the AdventureWorks sample database.</span></span> <span data-ttu-id="8d4ec-104">Sie können dieses Produkt kostenlos von der Microsoft-Downloadsite herunterladen.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-104">You can download this product free of charge from the Microsoft download site.</span></span> <span data-ttu-id="8d4ec-105">Als Datenspeicher für die Beispiele und exemplarischen Vorgehensweisen in der [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Dokumentation wird SQL Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-105">The samples and walkthroughs in the [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] documentation use SQL Server as the data store.</span></span> <span data-ttu-id="8d4ec-106">Statt SQL Server kann als Datenspeicher auch die kostenlos erhältliche SQL Server Express Edition verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-106">SQL Server Express Edition, which is available without charge, can also be used as the data store instead of SQL Server.</span></span>  
  
## <a name="downloading-and-installing-the-adventureworks-database"></a><span data-ttu-id="8d4ec-107">Herunterladen und Installieren der <legacyBold>AdventureWorks</legacyBold>-Datenbank</span><span class="sxs-lookup"><span data-stu-id="8d4ec-107">Downloading and Installing the AdventureWorks Database</span></span>  
  
#### <a name="to-download-and-install-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="8d4ec-108">So können Sie die <legacyBold>AdventureWorks</legacyBold>-Beispieldatenbank für SQL Server herunterladen und installieren</span><span class="sxs-lookup"><span data-stu-id="8d4ec-108">To download and install the AdventureWorks sample database for SQL Server</span></span>  
  
1.  <span data-ttu-id="8d4ec-109">Öffnen Sie Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-109">Open Internet Explorer.</span></span>  
  
2.  <span data-ttu-id="8d4ec-110">Wechseln Sie zu der [SQL Server 2005 Samples and Sample Databases](https://go.microsoft.com/fwlink/?linkid=31046) Website.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-110">Go to the [SQL Server 2005 Samples and Sample Databases](https://go.microsoft.com/fwlink/?linkid=31046) Web site.</span></span>  
  
3.  <span data-ttu-id="8d4ec-111">Befolgen Sie die Anweisungen zum Herunterladen der <legacyBold>AdventureWorks</legacyBold>-Beispieldatenbank für Ihren Prozessortyp (z. B. <legacyBold>AdventureWorksDB.msi</legacyBold>), und speichern Sie die MSI-Datei auf Ihrem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-111">Follow the instructions for downloading the AdventureWorks sample database for your processor type (such as AdventureWorksDB.msi), and save the .MSI file to your local computer.</span></span>  
  
4.  <span data-ttu-id="8d4ec-112">Wenn Sie bereits eine frühere <legacyBold>AdventureWorks</legacyBold>-Version heruntergeladen und installiert haben oder wenn <legacyBold>AdventureWorks</legacyBold> während der SQL-Einrichtung installiert wurde, müssen Sie diese frühere Version entfernen, bevor Sie <legacyBold>AdventureWorks.msi</legacyBold> ausführen.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-112">If you have a previous version of AdventureWorks installed from the download or during the SQL Server setup, you must remove it before running AdventureWorks.msi.</span></span>  
  
#### <a name="to-remove-a-previous-download-of-an-adventureworks-sample-database"></a><span data-ttu-id="8d4ec-113">So entfernen Sie eine zuvor heruntergeladene und installierte "AdventureWorks"-Beispieldatenbank</span><span class="sxs-lookup"><span data-stu-id="8d4ec-113">To remove a previous download of an AdventureWorks sample database</span></span>  
  
1.  <span data-ttu-id="8d4ec-114">Trennen Sie die Verbindung zur <legacyBold>AdventureWorks</legacyBold>- bzw. <legacyBold>AdventureWorksDW</legacyBold>-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-114">Drop the AdventureWorks or AdventureWorksDW database.</span></span>  
  
2.  <span data-ttu-id="8d4ec-115">Von **Software**Option **AdventureWorksDB** oder **AdventureWorksBI** , und klicken Sie auf **entfernen**.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-115">From **Add or Remove Programs**, select **AdventureWorksDB** or **AdventureWorksBI** and click **Remove**.</span></span>  
  
#### <a name="to-remove-an-adventureworks-sample-database-previously-installed-using-setup"></a><span data-ttu-id="8d4ec-116">So entfernen Sie eine zuvor mit Setup installierte "AdventureWorks"-Beispieldatenbank</span><span class="sxs-lookup"><span data-stu-id="8d4ec-116">To remove an AdventureWorks sample database previously installed using Setup</span></span>  
  
1.  <span data-ttu-id="8d4ec-117">Trennen Sie die Verbindung zur <legacyBold>AdventureWorks</legacyBold>- bzw. <legacyBold>AdventureWorksDW</legacyBold>-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-117">Drop the AdventureWorks or AdventureWorksDW database.</span></span>  
  
2.  <span data-ttu-id="8d4ec-118">Von **Software**Option **Microsoft SQL Server 2005** , und klicken Sie auf **Änderung**.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-118">From **Add or Remove Programs**, select **Microsoft SQL Server 2005** and click **Change**.</span></span>  
  
3.  <span data-ttu-id="8d4ec-119">Von **Komponentenauswahl**Option **Arbeitsstationskomponenten** , und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-119">From **Component Selection**, select **Workstation Components** and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="8d4ec-120">Von **Willkommen beim SQL Server-Installations-Assistenten**, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-120">From **Welcome to the SQL Server Installation Wizard**, click **Next**.</span></span>  
  
5.  <span data-ttu-id="8d4ec-121">Von **Systemkonfigurationsüberprüfung**, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-121">From **System Configuration Check**, click **Next**.</span></span>  
  
6.  <span data-ttu-id="8d4ec-122">Von **Instanz ändern oder entfernen**, klicken Sie auf **installierte Komponenten ändern**.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-122">From **Change or Remove Instance**, click **Change Installed Components**.</span></span>  
  
7.  <span data-ttu-id="8d4ec-123">Von **Funktionsauswahl**, erweitern Sie die **Dokumentation, Beispiele und Beispieldatenbanken** Knoten.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-123">From **Feature Selection**, expand the **Documentation, Samples, and Sample Databases** node.</span></span>  
  
8.  <span data-ttu-id="8d4ec-124">Wählen Sie **Beispielcode und Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-124">Select **Sample Code and Applications**.</span></span> <span data-ttu-id="8d4ec-125">Erweitern Sie **Sample Databases**, wählen Sie die Beispieldatenbank entfernt werden soll, und wählen Sie **gesamte Feature wird nicht mehr verfügbar sein**.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-125">Expand **Sample Databases**, select the sample database to be removed, and select **Entire feature will be unavailable**.</span></span> <span data-ttu-id="8d4ec-126">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-126">Click **Next**.</span></span>  
  
9. <span data-ttu-id="8d4ec-127">Klicken Sie auf **installieren** , und schließen Sie den Installations-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-127">Click **Install** and finish the installation wizard.</span></span>  
  
#### <a name="to-attach-the-adventureworks-sample-database-files-to-an-instance-of-sql-server"></a><span data-ttu-id="8d4ec-128">So fügen Sie die "AdventureWorks"-Beispieldatenbankdateien an eine Instanz von SQL Server an</span><span class="sxs-lookup"><span data-stu-id="8d4ec-128">To attach the AdventureWorks sample database files to an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="8d4ec-129">Nachdem die Datei-Beispiel-Datenbank-Installer-Datei heruntergeladen wurde, doppelklicken Sie auf die **AdventureWorksDB.msi** Datei (oder die Datei, die Sie heruntergeladen haben) zum Installieren der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-129">After the file sample database installer file has downloaded, double-click the **AdventureWorksDB.msi** file (or the file you downloaded) to install the database.</span></span> <span data-ttu-id="8d4ec-130">Der Standardspeicherort für die Datenbank ist <legacyBold>c:\Programme\Microsoft SQL Server\MSSQL.1\MSSQL\Data</legacyBold>.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-130">By default, the database is installed at c:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data.</span></span>  
  
2.  <span data-ttu-id="8d4ec-131">Fügen Sie die <legacyBold>AdventureWorks</legacyBold>-Datenbankdateien an eine Instanz von SQL Server an, indem Sie das folgende SQLCMD- oder SQL Server Management Studio-Skript ausführen:</span><span class="sxs-lookup"><span data-stu-id="8d4ec-131">Attach the AdventureWorks database files to an instance of SQL Server by executing the following script SQLCMD or SQL Server Management Studio:</span></span>  
  
    ```sql
    exec sp_attach_db @dbname=N'AdventureWorks', @filename1=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_Data.mdf', @filename2=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_log.ldf'  
    ```  
  
     <span data-ttu-id="8d4ec-132">Wenn Sie diese Dateien in einem anderen Verzeichnis oder auf einem anderen Laufwerk installiert haben, müssen Sie die Pfade entsprechend anpassen, bevor Sie die gespeicherte Prozedur `sp_attach_db` ausführen.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-132">If you have installed these files to a different drive or directory, you must revise the paths appropriately before you execute the `sp_attach_db` stored procedure.</span></span>  
  
## <a name="downloading-sql-server-express-edition"></a><span data-ttu-id="8d4ec-133">Herunterladen von SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="8d4ec-133">Downloading SQL Server Express Edition</span></span>  
 <span data-ttu-id="8d4ec-134">Die Beispiele und exemplarischen Vorgehensweisen in der [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abschnitt SQL Server 2005 als Datenspeicher verwenden, jedoch kann geändert werden, um SQL Server Express Edition verwenden.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-134">The samples and walkthroughs in the [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] section use SQL Server 2005 as the data store but can be modified to use SQL Server Express Edition, instead.</span></span> <span data-ttu-id="8d4ec-135">SQL Server Express Edition ist frei verfügbar, und Sie können diese Lösung mit Anwendungen verteilen.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-135">SQL Server Express Edition is available without charge, and you can redistribute it with applications.</span></span> <span data-ttu-id="8d4ec-136">Wenn Sie Visual Studio verwenden, ist SQL Server Express Edition in den Editionen Pro und höheren enthalten.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-136">If you are using Visual Studio, SQL Server Express Edition is included in the Pro and higher editions.</span></span>  
  
#### <a name="to-download-and-install-sql-server-express-edition"></a><span data-ttu-id="8d4ec-137">So können Sie SQL Server Express Edition herunterladen und installieren</span><span class="sxs-lookup"><span data-stu-id="8d4ec-137">To download and install SQL Server Express Edition</span></span>  
  
1.  <span data-ttu-id="8d4ec-138">Öffnen Sie Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-138">Start Internet Explorer.</span></span>  
  
2.  <span data-ttu-id="8d4ec-139">Wechseln Sie zu der [Microsoft SQL Server 2005 Express Edition](https://go.microsoft.com/fwlink/?LinkID=31070) Downloadseite.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-139">Go to the  [Microsoft SQL Server 2005 Express Edition](https://go.microsoft.com/fwlink/?LinkID=31070) download page.</span></span>  
  
3.  <span data-ttu-id="8d4ec-140">Befolgen Sie die Installationsanleitungen auf der Website.</span><span class="sxs-lookup"><span data-stu-id="8d4ec-140">Follow the installation instructions on the Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d4ec-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d4ec-141">See also</span></span>
- [<span data-ttu-id="8d4ec-142">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="8d4ec-142">Getting Started</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)
