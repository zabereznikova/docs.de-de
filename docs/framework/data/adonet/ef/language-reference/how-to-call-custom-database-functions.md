---
title: 'Vorgehensweise: Rufen benutzerdefinierter Datenbankfunktionen auf'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4354e5eb-dd45-469d-97fb-1c495705ee59
ms.openlocfilehash: 5ea558e23b6b0c191244031560c0fcf4738604e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54731100"
---
# <a name="how-to-call-custom-database-functions"></a><span data-ttu-id="93eec-102">Vorgehensweise: Rufen benutzerdefinierter Datenbankfunktionen auf</span><span class="sxs-lookup"><span data-stu-id="93eec-102">How to: Call Custom Database Functions</span></span>
<span data-ttu-id="93eec-103">In diesem Thema wird das Aufrufen von benutzerdefinierten Funktionen beschrieben, die in der Datenbank in LINQ to Entities-Abfragen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="93eec-103">This topic describes how to call custom functions that are defined in the database from within LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="93eec-104">Datenbankfunktionen, die von LINQ to Entities-Abfragen aufgerufen werden, werden in der Datenbank ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="93eec-104">Database functions that are called from LINQ to Entities queries are executed in the database.</span></span> <span data-ttu-id="93eec-105">Das Ausführen von Funktionen in der Datenbank kann die Anwendungsleistung verbessern.</span><span class="sxs-lookup"><span data-stu-id="93eec-105">Executing functions in the database can improve application performance.</span></span>  
  
 <span data-ttu-id="93eec-106">Die folgende Prozedur stellt in knapper Form dar, wie eine benutzerdefinierte Datenbankfunktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="93eec-106">The procedure below provides a high-level outline for calling a custom database function.</span></span> <span data-ttu-id="93eec-107">Das folgende Beispiel enthält weitere Details zu den Schritten in der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="93eec-107">The example that follows provides more detail about the steps in the procedure.</span></span>  
  
### <a name="to-call-custom-functions-that-are-defined-in-the-database"></a><span data-ttu-id="93eec-108">So rufen Sie benutzerdefinierte Funktionen auf, die in der Datenbank definiert sind</span><span class="sxs-lookup"><span data-stu-id="93eec-108">To call custom functions that are defined in the database</span></span>  
  
1.  <span data-ttu-id="93eec-109">Erstellen Sie in der Datenbank eine benutzerdefinierte Funktion.</span><span class="sxs-lookup"><span data-stu-id="93eec-109">Create a custom function in your database.</span></span>  
  
     <span data-ttu-id="93eec-110">Weitere Informationen zum Erstellen von benutzerdefinierter Funktionen in SQL Server finden Sie unter [CREATE FUNCTION (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkID=139871).</span><span class="sxs-lookup"><span data-stu-id="93eec-110">For more information about creating custom functions in SQL Server, see [CREATE FUNCTION (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkID=139871).</span></span>  
  
2.  <span data-ttu-id="93eec-111">Beschreiben Sie in der Datenspeicherschema-Definitionssprache (SSDL) der EDMX-Datei eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="93eec-111">Declare a function in the store schema definition language (SSDL) of your .edmx file.</span></span> <span data-ttu-id="93eec-112">Der Name der Funktion muss mit der in der Datenbank deklarierten Funktion übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="93eec-112">The name of the function must be the same as the name of the function declared in the database.</span></span>  
  
     <span data-ttu-id="93eec-113">Weitere Informationen finden Sie unter [Function-Element (SSDL)](https://msdn.microsoft.com/library/b60cfc3d-8b93-423e-8c99-b867256640a4).</span><span class="sxs-lookup"><span data-stu-id="93eec-113">For more information, see [Function Element (SSDL)](https://msdn.microsoft.com/library/b60cfc3d-8b93-423e-8c99-b867256640a4).</span></span>  
  
3.  <span data-ttu-id="93eec-114">Fügen Sie einer Klasse im Anwendungscode eine entsprechende Methode hinzu, und übernehmen Sie ein <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> für die Methode. Der <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A>-Parameter und der <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A>-Parameter des Attributs sind die Namespacebezeichnung des konzeptionellen Modells bzw. der Funktionsname im konzeptionellen Modell.</span><span class="sxs-lookup"><span data-stu-id="93eec-114">Add a corresponding method to a class in your application code and apply a <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model respectively.</span></span> <span data-ttu-id="93eec-115">Bei der Funktionsnamenauflösung für LINQ wird die Groß-/Kleinschreibung berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="93eec-115">Function name resolution for LINQ is case sensitive.</span></span>  
  
4.  <span data-ttu-id="93eec-116">Rufen Sie die Methode in einer LINQ to Entities-Abfrage auf.</span><span class="sxs-lookup"><span data-stu-id="93eec-116">Call the method in a LINQ to Entities query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93eec-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="93eec-117">Example</span></span>  
 <span data-ttu-id="93eec-118">Das folgende Beispiel zeigt, wie eine benutzerdefinierte Datenbankfunktion innerhalb einer LINQ to Entities-Abfrage aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="93eec-118">The following example demonstrates how to call a custom database function from within a LINQ to Entities query.</span></span> <span data-ttu-id="93eec-119">Im Beispiel wird das Modell "School" verwendet.</span><span class="sxs-lookup"><span data-stu-id="93eec-119">The example uses the School model.</span></span> <span data-ttu-id="93eec-120">Weitere Informationen über das Modell "School" finden Sie unter [Erstellen der Beispieldatenbank "School"](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) und [Generieren der EDMX-Datei des "School"](https://msdn.microsoft.com/library/c48b3907-a8be-4fe6-884c-e95af1852758).</span><span class="sxs-lookup"><span data-stu-id="93eec-120">For information about the School model, see [Creating the School Sample Database](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) and [Generating the School .edmx File](https://msdn.microsoft.com/library/c48b3907-a8be-4fe6-884c-e95af1852758).</span></span>  
  
 <span data-ttu-id="93eec-121">Der folgende Code fügt die `AvgStudentGrade`-Funktion der Beispieldatenbank "School" hinzu.</span><span class="sxs-lookup"><span data-stu-id="93eec-121">The following code adds the `AvgStudentGrade` function to the School sample database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93eec-122">Die Schritte zum Aufrufen einer benutzerdefinierten Datenbankfunktion sind unabhängig vom Datenbankserver identisch.</span><span class="sxs-lookup"><span data-stu-id="93eec-122">The steps for calling a custom database function are the same regardless of the database server.</span></span> <span data-ttu-id="93eec-123">Der folgende Code wird jedoch speziell für die Erstellung einer Funktion in einer SQL Server-Datenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="93eec-123">However, the code below is specific to creating a function in a SQL Server database.</span></span> <span data-ttu-id="93eec-124">Der Code zum Erstellen einer benutzerdefinierten Funktion in einem anderen Datenbankserver kann ggf. abweichen.</span><span class="sxs-lookup"><span data-stu-id="93eec-124">The code for creating a custom function in other database servers might differ.</span></span>  
  
 [!code-sql[DP L2E MapToDBFunction#1](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp l2e maptodbfunction/tsql/create_avgstudentgrade.sql#1)]  
  
## <a name="example"></a><span data-ttu-id="93eec-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="93eec-125">Example</span></span>  
 <span data-ttu-id="93eec-126">Beschreiben Sie nun in der Datenspeicherschema-Definitionssprache (SSDL) der EDMX-Datei eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="93eec-126">Next, declare a function in the store schema definition language (SSDL) of your .edmx file.</span></span> <span data-ttu-id="93eec-127">Der folgenden Code beschreibt die `AvgStudentGrade`-Funktion in SSDL:</span><span class="sxs-lookup"><span data-stu-id="93eec-127">the following code declares the `AvgStudentGrade` function in SSDL:</span></span>  
  
 [!code-xml[DP L2E MapToDBFunction#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/school.edmx#2)]  
  
## <a name="example"></a><span data-ttu-id="93eec-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="93eec-128">Example</span></span>  
 <span data-ttu-id="93eec-129">Erstellen Sie jetzt eine Methode, und ordnen Sie sie der in der SSDL beschriebenen Funktion zu.</span><span class="sxs-lookup"><span data-stu-id="93eec-129">Now create a method and map it to the function declared in the SSDL.</span></span> <span data-ttu-id="93eec-130">Die Methode in der folgenden Klasse wird der Funktion zugeordnet, die in der SSDL (oben) mithilfe eines <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="93eec-130">The method in the following class is mapped to the function defined in the SSDL (above) by using an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span> <span data-ttu-id="93eec-131">Wird diese Methode aufgerufen, wird die entsprechende Funktion in der Datenbank ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="93eec-131">When this method is called, the corresponding function in the database is executed.</span></span>  
  
 [!code-csharp[DP L2E MapToDBFunction#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#3)]
 [!code-vb[DP L2E MapToDBFunction#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="93eec-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="93eec-132">Example</span></span>  
 <span data-ttu-id="93eec-133">Rufen Sie schließlich die Methode in einer LINQ to Entities-Abfrage auf.</span><span class="sxs-lookup"><span data-stu-id="93eec-133">Finally, call the method in a LINQ to Entities query.</span></span> <span data-ttu-id="93eec-134">Im folgenden Code werden die Nachnamen und Durchschnittsnoten von Schülern auf der Konsole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="93eec-134">The following code displays students' last names and average grades to the console:</span></span>  
  
 [!code-csharp[DP L2E MapToDBFunction#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#4)]
 [!code-vb[DP L2E MapToDBFunction#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="93eec-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93eec-135">See also</span></span>
- [<span data-ttu-id="93eec-136">Übersicht über die EDMX-Datei</span><span class="sxs-lookup"><span data-stu-id="93eec-136">.edmx File Overview</span></span>](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)
- [<span data-ttu-id="93eec-137">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="93eec-137">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
