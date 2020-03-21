---
title: Abrufen der SQL Server-Beispieldatenbanken für ADO.NET Codebeispiele
description: Laden Sie die SQL Server-Beispieldatenbanken herunter, die in den Codebeispielen in der ADO.NET-Dokumentation sowie sql Server- und Verwaltungstools verwendet werden.
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 19d659cbe8f39d27b71dc59c738355f12fce92a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148386"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="38856-103">Abrufen der Beispieldatenbanken für ADO.NET Codebeispiele</span><span class="sxs-lookup"><span data-stu-id="38856-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="38856-104">Eine Reihe von Beispielen und [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] exemplarischen Vorgehensweisen in der Dokumentation verwenden Beispielsql Server-Datenbanken und SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="38856-104">A number of examples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample SQL Server databases and SQL Server Express.</span></span> <span data-ttu-id="38856-105">Sie können diese Produkte kostenlos von Microsoft herunterladen.</span><span class="sxs-lookup"><span data-stu-id="38856-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-northwind-sample-database-for-sql-server"></a><span data-ttu-id="38856-106">Abrufen der Northwind-Beispieldatenbank für SQL Server</span><span class="sxs-lookup"><span data-stu-id="38856-106">Get the Northwind sample database for SQL Server</span></span>

<span data-ttu-id="38856-107">Laden Sie `instnwnd.sql` das Skript aus dem folgenden GitHub-Repository herunter, um die Northwind-Beispieldatenbank für SQL Server zu erstellen und zu laden:</span><span class="sxs-lookup"><span data-stu-id="38856-107">Download the script `instnwnd.sql` from the following GitHub repository to create and load the Northwind sample database for SQL Server:</span></span>

[<span data-ttu-id="38856-108">Northwind- und Pubs-Beispieldatenbanken für Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="38856-108">Northwind and pubs sample databases for Microsoft SQL Server</span></span>](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

<span data-ttu-id="38856-109">Bevor Sie die Northwind-Datenbank verwenden können, `instnwnd.sql` müssen Sie die heruntergeladene Skriptdatei ausführen, um die Datenbank auf einer Instanz von SQL Server mithilfe von [SQL Server Management Studio](#get_ssms) oder einem ähnlichen Tool neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="38856-109">Before you can use the Northwind database, you have to run the downloaded `instnwnd.sql` script file to recreate the database on an instance of SQL Server by using [SQL Server Management Studio](#get_ssms) or a similar tool.</span></span> <span data-ttu-id="38856-110">Folgen Sie den Anweisungen in der Readme-Datei im Repository.</span><span class="sxs-lookup"><span data-stu-id="38856-110">Follow the instructions in the Readme file in the repository.</span></span>

> [!TIP]
> <span data-ttu-id="38856-111">Informationen zur Northwind-Datenbank für Microsoft Access finden Sie unter [Installieren der Northwind-Beispieldatenbank für Microsoft Access](#northwind_access).</span><span class="sxs-lookup"><span data-stu-id="38856-111">If you're looking for the Northwind database for Microsoft Access, see [Install the Northwind sample database for Microsoft Access](#northwind_access).</span></span>

## <a name="get-the-northwind-sample-database-for-microsoft-access"></a><a name="northwind_access"></a><span data-ttu-id="38856-112">Abrufen der Northwind-Beispieldatenbank für Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="38856-112">Get the Northwind sample database for Microsoft Access</span></span>

<span data-ttu-id="38856-113">Die Northwind-Beispieldatenbank für Microsoft Access ist im Microsoft Download Center nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="38856-113">The Northwind sample database for Microsoft Access is not available on the Microsoft Download Center.</span></span> <span data-ttu-id="38856-114">Gehen Sie folgendzulande vor, um Northwind direkt in Access zu installieren:</span><span class="sxs-lookup"><span data-stu-id="38856-114">To install Northwind directly from within Access, do the following things:</span></span>

1. <span data-ttu-id="38856-115">Open Access.</span><span class="sxs-lookup"><span data-stu-id="38856-115">Open Access.</span></span>

1. <span data-ttu-id="38856-116">Geben Sie **Northwind** in das Feld **Suchen nach Onlinevorlagen** ein, und wählen Sie dann **Eingeben**aus.</span><span class="sxs-lookup"><span data-stu-id="38856-116">Enter **Northwind** in the **Search for Online Templates** box, and then select **Enter**.</span></span>

1. <span data-ttu-id="38856-117">Wählen Sie auf dem Ergebnisbildschirm **Northwind**aus.</span><span class="sxs-lookup"><span data-stu-id="38856-117">On the results screen, select **Northwind**.</span></span> <span data-ttu-id="38856-118">Ein neues Fenster wird mit einer Beschreibung der Northwind-Datenbank geöffnet.</span><span class="sxs-lookup"><span data-stu-id="38856-118">A new window opens with a description of the Northwind database.</span></span>

1. <span data-ttu-id="38856-119">Geben Sie im neuen Fenster im Textfeld **Dateiname** einen Dateinamen für Ihre Kopie der Northwind-Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="38856-119">In the new window, in the **File Name** text box, provide a filename for your copy of the Northwind database.</span></span>

1. <span data-ttu-id="38856-120">Wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="38856-120">Select **Create**.</span></span> <span data-ttu-id="38856-121">Access lädt die Northwind-Datenbank herunter und bereitet die Datei vor.</span><span class="sxs-lookup"><span data-stu-id="38856-121">Access downloads the Northwind database and prepares the file.</span></span>

1. <span data-ttu-id="38856-122">Wenn dieser Vorgang abgeschlossen ist, wird die Datenbank mit einem Begrüßungsbildschirm geöffnet.</span><span class="sxs-lookup"><span data-stu-id="38856-122">When this process is complete, the database opens with a Welcome screen.</span></span>

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="38856-123">Abrufen der AdventureWorks-Beispieldatenbank für SQL Server</span><span class="sxs-lookup"><span data-stu-id="38856-123">Get the AdventureWorks sample database for SQL Server</span></span>

<span data-ttu-id="38856-124">Laden Sie die AdventureWorks-Beispieldatenbank für SQL Server aus dem folgenden GitHub-Repository herunter:</span><span class="sxs-lookup"><span data-stu-id="38856-124">Download the AdventureWorks sample database for SQL Server from the following GitHub repository:</span></span>

[<span data-ttu-id="38856-125">AdventureWorks-Beispieldatenbanken</span><span class="sxs-lookup"><span data-stu-id="38856-125">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="38856-126">Nachdem Sie eine der Datenbanksicherungsdateien (.bak)\*heruntergeladen haben, stellen Sie die Sicherung mithilfe von SQL Server Management Studio (SSMS) auf einer Instanz von SQL Server wieder her.</span><span class="sxs-lookup"><span data-stu-id="38856-126">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="38856-127">Weitere Informationen finden Sie unter Abrufen von [SQL Server Management Studio](#get_ssms).</span><span class="sxs-lookup"><span data-stu-id="38856-127">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get-sql-server-management-studio"></a><a name="get_ssms"></a><span data-ttu-id="38856-128">SQL Server Management Studio abrufen</span><span class="sxs-lookup"><span data-stu-id="38856-128">Get SQL Server Management Studio</span></span>
<span data-ttu-id="38856-129">Wenn Sie eine heruntergeladene Datenbank anzeigen oder ändern möchten, können Sie SQL Server Management Studio (SSMS) verwenden.</span><span class="sxs-lookup"><span data-stu-id="38856-129">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="38856-130">Laden Sie SSMS von der folgenden Seite herunter:</span><span class="sxs-lookup"><span data-stu-id="38856-130">Download SSMS from the following page:</span></span>

[<span data-ttu-id="38856-131">Herunterladen von SQL Server Management Studio (SSMS)</span><span class="sxs-lookup"><span data-stu-id="38856-131">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms)

<span data-ttu-id="38856-132">Sie können Datenbanken auch in der integrierten Visual Studio-Entwicklungsumgebung (IDE) anzeigen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="38856-132">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="38856-133">Stellen Sie in [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)eine Verbindung mit der Datenbank über den **SQL Server-Objekt-Explorer**her, oder erstellen Sie eine Datenverbindung zur Datenbank im **Server-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="38856-133">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="38856-134">Öffnen Sie diese Explorer-Bereiche im Menü **Ansicht.**</span><span class="sxs-lookup"><span data-stu-id="38856-134">Open these explorer panes from the **View** menu.</span></span>

## <a name="get-sql-server-express"></a><a name="get_sql"></a><span data-ttu-id="38856-135">SQL Server Express abrufen</span><span class="sxs-lookup"><span data-stu-id="38856-135">Get SQL Server Express</span></span>

<span data-ttu-id="38856-136">SQL Server Express ist eine kostenlose Einstiegsedition von SQL Server, die Sie mit Anwendungen weiterverteilen können.</span><span class="sxs-lookup"><span data-stu-id="38856-136">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="38856-137">Laden Sie SQL Server Express von der folgenden Seite herunter:</span><span class="sxs-lookup"><span data-stu-id="38856-137">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="38856-138">SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="38856-138">SQL Server Express Edition</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="38856-139">Wenn Sie [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)verwenden, ist SQL Server Express LocalDB in der kostenlosen Community-Edition von Visual Studio sowie in den Professional- und höheren Editionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="38856-139">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB is included in the free Community edition of Visual Studio, as well as the Professional and higher editions.</span></span>  

## <a name="see-also"></a><span data-ttu-id="38856-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="38856-140">See also</span></span>

- [<span data-ttu-id="38856-141">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="38856-141">Getting Started</span></span>](getting-started.md)
