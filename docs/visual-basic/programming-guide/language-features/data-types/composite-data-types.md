---
title: Zusammengesetzte Datentypen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types
- composite data types
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures, composite data types
- classes [Visual Basic], composite types
- types [Visual Basic], composite
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 5f0c6215ce45d724a7b5c8c4f8e34ea27bce8fe4
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="composite-data-types-visual-basic"></a><span data-ttu-id="9e379-102">Zusammengesetzte Datentypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e379-102">Composite Data Types (Visual Basic)</span></span>
<span data-ttu-id="9e379-103">Zusätzlich zu den elementare Datentypen [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] bereitstellt, können Sie auch Elemente unterschiedlichen Typs erstellen zusammenstellen *zusammengesetzte Datentypen* wie Strukturen, Arrays und Klassen.</span><span class="sxs-lookup"><span data-stu-id="9e379-103">In addition to the elementary data types [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] supplies, you can also assemble items of different types to create *composite data types* such as structures, arrays, and classes.</span></span> <span data-ttu-id="9e379-104">Sie können zusammengesetzte Datentypen aus elementaren Typen und aus anderen zusammengesetzten Typen erstellen.</span><span class="sxs-lookup"><span data-stu-id="9e379-104">You can build composite data types from elementary types and from other composite types.</span></span> <span data-ttu-id="9e379-105">Beispielsweise können Sie ein Array von Strukturelementen oder eine Struktur mit Array-Elemente definieren.</span><span class="sxs-lookup"><span data-stu-id="9e379-105">For example, you can define an array of structure elements, or a structure with array members.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="9e379-106">Datentypen</span><span class="sxs-lookup"><span data-stu-id="9e379-106">Data Types</span></span>  
 <span data-ttu-id="9e379-107">Ein zusammengesetzter Typ unterscheidet sich von dem Datentyp seiner Komponenten.</span><span class="sxs-lookup"><span data-stu-id="9e379-107">A composite type is different from the data type of any of its components.</span></span> <span data-ttu-id="9e379-108">Angenommen, ein Array von `Integer` Elemente ist nicht von der `Integer` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="9e379-108">For example, an array of `Integer` elements is not of the `Integer` data type.</span></span>  
  
 <span data-ttu-id="9e379-109">Datentyp eines Arrays wird normalerweise mithilfe von Elementtyp, Klammern und Kommas nach Bedarf dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9e379-109">An array data type is normally represented using the element type, parentheses, and commas as necessary.</span></span> <span data-ttu-id="9e379-110">Angenommen, ein eindimensionales Array von `String` wird `String()`, und ein zweidimensionales Array von `Boolean` wird `Boolean(,)`.</span><span class="sxs-lookup"><span data-stu-id="9e379-110">For example, a one-dimensional array of `String` elements is represented as `String()`, and a two-dimensional array of `Boolean` elements is represented as `Boolean(,)`.</span></span>  
  
## <a name="structure-types"></a><span data-ttu-id="9e379-111">Strukturtypen</span><span class="sxs-lookup"><span data-stu-id="9e379-111">Structure Types</span></span>  
 <span data-ttu-id="9e379-112">Es gibt keinen universellen Datentyp, der alle Strukturen umfasst.</span><span class="sxs-lookup"><span data-stu-id="9e379-112">There is no single data type comprising all structures.</span></span> <span data-ttu-id="9e379-113">Stattdessen stellt jede Definition einer Struktur einen eindeutigen Datentyp dar, auch wenn zwei Strukturen identischer Elemente in der gleichen Reihenfolge definieren.</span><span class="sxs-lookup"><span data-stu-id="9e379-113">Instead, each definition of a structure represents a unique data type, even if two structures define identical elements in the same order.</span></span> <span data-ttu-id="9e379-114">Jedoch, wenn Sie zwei oder mehr Instanzen dieselbe Struktur erstellen [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] berücksichtigt diese den gleichen Datentyp sein.</span><span class="sxs-lookup"><span data-stu-id="9e379-114">However, if you create two or more instances of the same structure, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] considers them to be of the same data type.</span></span>  
  
## <a name="array-types"></a><span data-ttu-id="9e379-115">Arraytypen</span><span class="sxs-lookup"><span data-stu-id="9e379-115">Array Types</span></span>  
 <span data-ttu-id="9e379-116">Es gibt keinen universellen Datentyp aller Arrays aus.</span><span class="sxs-lookup"><span data-stu-id="9e379-116">There is no single data type comprising all arrays.</span></span> <span data-ttu-id="9e379-117">Der Datentyp einer bestimmten Instanz eines Arrays wird durch Folgendes bestimmt:</span><span class="sxs-lookup"><span data-stu-id="9e379-117">The data type of a particular instance of an array is determined by the following:</span></span>  
  
-   <span data-ttu-id="9e379-118">Die Tatsache, dass ein array</span><span class="sxs-lookup"><span data-stu-id="9e379-118">The fact of being an array</span></span>  
  
-   <span data-ttu-id="9e379-119">Der Rang (Anzahl der Dimensionen) des Arrays</span><span class="sxs-lookup"><span data-stu-id="9e379-119">The rank (number of dimensions) of the array</span></span>  
  
-   <span data-ttu-id="9e379-120">Der Elementtyp des Arrays</span><span class="sxs-lookup"><span data-stu-id="9e379-120">The element type of the array</span></span>  
  
 <span data-ttu-id="9e379-121">Insbesondere ist die Länge einer bestimmten Dimension nicht Teil des Datentyps für die Instanz.</span><span class="sxs-lookup"><span data-stu-id="9e379-121">In particular, the length of a given dimension is not part of the instance's data type.</span></span> <span data-ttu-id="9e379-122">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9e379-122">The following example illustrates this.</span></span>  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 <span data-ttu-id="9e379-123">Im vorangehenden Beispiel Arrayvariablen `arrayA` und `arrayB` gelten die gleichen Datentyp – `Byte()` –, obwohl sie mit unterschiedlichen Längen initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="9e379-123">In the preceding example, array variables `arrayA` and `arrayB` are considered to be of the same data type — `Byte()` — even though they are initialized to different lengths.</span></span> <span data-ttu-id="9e379-124">Variablen `arrayB` und `arrayC` sind nicht vom gleichen Typ, da ihre Elementtypen unterschiedlich sind.</span><span class="sxs-lookup"><span data-stu-id="9e379-124">Variables `arrayB` and `arrayC` are not of the same type because their element types are different.</span></span> <span data-ttu-id="9e379-125">Variablen `arrayC` und `arrayD` sind nicht vom gleichen Typ, da ihre Ränge unterschiedlich sind.</span><span class="sxs-lookup"><span data-stu-id="9e379-125">Variables `arrayC` and `arrayD` are not of the same type because their ranks are different.</span></span> <span data-ttu-id="9e379-126">Variablen `arrayD` und `arrayE` denselben Typ haben – `Short(,)` , da ihre Ränge und Elementtypen identisch, obwohl sind `arrayD` wurde noch nicht initialisiert.</span><span class="sxs-lookup"><span data-stu-id="9e379-126">Variables `arrayD` and `arrayE` have the same type — `Short(,)` — because their ranks and element types are the same, even though `arrayD` is not yet initialized.</span></span>  
  
 <span data-ttu-id="9e379-127">Weitere Informationen zu Arrays finden Sie unter [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="9e379-127">For more information on arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="class-types"></a><span data-ttu-id="9e379-128">Klassentypen</span><span class="sxs-lookup"><span data-stu-id="9e379-128">Class Types</span></span>  
 <span data-ttu-id="9e379-129">Es gibt keinen universellen Datentyp, der alle Klassen umfasst.</span><span class="sxs-lookup"><span data-stu-id="9e379-129">There is no single data type comprising all classes.</span></span> <span data-ttu-id="9e379-130">Obwohl eine Klasse von einer anderen Klasse erben kann, ist jede ein separater Datentyp.</span><span class="sxs-lookup"><span data-stu-id="9e379-130">Although one class can inherit from another class, each is a separate data type.</span></span> <span data-ttu-id="9e379-131">Mehrere Instanzen derselben Klasse sind vom gleichen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="9e379-131">Multiple instances of the same class are of the same data type.</span></span> <span data-ttu-id="9e379-132">Wenn Sie eine Klassenvariable Instanz zu einem anderen zuweisen, werden nicht nur besitzen den gleichen Datentyp aufweisen, sie zeigen auf die gleiche Klasseninstanz im Speicher.</span><span class="sxs-lookup"><span data-stu-id="9e379-132">If you assign one class instance variable to another, not only do they have the same data type, they point to the same class instance in memory.</span></span>  
  
 <span data-ttu-id="9e379-133">Weitere Informationen über Klassen finden Sie unter [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="9e379-133">For more information on classes, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e379-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e379-134">See Also</span></span>  
 <span data-ttu-id="9e379-135">[Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="9e379-135">[Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="9e379-136"> [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="9e379-136"> [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
<span data-ttu-id="9e379-137"> [Generische Typen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span><span class="sxs-lookup"><span data-stu-id="9e379-137"> [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span></span>  
<span data-ttu-id="9e379-138"> [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="9e379-138"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="9e379-139"> [Typumwandlungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="9e379-139"> [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="9e379-140"> [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span><span class="sxs-lookup"><span data-stu-id="9e379-140"> [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span></span>  
<span data-ttu-id="9e379-141"> [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="9e379-141"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="9e379-142"> [Gewusst wie: Ablegen mehrerer Werte in einer Variablen](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)</span><span class="sxs-lookup"><span data-stu-id="9e379-142"> [How to: Hold More Than One Value in a Variable](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)</span></span>
