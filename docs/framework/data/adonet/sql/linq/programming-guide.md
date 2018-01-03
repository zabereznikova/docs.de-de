---
title: Programmierhandbuch
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed1012d4-3ff2-4877-af27-93125c4180ea
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 431fb89c31e670b6a35a0d8908351a7ea60ce7ac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="programming-guide"></a><span data-ttu-id="77e13-102">Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="77e13-102">Programming Guide</span></span>
<span data-ttu-id="77e13-103">Dieser Abschnitt enthält Informationen zur Erstellung und Nutzung Ihres [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Objektmodells.</span><span class="sxs-lookup"><span data-stu-id="77e13-103">This section contains information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="77e13-104">Wenn Sie [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] verwenden, können Sie mit [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] viele dieser Aufgaben ausführen.</span><span class="sxs-lookup"><span data-stu-id="77e13-104">If you are using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], you can also use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to perform many of these same tasks.</span></span>  
  
 <span data-ttu-id="77e13-105">Sie können auch Microsoft Docs nach speziellen Themen suchen und Sie können teilnehmen, der [LINQ-Forum](http://go.microsoft.com/fwlink/?LinkId=76488), Hier können Sie komplexere Themen ausführlich mit Experten diskutieren.</span><span class="sxs-lookup"><span data-stu-id="77e13-105">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](http://go.microsoft.com/fwlink/?LinkId=76488), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="77e13-106">Schließlich bietet das Whitepaper [LINQ to SQL: .NET Language-Integrated Query for Relational Data (LINQ to SQL: .NET Language-Integrated Query für Relational Data)](http://go.microsoft.com/fwlink/?LinkId=93205) ausführliche Informationen zur [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Technologie sowie [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]- und C#-Codebeispiele.</span><span class="sxs-lookup"><span data-stu-id="77e13-106">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](http://go.microsoft.com/fwlink/?LinkId=93205) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="77e13-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="77e13-107">In This Section</span></span>  
 [<span data-ttu-id="77e13-108">Erstellen des Objektmodells</span><span class="sxs-lookup"><span data-stu-id="77e13-108">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 <span data-ttu-id="77e13-109">Erläutert das Erzeugen eines Objektmodells.</span><span class="sxs-lookup"><span data-stu-id="77e13-109">Describes how to generate an object model.</span></span>  
  
 [<span data-ttu-id="77e13-110">Kommunizieren mit der Datenbank</span><span class="sxs-lookup"><span data-stu-id="77e13-110">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)  
 <span data-ttu-id="77e13-111">Erläutert die Verwendung eines <xref:System.Data.Linq.DataContext>-Objekts als Verbindung zur Datenbank.</span><span class="sxs-lookup"><span data-stu-id="77e13-111">Describes how to use a <xref:System.Data.Linq.DataContext> object as a conduit to the database.</span></span>  
  
 [<span data-ttu-id="77e13-112">Abfragen der Datenbank</span><span class="sxs-lookup"><span data-stu-id="77e13-112">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)  
 <span data-ttu-id="77e13-113">Beschreibt, wie Abfragen in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ausgeführt werden, und stellt mehrere Beispiele bereit.</span><span class="sxs-lookup"><span data-stu-id="77e13-113">Describes how to execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], and provides many examples.</span></span>  
  
 [<span data-ttu-id="77e13-114">Vornehmen und Übergeben von Datenänderungen</span><span class="sxs-lookup"><span data-stu-id="77e13-114">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 <span data-ttu-id="77e13-115">Beschreibt, wie Daten in der Datenbank geändert werden.</span><span class="sxs-lookup"><span data-stu-id="77e13-115">Describes how change data in the database.</span></span>  
  
 [<span data-ttu-id="77e13-116">Debugunterstützung</span><span class="sxs-lookup"><span data-stu-id="77e13-116">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)  
 <span data-ttu-id="77e13-117">Beschreibt die verfügbare Unterstützung für das Debugging von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Projekten.</span><span class="sxs-lookup"><span data-stu-id="77e13-117">Describes the support available for debugging [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
 [<span data-ttu-id="77e13-118">Hintergrundinformationen</span><span class="sxs-lookup"><span data-stu-id="77e13-118">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 <span data-ttu-id="77e13-119">Umfasst zusätzliche Elemente für fortgeschrittene Benutzer, z. B. die Auflösung von Parallelitätskonflikten, die Erstellung neuer Datenbanken etc.</span><span class="sxs-lookup"><span data-stu-id="77e13-119">Includes additional items, such as concurrency conflict resolution, creating new databases, and more, for more advanced users.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="77e13-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="77e13-120">Related Sections</span></span>  
 [<span data-ttu-id="77e13-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="77e13-121">LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 <span data-ttu-id="77e13-122">Bietet Links zu Abschnitten, die die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Technologie erläutern und Funktionen demonstrieren.</span><span class="sxs-lookup"><span data-stu-id="77e13-122">Provides links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology and demonstrate features.</span></span>  
  
 [<span data-ttu-id="77e13-123">Gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="77e13-123">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 <span data-ttu-id="77e13-124">Umfasst Links zu Themen, die die Verwendung gespeicherter Prozeduren erläutern.</span><span class="sxs-lookup"><span data-stu-id="77e13-124">Includes links to topics that illustrate how to use stored procedures.</span></span>  
  
 [<span data-ttu-id="77e13-125">Einführung in LINQ</span><span class="sxs-lookup"><span data-stu-id="77e13-125">Introduction to LINQ</span></span>](http://msdn.microsoft.com/library/24dddf19-12a0-4707-a4bc-eba4fa7f219e)  
 <span data-ttu-id="77e13-126">Stellt Ressourcen bereit, die Ihnen die ersten Schritte mit [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erleichtern.</span><span class="sxs-lookup"><span data-stu-id="77e13-126">Provides resources to help you begin to learn about [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
