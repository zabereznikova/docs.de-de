---
title: Zusammengesetzte Datentypen
ms.date: 04/25/2017
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- classes [Visual Basic], composite types
- types [Visual Basic], composite
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
ms.openlocfilehash: 3e8df5ccfeca4bc0a19237ba6d59e9d0747080ea
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84394297"
---
# <a name="composite-data-types-visual-basic"></a><span data-ttu-id="39177-102">Zusammengesetzte Datentypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39177-102">Composite Data Types (Visual Basic)</span></span>
<span data-ttu-id="39177-103">Zusätzlich zu den elementaren Datentypen Visual Basic-Bereitstellung können Sie auch Elemente verschiedener Typen zusammenstellen, um zusammen *gesetzte Datentypen* wie Strukturen, Arrays und Klassen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="39177-103">In addition to the elementary data types Visual Basic supplies, you can also assemble items of different types to create *composite data types* such as structures, arrays, and classes.</span></span> <span data-ttu-id="39177-104">Sie können zusammengesetzte Datentypen aus elementaren Typen und aus anderen zusammengesetzten Typen erstellen.</span><span class="sxs-lookup"><span data-stu-id="39177-104">You can build composite data types from elementary types and from other composite types.</span></span> <span data-ttu-id="39177-105">Beispielsweise können Sie ein Array von Strukturelementen oder eine Struktur mit Array Elementen definieren.</span><span class="sxs-lookup"><span data-stu-id="39177-105">For example, you can define an array of structure elements, or a structure with array members.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="39177-106">Datentypen</span><span class="sxs-lookup"><span data-stu-id="39177-106">Data Types</span></span>  
 <span data-ttu-id="39177-107">Ein zusammengesetzter Typ unterscheidet sich vom Datentyp seiner Komponenten.</span><span class="sxs-lookup"><span data-stu-id="39177-107">A composite type is different from the data type of any of its components.</span></span> <span data-ttu-id="39177-108">Beispielsweise ist ein Array von- `Integer` Elementen nicht vom `Integer` Datentyp.</span><span class="sxs-lookup"><span data-stu-id="39177-108">For example, an array of `Integer` elements is not of the `Integer` data type.</span></span>  
  
 <span data-ttu-id="39177-109">Ein Array Datentyp wird normalerweise mit dem Elementtyp, Klammern und Kommas dargestellt, wenn dies erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="39177-109">An array data type is normally represented using the element type, parentheses, and commas as necessary.</span></span> <span data-ttu-id="39177-110">Beispielsweise wird ein eindimensionales Array von- `String` Elementen als dargestellt `String()` , und ein zweidimensionales Array von- `Boolean` Elementen wird als dargestellt `Boolean(,)` .</span><span class="sxs-lookup"><span data-stu-id="39177-110">For example, a one-dimensional array of `String` elements is represented as `String()`, and a two-dimensional array of `Boolean` elements is represented as `Boolean(,)`.</span></span>  
  
## <a name="structure-types"></a><span data-ttu-id="39177-111">Strukturtypen</span><span class="sxs-lookup"><span data-stu-id="39177-111">Structure Types</span></span>  
 <span data-ttu-id="39177-112">Es gibt keinen einzelnen Datentyp, der alle Strukturen umfasst.</span><span class="sxs-lookup"><span data-stu-id="39177-112">There is no single data type comprising all structures.</span></span> <span data-ttu-id="39177-113">Stattdessen stellt jede Definition einer Struktur einen eindeutigen Datentyp dar, auch wenn zwei Strukturen identische Elemente in derselben Reihenfolge definieren.</span><span class="sxs-lookup"><span data-stu-id="39177-113">Instead, each definition of a structure represents a unique data type, even if two structures define identical elements in the same order.</span></span> <span data-ttu-id="39177-114">Wenn Sie jedoch zwei oder mehr Instanzen derselben Struktur erstellen, Visual Basic Sie als denselben Datentyp betrachtet.</span><span class="sxs-lookup"><span data-stu-id="39177-114">However, if you create two or more instances of the same structure, Visual Basic considers them to be of the same data type.</span></span>  
  
## <a name="tuples"></a><span data-ttu-id="39177-115">Tupel</span><span class="sxs-lookup"><span data-stu-id="39177-115">Tuples</span></span>

<span data-ttu-id="39177-116">Ein Tupel ist eine vereinfachte Struktur, die zwei oder mehr Felder enthält, deren Typen vordefiniert sind.</span><span class="sxs-lookup"><span data-stu-id="39177-116">A tuple is a lightweight structure that contains two or more fields whose types are predefined.</span></span> <span data-ttu-id="39177-117">Tupel werden ab Visual Basic 2017 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="39177-117">Tuples are supported starting with Visual Basic 2017.</span></span> <span data-ttu-id="39177-118">Tupel werden am häufigsten verwendet, um mehrere Werte aus einem einzelnen Methoden aufzurufen, ohne Argumente als Verweis übergeben oder die zurückgegebenen Felder in einer höheren Klasse oder Struktur Verpacken zu müssen.</span><span class="sxs-lookup"><span data-stu-id="39177-118">Tuples are most commonly used to return multiple values from a single method call without having to pass arguments by reference or packaging the returned fields in a more heavy-weight class or structure.</span></span> <span data-ttu-id="39177-119">Weitere Informationen zu Tupeln finden Sie im Thema [Tupel](tuples.md) .</span><span class="sxs-lookup"><span data-stu-id="39177-119">See the [Tuples](tuples.md) topic for more information on tuples.</span></span>

## <a name="array-types"></a><span data-ttu-id="39177-120">Array Typen</span><span class="sxs-lookup"><span data-stu-id="39177-120">Array Types</span></span>  
 <span data-ttu-id="39177-121">Es gibt keinen einzelnen Datentyp, der alle Arrays umfasst.</span><span class="sxs-lookup"><span data-stu-id="39177-121">There is no single data type comprising all arrays.</span></span> <span data-ttu-id="39177-122">Der Datentyp einer bestimmten Instanz eines Arrays wird durch Folgendes bestimmt:</span><span class="sxs-lookup"><span data-stu-id="39177-122">The data type of a particular instance of an array is determined by the following:</span></span>  
  
- <span data-ttu-id="39177-123">Die Tatsache, dass es sich um ein Array handelt</span><span class="sxs-lookup"><span data-stu-id="39177-123">The fact of being an array</span></span>  
  
- <span data-ttu-id="39177-124">Der Rang (Anzahl der Dimensionen) des Arrays.</span><span class="sxs-lookup"><span data-stu-id="39177-124">The rank (number of dimensions) of the array</span></span>  
  
- <span data-ttu-id="39177-125">Der Elementtyp des Arrays.</span><span class="sxs-lookup"><span data-stu-id="39177-125">The element type of the array</span></span>  
  
 <span data-ttu-id="39177-126">Insbesondere die Länge einer bestimmten Dimension ist nicht Teil des Datentyps der-Instanz.</span><span class="sxs-lookup"><span data-stu-id="39177-126">In particular, the length of a given dimension is not part of the instance's data type.</span></span> <span data-ttu-id="39177-127">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="39177-127">The following example illustrates this.</span></span>  
  
```vb  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 <span data-ttu-id="39177-128">Im vorherigen Beispiel werden Array Variablen `arrayA` und `arrayB` als denselben Datentyp – `Byte()` –, auch wenn Sie mit unterschiedlichen Längen initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="39177-128">In the preceding example, array variables `arrayA` and `arrayB` are considered to be of the same data type — `Byte()` — even though they are initialized to different lengths.</span></span> <span data-ttu-id="39177-129">Variablen `arrayB` und weisen `arrayC` nicht denselben Typ auf, da deren Elementtypen unterschiedlich sind.</span><span class="sxs-lookup"><span data-stu-id="39177-129">Variables `arrayB` and `arrayC` are not of the same type because their element types are different.</span></span> <span data-ttu-id="39177-130">Variablen `arrayC` und weisen `arrayD` nicht denselben Typ auf, da sich ihre Ränge unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="39177-130">Variables `arrayC` and `arrayD` are not of the same type because their ranks are different.</span></span> <span data-ttu-id="39177-131">Variablen `arrayD` und `arrayE` haben denselben Typ – `Short(,)` –, weil ihre Ränge und Elementtypen identisch sind, obwohl `arrayD` noch nicht initialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="39177-131">Variables `arrayD` and `arrayE` have the same type — `Short(,)` — because their ranks and element types are the same, even though `arrayD` is not yet initialized.</span></span>  
  
 <span data-ttu-id="39177-132">Weitere Informationen zu Arrays finden Sie unter [Arrays](../arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="39177-132">For more information on arrays, see [Arrays](../arrays/index.md).</span></span>  
  
## <a name="class-types"></a><span data-ttu-id="39177-133">Klassentypen</span><span class="sxs-lookup"><span data-stu-id="39177-133">Class Types</span></span>  
 <span data-ttu-id="39177-134">Es gibt keinen einzelnen Datentyp, der alle Klassen umfasst.</span><span class="sxs-lookup"><span data-stu-id="39177-134">There is no single data type comprising all classes.</span></span> <span data-ttu-id="39177-135">Obwohl eine Klasse von einer anderen Klasse erben kann, handelt es sich bei jedem um einen separaten Datentyp.</span><span class="sxs-lookup"><span data-stu-id="39177-135">Although one class can inherit from another class, each is a separate data type.</span></span> <span data-ttu-id="39177-136">Mehrere Instanzen derselben Klasse weisen denselben Datentyp auf.</span><span class="sxs-lookup"><span data-stu-id="39177-136">Multiple instances of the same class are of the same data type.</span></span> <span data-ttu-id="39177-137">Wenn Sie eine Klasseninstanzvariable einem anderen zuweisen, nicht nur denselben Datentyp haben, zeigen Sie auf dieselbe Klasseninstanz im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="39177-137">If you assign one class instance variable to another, not only do they have the same data type, they point to the same class instance in memory.</span></span>  
  
 <span data-ttu-id="39177-138">Weitere Informationen zu-Klassen finden Sie unter [Objekte und Klassen](../objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="39177-138">For more information on classes, see [Objects and Classes](../objects-and-classes/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39177-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="39177-139">See also</span></span>

- [<span data-ttu-id="39177-140">Datentypen</span><span class="sxs-lookup"><span data-stu-id="39177-140">Data Types</span></span>](index.md)
- [<span data-ttu-id="39177-141">Elementare Datentypen</span><span class="sxs-lookup"><span data-stu-id="39177-141">Elementary Data Types</span></span>](elementary-data-types.md)
- [<span data-ttu-id="39177-142">Generische Typen in Visual Basic (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39177-142">Generic Types in Visual Basic</span></span>](generic-types.md)
- [<span data-ttu-id="39177-143">Wert- und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="39177-143">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="39177-144">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="39177-144">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="39177-145">Strukturen</span><span class="sxs-lookup"><span data-stu-id="39177-145">Structures</span></span>](structures.md)
- [<span data-ttu-id="39177-146">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="39177-146">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="39177-147">Vorgehensweise: Ablegen mehrerer Werte in einer Variablen</span><span class="sxs-lookup"><span data-stu-id="39177-147">How to: Hold More Than One Value in a Variable</span></span>](how-to-hold-more-than-one-value-in-a-variable.md)
