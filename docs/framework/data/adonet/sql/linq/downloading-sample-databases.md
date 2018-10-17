---
title: Rufen Sie die Beispieldatenbanken für ADO.NET-Codebeispiele
description: Laden Sie die Beispieldatenbanken, die in den Codebeispielen in der Dokumentation zu ADO.NET sowie SQL Server und Verwaltungstools verwendet
ms.date: 10/12/2018
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 75ae1895d683b669f51b33130fc2f47010e39814
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2018
ms.locfileid: "49347506"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="a33f2-103">Rufen Sie die Beispieldatenbanken für ADO.NET-Codebeispiele</span><span class="sxs-lookup"><span data-stu-id="a33f2-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="a33f2-104">Eine Reihe von Beispielen und exemplarischen Vorgehensweisen in der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Dokumentation zu verwenden, Beispieldatenbanken und SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="a33f2-104">A number of samples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample databases and SQL Server Express.</span></span> <span data-ttu-id="a33f2-105">Sie können diese Produkte kostenlos von Microsoft herunterladen.</span><span class="sxs-lookup"><span data-stu-id="a33f2-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-adventureworks-sample-database"></a><span data-ttu-id="a33f2-106">Abrufen der AdventureWorks-Beispieldatenbank</span><span class="sxs-lookup"><span data-stu-id="a33f2-106">Get the AdventureWorks sample database</span></span>

<span data-ttu-id="a33f2-107">Laden Sie die AdventureWorks-Beispieldatenbank aus den folgenden GitHub-Repository herunter:</span><span class="sxs-lookup"><span data-stu-id="a33f2-107">Download the AdventureWorks sample database from the following GitHub repository:</span></span>

[<span data-ttu-id="a33f2-108">AdventureWorks-Beispieldatenbanken</span><span class="sxs-lookup"><span data-stu-id="a33f2-108">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="a33f2-109">Nachdem Sie eine der Sicherungskopie der Datenbank herunterladen (\*. bak) Dateien wiederherstellen die Sicherung mit einer Instanz von SQL Server mithilfe von SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="a33f2-109">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="a33f2-110">Finden Sie unter [erhalten SQL Server Management Studio](#get_ssms).</span><span class="sxs-lookup"><span data-stu-id="a33f2-110">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get-the-northwind-sample-database"></a><span data-ttu-id="a33f2-111">Abrufen der Northwind-Beispieldatenbank</span><span class="sxs-lookup"><span data-stu-id="a33f2-111">Get the Northwind sample database</span></span>

<span data-ttu-id="a33f2-112">Laden Sie die Beispieldatenbank Northwind aus der folgenden Seite im Microsoft Download Center herunter:</span><span class="sxs-lookup"><span data-stu-id="a33f2-112">Download the Northwind sample database from the following page in the Microsoft Download Center:</span></span>

[<span data-ttu-id="a33f2-113">Northwind und Pubs-Beispieldatenbanken</span><span class="sxs-lookup"><span data-stu-id="a33f2-113">Northwind and Pubs Sample Databases</span></span>](https://go.microsoft.com/fwlink?linkid=64296)

<span data-ttu-id="a33f2-114">Nachdem die Datei heruntergeladen wurde, doppelklicken Sie auf die Datei, um die Datenbanken und die Skripts extrahieren.</span><span class="sxs-lookup"><span data-stu-id="a33f2-114">After the file has downloaded, double-click the file to extract the databases and scripts.</span></span> <span data-ttu-id="a33f2-115">Standardmäßig werden die Dateien im Ordner installiert `<drive>:\SQL Server 2000 Sample Databases`.</span><span class="sxs-lookup"><span data-stu-id="a33f2-115">By default, the files are installed in the folder `<drive>:\SQL Server 2000 Sample Databases`.</span></span>

<span data-ttu-id="a33f2-116">Bevor Sie die Northwind-Datenbank verwenden können, müssen Sie eine der folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="a33f2-116">Before you can use the Northwind database, you have to do one of the following things:</span></span>

- <span data-ttu-id="a33f2-117">Die Datenbank auf einer Instanz von SQL Server neu erstellen, mit der `instnwnd.sql` Skriptdatei im Installationsordner.</span><span class="sxs-lookup"><span data-stu-id="a33f2-117">Recreate the database on an instance of SQL Server by running the `instnwnd.sql` script file in the installation folder.</span></span>

- <span data-ttu-id="a33f2-118">Fügen Sie der `northwnd.mdf` Datei mit den entsprechenden `*.ldf` Protokolldatei mit einer Instanz von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a33f2-118">Attach the `northwnd.mdf` file with its corresponding `*.ldf` log file to an instance of SQL Server.</span></span>

## <a name="get_sql"></a> <span data-ttu-id="a33f2-119">Erwerben von SQLServer Express</span><span class="sxs-lookup"><span data-stu-id="a33f2-119">Get SQL Server Express</span></span>

<span data-ttu-id="a33f2-120">SQL Server Express ist eine kostenlose, professionelles Edition von SQL Server, die Sie mit Anwendungen verteilen können.</span><span class="sxs-lookup"><span data-stu-id="a33f2-120">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="a33f2-121">SQL Server Express auf der folgenden Seite herunterladen:</span><span class="sxs-lookup"><span data-stu-id="a33f2-121">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="a33f2-122">SQL Server Express-Editionen</span><span class="sxs-lookup"><span data-stu-id="a33f2-122">SQL Server Express Editions</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="a33f2-123">Bei Verwendung von [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB ist in der Community-Edition als auch für die Editionen Professional und höheren enthalten.</span><span class="sxs-lookup"><span data-stu-id="a33f2-123">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB is included in the Community edition as well as the Professional and higher editions.</span></span>  

## <a name="get_ssms"></a> <span data-ttu-id="a33f2-124">Abrufen von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a33f2-124">Get SQL Server Management Studio</span></span>
<span data-ttu-id="a33f2-125">Wenn Sie möchten anzeigen oder Ändern einer Datenbank, die Sie heruntergeladen haben, können Sie SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="a33f2-125">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="a33f2-126">Herunterladen von SSMS auf der folgenden Seite:</span><span class="sxs-lookup"><span data-stu-id="a33f2-126">Download SSMS from the following page:</span></span>

[<span data-ttu-id="a33f2-127">SQL Server Management Studio (SSMS) herunterladen</span><span class="sxs-lookup"><span data-stu-id="a33f2-127">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms) 

<span data-ttu-id="a33f2-128">Sie können auch anzeigen und Verwalten von Datenbanken in der integrierten Entwicklungsumgebung (IDE) von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a33f2-128">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="a33f2-129">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), Verbinden mit der Datenbank aus **Objekt-Explorer von SQL Server**, oder erstellen Sie eine Datenverbindung mit der Datenbank in **Server-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="a33f2-129">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="a33f2-130">Öffnen Sie diese Explorer-Bereiche aus der **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="a33f2-130">Open these explorer panes from the **View** menu.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a33f2-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a33f2-131">See also</span></span>

- [<span data-ttu-id="a33f2-132">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="a33f2-132">Getting Started</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
