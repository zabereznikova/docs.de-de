---
title: ReDim-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ReDim
- vb.Preserve
helpviewer_keywords:
- fixed-length strings [Visual Basic], declaring
- ReDim statement [Visual Basic], syntax
- dynamic arrays [Visual Basic], ReDim statement
- arrays [Visual Basic], reallocating
- arrays [Visual Basic], reinitializing
- arrays [Visual Basic], dimensions
- scalars, and arrays
- scalars
- declarations [Visual Basic], dynamic arrays
- variables [Visual Basic], scalar
- ReDim statement [Visual Basic]
- data types [Visual Basic], assigning
- As keyword [Visual Basic], in ReDim statement
- To keyword [Visual Basic], ReDim statement
- arrays [Visual Basic], declaring
- Preserve keyword [Visual Basic], ReDim statement
- storage [Visual Basic], allocating
- arrays [Visual Basic], and scalars
- declaration statements [Visual Basic]
- scalar variables [Visual Basic]
ms.assetid: ad1c5e07-dcd7-4ae1-a79e-ad3f2dcc2083
ms.openlocfilehash: e8689820d13db173950f8df45431011968899bed
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64582899"
---
# <a name="redim-statement-visual-basic"></a><span data-ttu-id="d916b-102">ReDim-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d916b-102">ReDim Statement (Visual Basic)</span></span>
<span data-ttu-id="d916b-103">Reserviert Speicherplatz für eine Arrayvariable neu.</span><span class="sxs-lookup"><span data-stu-id="d916b-103">Reallocates storage space for an array variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d916b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d916b-104">Syntax</span></span>  
  
```  
ReDim [ Preserve ] name(boundlist) [ ,  name(boundlist) [, ... ] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="d916b-105">Teile</span><span class="sxs-lookup"><span data-stu-id="d916b-105">Parts</span></span>  
  
|<span data-ttu-id="d916b-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="d916b-106">Term</span></span>|<span data-ttu-id="d916b-107">Definition</span><span class="sxs-lookup"><span data-stu-id="d916b-107">Definition</span></span>|  
|----------|----------------|  
|`Preserve`|<span data-ttu-id="d916b-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="d916b-108">Optional.</span></span> <span data-ttu-id="d916b-109">Modifizierer zum Beibehalten der Daten im vorhandenen Array, wenn lediglich die Größe der letzten Dimension geändert wird.</span><span class="sxs-lookup"><span data-stu-id="d916b-109">Modifier used to preserve the data in the existing array when you change the size of only the last dimension.</span></span>|  
|`name`|<span data-ttu-id="d916b-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d916b-110">Required.</span></span> <span data-ttu-id="d916b-111">Name der Arrayvariablen.</span><span class="sxs-lookup"><span data-stu-id="d916b-111">Name of the array variable.</span></span> <span data-ttu-id="d916b-112">Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="d916b-112">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`boundlist`|<span data-ttu-id="d916b-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d916b-113">Required.</span></span> <span data-ttu-id="d916b-114">Liste der Grenzen jeder Dimension des neu definierten Arrays.</span><span class="sxs-lookup"><span data-stu-id="d916b-114">List of bounds of each dimension of the redefined array.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d916b-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d916b-115">Remarks</span></span>  
 <span data-ttu-id="d916b-116">Sie können die `ReDim`-Anweisung verwenden, um die Größe einer oder mehrerer Dimensionen eines Arrays zu ändern, das bereits deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="d916b-116">You can use the `ReDim` statement to change the size of one or more dimensions of an array that has already been declared.</span></span> <span data-ttu-id="d916b-117">Wenn Sie ein großes Array verwenden und einige Elemente nicht mehr benötigen, kann `ReDim` durch das Reduzieren der Arraygröße Arbeitsspeicher freigeben.</span><span class="sxs-lookup"><span data-stu-id="d916b-117">If you have a large array and you no longer need some of its elements, `ReDim` can free up memory by reducing the array size.</span></span> <span data-ttu-id="d916b-118">Falls Ihr Array mehr Elemente benötigt, kann `ReDim` diese auch hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d916b-118">On the other hand, if your array needs more elements, `ReDim` can add them.</span></span>  
  
 <span data-ttu-id="d916b-119">Die `ReDim`-Anweisung ist nur für Arrays bestimmt.</span><span class="sxs-lookup"><span data-stu-id="d916b-119">The `ReDim` statement is intended only for arrays.</span></span> <span data-ttu-id="d916b-120">Sie gilt nicht für Skalare (Variablen, die nur einen einzelnen Wert enthalten), Auflistungen oder Strukturen.</span><span class="sxs-lookup"><span data-stu-id="d916b-120">It's not valid on scalars (variables that contain only a single value), collections, or structures.</span></span> <span data-ttu-id="d916b-121">Beachten Sie Folgendes: Wenn Sie für eine Variable den Typ `Array` deklarieren, verfügt die `ReDim`-Anweisung nicht über genügend Typinformationen zum Erstellen des neuen Arrays.</span><span class="sxs-lookup"><span data-stu-id="d916b-121">Note that if you declare a variable to be of type `Array`, the `ReDim` statement doesn't have sufficient type information to create the new array.</span></span>  
  
 <span data-ttu-id="d916b-122">Sie können `ReDim` nur auf Prozedurebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="d916b-122">You can use `ReDim` only at procedure level.</span></span> <span data-ttu-id="d916b-123">Aus diesem Grund muss der Deklarationskontext für die Variable eine Prozedur sein. Folgende Kontexte sind nicht möglich: Quelldatei, Namespace, Schnittstelle, Klasse, Struktur, Modul oder Block.</span><span class="sxs-lookup"><span data-stu-id="d916b-123">Therefore, the declaration context for the variable must be a procedure; it can't be a source file, a namespace, an interface, a class, a structure, a module, or a block.</span></span> <span data-ttu-id="d916b-124">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="d916b-124">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="d916b-125">Regeln</span><span class="sxs-lookup"><span data-stu-id="d916b-125">Rules</span></span>  
  
- <span data-ttu-id="d916b-126">**Mehrere Variablen.**</span><span class="sxs-lookup"><span data-stu-id="d916b-126">**Multiple Variables.**</span></span> <span data-ttu-id="d916b-127">Sie können die Größe mehrerer Arrayvariablen in derselben Deklarationsanweisung ändern und die Teile `name` und `boundlist` für jede Variable angeben.</span><span class="sxs-lookup"><span data-stu-id="d916b-127">You can resize several array variables in the same declaration statement and specify the `name` and `boundlist` parts for each variable.</span></span> <span data-ttu-id="d916b-128">Mehrere Variablen werden durch Kommas voneinander getrennt.</span><span class="sxs-lookup"><span data-stu-id="d916b-128">Multiple variables are separated by commas.</span></span>  
  
- <span data-ttu-id="d916b-129">**Arraygrenzen.**</span><span class="sxs-lookup"><span data-stu-id="d916b-129">**Array Bounds.**</span></span> <span data-ttu-id="d916b-130">Für jeden Eintrag in `boundlist` können die unteren und oberen Grenzen der Dimension angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d916b-130">Each entry in `boundlist` can specify the lower and upper bounds of that dimension.</span></span> <span data-ttu-id="d916b-131">Die untere Grenze ist immer 0 (null).</span><span class="sxs-lookup"><span data-stu-id="d916b-131">The lower bound is always 0 (zero).</span></span> <span data-ttu-id="d916b-132">Die Obergrenze ist der größtmögliche Indexwert für diese Dimension, nicht die Länge der Dimension (dies ist die obere Grenze plus 1).</span><span class="sxs-lookup"><span data-stu-id="d916b-132">The upper bound is the highest possible index value for that dimension, not the length of the dimension (which is the upper bound plus one).</span></span> <span data-ttu-id="d916b-133">Der Index für jede Dimension kann zwischen 0 und dem Wert der oberen Grenze variieren.</span><span class="sxs-lookup"><span data-stu-id="d916b-133">The index for each dimension can vary from 0 through its upper bound value.</span></span>  
  
     <span data-ttu-id="d916b-134">Die Anzahl der Dimensionen in `boundlist` muss mit der ursprünglichen Anzahl von Dimensionen (Rang) des Arrays übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d916b-134">The number of dimensions in `boundlist` must match the original number of dimensions (rank) of the array.</span></span>  
  
- <span data-ttu-id="d916b-135">**Datentypen.**</span><span class="sxs-lookup"><span data-stu-id="d916b-135">**Data Types.**</span></span> <span data-ttu-id="d916b-136">Mit der `ReDim`-Anweisung kann der Datentyp einer Arrayvariablen oder ihrer Elemente nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d916b-136">The `ReDim` statement cannot change the data type of an array variable or its elements.</span></span>  
  
- <span data-ttu-id="d916b-137">**Die Initialisierung.**</span><span class="sxs-lookup"><span data-stu-id="d916b-137">**Initialization.**</span></span> <span data-ttu-id="d916b-138">Mit der `ReDim`-Anweisung können keine neuen Initialisierungswerte für die Arrayelemente bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d916b-138">The `ReDim` statement cannot provide new initialization values for the array elements.</span></span>  
  
- <span data-ttu-id="d916b-139">**Rang.**</span><span class="sxs-lookup"><span data-stu-id="d916b-139">**Rank.**</span></span> <span data-ttu-id="d916b-140">Mit der `ReDim`-Anweisung kann der Rang (Anzahl von Dimensionen) des Arrays nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d916b-140">The `ReDim` statement cannot change the rank (the number of dimensions) of the array.</span></span>  
  
- <span data-ttu-id="d916b-141">**Ändern der Größe mit beibehalten.**</span><span class="sxs-lookup"><span data-stu-id="d916b-141">**Resizing with Preserve.**</span></span> <span data-ttu-id="d916b-142">Bei Verwendung von `Preserve` können Sie nur die Größe der letzten Dimension des Arrays ändern.</span><span class="sxs-lookup"><span data-stu-id="d916b-142">If you use `Preserve`, you can resize only the last dimension of the array.</span></span> <span data-ttu-id="d916b-143">Für alle anderen Dimensionen müssen Sie die Grenze des vorhandenen Arrays angeben.</span><span class="sxs-lookup"><span data-stu-id="d916b-143">For every other dimension, you must specify the bound of the existing array.</span></span>  
  
     <span data-ttu-id="d916b-144">Wenn das Array nur eine Dimension hat, können Sie beispielsweise die Größe dieser Dimension ändern und trotzdem den gesamten Inhalt des Arrays beibehalten. Dies liegt daran, dass Sie die letzte und einzige Dimension ändern.</span><span class="sxs-lookup"><span data-stu-id="d916b-144">For example, if your array has only one dimension, you can resize that dimension and still preserve all the contents of the array, because you are changing the last and only dimension.</span></span> <span data-ttu-id="d916b-145">Wenn das Array aber über zwei oder mehr Dimensionen verfügt, können Sie bei Verwendung von `Preserve` nur die Größe der letzten Dimension ändern.</span><span class="sxs-lookup"><span data-stu-id="d916b-145">However, if your array has two or more dimensions, you can change the size of only the last dimension if you use `Preserve`.</span></span>  
  
- <span data-ttu-id="d916b-146">**Eigenschaften.**</span><span class="sxs-lookup"><span data-stu-id="d916b-146">**Properties.**</span></span> <span data-ttu-id="d916b-147">Sie können `ReDim` für eine Eigenschaft verwenden, die ein Array von Werten enthält.</span><span class="sxs-lookup"><span data-stu-id="d916b-147">You can use `ReDim` on a property that holds an array of values.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="d916b-148">Verhalten</span><span class="sxs-lookup"><span data-stu-id="d916b-148">Behavior</span></span>  
  
- <span data-ttu-id="d916b-149">**Array-Ersatz.**</span><span class="sxs-lookup"><span data-stu-id="d916b-149">**Array Replacement.**</span></span> <span data-ttu-id="d916b-150">`ReDim` Gibt das vorhandene Array frei und erstellt ein neues Array mit den gleichen Rang.</span><span class="sxs-lookup"><span data-stu-id="d916b-150">`ReDim` releases the existing array and creates a new array with the same rank.</span></span> <span data-ttu-id="d916b-151">Das neue Array ersetzt das freigegebene Array in der Arrayvariablen.</span><span class="sxs-lookup"><span data-stu-id="d916b-151">The new array replaces the released array in the array variable.</span></span>  
  
- <span data-ttu-id="d916b-152">**Initialisierung ohne beibehalten.**</span><span class="sxs-lookup"><span data-stu-id="d916b-152">**Initialization without Preserve.**</span></span> <span data-ttu-id="d916b-153">Wenn Sie kein `Preserve`-Element angeben, werden die Elemente des neuen Arrays von `ReDim` mit dem Standardwert für ihren Datentyp initialisiert.</span><span class="sxs-lookup"><span data-stu-id="d916b-153">If you do not specify `Preserve`, `ReDim` initializes the elements of the new array by using the default value for their data type.</span></span>  
  
- <span data-ttu-id="d916b-154">**Die Initialisierung mit beibehalten.**</span><span class="sxs-lookup"><span data-stu-id="d916b-154">**Initialization with Preserve.**</span></span> <span data-ttu-id="d916b-155">Wenn Sie `Preserve` angeben, kopiert Visual Basic die Elemente aus dem vorhandenen Array in das neue Array.</span><span class="sxs-lookup"><span data-stu-id="d916b-155">If you specify `Preserve`, Visual Basic copies the elements from the existing array to the new array.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d916b-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d916b-156">Example</span></span>  
 <span data-ttu-id="d916b-157">Im folgenden Beispiel wird die Größe der letzten Dimension eines dynamischen Arrays erhöht, ohne dass vorhandene Daten im Array verloren gehen. Anschließend wird die Größe mit einem Teilverlust der Daten reduziert.</span><span class="sxs-lookup"><span data-stu-id="d916b-157">The following example increases the size of the last dimension of a dynamic array without losing any existing data in the array, and then decreases the size with partial data loss.</span></span> <span data-ttu-id="d916b-158">Zuletzt wird die Größe zurück auf den Originalwert reduziert, und alle Arrayelemente werden neu initialisiert.</span><span class="sxs-lookup"><span data-stu-id="d916b-158">Finally, it decreases the size back to its original value and reinitializes all the array elements.</span></span>  
  
 [!code-vb[VbVbalrStatements#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#52)]  
  
 <span data-ttu-id="d916b-159">Mit der `Dim`-Anweisung wird ein neues Array mit drei Dimensionen erstellt.</span><span class="sxs-lookup"><span data-stu-id="d916b-159">The `Dim` statement creates a new array with three dimensions.</span></span> <span data-ttu-id="d916b-160">Jede Dimension wird mit einer Grenze von 10 deklariert, sodass der Arrayindex für jede Dimension von 0 bis 10 reichen kann.</span><span class="sxs-lookup"><span data-stu-id="d916b-160">Each dimension is declared with a bound of 10, so the array index for each dimension can range from 0 through 10.</span></span> <span data-ttu-id="d916b-161">Im folgenden Text werden die drei Dimensionen als Ebene (Layer), Zeile (Row) und Spalte (Column) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d916b-161">In the following discussion, the three dimensions are referred to as layer, row, and column.</span></span>  
  
 <span data-ttu-id="d916b-162">Das erste `ReDim`-Element erstellt ein neues Array, mit dem das vorhandene Array in der Variablen `intArray` ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="d916b-162">The first `ReDim` creates a new array which replaces the existing array in variable `intArray`.</span></span> <span data-ttu-id="d916b-163">`ReDim` kopiert alle Elemente aus dem vorhandenen Array in das neue Array.</span><span class="sxs-lookup"><span data-stu-id="d916b-163">`ReDim` copies all the elements from the existing array into the new array.</span></span> <span data-ttu-id="d916b-164">Außerdem werden auf jeder Ebene am Ende jeder Zeile zehn weitere Spalten hinzugefügt, und die Elemente in diesen neuen Spalten werden mit dem Wert 0 initialisiert (Standardwert von `Integer`, dem Elementtyp des Arrays).</span><span class="sxs-lookup"><span data-stu-id="d916b-164">It also adds 10 more columns to the end of every row in every layer and initializes the elements in these new columns to 0 (the default value of `Integer`, which is the element type of the array).</span></span>  
  
 <span data-ttu-id="d916b-165">Das zweite `ReDim`-Element erstellt ein neues Array und kopiert alle passenden Elemente.</span><span class="sxs-lookup"><span data-stu-id="d916b-165">The second `ReDim` creates another new array and copies all the elements that fit.</span></span> <span data-ttu-id="d916b-166">Am Ende jeder Zeile auf jeder Ebene gehen aber fünf Spalten verloren.</span><span class="sxs-lookup"><span data-stu-id="d916b-166">However, five columns are lost from the end of every row in every layer.</span></span> <span data-ttu-id="d916b-167">Dies ist kein Problem, wenn Sie mit der Verwendung dieser Spalten fertig sind.</span><span class="sxs-lookup"><span data-stu-id="d916b-167">This is not a problem if you have finished using these columns.</span></span> <span data-ttu-id="d916b-168">Durch das Reduzieren der Größe eines großen Arrays kann Speicher freigegeben werden, den Sie nicht mehr benötigen.</span><span class="sxs-lookup"><span data-stu-id="d916b-168">Reducing the size of a large array can free up memory that you no longer need.</span></span>  
  
 <span data-ttu-id="d916b-169">Das dritte `ReDim`-Element erstellt ein weiteres neues Array und entfernt auf jeder Ebene weitere fünf Spalten vom Ende jeder Zeile.</span><span class="sxs-lookup"><span data-stu-id="d916b-169">The third `ReDim` creates another new array and removes another five columns from the end of every row in every layer.</span></span> <span data-ttu-id="d916b-170">Dieses Mal werden keine vorhandenen Elemente kopiert.</span><span class="sxs-lookup"><span data-stu-id="d916b-170">This time it does not copy any existing elements.</span></span> <span data-ttu-id="d916b-171">Mit dieser Anweisung wird das Array auf seine ursprüngliche Größe zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="d916b-171">This statement reverts the array to its original size.</span></span> <span data-ttu-id="d916b-172">Da die Anweisung den `Preserve`-Modifizierer nicht enthält, werden alle Arrayelemente auf ihre ursprünglichen Standardwerte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d916b-172">Because the statement doesn't include the `Preserve` modifier, it sets all array elements to their original default values.</span></span>  
  
 <span data-ttu-id="d916b-173">Weitere Beispiele finden Sie unter [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="d916b-173">For additional examples, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d916b-174">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d916b-174">See also</span></span>

- <xref:System.IndexOutOfRangeException>
- [<span data-ttu-id="d916b-175">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d916b-175">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="d916b-176">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d916b-176">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="d916b-177">Erase-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d916b-177">Erase Statement</span></span>](../../../visual-basic/language-reference/statements/erase-statement.md)
- [<span data-ttu-id="d916b-178">Nothing</span><span class="sxs-lookup"><span data-stu-id="d916b-178">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="d916b-179">Arrays</span><span class="sxs-lookup"><span data-stu-id="d916b-179">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
