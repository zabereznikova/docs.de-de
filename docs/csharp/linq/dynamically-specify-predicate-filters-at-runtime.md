---
title: Dynamisches Festlegen von Prädikatfiltern zur Laufzeit
description: So legen Sie Prädikatfilter zur Laufzeit dynamisch fest.
ms.date: 12/1/2016
ms.assetid: 90238470-0767-497c-916c-52d0d16845e0
ms.openlocfilehash: fa3426a513758d8c30bf381ec480b9b8d12a5f81
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dynamically-specify-predicate-filters-at-runtime"></a><span data-ttu-id="a54e0-103">Dynamisches Festlegen von Prädikatfiltern zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a54e0-103">Dynamically specify predicate filters at runtime</span></span>

<span data-ttu-id="a54e0-104">In einigen Fällen wissen Sie bis zur Laufzeit nicht, wie viele Prädikate Sie für die Quellelemente in die `where`-Klausel übernehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="a54e0-104">In some cases you do not know until run time how many predicates you have to apply to source elements in the `where` clause.</span></span> <span data-ttu-id="a54e0-105">Eine Möglichkeit, mehrere Prädikatfilter dynamisch festzulegen, ist die Verwendung der Methode <xref:System.Linq.Enumerable.Contains%2A>, wie im folgenden Beispiel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a54e0-105">One way to dynamically specify multiple predicate filters is to use the <xref:System.Linq.Enumerable.Contains%2A> method, as shown in the following example.</span></span> <span data-ttu-id="a54e0-106">Das Beispiel wird auf zwei Arten erstellt.</span><span class="sxs-lookup"><span data-stu-id="a54e0-106">The example is constructed in two ways.</span></span> <span data-ttu-id="a54e0-107">Zuerst wird das Projekt durch Filtern nach Werten, die im Programm bereitgestellt werden, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a54e0-107">First, the project is run by filtering on values that are provided in the program.</span></span> <span data-ttu-id="a54e0-108">Und dann wird das Projekt mithilfe der Eingabe, die zur Laufzeit bereitgestellt wird, erneut ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a54e0-108">Then the project is run again by using input provided at run time.</span></span>  
  
## <a name="to-filter-by-using-the-contains-method"></a><span data-ttu-id="a54e0-109">Filtern mithilfe der Contains-Methode</span><span class="sxs-lookup"><span data-stu-id="a54e0-109">To filter by using the Contains method</span></span>  
  
1.  <span data-ttu-id="a54e0-110">Erstellen Sie eine neue Konsolenanwendung und nennen Sie sie `PredicateFilters`.</span><span class="sxs-lookup"><span data-stu-id="a54e0-110">Open a new console application and name it `PredicateFilters`.</span></span>  
  
2.  <span data-ttu-id="a54e0-111">Kopieren Sie die `StudentClass`-Klasse aus [Query a collection of objects (Abfragen einer Auflistung von Objekten)](query-a-collection-of-objects.md) und fügen Sie ihn in Namespace `PredicateFilters` unter Klasse `Program` ein.</span><span class="sxs-lookup"><span data-stu-id="a54e0-111">Copy the `StudentClass` class from [Query a collection of objects](query-a-collection-of-objects.md) and paste it into namespace `PredicateFilters` underneath class `Program`.</span></span> <span data-ttu-id="a54e0-112">`StudentClass` stellt eine Liste von `Student`-Objekten bereit.</span><span class="sxs-lookup"><span data-stu-id="a54e0-112">`StudentClass` provides a list of `Student` objects.</span></span>  
  
3.  <span data-ttu-id="a54e0-113">Kommentieren Sie die `Main`-Methode in `StudentClass` aus.</span><span class="sxs-lookup"><span data-stu-id="a54e0-113">Comment out the `Main` method in `StudentClass`.</span></span>  
  
4.  <span data-ttu-id="a54e0-114">Ersetzen Sie die `Program`-Klasse durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="a54e0-114">Replace class `Program` with the following code.</span></span>  
  
     [!code-csharp[csProgGuideLINQ#26](../../../samples/snippets/csharp/concepts/linq/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]  
  
5.  <span data-ttu-id="a54e0-115">Fügen Sie die folgende Zeile in die `Main`-Methode in Klasse `DynamicPredicates` unter der Deklaration von `ids` ein.</span><span class="sxs-lookup"><span data-stu-id="a54e0-115">Add the following line to the `Main` method in class `DynamicPredicates`, under the declaration of `ids`.</span></span>  
  
     ```csharp
     QueryById(ids);
     ```

6.  <span data-ttu-id="a54e0-116">Führen Sie das Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="a54e0-116">Run the project.</span></span>  
  
7.  <span data-ttu-id="a54e0-117">In einem Konsolenfenster wird die folgende Ausgabe angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="a54e0-117">The following output is displayed in a console window:</span></span>  
  
     <span data-ttu-id="a54e0-118">Garcia: 114</span><span class="sxs-lookup"><span data-stu-id="a54e0-118">Garcia: 114</span></span>  
  
     <span data-ttu-id="a54e0-119">O'Donnell: 112</span><span class="sxs-lookup"><span data-stu-id="a54e0-119">O'Donnell: 112</span></span>  
  
     <span data-ttu-id="a54e0-120">Omelchenko: 111</span><span class="sxs-lookup"><span data-stu-id="a54e0-120">Omelchenko: 111</span></span>  
  
8.  <span data-ttu-id="a54e0-121">Im nächsten Schritt wird das Projekt erneut ausgeführt, dieses Mal mit der Eingabe zur Laufzeit anstelle von Array `ids`.</span><span class="sxs-lookup"><span data-stu-id="a54e0-121">The next step is to run the project again, this time by using input entered at run time instead of array `ids`.</span></span> <span data-ttu-id="a54e0-122">Ändern Sie `QueryByID(ids)` zu `QueryByID(args)` in der `Main`-Methode.</span><span class="sxs-lookup"><span data-stu-id="a54e0-122">Change `QueryByID(ids)` to `QueryByID(args)` in the `Main` method.</span></span>  
  
9. <span data-ttu-id="a54e0-123">Führen Sie das Projekt mit den Befehlszeilenargumenten `122 117 120 115` aus.</span><span class="sxs-lookup"><span data-stu-id="a54e0-123">Run the project with the command line arguments `122 117 120 115`.</span></span> <span data-ttu-id="a54e0-124">Wenn das Projekt ausgeführt wird, werden diese Werte Elemente von `args`, dem Parameter der `Main`-Methode.</span><span class="sxs-lookup"><span data-stu-id="a54e0-124">When the project is run, those values become elements of `args`, the parameter of the `Main` method..</span></span>  
  
10. <span data-ttu-id="a54e0-125">In einem Konsolenfenster wird die folgende Ausgabe angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="a54e0-125">The following output is displayed in a console window:</span></span>  
  
     <span data-ttu-id="a54e0-126">Adams: 120</span><span class="sxs-lookup"><span data-stu-id="a54e0-126">Adams: 120</span></span>  
  
     <span data-ttu-id="a54e0-127">Feng: 117</span><span class="sxs-lookup"><span data-stu-id="a54e0-127">Feng: 117</span></span>  
  
     <span data-ttu-id="a54e0-128">Garcia: 115</span><span class="sxs-lookup"><span data-stu-id="a54e0-128">Garcia: 115</span></span>  
  
     <span data-ttu-id="a54e0-129">Tucker: 122</span><span class="sxs-lookup"><span data-stu-id="a54e0-129">Tucker: 122</span></span>  
  
## <a name="to-filter-by-using-a-switch-statement"></a><span data-ttu-id="a54e0-130">Filtern mithilfe einer Switch-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a54e0-130">To filter by using a switch statement</span></span>  
  
1.  <span data-ttu-id="a54e0-131">Sie können eine `switch`-Anweisung zum Auswählen zwischen vordefinierten alternativen Abfragen verwenden.</span><span class="sxs-lookup"><span data-stu-id="a54e0-131">You can use a `switch` statement to select among predetermined alternative queries.</span></span> <span data-ttu-id="a54e0-132">Im folgenden Beispiel verwendet `studentQuery` eine andere `where`-Klausel, abhängig davon, welche Klassenstufe oder welches Jahr zur Laufzeit angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a54e0-132">In the following example, `studentQuery` uses a different `where` clause depending on which grade level, or year, is specified at run time.</span></span>  
  
2.  <span data-ttu-id="a54e0-133">Kopieren Sie die folgende Methode, und fügen Sie sie in die Klasse `DynamicPredicates` ein.</span><span class="sxs-lookup"><span data-stu-id="a54e0-133">Copy the following method and paste it into class `DynamicPredicates`.</span></span>  
  
     [!code-csharp[csProgGuideLINQ#27](../../../samples/snippets/csharp/concepts/linq//how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]  
  
3.  <span data-ttu-id="a54e0-134">Ersetzen Sie in der `Main`-Methode den Aufruf von `QueryByID` mit dem folgenden Aufruf, der das erste Element aus dem `args`-Array als sein Argument sendet: `QueryByYear(args[0])`.</span><span class="sxs-lookup"><span data-stu-id="a54e0-134">In the `Main` method, replace the call to `QueryByID` with the following call, which sends the first element from the `args` array as its argument: `QueryByYear(args[0])`.</span></span>  
  
4.  <span data-ttu-id="a54e0-135">Führen Sie das Projekt mit einem Befehlszeilenargument für einen ganzzahligen Wert zwischen 1 und 4 aus.</span><span class="sxs-lookup"><span data-stu-id="a54e0-135">Run the project with a command line argument of an integer value between 1 and 4.</span></span>  
  
 
## <a name="see-also"></a><span data-ttu-id="a54e0-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a54e0-136">See Also</span></span>  
 [<span data-ttu-id="a54e0-137">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="a54e0-137">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="a54e0-138">where-Klausel</span><span class="sxs-lookup"><span data-stu-id="a54e0-138">where clause</span></span>](../language-reference/keywords/where-clause.md)
