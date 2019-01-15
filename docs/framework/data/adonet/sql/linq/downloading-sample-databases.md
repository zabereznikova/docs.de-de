---
title: Rufen Sie die SQL Server-Beispieldatenbanken für ADO.NET-Codebeispiele
description: Laden Sie die SQL Server-Beispieldatenbanken, die in den Codebeispielen in der Dokumentation zu ADO.NET sowie SQL Server und Verwaltungstools verwendet
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 5580f06f3d28ed6d70f75b619498ac8de7bc3326
ms.sourcegitcommit: 75567a3cb437009db55949c6092f4e77ed1a9da4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2019
ms.locfileid: "54307291"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="d3c4c-103">Rufen Sie die Beispieldatenbanken für ADO.NET-Codebeispiele</span><span class="sxs-lookup"><span data-stu-id="d3c4c-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="d3c4c-104">Eine Reihe von Beispielen und exemplarischen Vorgehensweisen in der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Dokumentation Beispieldatenbanken für SQL Server und SQL Server Express zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-104">A number of examples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample SQL Server databases and SQL Server Express.</span></span> <span data-ttu-id="d3c4c-105">Sie können diese Produkte kostenlos von Microsoft herunterladen.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-northwind-sample-database-for-sql-server"></a><span data-ttu-id="d3c4c-106">Abrufen der Northwind-Beispieldatenbank für SQL Server</span><span class="sxs-lookup"><span data-stu-id="d3c4c-106">Get the Northwind sample database for SQL Server</span></span>

<span data-ttu-id="d3c4c-107">Das Skript herunterladen `instnwnd.sql` aus den folgenden GitHub-Repository zum Erstellen und laden die Beispieldatenbank Northwind für SQL Server:</span><span class="sxs-lookup"><span data-stu-id="d3c4c-107">Download the script `instnwnd.sql` from the following GitHub repository to create and load the Northwind sample database for SQL Server:</span></span>

[<span data-ttu-id="d3c4c-108">Northwind und Pubs-Beispieldatenbanken für Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="d3c4c-108">Northwind and pubs sample databases for Microsoft SQL Server</span></span>](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

<span data-ttu-id="d3c4c-109">Bevor Sie die Northwind-Datenbank verwenden können, müssen Sie führen Sie die heruntergeladene `instnwnd.sql` Skriptdatei, mit die Datenbank auf einer Instanz von SQL Server neu zu erstellen [SQL Server Management Studio](#get_ssms) oder ein ähnliches Tool.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-109">Before you can use the Northwind database, you have to run the downloaded `instnwnd.sql` script file to recreate the database on an instance of SQL Server by using [SQL Server Management Studio](#get_ssms) or a similar tool.</span></span> <span data-ttu-id="d3c4c-110">Folgen Sie den Anweisungen der Readme-Datei im Repository aus.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-110">Follow the instructions in the Readme file in the repository.</span></span>

> [!TIP]
> <span data-ttu-id="d3c4c-111">Wenn Sie für die Datenbank Northwind für Microsoft Access suchen, finden Sie unter [installieren die Beispieldatenbank Northwind für Microsoft Access](#northwind_access).</span><span class="sxs-lookup"><span data-stu-id="d3c4c-111">If you're looking for the Northwind database for Microsoft Access, see [Install the Northwind sample database for Microsoft Access](#northwind_access).</span></span>

## <a name="northwind_access"></a> <span data-ttu-id="d3c4c-112">Abrufen der Northwind-Beispieldatenbank für Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="d3c4c-112">Get the Northwind sample database for Microsoft Access</span></span>

<span data-ttu-id="d3c4c-113">Die Northwind-Beispieldatenbank für Microsoft Access ist nicht im Microsoft Download Center verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-113">The Northwind sample database for Microsoft Access is not available on the Microsoft Download Center.</span></span> <span data-ttu-id="d3c4c-114">Um Northwind direkt von innerhalb von Access zu installieren, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="d3c4c-114">To install Northwind directly from within Access, do the following things:</span></span>

1. <span data-ttu-id="d3c4c-115">Öffnen Sie den Zugriff.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-115">Open Access.</span></span>

1. <span data-ttu-id="d3c4c-116">Geben Sie **Northwind** in die **Onlinevorlagen suchen** Feld, und wählen Sie dann **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-116">Enter **Northwind** in the **Search for Online Templates** box, and then select **Enter**.</span></span>

1. <span data-ttu-id="d3c4c-117">Wählen Sie auf dem Bildschirm "Ergebnisse" **Northwind**.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-117">On the results screen, select **Northwind**.</span></span> <span data-ttu-id="d3c4c-118">Es wird ein neues Fenster mit einer Beschreibung der Northwind-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-118">A new window opens with a description of the Northwind database.</span></span>

1. <span data-ttu-id="d3c4c-119">Im neuen Fenster in der **Dateiname** Text geben einen Dateinamen für Ihre Kopie der Northwind-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-119">In the new window, in the **File Name** text box, provide a filename for your copy of the Northwind database.</span></span>

1. <span data-ttu-id="d3c4c-120">Wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-120">Select **Create**.</span></span> <span data-ttu-id="d3c4c-121">Der Zugriff die Northwind-Datenbank-downloads und bereitet Sie vor.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-121">Access downloads the Northwind database and prepares the file.</span></span>

1. <span data-ttu-id="d3c4c-122">Wenn dieser Prozess abgeschlossen ist, öffnet sich die Datenbank mit der eine Willkommensseite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-122">When this process is complete, the database opens with a Welcome screen.</span></span>

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="d3c4c-123">Abrufen der AdventureWorks-Beispieldatenbank für SQL Server</span><span class="sxs-lookup"><span data-stu-id="d3c4c-123">Get the AdventureWorks sample database for SQL Server</span></span>

<span data-ttu-id="d3c4c-124">Laden Sie die AdventureWorks-Beispieldatenbank für SQL Server aus dem folgenden GitHub-Repository herunter:</span><span class="sxs-lookup"><span data-stu-id="d3c4c-124">Download the AdventureWorks sample database for SQL Server from the following GitHub repository:</span></span>

[<span data-ttu-id="d3c4c-125">AdventureWorks-Beispieldatenbanken</span><span class="sxs-lookup"><span data-stu-id="d3c4c-125">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="d3c4c-126">Nachdem Sie eine der Sicherungskopie der Datenbank herunterladen (\*. bak) Dateien wiederherstellen die Sicherung mit einer Instanz von SQL Server mithilfe von SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="d3c4c-126">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="d3c4c-127">Finden Sie unter [erhalten SQL Server Management Studio](#get_ssms).</span><span class="sxs-lookup"><span data-stu-id="d3c4c-127">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get_ssms"></a> <span data-ttu-id="d3c4c-128">Get SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d3c4c-128">Get SQL Server Management Studio</span></span>
<span data-ttu-id="d3c4c-129">Wenn Sie möchten anzeigen oder Ändern einer Datenbank, die Sie heruntergeladen haben, können Sie SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="d3c4c-129">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="d3c4c-130">Herunterladen von SSMS auf der folgenden Seite:</span><span class="sxs-lookup"><span data-stu-id="d3c4c-130">Download SSMS from the following page:</span></span>

[<span data-ttu-id="d3c4c-131">SQL Server Management Studio (SSMS) herunterladen</span><span class="sxs-lookup"><span data-stu-id="d3c4c-131">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms) 

<span data-ttu-id="d3c4c-132">Sie können auch anzeigen und Verwalten von Datenbanken in der integrierten Entwicklungsumgebung (IDE) von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-132">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="d3c4c-133">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), Verbinden mit der Datenbank aus **Objekt-Explorer von SQL Server**, oder erstellen Sie eine Datenverbindung mit der Datenbank in **Server-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-133">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="d3c4c-134">Öffnen Sie diese Explorer-Bereiche aus der **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-134">Open these explorer panes from the **View** menu.</span></span>

## <a name="get_sql"></a> <span data-ttu-id="d3c4c-135">Erwerben von SQLServer Express</span><span class="sxs-lookup"><span data-stu-id="d3c4c-135">Get SQL Server Express</span></span>

<span data-ttu-id="d3c4c-136">SQL Server Express ist eine kostenlose, professionelles Edition von SQL Server, die Sie mit Anwendungen verteilen können.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-136">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="d3c4c-137">SQL Server Express auf der folgenden Seite herunterladen:</span><span class="sxs-lookup"><span data-stu-id="d3c4c-137">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="d3c4c-138">SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="d3c4c-138">SQL Server Express Edition</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="d3c4c-139">Bei Verwendung von [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB ist in der kostenlosen communityedition von Visual Studio als auch die Editionen Professional und höheren enthalten.</span><span class="sxs-lookup"><span data-stu-id="d3c4c-139">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB is included in the free Community edition of Visual Studio, as well as the Professional and higher editions.</span></span>  

## <a name="see-also"></a><span data-ttu-id="d3c4c-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3c4c-140">See also</span></span>

- [<span data-ttu-id="d3c4c-141">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="d3c4c-141">Getting Started</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
