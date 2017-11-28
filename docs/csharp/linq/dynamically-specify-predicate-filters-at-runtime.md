---
title: "Dynamisches Festlegen von Prädikatfiltern zur Laufzeit"
description: "So legen Sie Prädikatfilter zur Laufzeit dynamisch fest."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 90238470-0767-497c-916c-52d0d16845e0
ms.openlocfilehash: 06bc594ac1357e7dca6c182fa28310559a79875c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="dynamically-specify-predicate-filters-at-runtime"></a><span data-ttu-id="175b5-104">Dynamisches Festlegen von Prädikatfiltern zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="175b5-104">Dynamically specify predicate filters at runtime</span></span>

<span data-ttu-id="175b5-105">In einigen Fällen wissen Sie bis zur Laufzeit nicht, wie viele Prädikate Sie für die Quellelemente in die `where`-Klausel übernehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="175b5-105">In some cases you do not know until run time how many predicates you have to apply to source elements in the `where` clause.</span></span> <span data-ttu-id="175b5-106">Eine Möglichkeit, mehrere Prädikatfilter dynamisch festzulegen, ist die Verwendung der Methode <xref:System.Linq.Enumerable.Contains%2A>, wie im folgenden Beispiel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="175b5-106">One way to dynamically specify multiple predicate filters is to use the <xref:System.Linq.Enumerable.Contains%2A> method, as shown in the following example.</span></span> <span data-ttu-id="175b5-107">Das Beispiel wird auf zwei Arten erstellt.</span><span class="sxs-lookup"><span data-stu-id="175b5-107">The example is constructed in two ways.</span></span> <span data-ttu-id="175b5-108">Zuerst wird das Projekt durch Filtern nach Werten, die im Programm bereitgestellt werden, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="175b5-108">First, the project is run by filtering on values that are provided in the program.</span></span> <span data-ttu-id="175b5-109">Und dann wird das Projekt mithilfe der Eingabe, die zur Laufzeit bereitgestellt wird, erneut ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="175b5-109">Then the project is run again by using input provided at run time.</span></span>  
  
## <a name="to-filter-by-using-the-contains-method"></a><span data-ttu-id="175b5-110">Filtern mithilfe der Contains-Methode</span><span class="sxs-lookup"><span data-stu-id="175b5-110">To filter by using the Contains method</span></span>  
  
1.  <span data-ttu-id="175b5-111">Erstellen Sie eine neue Konsolenanwendung und nennen Sie sie `PredicateFilters`.</span><span class="sxs-lookup"><span data-stu-id="175b5-111">Open a new console application and name it `PredicateFilters`.</span></span>  
  
2.  <span data-ttu-id="175b5-112">Kopieren Sie die `StudentClass`-Klasse aus [Query a collection of objects (Abfragen einer Auflistung von Objekten)](query-a-collection-of-objects.md) und fügen Sie ihn in Namespace `PredicateFilters` unter Klasse `Program` ein.</span><span class="sxs-lookup"><span data-stu-id="175b5-112">Copy the `StudentClass` class from [Query a collection of objects](query-a-collection-of-objects.md) and paste it into namespace `PredicateFilters` underneath class `Program`.</span></span> <span data-ttu-id="175b5-113">`StudentClass` stellt eine Liste von `Student`-Objekten bereit.</span><span class="sxs-lookup"><span data-stu-id="175b5-113">`StudentClass` provides a list of `Student` objects.</span></span>  
  
3.  <span data-ttu-id="175b5-114">Kommentieren Sie die `Main`-Methode in `StudentClass` aus.</span><span class="sxs-lookup"><span data-stu-id="175b5-114">Comment out the `Main` method in `StudentClass`.</span></span>  
  
4.  <span data-ttu-id="175b5-115">Ersetzen Sie die `Program`-Klasse durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="175b5-115">Replace class `Program` with the following code.</span></span>  
  
     [!code-csharp[csProgGuideLINQ#26](../../../samples/snippets/csharp/concepts/linq/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]  
  
5.  <span data-ttu-id="175b5-116">Fügen Sie die folgende Zeile in die `Main`-Methode in Klasse `DynamicPredicates` unter der Deklaration von `ids` ein.</span><span class="sxs-lookup"><span data-stu-id="175b5-116">Add the following line to the `Main` method in class `DynamicPredicates`, under the declaration of `ids`.</span></span>  
  
     ```csharp
     QueryById(ids);
     ```

6.  <span data-ttu-id="175b5-117">Führen Sie das Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="175b5-117">Run the project.</span></span>  
  
7.  <span data-ttu-id="175b5-118">In einem Konsolenfenster wird die folgende Ausgabe angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="175b5-118">The following output is displayed in a console window:</span></span>  
  
     <span data-ttu-id="175b5-119">Garcia: 114</span><span class="sxs-lookup"><span data-stu-id="175b5-119">Garcia: 114</span></span>  
  
     <span data-ttu-id="175b5-120">O'Donnell: 112</span><span class="sxs-lookup"><span data-stu-id="175b5-120">O'Donnell: 112</span></span>  
  
     <span data-ttu-id="175b5-121">Omelchenko: 111</span><span class="sxs-lookup"><span data-stu-id="175b5-121">Omelchenko: 111</span></span>  
  
8.  <span data-ttu-id="175b5-122">Im nächsten Schritt wird das Projekt erneut ausgeführt, dieses Mal mit der Eingabe zur Laufzeit anstelle von Array `ids`.</span><span class="sxs-lookup"><span data-stu-id="175b5-122">The next step is to run the project again, this time by using input entered at run time instead of array `ids`.</span></span> <span data-ttu-id="175b5-123">Ändern Sie `QueryByID(ids)` zu `QueryByID(args)` in der `Main`-Methode.</span><span class="sxs-lookup"><span data-stu-id="175b5-123">Change `QueryByID(ids)` to `QueryByID(args)` in the `Main` method.</span></span>  
  
9. <span data-ttu-id="175b5-124">Führen Sie das Projekt mit den Befehlszeilenargumenten `122 117 120 115` aus.</span><span class="sxs-lookup"><span data-stu-id="175b5-124">Run the project with the command line arguments `122 117 120 115`.</span></span> <span data-ttu-id="175b5-125">Wenn das Projekt ausgeführt wird, werden diese Werte Elemente von `args`, dem Parameter der `Main`-Methode.</span><span class="sxs-lookup"><span data-stu-id="175b5-125">When the project is run, those values become elements of `args`, the parameter of the `Main` method..</span></span>  
  
10. <span data-ttu-id="175b5-126">In einem Konsolenfenster wird die folgende Ausgabe angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="175b5-126">The following output is displayed in a console window:</span></span>  
  
     <span data-ttu-id="175b5-127">Adams: 120</span><span class="sxs-lookup"><span data-stu-id="175b5-127">Adams: 120</span></span>  
  
     <span data-ttu-id="175b5-128">Feng: 117</span><span class="sxs-lookup"><span data-stu-id="175b5-128">Feng: 117</span></span>  
  
     <span data-ttu-id="175b5-129">Garcia: 115</span><span class="sxs-lookup"><span data-stu-id="175b5-129">Garcia: 115</span></span>  
  
     <span data-ttu-id="175b5-130">Tucker: 122</span><span class="sxs-lookup"><span data-stu-id="175b5-130">Tucker: 122</span></span>  
  
## <a name="to-filter-by-using-a-switch-statement"></a><span data-ttu-id="175b5-131">Filtern mithilfe einer Switch-Anweisung</span><span class="sxs-lookup"><span data-stu-id="175b5-131">To filter by using a switch statement</span></span>  
  
1.  <span data-ttu-id="175b5-132">Sie können eine `switch`-Anweisung zum Auswählen zwischen vordefinierten alternativen Abfragen verwenden.</span><span class="sxs-lookup"><span data-stu-id="175b5-132">You can use a `switch` statement to select among predetermined alternative queries.</span></span> <span data-ttu-id="175b5-133">Im folgenden Beispiel verwendet `studentQuery` eine andere `where`-Klausel, abhängig davon, welche Klassenstufe oder welches Jahr zur Laufzeit angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="175b5-133">In the following example, `studentQuery` uses a different `where` clause depending on which grade level, or year, is specified at run time.</span></span>  
  
2.  <span data-ttu-id="175b5-134">Kopieren Sie die folgende Methode, und fügen Sie sie in die Klasse `DynamicPredicates` ein.</span><span class="sxs-lookup"><span data-stu-id="175b5-134">Copy the following method and paste it into class `DynamicPredicates`.</span></span>  
  
     [!code-csharp[csProgGuideLINQ#27](../../../samples/snippets/csharp/concepts/linq//how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]  
  
3.  <span data-ttu-id="175b5-135">Ersetzen Sie in der `Main`-Methode den Aufruf von `QueryByID` mit dem folgenden Aufruf, der das erste Element aus dem `args`-Array als sein Argument sendet: `QueryByYear(args[0])`.</span><span class="sxs-lookup"><span data-stu-id="175b5-135">In the `Main` method, replace the call to `QueryByID` with the following call, which sends the first element from the `args` array as its argument: `QueryByYear(args[0])`.</span></span>  
  
4.  <span data-ttu-id="175b5-136">Führen Sie das Projekt mit einem Befehlszeilenargument für einen ganzzahligen Wert zwischen 1 und 4 aus.</span><span class="sxs-lookup"><span data-stu-id="175b5-136">Run the project with a command line argument of an integer value between 1 and 4.</span></span>  
  
 
## <a name="see-also"></a><span data-ttu-id="175b5-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="175b5-137">See Also</span></span>  
 [<span data-ttu-id="175b5-138">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="175b5-138">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="175b5-139">where-Klausel</span><span class="sxs-lookup"><span data-stu-id="175b5-139">where clause</span></span>](../language-reference/keywords/where-clause.md)
