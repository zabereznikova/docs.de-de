---
title: Arraydimensionen in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- dimensions, arrays
- arrays [Visual Basic], dimensions
- arrays [Visual Basic], rectangular
- arrays [Visual Basic], rank
- rectangular arrays
- ranking, arrays
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
ms.openlocfilehash: cf295288dd034d744dceb71b5c58278be5cc2a2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651755"
---
# <a name="array-dimensions-in-visual-basic"></a><span data-ttu-id="1714d-102">Arraydimensionen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1714d-102">Array Dimensions in Visual Basic</span></span>
<span data-ttu-id="1714d-103">Ein *Dimension* ist eine Richtung, in dem Sie die Spezifikation der Elemente eines Arrays können variieren.</span><span class="sxs-lookup"><span data-stu-id="1714d-103">A *dimension* is a direction in which you can vary the specification of an array's elements.</span></span> <span data-ttu-id="1714d-104">Ein Array, das den Umsatz für jeden Tag des Monats insgesamt enthält hat es sich um eine Dimension (Tag des Monats).</span><span class="sxs-lookup"><span data-stu-id="1714d-104">An array that holds the sales total for each day of the month has one dimension (the day of the month).</span></span> <span data-ttu-id="1714d-105">Ein Array, das die Verkäufe nach Abteilung für jeden Tag des Monats insgesamt enthält hat zwei Dimensionen (die Abteilungsnummer und den Tag des Monats).</span><span class="sxs-lookup"><span data-stu-id="1714d-105">An array that holds the sales total by department for each day of the month has two dimensions (the department number and the day of the month).</span></span> <span data-ttu-id="1714d-106">Wird aufgerufen, die Anzahl der Dimensionen, die ein Array hat seine *Rang*.</span><span class="sxs-lookup"><span data-stu-id="1714d-106">The number of dimensions an array has is called its *rank*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1714d-107">Sie können die <xref:System.Array.Rank%2A> -Eigenschaft können Sie bestimmen, wie viele Dimensionen ein Array ist.</span><span class="sxs-lookup"><span data-stu-id="1714d-107">You can use the <xref:System.Array.Rank%2A> property to determine the how many dimensions an array has.</span></span>  
  
## <a name="working-with-dimensions"></a><span data-ttu-id="1714d-108">Arbeiten mit Dimensionen</span><span class="sxs-lookup"><span data-stu-id="1714d-108">Working with Dimensions</span></span>  
 <span data-ttu-id="1714d-109">Geben Sie ein Element eines Arrays, durch Angabe einer *Index* oder *Feldindex* aller seiner Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="1714d-109">You specify an element of an array by supplying an *index* or *subscript* for each of its dimensions.</span></span> <span data-ttu-id="1714d-110">Die Elemente werden fortlaufend über die einzelnen Dimensionen von Index 0 bis zum höchsten Index für diese Dimension.</span><span class="sxs-lookup"><span data-stu-id="1714d-110">The elements are contiguous along each dimension from index 0 through the highest index for that dimension.</span></span>  
  
 <span data-ttu-id="1714d-111">Die folgenden Abbildungen zeigen die grundlegende Struktur von Arrays mit unterschiedlichem Rang.</span><span class="sxs-lookup"><span data-stu-id="1714d-111">The following illustrations show the conceptual structure of arrays with different ranks.</span></span> <span data-ttu-id="1714d-112">Jedes Element in der Abbildung zeigt die Werte des Indexes, die darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="1714d-112">Each element in the illustrations shows the index values that access it.</span></span> <span data-ttu-id="1714d-113">Sie können z. B. das erste Element der zweiten Zeile des zweidimensionalen Arrays zugreifen, durch Angabe von Indizes `(1, 0)`.</span><span class="sxs-lookup"><span data-stu-id="1714d-113">For example, you can access the first element of the second row of the two-dimensional array by specifying indexes `(1, 0)`.</span></span>  
  
 <span data-ttu-id="1714d-114">![Grafisches Diagramm eines&#45;-dimensionales Array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimone.gif "ArrayExDimOne")</span><span class="sxs-lookup"><span data-stu-id="1714d-114">![Graphic diagram of one&#45;dimensional array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimone.gif "ArrayExDimOne")</span></span>  
<span data-ttu-id="1714d-115">Eindimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="1714d-115">One-dimensional array</span></span>  
  
 <span data-ttu-id="1714d-116">![Grafisches Diagramm der zwei&#45;-dimensionales Array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimtwo.gif "ArrayExDimTwo")</span><span class="sxs-lookup"><span data-stu-id="1714d-116">![Graphic diagram of two&#45;dimensional array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimtwo.gif "ArrayExDimTwo")</span></span>  
<span data-ttu-id="1714d-117">zweidimensionales array</span><span class="sxs-lookup"><span data-stu-id="1714d-117">Two-dimensional array</span></span>  
  
 <span data-ttu-id="1714d-118">![Grafisches Diagramm der drei&#45;-dimensionales Array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimthree.gif "ArrayExDimThree")</span><span class="sxs-lookup"><span data-stu-id="1714d-118">![Graphic diagram of three&#45;dimensional array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimthree.gif "ArrayExDimThree")</span></span>  
<span data-ttu-id="1714d-119">dreidimensionale array</span><span class="sxs-lookup"><span data-stu-id="1714d-119">Three-dimensional array</span></span>  
  
### <a name="one-dimension"></a><span data-ttu-id="1714d-120">Eine Dimension</span><span class="sxs-lookup"><span data-stu-id="1714d-120">One Dimension</span></span>  
 <span data-ttu-id="1714d-121">Viele Arrays haben nur eine Dimension, z. B. die Anzahl der einzelnen Altersgruppen.</span><span class="sxs-lookup"><span data-stu-id="1714d-121">Many arrays have only one dimension, such as the number of people of each age.</span></span> <span data-ttu-id="1714d-122">Die einzige Anforderung an ein Element ist das Alter an, für das die Anzahl von dieses Element enthält.</span><span class="sxs-lookup"><span data-stu-id="1714d-122">The only requirement to specify an element is the age for which that element holds the count.</span></span> <span data-ttu-id="1714d-123">Ein solches Array wird daher nur einen Index verwendet.</span><span class="sxs-lookup"><span data-stu-id="1714d-123">Therefore, such an array uses only one index.</span></span> <span data-ttu-id="1714d-124">Das folgende Beispiel deklariert eine Variable für eine *1D-Array* Alter zählt für Alter von 0 bis 120.</span><span class="sxs-lookup"><span data-stu-id="1714d-124">The following example declares a variable to hold a *one-dimensional array* of age counts for ages 0 through 120.</span></span>  
  
```  
Dim ageCounts(120) As UInteger  
```  
  
### <a name="two-dimensions"></a><span data-ttu-id="1714d-125">Zwei Dimensionen</span><span class="sxs-lookup"><span data-stu-id="1714d-125">Two Dimensions</span></span>  
 <span data-ttu-id="1714d-126">Einige Arrays haben zwei Dimensionen, z. B. die Anzahl der Zweigstellen in jeder erzeugt, der jeder Erstellung auf eine Gelände.</span><span class="sxs-lookup"><span data-stu-id="1714d-126">Some arrays have two dimensions, such as the number of offices on each floor of each building on a campus.</span></span> <span data-ttu-id="1714d-127">Die Spezifikation eines Elements erfordert, die Gebäudenummer und der Floor, und jedes Element enthält die Anzahl die für diese Kombination von Gebäude und Etage.</span><span class="sxs-lookup"><span data-stu-id="1714d-127">The specification of an element requires both the building number and the floor, and each element holds the count for that combination of building and floor.</span></span> <span data-ttu-id="1714d-128">Aus diesem Grund wird ein solches Array zwei Indizes verwendet.</span><span class="sxs-lookup"><span data-stu-id="1714d-128">Therefore, such an array uses two indexes.</span></span> <span data-ttu-id="1714d-129">Das folgende Beispiel deklariert eine Variable für eine *zweidimensionales Array* der Office-Anzahl für Gebäude 0 bis 40 und Stockwerken 0 bis 5.</span><span class="sxs-lookup"><span data-stu-id="1714d-129">The following example declares a variable to hold a *two-dimensional array* of office counts, for buildings 0 through 40 and floors 0 through 5.</span></span>  
  
```  
Dim officeCounts(40, 5) As Byte  
```  
  
 <span data-ttu-id="1714d-130">Ein zweidimensionales Array wird auch bezeichnet eine *rechteckiges Array*.</span><span class="sxs-lookup"><span data-stu-id="1714d-130">A two-dimensional array is also called a *rectangular array*.</span></span>  
  
### <a name="three-dimensions"></a><span data-ttu-id="1714d-131">Drei Dimensionen</span><span class="sxs-lookup"><span data-stu-id="1714d-131">Three Dimensions</span></span>  
 <span data-ttu-id="1714d-132">Einige Arrays haben drei Dimensionen, z. B. Werte im dreidimensionalen Raum.</span><span class="sxs-lookup"><span data-stu-id="1714d-132">A few arrays have three dimensions, such as values in three-dimensional space.</span></span> <span data-ttu-id="1714d-133">Ein solches Array verwendet drei Indizes, die in diesem Fall die x-, y- und Z-Koordinaten des physischen Speicherplatzes darstellen.</span><span class="sxs-lookup"><span data-stu-id="1714d-133">Such an array uses three indexes, which in this case represent the x, y, and z coordinates of physical space.</span></span> <span data-ttu-id="1714d-134">Das folgende Beispiel deklariert eine Variable für eine *dreidimensionale Array* per Funk temperaturspalte an verschiedenen Punkten in einem dreidimensionalen Volume.</span><span class="sxs-lookup"><span data-stu-id="1714d-134">The following example declares a variable to hold a *three-dimensional array* of air temperatures at various points in a three-dimensional volume.</span></span>  
  
```  
Dim airTemperatures(99, 99, 24) As Single  
```  
  
### <a name="more-than-three-dimensions"></a><span data-ttu-id="1714d-135">Mehr als drei Dimensionen</span><span class="sxs-lookup"><span data-stu-id="1714d-135">More than Three Dimensions</span></span>  
 <span data-ttu-id="1714d-136">Obwohl ein Array mit bis zu 32 Dimensionen aufweisen kann, ist es jedoch selten mehr als drei aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1714d-136">Although an array can have as many as 32 dimensions, it is rare to have more than three.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1714d-137">Wenn Sie ein Array Dimensionen hinzufügen, erhöht der gesamte Speicher, der vom Array benötigt beträchtlich, daher verwenden mehrdimensionale Arrays mit Vorsicht zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1714d-137">When you add dimensions to an array, the total storage needed by the array increases considerably, so use multidimensional arrays with care.</span></span>  
  
## <a name="using-different-dimensions"></a><span data-ttu-id="1714d-138">Verwenden unterschiedliche Dimensionen</span><span class="sxs-lookup"><span data-stu-id="1714d-138">Using Different Dimensions</span></span>  
 <span data-ttu-id="1714d-139">Angenommen Sie, Sie möchten zum Nachverfolgen der Umsätze für jeden Tag des Monats vorhanden.</span><span class="sxs-lookup"><span data-stu-id="1714d-139">Suppose you want to track sales amounts for every day of the present month.</span></span> <span data-ttu-id="1714d-140">Sie können ein eindimensionales Array mit 31 Elementen deklarieren, eine für jeden Tag des Monats, wie das folgende Beispiel zeigt.</span><span class="sxs-lookup"><span data-stu-id="1714d-140">You might declare a one-dimensional array with 31 elements, one for each day of the month, as the following example shows.</span></span>  
  
```  
Dim salesAmounts(30) As Double  
```  
  
 <span data-ttu-id="1714d-141">Jetzt nehmen Sie die gleiche Informationen nicht nur für jeden Tag eines Monats, sondern auch für jeden Monat des Jahres verfolgen möchten.</span><span class="sxs-lookup"><span data-stu-id="1714d-141">Now suppose you want to track the same information not only for every day of a month but also for every month of the year.</span></span> <span data-ttu-id="1714d-142">Sie können ein zweidimensionales Array mit 12 Zeilen (für die Monate) und 31 Spalten (für die Tage), wie im folgenden Beispiel gezeigt deklarieren.</span><span class="sxs-lookup"><span data-stu-id="1714d-142">You might declare a two-dimensional array with 12 rows (for the months) and 31 columns (for the days), as the following example shows.</span></span>  
  
```  
Dim salesAmounts(11, 30) As Double  
```  
  
 <span data-ttu-id="1714d-143">Angenommen, Sie entscheiden, damit Ihr Array enthalten jetzt Informationen für mehr als ein Jahr.</span><span class="sxs-lookup"><span data-stu-id="1714d-143">Now suppose you decide to have your array hold information for more than one year.</span></span> <span data-ttu-id="1714d-144">Wenn Sie die Umsatzbeträge für fünf Jahre nachverfolgen möchten, konnte Sie ein dreidimensionales Array mit 5 Ebenen, 12 Zeilen und 31 Spalten wie im folgenden Beispiel gezeigt deklarieren.</span><span class="sxs-lookup"><span data-stu-id="1714d-144">If you want to track sales amounts for 5 years, you could declare a three-dimensional array with 5 layers, 12 rows, and 31 columns, as the following example shows.</span></span>  
  
```  
Dim salesAmounts(4, 11, 30) As Double  
```  
  
 <span data-ttu-id="1714d-145">Beachten Sie Folgendes: Da jeder Index von 0 auf das Maximum, jede Dimension des variiert `salesAmounts` als eins kleiner als die erforderliche Länge für diese Dimension deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="1714d-145">Note that, because each index varies from 0 to its maximum, each dimension of `salesAmounts` is declared as one less than the required length for that dimension.</span></span> <span data-ttu-id="1714d-146">Beachten Sie außerdem, dass die Größe des Arrays mit jeder neuen Dimension zunimmt.</span><span class="sxs-lookup"><span data-stu-id="1714d-146">Note also that the size of the array increases with each new dimension.</span></span> <span data-ttu-id="1714d-147">Die drei Größen in den vorherigen Beispielen sind 31, 372 und 1.860 Elementen.</span><span class="sxs-lookup"><span data-stu-id="1714d-147">The three sizes in the preceding examples are 31, 372, and 1,860 elements respectively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1714d-148">Sie können ein Array erstellen, ohne die `Dim` Anweisung oder der `New` Klausel.</span><span class="sxs-lookup"><span data-stu-id="1714d-148">You can create an array without using the `Dim` statement or the `New` clause.</span></span> <span data-ttu-id="1714d-149">Sie können z. B. Aufrufen der <xref:System.Array.CreateInstance%2A> -Methode oder eine andere Komponente kann Ihrem Code auf diese Weise erstellte Array übergeben.</span><span class="sxs-lookup"><span data-stu-id="1714d-149">For example, you can call the <xref:System.Array.CreateInstance%2A> method, or another component can pass your code an array created in this manner.</span></span> <span data-ttu-id="1714d-150">Ein solches Array kann mit eine unteren Grenze ungleich 0 haben.</span><span class="sxs-lookup"><span data-stu-id="1714d-150">Such an array can have a lower bound other than 0.</span></span> <span data-ttu-id="1714d-151">Sie können immer für die untere Grenze einer Dimension testen, indem die <xref:System.Array.GetLowerBound%2A> Methode oder die `LBound` Funktion.</span><span class="sxs-lookup"><span data-stu-id="1714d-151">You can always test for the lower bound of a dimension by using the <xref:System.Array.GetLowerBound%2A> method or the `LBound` function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1714d-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1714d-152">See Also</span></span>  
 [<span data-ttu-id="1714d-153">Arrays</span><span class="sxs-lookup"><span data-stu-id="1714d-153">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="1714d-154">Problembehandlung bei Arrays</span><span class="sxs-lookup"><span data-stu-id="1714d-154">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
