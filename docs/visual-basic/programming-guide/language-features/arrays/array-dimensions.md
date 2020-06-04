---
title: Arraydimensionen
ms.date: 07/20/2015
helpviewer_keywords:
- dimensions, arrays
- arrays [Visual Basic], dimensions
- arrays [Visual Basic], rectangular
- arrays [Visual Basic], rank
- rectangular arrays
- ranking, arrays
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
ms.openlocfilehash: f971f0c3693177adbcb8869d487e3ad41d49ddc2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413103"
---
# <a name="array-dimensions-in-visual-basic"></a><span data-ttu-id="37e75-102">Arraydimensionen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="37e75-102">Array Dimensions in Visual Basic</span></span>

<span data-ttu-id="37e75-103">Eine *Dimension* ist eine Richtung, in der Sie die Spezifikation der Elemente eines Arrays variieren können.</span><span class="sxs-lookup"><span data-stu-id="37e75-103">A *dimension* is a direction in which you can vary the specification of an array's elements.</span></span> <span data-ttu-id="37e75-104">Ein Array, das die Gesamtumsätze für jeden Tag des Monats enthält, verfügt über eine Dimension (den Tag des Monats).</span><span class="sxs-lookup"><span data-stu-id="37e75-104">An array that holds the sales total for each day of the month has one dimension (the day of the month).</span></span> <span data-ttu-id="37e75-105">Ein Array, das die Gesamtumsätze pro Abteilung für jeden Tag des Monats enthält, hat zwei Dimensionen (die Abteilungs Nummer und den Tag des Monats).</span><span class="sxs-lookup"><span data-stu-id="37e75-105">An array that holds the sales total by department for each day of the month has two dimensions (the department number and the day of the month).</span></span> <span data-ttu-id="37e75-106">Die Anzahl der Dimensionen, die ein Array hat, wird als *Rang*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="37e75-106">The number of dimensions an array has is called its *rank*.</span></span>

> [!NOTE]
> <span data-ttu-id="37e75-107">Sie können die- <xref:System.Array.Rank%2A> Eigenschaft verwenden, um die Anzahl der Dimensionen eines Arrays zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="37e75-107">You can use the <xref:System.Array.Rank%2A> property to determine the how many dimensions an array has.</span></span>

## <a name="working-with-dimensions"></a><span data-ttu-id="37e75-108">Arbeiten mit Dimensionen</span><span class="sxs-lookup"><span data-stu-id="37e75-108">Working with Dimensions</span></span>

<span data-ttu-id="37e75-109">Sie geben ein Element eines Arrays an, indem Sie einen Index bereit *stellen oder für* jede seiner Dimensionen einen *Index* festlegen.</span><span class="sxs-lookup"><span data-stu-id="37e75-109">You specify an element of an array by supplying an *index* or *subscript* for each of its dimensions.</span></span> <span data-ttu-id="37e75-110">Die Elemente sind zusammenhängend entlang jeder Dimension von Index 0 bis zum höchsten Index für diese Dimension.</span><span class="sxs-lookup"><span data-stu-id="37e75-110">The elements are contiguous along each dimension from index 0 through the highest index for that dimension.</span></span>

<span data-ttu-id="37e75-111">Die folgenden Abbildungen zeigen die konzeptionelle Struktur von Arrays mit unterschiedlichen Rang folgen.</span><span class="sxs-lookup"><span data-stu-id="37e75-111">The following illustrations show the conceptual structure of arrays with different ranks.</span></span> <span data-ttu-id="37e75-112">Jedes Element in den Abbildungen zeigt die Indexwerte, die darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="37e75-112">Each element in the illustrations shows the index values that access it.</span></span> <span data-ttu-id="37e75-113">Beispielsweise können Sie durch Angabe von Indizes auf das erste Element der zweiten Zeile des zweidimensionalen Arrays zugreifen `(1, 0)` .</span><span class="sxs-lookup"><span data-stu-id="37e75-113">For example, you can access the first element of the second row of the two-dimensional array by specifying indexes `(1, 0)`.</span></span>

![Diagramm, das ein eindimensionales Array anzeigt.](./media/array-dimensions/one-dimensional-array.gif)

![Diagramm, das ein zweidimensionales Array anzeigt.](./media/array-dimensions/two-dimensional-array.gif)

![Diagramm, das ein dreidimensionales Array anzeigt.](./media/array-dimensions/three-dimensional-array.gif)

### <a name="one-dimension"></a><span data-ttu-id="37e75-117">Eine Dimension</span><span class="sxs-lookup"><span data-stu-id="37e75-117">One Dimension</span></span>

<span data-ttu-id="37e75-118">Viele Arrays verfügen nur über eine Dimension, z. b. die Anzahl der Personen jedes Alters.</span><span class="sxs-lookup"><span data-stu-id="37e75-118">Many arrays have only one dimension, such as the number of people of each age.</span></span> <span data-ttu-id="37e75-119">Die einzige Anforderung, ein Element anzugeben, ist das Alter, für das dieses Element die Anzahl enthält.</span><span class="sxs-lookup"><span data-stu-id="37e75-119">The only requirement to specify an element is the age for which that element holds the count.</span></span> <span data-ttu-id="37e75-120">Daher verwendet ein solches Array nur einen Index.</span><span class="sxs-lookup"><span data-stu-id="37e75-120">Therefore, such an array uses only one index.</span></span> <span data-ttu-id="37e75-121">Im folgenden Beispiel wird eine Variable deklariert, die ein *eindimensionales Array* von Alters Zählungen für die Alters Zahlen 0 bis 120 enthält.</span><span class="sxs-lookup"><span data-stu-id="37e75-121">The following example declares a variable to hold a *one-dimensional array* of age counts for ages 0 through 120.</span></span>

```vb
Dim ageCounts(120) As UInteger
```

### <a name="two-dimensions"></a><span data-ttu-id="37e75-122">Zwei Dimensionen</span><span class="sxs-lookup"><span data-stu-id="37e75-122">Two Dimensions</span></span>

<span data-ttu-id="37e75-123">Einige Arrays verfügen über zwei Dimensionen, z. b. die Anzahl der Niederlassungen in jeder Etage der einzelnen Gebäude auf einem Campus.</span><span class="sxs-lookup"><span data-stu-id="37e75-123">Some arrays have two dimensions, such as the number of offices on each floor of each building on a campus.</span></span> <span data-ttu-id="37e75-124">Die Angabe eines Elements erfordert sowohl die Gebäude Nummer als auch die Etage, und jedes Element enthält die Anzahl für diese Kombination aus Gebäude und Etage.</span><span class="sxs-lookup"><span data-stu-id="37e75-124">The specification of an element requires both the building number and the floor, and each element holds the count for that combination of building and floor.</span></span> <span data-ttu-id="37e75-125">Daher verwendet ein solches Array zwei Indizes.</span><span class="sxs-lookup"><span data-stu-id="37e75-125">Therefore, such an array uses two indexes.</span></span> <span data-ttu-id="37e75-126">Im folgenden Beispiel wird eine Variable deklariert, die ein *zweidimensionales Array* von Office-Zählungen enthält, für Gebäude 0 bis 40 und die Stock-Werte 0 bis 5.</span><span class="sxs-lookup"><span data-stu-id="37e75-126">The following example declares a variable to hold a *two-dimensional array* of office counts, for buildings 0 through 40 and floors 0 through 5.</span></span>

```vb
Dim officeCounts(40, 5) As Byte
```

<span data-ttu-id="37e75-127">Ein zweidimensionales Array wird auch als *rechteckiges Array*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="37e75-127">A two-dimensional array is also called a *rectangular array*.</span></span>

### <a name="three-dimensions"></a><span data-ttu-id="37e75-128">Drei Dimensionen</span><span class="sxs-lookup"><span data-stu-id="37e75-128">Three Dimensions</span></span>

<span data-ttu-id="37e75-129">Einige Arrays verfügen über drei Dimensionen, z. b. Werte im dreidimensionalen Raum.</span><span class="sxs-lookup"><span data-stu-id="37e75-129">A few arrays have three dimensions, such as values in three-dimensional space.</span></span> <span data-ttu-id="37e75-130">Ein solches Array verwendet drei Indizes, die in diesem Fall die x-, y-und z-Koordinaten von physischem Raum darstellen.</span><span class="sxs-lookup"><span data-stu-id="37e75-130">Such an array uses three indexes, which in this case represent the x, y, and z coordinates of physical space.</span></span> <span data-ttu-id="37e75-131">Im folgenden Beispiel wird eine Variable deklariert, die ein *dreidimensionales Array* von Lufttemperaturen an verschiedenen Punkten in einem dreidimensionalen Volume enthält.</span><span class="sxs-lookup"><span data-stu-id="37e75-131">The following example declares a variable to hold a *three-dimensional array* of air temperatures at various points in a three-dimensional volume.</span></span>

```vb
Dim airTemperatures(99, 99, 24) As Single
```

### <a name="more-than-three-dimensions"></a><span data-ttu-id="37e75-132">Mehr als drei Dimensionen</span><span class="sxs-lookup"><span data-stu-id="37e75-132">More than Three Dimensions</span></span>

<span data-ttu-id="37e75-133">Obwohl ein Array bis zu 32 Dimensionen aufweisen kann, ist es selten, dass mehr als drei Dimensionen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="37e75-133">Although an array can have as many as 32 dimensions, it is rare to have more than three.</span></span>

> [!NOTE]
> <span data-ttu-id="37e75-134">Wenn Sie einem Array Dimensionen hinzufügen, erhöht sich der für das Array benötigte Gesamtspeicher erheblich. verwenden Sie daher mehrdimensionale Arrays mit Sorgfalt.</span><span class="sxs-lookup"><span data-stu-id="37e75-134">When you add dimensions to an array, the total storage needed by the array increases considerably, so use multidimensional arrays with care.</span></span>

## <a name="using-different-dimensions"></a><span data-ttu-id="37e75-135">Verwenden verschiedener Dimensionen</span><span class="sxs-lookup"><span data-stu-id="37e75-135">Using Different Dimensions</span></span>

<span data-ttu-id="37e75-136">Angenommen, Sie möchten die Umsatz Beträge für jeden Tag des aktuellen Monats nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="37e75-136">Suppose you want to track sales amounts for every day of the present month.</span></span> <span data-ttu-id="37e75-137">Sie können ein eindimensionales Array mit 31 Elementen deklarieren, eine für jeden Tag des Monats, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="37e75-137">You might declare a one-dimensional array with 31 elements, one for each day of the month, as the following example shows.</span></span>

```vb
Dim salesAmounts(30) As Double
```

<span data-ttu-id="37e75-138">Nehmen Sie nun an, Sie möchten die gleichen Informationen nicht nur für jeden Tag eines Monats, sondern auch für jeden Monat des Jahres nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="37e75-138">Now suppose you want to track the same information not only for every day of a month but also for every month of the year.</span></span> <span data-ttu-id="37e75-139">Sie können ein zweidimensionales Array mit 12 Zeilen (für die Monate) und 31 Spalten (für die Tage) deklarieren, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="37e75-139">You might declare a two-dimensional array with 12 rows (for the months) and 31 columns (for the days), as the following example shows.</span></span>

```vb
Dim salesAmounts(11, 30) As Double
```

<span data-ttu-id="37e75-140">Angenommen, Sie entscheiden sich dafür, dass Ihr Array Informationen für mehr als ein Jahr enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="37e75-140">Now suppose you decide to have your array hold information for more than one year.</span></span> <span data-ttu-id="37e75-141">Wenn Sie Umsatz Beträge für 5 Jahre nachverfolgen möchten, können Sie ein dreidimensionales Array mit 5 Ebenen, 12 Zeilen und 31 Spalten deklarieren, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="37e75-141">If you want to track sales amounts for 5 years, you could declare a three-dimensional array with 5 layers, 12 rows, and 31 columns, as the following example shows.</span></span>

```vb
Dim salesAmounts(4, 11, 30) As Double
```

<span data-ttu-id="37e75-142">Beachten Sie, dass jede Dimension von `salesAmounts` als eine kleiner als die für diese Dimension erforderliche Länge deklariert wird, da jeder Index von 0 bis zum Maximum abweicht.</span><span class="sxs-lookup"><span data-stu-id="37e75-142">Note that, because each index varies from 0 to its maximum, each dimension of `salesAmounts` is declared as one less than the required length for that dimension.</span></span> <span data-ttu-id="37e75-143">Beachten Sie auch, dass sich die Größe des Arrays mit jeder neuen Dimension vergrößert.</span><span class="sxs-lookup"><span data-stu-id="37e75-143">Note also that the size of the array increases with each new dimension.</span></span> <span data-ttu-id="37e75-144">Die drei Größen in den vorangehenden Beispielen sind die Elemente 31, 372 und 1.860.</span><span class="sxs-lookup"><span data-stu-id="37e75-144">The three sizes in the preceding examples are 31, 372, and 1,860 elements respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="37e75-145">Sie können ein Array erstellen, ohne die- `Dim` Anweisung oder die-Klausel zu verwenden `New` .</span><span class="sxs-lookup"><span data-stu-id="37e75-145">You can create an array without using the `Dim` statement or the `New` clause.</span></span> <span data-ttu-id="37e75-146">Sie können z. b. die- <xref:System.Array.CreateInstance%2A> Methode oder eine andere Komponente den Code an ein auf diese Weise erstelltes Array übergeben.</span><span class="sxs-lookup"><span data-stu-id="37e75-146">For example, you can call the <xref:System.Array.CreateInstance%2A> method, or another component can pass your code an array created in this manner.</span></span> <span data-ttu-id="37e75-147">Ein solches Array kann eine untere Grenze aufweisen, die nicht 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="37e75-147">Such an array can have a lower bound other than 0.</span></span> <span data-ttu-id="37e75-148">Mithilfe der-Methode oder der-Funktion können Sie immer die untere Grenze einer Dimension testen <xref:System.Array.GetLowerBound%2A> `LBound` .</span><span class="sxs-lookup"><span data-stu-id="37e75-148">You can always test for the lower bound of a dimension by using the <xref:System.Array.GetLowerBound%2A> method or the `LBound` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="37e75-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="37e75-149">See also</span></span>

- [<span data-ttu-id="37e75-150">Arrays</span><span class="sxs-lookup"><span data-stu-id="37e75-150">Arrays</span></span>](index.md)
- [<span data-ttu-id="37e75-151">Problembehandlung bei Arrays</span><span class="sxs-lookup"><span data-stu-id="37e75-151">Troubleshooting Arrays</span></span>](troubleshooting-arrays.md)
