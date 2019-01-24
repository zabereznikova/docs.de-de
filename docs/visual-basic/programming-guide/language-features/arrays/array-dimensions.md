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
ms.openlocfilehash: 5ba92e113faf9d68bad97968937cc736132b2065
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708531"
---
# <a name="array-dimensions-in-visual-basic"></a><span data-ttu-id="1ee16-102">Arraydimensionen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1ee16-102">Array Dimensions in Visual Basic</span></span>
<span data-ttu-id="1ee16-103">Ein *Dimension* ist eine Richtung, in dem Sie die Spezifikation der Elemente eines Arrays können variieren.</span><span class="sxs-lookup"><span data-stu-id="1ee16-103">A *dimension* is a direction in which you can vary the specification of an array's elements.</span></span> <span data-ttu-id="1ee16-104">Ein Array, das den Umsatz für jeden Tag des Monats insgesamt enthält hat es sich um eine Dimension (Tag des Monats).</span><span class="sxs-lookup"><span data-stu-id="1ee16-104">An array that holds the sales total for each day of the month has one dimension (the day of the month).</span></span> <span data-ttu-id="1ee16-105">Ein Array, das den Umsatz nach Abteilung für jeden Tag des Monats insgesamt enthält verfügt über zwei Dimensionen (die Abteilung-Anzahl und den Tag des Monats).</span><span class="sxs-lookup"><span data-stu-id="1ee16-105">An array that holds the sales total by department for each day of the month has two dimensions (the department number and the day of the month).</span></span> <span data-ttu-id="1ee16-106">Wird aufgerufen, die Anzahl der Dimensionen, die ein Array hat seine *Rang*.</span><span class="sxs-lookup"><span data-stu-id="1ee16-106">The number of dimensions an array has is called its *rank*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ee16-107">Sie können die <xref:System.Array.Rank%2A> Eigenschaft, um zu bestimmen, wie viele Dimensionen ein Array enthält.</span><span class="sxs-lookup"><span data-stu-id="1ee16-107">You can use the <xref:System.Array.Rank%2A> property to determine the how many dimensions an array has.</span></span>  
  
## <a name="working-with-dimensions"></a><span data-ttu-id="1ee16-108">Arbeiten mit Dimensionen</span><span class="sxs-lookup"><span data-stu-id="1ee16-108">Working with Dimensions</span></span>  
 <span data-ttu-id="1ee16-109">Sie geben Sie ein Element eines Arrays durch Angabe einer *Index* oder *Feldindex* für jeden seiner Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="1ee16-109">You specify an element of an array by supplying an *index* or *subscript* for each of its dimensions.</span></span> <span data-ttu-id="1ee16-110">Die Elemente sind über die einzelnen Dimensionen von Index 0 bis zum höchsten Indexwert für diese Dimension zusammenhängenden.</span><span class="sxs-lookup"><span data-stu-id="1ee16-110">The elements are contiguous along each dimension from index 0 through the highest index for that dimension.</span></span>  
  
 <span data-ttu-id="1ee16-111">Die folgenden Abbildungen zeigen die grundlegende Struktur von Arrays mit unterschiedlichem Rang.</span><span class="sxs-lookup"><span data-stu-id="1ee16-111">The following illustrations show the conceptual structure of arrays with different ranks.</span></span> <span data-ttu-id="1ee16-112">Jedes Element in den Abbildungen zeigt die Werte des Indexes, die darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="1ee16-112">Each element in the illustrations shows the index values that access it.</span></span> <span data-ttu-id="1ee16-113">Sie können z. B. das erste Element der zweiten Zeile des zweidimensionalen Arrays zugreifen, durch Angabe von Indizes `(1, 0)`.</span><span class="sxs-lookup"><span data-stu-id="1ee16-113">For example, you can access the first element of the second row of the two-dimensional array by specifying indexes `(1, 0)`.</span></span>  
  
 <span data-ttu-id="1ee16-114">![Grafisches Diagramm eines&#45;-dimensionales Array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimone.gif "ArrayExDimOne")</span><span class="sxs-lookup"><span data-stu-id="1ee16-114">![Graphic diagram of one&#45;dimensional array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimone.gif "ArrayExDimOne")</span></span>  
<span data-ttu-id="1ee16-115">Eindimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="1ee16-115">One-dimensional array</span></span>  
  
 <span data-ttu-id="1ee16-116">![Grafisches Diagramm der beiden&#45;-dimensionales Array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimtwo.gif "ArrayExDimTwo")</span><span class="sxs-lookup"><span data-stu-id="1ee16-116">![Graphic diagram of two&#45;dimensional array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimtwo.gif "ArrayExDimTwo")</span></span>  
<span data-ttu-id="1ee16-117">zweidimensionales array</span><span class="sxs-lookup"><span data-stu-id="1ee16-117">Two-dimensional array</span></span>  
  
 <span data-ttu-id="1ee16-118">![Grafisches Diagramm der drei&#45;-dimensionales Array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimthree.gif "ArrayExDimThree")</span><span class="sxs-lookup"><span data-stu-id="1ee16-118">![Graphic diagram of three&#45;dimensional array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimthree.gif "ArrayExDimThree")</span></span>  
<span data-ttu-id="1ee16-119">dreidimensionale array</span><span class="sxs-lookup"><span data-stu-id="1ee16-119">Three-dimensional array</span></span>  
  
### <a name="one-dimension"></a><span data-ttu-id="1ee16-120">Eine Dimension</span><span class="sxs-lookup"><span data-stu-id="1ee16-120">One Dimension</span></span>  
 <span data-ttu-id="1ee16-121">Viele Arrays haben nur eine Dimension, wie z. B. die Anzahl der einzelnen Altersgruppen.</span><span class="sxs-lookup"><span data-stu-id="1ee16-121">Many arrays have only one dimension, such as the number of people of each age.</span></span> <span data-ttu-id="1ee16-122">Die einzige Voraussetzung für ein Element angeben, ist das Alter, das die Anzahl die dieses Element enthält.</span><span class="sxs-lookup"><span data-stu-id="1ee16-122">The only requirement to specify an element is the age for which that element holds the count.</span></span> <span data-ttu-id="1ee16-123">Aus diesem Grund wird ein entsprechendes Array nur ein Index verwendet.</span><span class="sxs-lookup"><span data-stu-id="1ee16-123">Therefore, such an array uses only one index.</span></span> <span data-ttu-id="1ee16-124">Das folgende Beispiel deklariert eine Variable für eine *eindimensionales Array* ALT Anzahl der Zugriffe von 0 bis 120.</span><span class="sxs-lookup"><span data-stu-id="1ee16-124">The following example declares a variable to hold a *one-dimensional array* of age counts for ages 0 through 120.</span></span>  
  
```  
Dim ageCounts(120) As UInteger  
```  
  
### <a name="two-dimensions"></a><span data-ttu-id="1ee16-125">Zwei Dimensionen</span><span class="sxs-lookup"><span data-stu-id="1ee16-125">Two Dimensions</span></span>  
 <span data-ttu-id="1ee16-126">Einige Arrays haben zwei Dimensionen, z. B. die Anzahl der Niederlassungen auf jede Boden der jedes Gebäude an einem Campus.</span><span class="sxs-lookup"><span data-stu-id="1ee16-126">Some arrays have two dimensions, such as the number of offices on each floor of each building on a campus.</span></span> <span data-ttu-id="1ee16-127">Die Spezifikation eines Elements erfordert, Erstellen von Anzahl und der Boden und jedes Element enthält die Anzahl der für diese Kombination von Gebäude und Etage.</span><span class="sxs-lookup"><span data-stu-id="1ee16-127">The specification of an element requires both the building number and the floor, and each element holds the count for that combination of building and floor.</span></span> <span data-ttu-id="1ee16-128">Aus diesem Grund wird ein entsprechendes Array zwei Indizes verwendet.</span><span class="sxs-lookup"><span data-stu-id="1ee16-128">Therefore, such an array uses two indexes.</span></span> <span data-ttu-id="1ee16-129">Das folgende Beispiel deklariert eine Variable für eine *zweidimensionales Array* der Anzahl der Büros, Gebäuden 0 bis 40 und Stockwerken 0 bis 5.</span><span class="sxs-lookup"><span data-stu-id="1ee16-129">The following example declares a variable to hold a *two-dimensional array* of office counts, for buildings 0 through 40 and floors 0 through 5.</span></span>  
  
```  
Dim officeCounts(40, 5) As Byte  
```  
  
 <span data-ttu-id="1ee16-130">Ein zweidimensionales Array wird auch bezeichnet ein *rechteckiges Array*.</span><span class="sxs-lookup"><span data-stu-id="1ee16-130">A two-dimensional array is also called a *rectangular array*.</span></span>  
  
### <a name="three-dimensions"></a><span data-ttu-id="1ee16-131">Drei Dimensionen</span><span class="sxs-lookup"><span data-stu-id="1ee16-131">Three Dimensions</span></span>  
 <span data-ttu-id="1ee16-132">Einige Arrays haben drei Dimensionen, z. B. Werte im dreidimensionalen Raum.</span><span class="sxs-lookup"><span data-stu-id="1ee16-132">A few arrays have three dimensions, such as values in three-dimensional space.</span></span> <span data-ttu-id="1ee16-133">Ein solches Array verwendet drei Indizes, die in diesem Fall die x-, y- und Z-Koordinaten des physischen Speicherplatzes darstellen.</span><span class="sxs-lookup"><span data-stu-id="1ee16-133">Such an array uses three indexes, which in this case represent the x, y, and z coordinates of physical space.</span></span> <span data-ttu-id="1ee16-134">Das folgende Beispiel deklariert eine Variable für eine *dreidimensionale Array* Air temperaturspalte an verschiedenen Punkten in einem dreidimensionalen Volume.</span><span class="sxs-lookup"><span data-stu-id="1ee16-134">The following example declares a variable to hold a *three-dimensional array* of air temperatures at various points in a three-dimensional volume.</span></span>  
  
```  
Dim airTemperatures(99, 99, 24) As Single  
```  
  
### <a name="more-than-three-dimensions"></a><span data-ttu-id="1ee16-135">Mehr als drei Dimensionen</span><span class="sxs-lookup"><span data-stu-id="1ee16-135">More than Three Dimensions</span></span>  
 <span data-ttu-id="1ee16-136">Obwohl ein Array mit bis zu 32 Dimensionen aufweisen kann, ist es selten um mehr als drei zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1ee16-136">Although an array can have as many as 32 dimensions, it is rare to have more than three.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ee16-137">Wenn Sie die Dimensionen in ein Array hinzufügen, erhöht der gesamte Speicher erforderlich, die vom Array sind beträchtlich, also verwenden mehrdimensionale Arrays mit Vorsicht.</span><span class="sxs-lookup"><span data-stu-id="1ee16-137">When you add dimensions to an array, the total storage needed by the array increases considerably, so use multidimensional arrays with care.</span></span>  
  
## <a name="using-different-dimensions"></a><span data-ttu-id="1ee16-138">Verwenden von verschiedenen Dimensionen</span><span class="sxs-lookup"><span data-stu-id="1ee16-138">Using Different Dimensions</span></span>  
 <span data-ttu-id="1ee16-139">Angenommen Sie, Sie Umsätze für jeden Tag des aktuellen Monats nachverfolgen möchten.</span><span class="sxs-lookup"><span data-stu-id="1ee16-139">Suppose you want to track sales amounts for every day of the present month.</span></span> <span data-ttu-id="1ee16-140">Sie können ein eindimensionales Array mit 31 Elementen deklarieren, eine für jeden Tag des Monats, wie im folgenden Beispiel wird gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1ee16-140">You might declare a one-dimensional array with 31 elements, one for each day of the month, as the following example shows.</span></span>  
  
```  
Dim salesAmounts(30) As Double  
```  
  
 <span data-ttu-id="1ee16-141">Jetzt nehmen Sie die gleiche Informationen nicht nur für jeden Tag eines Monats, sondern auch für jeden Monat des Jahres nachverfolgen möchten.</span><span class="sxs-lookup"><span data-stu-id="1ee16-141">Now suppose you want to track the same information not only for every day of a month but also for every month of the year.</span></span> <span data-ttu-id="1ee16-142">Sie können ein zweidimensionales Array mit 12 Zeilen (für die Monate) und 31 Spalten (für die Tage), wie im folgenden Beispiel gezeigt deklarieren.</span><span class="sxs-lookup"><span data-stu-id="1ee16-142">You might declare a two-dimensional array with 12 rows (for the months) and 31 columns (for the days), as the following example shows.</span></span>  
  
```  
Dim salesAmounts(11, 30) As Double  
```  
  
 <span data-ttu-id="1ee16-143">Angenommen, Sie entscheiden, damit Ihr Array enthalten jetzt Informationen für mehr als ein Jahr.</span><span class="sxs-lookup"><span data-stu-id="1ee16-143">Now suppose you decide to have your array hold information for more than one year.</span></span> <span data-ttu-id="1ee16-144">Wenn Sie die Umsatzbeträge für fünf Jahre nachverfolgen möchten, können Sie ein dreidimensionales Array mit 5 Ebenen, 12 Zeilen und 31 Spalten, wie im folgenden Beispiel gezeigt deklarieren.</span><span class="sxs-lookup"><span data-stu-id="1ee16-144">If you want to track sales amounts for 5 years, you could declare a three-dimensional array with 5 layers, 12 rows, and 31 columns, as the following example shows.</span></span>  
  
```  
Dim salesAmounts(4, 11, 30) As Double  
```  
  
 <span data-ttu-id="1ee16-145">Beachten Sie Folgendes: Da jeder Index von 0 abweicht, die auf seinen Maximalwert, jede Dimension des `salesAmounts` als eins kleiner ist als die erforderliche Länge für diese Dimension deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="1ee16-145">Note that, because each index varies from 0 to its maximum, each dimension of `salesAmounts` is declared as one less than the required length for that dimension.</span></span> <span data-ttu-id="1ee16-146">Beachten Sie, dass die Größe des Arrays mit jeder neuen Dimension zunimmt.</span><span class="sxs-lookup"><span data-stu-id="1ee16-146">Note also that the size of the array increases with each new dimension.</span></span> <span data-ttu-id="1ee16-147">Die drei Größen in den vorherigen Beispielen werden 31 372 und 1.860 Elementen.</span><span class="sxs-lookup"><span data-stu-id="1ee16-147">The three sizes in the preceding examples are 31, 372, and 1,860 elements respectively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ee16-148">Sie können ein Array erstellen, ohne die `Dim` Anweisung oder der `New` Klausel.</span><span class="sxs-lookup"><span data-stu-id="1ee16-148">You can create an array without using the `Dim` statement or the `New` clause.</span></span> <span data-ttu-id="1ee16-149">Sie können z. B. Aufrufen der <xref:System.Array.CreateInstance%2A> Methode oder eine andere Komponente kann Ihren Code auf diese Weise erstellte Array übergeben.</span><span class="sxs-lookup"><span data-stu-id="1ee16-149">For example, you can call the <xref:System.Array.CreateInstance%2A> method, or another component can pass your code an array created in this manner.</span></span> <span data-ttu-id="1ee16-150">Ein Array dieser Art lassen sich auf eine unteren Grenze ungleich 0.</span><span class="sxs-lookup"><span data-stu-id="1ee16-150">Such an array can have a lower bound other than 0.</span></span> <span data-ttu-id="1ee16-151">Sie können immer auf die untere Grenze einer Dimension testen, mit der <xref:System.Array.GetLowerBound%2A> Methode oder der `LBound` Funktion.</span><span class="sxs-lookup"><span data-stu-id="1ee16-151">You can always test for the lower bound of a dimension by using the <xref:System.Array.GetLowerBound%2A> method or the `LBound` function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ee16-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ee16-152">See also</span></span>
- [<span data-ttu-id="1ee16-153">Arrays</span><span class="sxs-lookup"><span data-stu-id="1ee16-153">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="1ee16-154">Problembehandlung bei Arrays</span><span class="sxs-lookup"><span data-stu-id="1ee16-154">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
