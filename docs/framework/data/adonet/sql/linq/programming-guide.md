---
title: Programmierhandbuch
ms.date: 03/30/2017
ms.assetid: ed1012d4-3ff2-4877-af27-93125c4180ea
ms.openlocfilehash: 542567cf07e86b642a23a879fa6e5476253005b8
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2020
ms.locfileid: "78848937"
---
# <a name="programming-guide"></a><span data-ttu-id="6983c-102">Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6983c-102">Programming Guide</span></span>
<span data-ttu-id="6983c-103">Dieser Abschnitt enthält Informationen zur Erstellung und Nutzung Ihres [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Objektmodells.</span><span class="sxs-lookup"><span data-stu-id="6983c-103">This section contains information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="6983c-104">Wenn Sie Visual Studio verwenden, können Sie auch den Objektrelational-Designer verwenden, um viele dieser Aufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6983c-104">If you are using Visual Studio, you can also use the Object Relational Designer to perform many of these same tasks.</span></span>  
  
 <span data-ttu-id="6983c-105">Sie können auch Microsoft Docs nach bestimmten Problemen durchsuchen und am [LINQ-Forum](https://social.msdn.microsoft.com/forums/home?forum=linqtosql)teilnehmen, in dem Sie komplexere Themen mit Experten ausführlich diskutieren können.</span><span class="sxs-lookup"><span data-stu-id="6983c-105">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](https://social.msdn.microsoft.com/forums/home?forum=linqtosql), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="6983c-106">Schließlich wird die [LINQ to SQL: .NET Language-Integrated Query for Relational](https://docs.microsoft.com/previous-versions/dotnet/articles/bb425822(v=msdn.10)) Data-Whitepaper-Detailstechnologie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mit Visual Basic- und C-Codebeispielen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6983c-106">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](https://docs.microsoft.com/previous-versions/dotnet/articles/bb425822(v=msdn.10)) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with Visual Basic and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6983c-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6983c-107">In This Section</span></span>  
 [<span data-ttu-id="6983c-108">Erstellen des Objektmodells</span><span class="sxs-lookup"><span data-stu-id="6983c-108">Creating the Object Model</span></span>](creating-the-object-model.md)  
 <span data-ttu-id="6983c-109">Erläutert das Erzeugen eines Objektmodells.</span><span class="sxs-lookup"><span data-stu-id="6983c-109">Describes how to generate an object model.</span></span>  
  
 [<span data-ttu-id="6983c-110">Kommunizieren mit der Datenbank</span><span class="sxs-lookup"><span data-stu-id="6983c-110">Communicating with the Database</span></span>](communicating-with-the-database.md)  
 <span data-ttu-id="6983c-111">Erläutert die Verwendung eines <xref:System.Data.Linq.DataContext>-Objekts als Verbindung zur Datenbank.</span><span class="sxs-lookup"><span data-stu-id="6983c-111">Describes how to use a <xref:System.Data.Linq.DataContext> object as a conduit to the database.</span></span>  
  
 [<span data-ttu-id="6983c-112">Abfragen der Datenbank</span><span class="sxs-lookup"><span data-stu-id="6983c-112">Querying the Database</span></span>](querying-the-database.md)  
 <span data-ttu-id="6983c-113">Beschreibt, wie Abfragen in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ausgeführt werden, und stellt mehrere Beispiele bereit.</span><span class="sxs-lookup"><span data-stu-id="6983c-113">Describes how to execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], and provides many examples.</span></span>  
  
 [<span data-ttu-id="6983c-114">Vornehmen und Übergeben von Datenänderungen</span><span class="sxs-lookup"><span data-stu-id="6983c-114">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)  
 <span data-ttu-id="6983c-115">Beschreibt, wie Daten in der Datenbank geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6983c-115">Describes how change data in the database.</span></span>  
  
 [<span data-ttu-id="6983c-116">Debugging-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="6983c-116">Debugging Support</span></span>](debugging-support.md)  
 <span data-ttu-id="6983c-117">Beschreibt die verfügbare Unterstützung für das Debugging von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Projekten.</span><span class="sxs-lookup"><span data-stu-id="6983c-117">Describes the support available for debugging [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
 [<span data-ttu-id="6983c-118">Hintergrundinformationen</span><span class="sxs-lookup"><span data-stu-id="6983c-118">Background Information</span></span>](background-information.md)  
 <span data-ttu-id="6983c-119">Umfasst zusätzliche Elemente für fortgeschrittene Benutzer, z. B. die Auflösung von Parallelitätskonflikten, die Erstellung neuer Datenbanken etc.</span><span class="sxs-lookup"><span data-stu-id="6983c-119">Includes additional items, such as concurrency conflict resolution, creating new databases, and more, for more advanced users.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6983c-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="6983c-120">Related Sections</span></span>  
 [<span data-ttu-id="6983c-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="6983c-121">LINQ to SQL</span></span>](index.md)  
 <span data-ttu-id="6983c-122">Bietet Links zu Abschnitten, die die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Technologie erläutern und Funktionen demonstrieren.</span><span class="sxs-lookup"><span data-stu-id="6983c-122">Provides links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology and demonstrate features.</span></span>  
  
 [<span data-ttu-id="6983c-123">Gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="6983c-123">Stored Procedures</span></span>](stored-procedures.md)  
 <span data-ttu-id="6983c-124">Umfasst Links zu Themen, die die Verwendung gespeicherter Prozeduren erläutern.</span><span class="sxs-lookup"><span data-stu-id="6983c-124">Includes links to topics that illustrate how to use stored procedures.</span></span>  
  
 [<span data-ttu-id="6983c-125">Einführung in LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="6983c-125">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="6983c-126">Stellt Ressourcen bereit, mit denen Sie informationen zu LINQ to SQL mithilfe von C- und SQL-Code erfahren können.</span><span class="sxs-lookup"><span data-stu-id="6983c-126">Provides resources to help you begin to learn about LINQ to SQL using C#.</span></span>

 [<span data-ttu-id="6983c-127">Introduction to LINQ (Visual Basic) (Einführung in LINQ (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="6983c-127">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)  
 <span data-ttu-id="6983c-128">Stellt Ressourcen bereit, mit denen Sie mit Visual Basic mehr über LINQ in SQL erfahren können.</span><span class="sxs-lookup"><span data-stu-id="6983c-128">Provides resources to help you begin to learn about LINQ to SQL using Visual Basic.</span></span>
