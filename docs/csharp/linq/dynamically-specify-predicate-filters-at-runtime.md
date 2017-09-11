---
title: "Dynamisches Festlegen von Prädikatfiltern zur Laufzeit"
description: "So legen Sie Prädikatfilter zur Laufzeit dynamisch fest."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 90238470-0767-497c-916c-52d0d16845e0
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9e724428bce09e2b2fa20b9391ad131424e16413
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="dynamically-specify-predicate-filters-at-runtime"></a><span data-ttu-id="4e64f-104">Dynamisches Festlegen von Prädikatfiltern zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="4e64f-104">Dynamically specify predicate filters at runtime</span></span>

<span data-ttu-id="4e64f-105">In einigen Fällen wissen Sie bis zur Laufzeit nicht, wie viele Prädikate Sie für die Quellelemente in die `where`-Klausel übernehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="4e64f-105">In some cases you do not know until run time how many predicates you have to apply to source elements in the `where` clause.</span></span> <span data-ttu-id="4e64f-106">Eine Möglichkeit, mehrere Prädikatfilter dynamisch festzulegen, ist die Verwendung der Methode <xref:System.Linq.Enumerable.Contains%2A>, wie im folgenden Beispiel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4e64f-106">One way to dynamically specify multiple predicate filters is to use the <xref:System.Linq.Enumerable.Contains%2A> method, as shown in the following example.</span></span> <span data-ttu-id="4e64f-107">Das Beispiel wird auf zwei Arten erstellt.</span><span class="sxs-lookup"><span data-stu-id="4e64f-107">The example is constructed in two ways.</span></span> <span data-ttu-id="4e64f-108">Zuerst wird das Projekt durch Filtern nach Werten, die im Programm bereitgestellt werden, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4e64f-108">First, the project is run by filtering on values that are provided in the program.</span></span> <span data-ttu-id="4e64f-109">Und dann wird das Projekt mithilfe der Eingabe, die zur Laufzeit bereitgestellt wird, erneut ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4e64f-109">Then the project is run again by using input provided at run time.</span></span>  
  
## <a name="to-filter-by-using-the-contains-method"></a><span data-ttu-id="4e64f-110">Filtern mithilfe der Contains-Methode</span><span class="sxs-lookup"><span data-stu-id="4e64f-110">To filter by using the Contains method</span></span>  
  
1.  <span data-ttu-id="4e64f-111">Erstellen Sie eine neue Konsolenanwendung und nennen Sie sie `PredicateFilters`.</span><span class="sxs-lookup"><span data-stu-id="4e64f-111">Open a new console application and name it `PredicateFilters`.</span></span>  
  
2.  <span data-ttu-id="4e64f-112">Kopieren Sie die `StudentClass`-Klasse aus [Query a collection of objects (Abfragen einer Auflistung von Objekten)](query-a-collection-of-objects.md) und fügen Sie ihn in Namespace `PredicateFilters` unter Klasse `Program` ein.</span><span class="sxs-lookup"><span data-stu-id="4e64f-112">Copy the `StudentClass` class from [Query a collection of objects](query-a-collection-of-objects.md) and paste it into namespace `PredicateFilters` underneath class `Program`.</span></span> <span data-ttu-id="4e64f-113">`StudentClass` stellt eine Liste von `Student`-Objekten bereit.</span><span class="sxs-lookup"><span data-stu-id="4e64f-113">`StudentClass` provides a list of `Student` objects.</span></span>  
  
3.  <span data-ttu-id="4e64f-114">Kommentieren Sie die `Main`-Methode in `StudentClass` aus.</span><span class="sxs-lookup"><span data-stu-id="4e64f-114">Comment out the `Main` method in `StudentClass`.</span></span>  
  
4.  <span data-ttu-id="4e64f-115">Ersetzen Sie die `Program`-Klasse durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="4e64f-115">Replace class `Program` with the following code.</span></span>  
  
     <span data-ttu-id="4e64f-116">[!code-cs[csProgGuideLINQ#26](../../../samples/snippets/csharp/concepts/linq/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4e64f-116">[!code-cs[csProgGuideLINQ#26](../../../samples/snippets/csharp/concepts/linq/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]</span></span>  
  
5.  <span data-ttu-id="4e64f-117">Fügen Sie die folgende Zeile in die `Main`-Methode in Klasse `DynamicPredicates` unter der Deklaration von `ids` ein.</span><span class="sxs-lookup"><span data-stu-id="4e64f-117">Add the following line to the `Main` method in class `DynamicPredicates`, under the declaration of `ids`.</span></span>  
  
     ```csharp
     QueryById(ids);
     ```

6.  <span data-ttu-id="4e64f-118">Führen Sie das Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="4e64f-118">Run the project.</span></span>  
  
7.  <span data-ttu-id="4e64f-119">In einem Konsolenfenster wird die folgende Ausgabe angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="4e64f-119">The following output is displayed in a console window:</span></span>  
  
     <span data-ttu-id="4e64f-120">Garcia: 114</span><span class="sxs-lookup"><span data-stu-id="4e64f-120">Garcia: 114</span></span>  
  
     <span data-ttu-id="4e64f-121">O'Donnell: 112</span><span class="sxs-lookup"><span data-stu-id="4e64f-121">O'Donnell: 112</span></span>  
  
     <span data-ttu-id="4e64f-122">Omelchenko: 111</span><span class="sxs-lookup"><span data-stu-id="4e64f-122">Omelchenko: 111</span></span>  
  
8.  <span data-ttu-id="4e64f-123">Im nächsten Schritt wird das Projekt erneut ausgeführt, dieses Mal mit der Eingabe zur Laufzeit anstelle von Array `ids`.</span><span class="sxs-lookup"><span data-stu-id="4e64f-123">The next step is to run the project again, this time by using input entered at run time instead of array `ids`.</span></span> <span data-ttu-id="4e64f-124">Ändern Sie `QueryByID(ids)` zu `QueryByID(args)` in der `Main`-Methode.</span><span class="sxs-lookup"><span data-stu-id="4e64f-124">Change `QueryByID(ids)` to `QueryByID(args)` in the `Main` method.</span></span>  
  
9. <span data-ttu-id="4e64f-125">Führen Sie das Projekt mit den Befehlszeilenargumenten `122 117 120 115` aus.</span><span class="sxs-lookup"><span data-stu-id="4e64f-125">Run the project with the command line arguments `122 117 120 115`.</span></span> <span data-ttu-id="4e64f-126">Wenn das Projekt ausgeführt wird, werden diese Werte Elemente von `args`, dem Parameter der `Main`-Methode.</span><span class="sxs-lookup"><span data-stu-id="4e64f-126">When the project is run, those values become elements of `args`, the parameter of the `Main` method..</span></span>  
  
10. <span data-ttu-id="4e64f-127">In einem Konsolenfenster wird die folgende Ausgabe angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="4e64f-127">The following output is displayed in a console window:</span></span>  
  
     <span data-ttu-id="4e64f-128">Adams: 120</span><span class="sxs-lookup"><span data-stu-id="4e64f-128">Adams: 120</span></span>  
  
     <span data-ttu-id="4e64f-129">Feng: 117</span><span class="sxs-lookup"><span data-stu-id="4e64f-129">Feng: 117</span></span>  
  
     <span data-ttu-id="4e64f-130">Garcia: 115</span><span class="sxs-lookup"><span data-stu-id="4e64f-130">Garcia: 115</span></span>  
  
     <span data-ttu-id="4e64f-131">Tucker: 122</span><span class="sxs-lookup"><span data-stu-id="4e64f-131">Tucker: 122</span></span>  
  
## <a name="to-filter-by-using-a-switch-statement"></a><span data-ttu-id="4e64f-132">Filtern mithilfe einer Switch-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4e64f-132">To filter by using a switch statement</span></span>  
  
1.  <span data-ttu-id="4e64f-133">Sie können eine `switch`-Anweisung zum Auswählen zwischen vordefinierten alternativen Abfragen verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e64f-133">You can use a `switch` statement to select among predetermined alternative queries.</span></span> <span data-ttu-id="4e64f-134">Im folgenden Beispiel verwendet `studentQuery` eine andere `where`-Klausel, abhängig davon, welche Klassenstufe oder welches Jahr zur Laufzeit angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4e64f-134">In the following example, `studentQuery` uses a different `where` clause depending on which grade level, or year, is specified at run time.</span></span>  
  
2.  <span data-ttu-id="4e64f-135">Kopieren Sie die folgende Methode, und fügen Sie sie in die Klasse `DynamicPredicates` ein.</span><span class="sxs-lookup"><span data-stu-id="4e64f-135">Copy the following method and paste it into class `DynamicPredicates`.</span></span>  
  
     <span data-ttu-id="4e64f-136">[!code-cs[csProgGuideLINQ#27](../../../samples/snippets/csharp/concepts/linq//how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="4e64f-136">[!code-cs[csProgGuideLINQ#27](../../../samples/snippets/csharp/concepts/linq//how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]</span></span>  
  
3.  <span data-ttu-id="4e64f-137">Ersetzen Sie in der `Main`-Methode den Aufruf von `QueryByID` mit dem folgenden Aufruf, der das erste Element aus dem `args`-Array als sein Argument sendet: `QueryByYear(args[0])`.</span><span class="sxs-lookup"><span data-stu-id="4e64f-137">In the `Main` method, replace the call to `QueryByID` with the following call, which sends the first element from the `args` array as its argument: `QueryByYear(args[0])`.</span></span>  
  
4.  <span data-ttu-id="4e64f-138">Führen Sie das Projekt mit einem Befehlszeilenargument für einen ganzzahligen Wert zwischen 1 und 4 aus.</span><span class="sxs-lookup"><span data-stu-id="4e64f-138">Run the project with a command line argument of an integer value between 1 and 4.</span></span>  
  
 
## <a name="see-also"></a><span data-ttu-id="4e64f-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e64f-139">See Also</span></span>  
 <span data-ttu-id="4e64f-140">[LINQ-Abfrageausdrücke](index.md) </span><span class="sxs-lookup"><span data-stu-id="4e64f-140">[LINQ Query Expressions](index.md) </span></span>  
 [<span data-ttu-id="4e64f-141">where-Klausel</span><span class="sxs-lookup"><span data-stu-id="4e64f-141">where clause</span></span>](../language-reference/keywords/where-clause.md)

