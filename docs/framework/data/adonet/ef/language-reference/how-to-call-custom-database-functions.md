---
title: 'Gewusst wie: Aufrufen benutzerdefinierter Datenbankfunktionen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4354e5eb-dd45-469d-97fb-1c495705ee59
ms.openlocfilehash: e357868361e11dc919fa09db9a36185923a6e40e
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847098"
---
# <a name="how-to-call-custom-database-functions"></a><span data-ttu-id="0b617-102">Gewusst wie: Aufrufen benutzerdefinierter Datenbankfunktionen</span><span class="sxs-lookup"><span data-stu-id="0b617-102">How to: Call Custom Database Functions</span></span>

<span data-ttu-id="0b617-103">In diesem Thema wird das Aufrufen von benutzerdefinierten Funktionen beschrieben, die in der Datenbank in LINQ to Entities-Abfragen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="0b617-103">This topic describes how to call custom functions that are defined in the database from within LINQ to Entities queries.</span></span>

<span data-ttu-id="0b617-104">Datenbankfunktionen, die von LINQ to Entities-Abfragen aufgerufen werden, werden in der Datenbank ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0b617-104">Database functions that are called from LINQ to Entities queries are executed in the database.</span></span> <span data-ttu-id="0b617-105">Das Ausführen von Funktionen in der Datenbank kann die Anwendungsleistung verbessern.</span><span class="sxs-lookup"><span data-stu-id="0b617-105">Executing functions in the database can improve application performance.</span></span>

<span data-ttu-id="0b617-106">Die folgende Prozedur stellt in knapper Form dar, wie eine benutzerdefinierte Datenbankfunktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="0b617-106">The procedure below provides a high-level outline for calling a custom database function.</span></span> <span data-ttu-id="0b617-107">Das folgende Beispiel enthält weitere Details zu den Schritten in der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="0b617-107">The example that follows provides more detail about the steps in the procedure.</span></span>

## <a name="to-call-custom-functions-that-are-defined-in-the-database"></a><span data-ttu-id="0b617-108">So rufen Sie benutzerdefinierte Funktionen auf, die in der Datenbank definiert sind</span><span class="sxs-lookup"><span data-stu-id="0b617-108">To call custom functions that are defined in the database</span></span>

1. <span data-ttu-id="0b617-109">Erstellen Sie in der Datenbank eine benutzerdefinierte Funktion.</span><span class="sxs-lookup"><span data-stu-id="0b617-109">Create a custom function in your database.</span></span>

     <span data-ttu-id="0b617-110">Weitere Informationen zum Erstellen von benutzerdefinierten Funktionen in SQL Server finden Sie unter [CREATE FUNCTION (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkID=139871).</span><span class="sxs-lookup"><span data-stu-id="0b617-110">For more information about creating custom functions in SQL Server, see [CREATE FUNCTION (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkID=139871).</span></span>

2. <span data-ttu-id="0b617-111">Beschreiben Sie in der Datenspeicherschema-Definitionssprache (SSDL) der EDMX-Datei eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="0b617-111">Declare a function in the store schema definition language (SSDL) of your .edmx file.</span></span> <span data-ttu-id="0b617-112">Der Name der Funktion muss mit der in der Datenbank deklarierten Funktion übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="0b617-112">The name of the function must be the same as the name of the function declared in the database.</span></span>

     <span data-ttu-id="0b617-113">Weitere Informationen finden Sie unter [Function-Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#function-element-ssdl).</span><span class="sxs-lookup"><span data-stu-id="0b617-113">For more information, see [Function Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#function-element-ssdl).</span></span>

3. <span data-ttu-id="0b617-114">Fügen Sie einer Klasse im Anwendungscode eine entsprechende Methode hinzu, und übernehmen Sie ein <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> für die Methode. Der <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A>-Parameter und der <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A>-Parameter des Attributs sind die Namespacebezeichnung des konzeptionellen Modells bzw. der Funktionsname im konzeptionellen Modell.</span><span class="sxs-lookup"><span data-stu-id="0b617-114">Add a corresponding method to a class in your application code and apply a <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model respectively.</span></span> <span data-ttu-id="0b617-115">Bei der Funktionsnamenauflösung für LINQ wird die Groß-/Kleinschreibung berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="0b617-115">Function name resolution for LINQ is case sensitive.</span></span>

4. <span data-ttu-id="0b617-116">Rufen Sie die Methode in einer LINQ to Entities-Abfrage auf.</span><span class="sxs-lookup"><span data-stu-id="0b617-116">Call the method in a LINQ to Entities query.</span></span>  

## <a name="example"></a><span data-ttu-id="0b617-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0b617-117">Example</span></span>

<span data-ttu-id="0b617-118">Das folgende Beispiel zeigt, wie eine benutzerdefinierte Datenbankfunktion innerhalb einer LINQ to Entities-Abfrage aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="0b617-118">The following example demonstrates how to call a custom database function from within a LINQ to Entities query.</span></span> <span data-ttu-id="0b617-119">Im Beispiel wird das Modell "School" verwendet.</span><span class="sxs-lookup"><span data-stu-id="0b617-119">The example uses the School model.</span></span> <span data-ttu-id="0b617-120">Weitere Informationen zum Modell "School" finden Sie unter [Erstellen der Beispieldatenbank "School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) " und erstellen [der Datei "School. edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100))".</span><span class="sxs-lookup"><span data-stu-id="0b617-120">For information about the School model, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) and [Generating the School .edmx File](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).</span></span>

<span data-ttu-id="0b617-121">Der folgende Code fügt die `AvgStudentGrade`-Funktion der Beispieldatenbank "School" hinzu.</span><span class="sxs-lookup"><span data-stu-id="0b617-121">The following code adds the `AvgStudentGrade` function to the School sample database.</span></span>

> [!NOTE]
> <span data-ttu-id="0b617-122">Die Schritte zum Aufrufen einer benutzerdefinierten Datenbankfunktion sind unabhängig vom Datenbankserver identisch.</span><span class="sxs-lookup"><span data-stu-id="0b617-122">The steps for calling a custom database function are the same regardless of the database server.</span></span> <span data-ttu-id="0b617-123">Der folgende Code wird jedoch speziell für die Erstellung einer Funktion in einer SQL Server-Datenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="0b617-123">However, the code below is specific to creating a function in a SQL Server database.</span></span> <span data-ttu-id="0b617-124">Der Code zum Erstellen einer benutzerdefinierten Funktion in einem anderen Datenbankserver kann ggf. abweichen.</span><span class="sxs-lookup"><span data-stu-id="0b617-124">The code for creating a custom function in other database servers might differ.</span></span>

[!code-sql[DP L2E MapToDBFunction#1](~/samples/snippets/tsql/VS_Snippets_Data/dp l2e maptodbfunction/tsql/create_avgstudentgrade.sql#1)]

## <a name="example"></a><span data-ttu-id="0b617-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0b617-125">Example</span></span>

<span data-ttu-id="0b617-126">Deklarieren Sie als nächstes eine Funktion in der Datenspeicher Schema-Definitions Sprache (SSDL) der *edmx* -Datei.</span><span class="sxs-lookup"><span data-stu-id="0b617-126">Next, declare a function in the store schema definition language (SSDL) of your *.edmx* file.</span></span> <span data-ttu-id="0b617-127">Im folgenden Code wird die `AvgStudentGrade`-Funktion in SSDL deklariert:</span><span class="sxs-lookup"><span data-stu-id="0b617-127">The following code declares the `AvgStudentGrade` function in SSDL:</span></span>

[!code-xml[DP L2E MapToDBFunction#2](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/school.edmx#2)]

## <a name="example"></a><span data-ttu-id="0b617-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0b617-128">Example</span></span>

<span data-ttu-id="0b617-129">Erstellen Sie jetzt eine Methode, und ordnen Sie Sie der Funktion zu, die in SSDL deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="0b617-129">Now, create a method and map it to the function declared in the SSDL.</span></span> <span data-ttu-id="0b617-130">Die Methode in der folgenden Klasse wird der Funktion zugeordnet, die in der SSDL (oben) mithilfe eines <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="0b617-130">The method in the following class is mapped to the function defined in the SSDL (above) by using an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span> <span data-ttu-id="0b617-131">Wird diese Methode aufgerufen, wird die entsprechende Funktion in der Datenbank ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0b617-131">When this method is called, the corresponding function in the database is executed.</span></span>

[!code-csharp[DP L2E MapToDBFunction#3](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#3)]
[!code-vb[DP L2E MapToDBFunction#3](~/samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#3)]

## <a name="example"></a><span data-ttu-id="0b617-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0b617-132">Example</span></span>

<span data-ttu-id="0b617-133">Rufen Sie schließlich die Methode in einer LINQ to Entities-Abfrage auf.</span><span class="sxs-lookup"><span data-stu-id="0b617-133">Finally, call the method in a LINQ to Entities query.</span></span> <span data-ttu-id="0b617-134">Im folgenden Code werden die Nachnamen und Durchschnittsnoten von Schülern auf der Konsole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="0b617-134">The following code displays students' last names and average grades to the console:</span></span>

[!code-csharp[DP L2E MapToDBFunction#4](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#4)]
[!code-vb[DP L2E MapToDBFunction#4](~/samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#4)]

## <a name="see-also"></a><span data-ttu-id="0b617-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b617-135">See also</span></span>

- <span data-ttu-id="0b617-136">[Übersicht über die EDMX-Datei](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0b617-136">[.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- [<span data-ttu-id="0b617-137">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="0b617-137">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
