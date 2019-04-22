---
title: Den benutzerdefinierten Datentyp (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- UserDefined
- UDT
- vb.UDT
- User-Defined
- vb.UserDefined
- vb.User-Defined
helpviewer_keywords:
- user-defined data types [Visual Basic], Visual Basic
- user-defined types
- structures [Visual Basic], as user-defined data types
- user-defined types [Visual Basic], Visual Basic
- user-defined types [Visual Basic], structure declaration
- user-defined types [Visual Basic], structures in Visual Basic
- user-defined data types [Visual Basic], structure declaration
- data types [Visual Basic], assigning
- Structure statement [Visual Basic]
- data types [Visual Basic], user-defined
- user-defined data types [Visual Basic], structures in Visual Basic
- user-defined data types
- types [Visual Basic], user-defined
ms.assetid: be913dca-a364-4a51-96a1-549a1b390b0a
ms.openlocfilehash: 5fe12d18c7f403c1a50ed548a260ba39e83280eb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58814197"
---
# <a name="user-defined-data-type"></a><span data-ttu-id="1ede2-102">Benutzerdefinierter Datentyp</span><span class="sxs-lookup"><span data-stu-id="1ede2-102">User-Defined Data Type</span></span>
<span data-ttu-id="1ede2-103">Enthält Daten in einem Format, die Sie definieren.</span><span class="sxs-lookup"><span data-stu-id="1ede2-103">Holds data in a format you define.</span></span> <span data-ttu-id="1ede2-104">Die `Structure` -Anweisung definiert das Format.</span><span class="sxs-lookup"><span data-stu-id="1ede2-104">The `Structure` statement defines the format.</span></span>  
  
 <span data-ttu-id="1ede2-105">Frühere Versionen von Visual Basic unterstützt den benutzerdefinierten Typ (UDT).</span><span class="sxs-lookup"><span data-stu-id="1ede2-105">Previous versions of Visual Basic support the user-defined type (UDT).</span></span> <span data-ttu-id="1ede2-106">Die aktuelle Version erweitert den UDT einen *Struktur*.</span><span class="sxs-lookup"><span data-stu-id="1ede2-106">The current version expands the UDT to a *structure*.</span></span> <span data-ttu-id="1ede2-107">Eine Struktur ist eine Verkettung aus einem oder mehreren *Mitglieder* verschiedener Datentypen.</span><span class="sxs-lookup"><span data-stu-id="1ede2-107">A structure is a concatenation of one or more *members* of various data types.</span></span> <span data-ttu-id="1ede2-108">Visual Basic behandelt eine Struktur als einzelne Einheit, jedoch auch einzeln seine Member zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="1ede2-108">Visual Basic treats a structure as a single unit, although you can also access its members individually.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ede2-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1ede2-109">Remarks</span></span>  
 <span data-ttu-id="1ede2-110">Definieren Sie und verwenden Sie einen Datentyp für die Struktur aus, wenn verschiedene Datentypen in einer einzigen Einheit kombiniert werden sollen, oder wenn keines der elementare Datentypen Ihre Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="1ede2-110">Define and use a structure data type when you need to combine various data types into a single unit, or when none of the elementary data types serve your needs.</span></span>  
  
 <span data-ttu-id="1ede2-111">Der Standardwert eines Datentyps für die Struktur besteht aus der Kombination der Standardwerte der einzelnen Elemente.</span><span class="sxs-lookup"><span data-stu-id="1ede2-111">The default value of a structure data type consists of the combination of the default values of each of its members.</span></span>  
  
## <a name="declaration-format"></a><span data-ttu-id="1ede2-112">Deklaration-Format</span><span class="sxs-lookup"><span data-stu-id="1ede2-112">Declaration Format</span></span>  
 <span data-ttu-id="1ede2-113">Eine Structure-Deklaration beginnt mit der [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md) und endet mit dem `End Structure` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="1ede2-113">A structure declaration starts with the [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) and ends with the `End Structure` statement.</span></span> <span data-ttu-id="1ede2-114">Die `Structure` -Anweisung gibt den Namen der Struktur, die auch der Bezeichner des Datentyps ist, wird die Struktur definiert.</span><span class="sxs-lookup"><span data-stu-id="1ede2-114">The `Structure` statement supplies the name of the structure, which is also the identifier of the data type the structure is defining.</span></span> <span data-ttu-id="1ede2-115">Andere Teile des Codes können diesen Bezeichner verwenden, um zu deklarieren, dass die Variablen, Parameter und Funktion Rückgabewerte von dieser Struktur den Datentyp.</span><span class="sxs-lookup"><span data-stu-id="1ede2-115">Other parts of the code can use this identifier to declare variables, parameters, and function return values to be of this structure's data type.</span></span>  
  
 <span data-ttu-id="1ede2-116">Die Deklarationen zwischen der `Structure` und `End Structure` Anweisungen definieren, die Member der Struktur.</span><span class="sxs-lookup"><span data-stu-id="1ede2-116">The declarations between the `Structure` and `End Structure` statements define the members of the structure.</span></span>  
  
## <a name="member-access-levels"></a><span data-ttu-id="1ede2-117">Zugriffsebenen für Member</span><span class="sxs-lookup"><span data-stu-id="1ede2-117">Member Access Levels</span></span>  
 <span data-ttu-id="1ede2-118">Deklarieren Sie jeden Member mit einem [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md) oder eine Anweisung, die Zugriffsebene, wie z. B. angibt [öffentliche](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), oder [Private](../../../visual-basic/language-reference/modifiers/private.md).</span><span class="sxs-lookup"><span data-stu-id="1ede2-118">You must declare every member using a [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) or a statement that specifies access level, such as [Public](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../visual-basic/language-reference/modifiers/private.md).</span></span> <span data-ttu-id="1ede2-119">Bei Verwendung einer `Dim` -Anweisung, die als Zugriffsebene standardmäßig öffentlich.</span><span class="sxs-lookup"><span data-stu-id="1ede2-119">If you use a `Dim` statement, the access level defaults to public.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="1ede2-120">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="1ede2-120">Programming Tips</span></span>  
  
-   <span data-ttu-id="1ede2-121">**Die Arbeitsspeichernutzung.**</span><span class="sxs-lookup"><span data-stu-id="1ede2-121">**Memory Consumption.**</span></span> <span data-ttu-id="1ede2-122">Wie bei allen zusammengesetzten Datentypen können Sie den gesamten Speicherverbrauch auch bei Strukturen nicht dadurch zuverlässig berechnen, indem Sie die nominalen Speicherbelegungen ihrer Member addieren.</span><span class="sxs-lookup"><span data-stu-id="1ede2-122">As with all composite data types, you cannot safely calculate the total memory consumption of a structure by adding together the nominal storage allocations of its members.</span></span> <span data-ttu-id="1ede2-123">Darüber hinaus können Sie nicht davon ausgehen, dass die Member im Speicher in derselben Reihenfolge wie in der Deklaration angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="1ede2-123">Furthermore, you cannot safely assume that the order of storage in memory is the same as your order of declaration.</span></span> <span data-ttu-id="1ede2-124">Wenn Sie das Speicherlayout einer Struktur steuern müssen, können Sie das <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut auf die `Structure`-Anweisung anwenden.</span><span class="sxs-lookup"><span data-stu-id="1ede2-124">If you need to control the storage layout of a structure, you can apply the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute to the `Structure` statement.</span></span>  
  
-   <span data-ttu-id="1ede2-125">**Interop-Überlegungen.**</span><span class="sxs-lookup"><span data-stu-id="1ede2-125">**Interop Considerations.**</span></span> <span data-ttu-id="1ede2-126">Wenn die Komponenten, die nicht für .NET Framework geschrieben wurden verbunden sind, strukturieren z. B. Automatisierungs- oder COM-Objekte, denken Sie daran, dass benutzerdefinierte Typen in anderen Umgebungen nicht kompatibel mit Visual Basic sind Typen.</span><span class="sxs-lookup"><span data-stu-id="1ede2-126">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that user-defined types in other environments are not compatible with Visual Basic structure types.</span></span>  
  
-   <span data-ttu-id="1ede2-127">**Erweiternde.**</span><span class="sxs-lookup"><span data-stu-id="1ede2-127">**Widening.**</span></span> <span data-ttu-id="1ede2-128">Es ist keine automatische Konvertierung zu oder von beliebigen Datentyps der Struktur.</span><span class="sxs-lookup"><span data-stu-id="1ede2-128">There is no automatic conversion to or from any structure data type.</span></span> <span data-ttu-id="1ede2-129">Sie können die Konvertierungsoperatoren definieren, bei der Struktur mit der [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md), und Sie können jeden Konvertierungsoperator sein deklarieren `Widening` oder `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="1ede2-129">You can define conversion operators on your structure using the [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md), and you can declare each conversion operator to be `Widening` or `Narrowing`.</span></span>  
  
-   <span data-ttu-id="1ede2-130">**Typzeichen.**</span><span class="sxs-lookup"><span data-stu-id="1ede2-130">**Type Characters.**</span></span> <span data-ttu-id="1ede2-131">Struktur-Datentypen haben keine literal-Typzeichen oder Bezeichner-Typzeichen.</span><span class="sxs-lookup"><span data-stu-id="1ede2-131">Structure data types have no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="1ede2-132">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="1ede2-132">**Framework Type.**</span></span> <span data-ttu-id="1ede2-133">Es gibt keinen entsprechenden Typ in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1ede2-133">There is no corresponding type in the .NET Framework.</span></span> <span data-ttu-id="1ede2-134">Alle Strukturen erben von der .NET Framework-Klasse <xref:System.ValueType?displayProperty=nameWithType>, aber keine einzelne Struktur entspricht <xref:System.ValueType?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1ede2-134">All structures inherit from the .NET Framework class <xref:System.ValueType?displayProperty=nameWithType>, but no individual structure corresponds to <xref:System.ValueType?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ede2-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ede2-135">Example</span></span>  
 <span data-ttu-id="1ede2-136">Das folgende Beispiel zeigt die Gliederung der Deklaration einer Struktur.</span><span class="sxs-lookup"><span data-stu-id="1ede2-136">The following paradigm shows the outline of the declaration of a structure.</span></span>  
  
```  
[Public | Protected | Friend | Protected Friend | Private] Structure structname  
    {Dim | Public | Friend | Private} member1 As datatype1  
    ' ...  
    {Dim | Public | Friend | Private} memberN As datatypeN  
End Structure  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ede2-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ede2-137">See also</span></span>

- <xref:System.ValueType>
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- [<span data-ttu-id="1ede2-138">Datentypen</span><span class="sxs-lookup"><span data-stu-id="1ede2-138">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="1ede2-139">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="1ede2-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="1ede2-140">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="1ede2-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="1ede2-141">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1ede2-141">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="1ede2-142">Widening</span><span class="sxs-lookup"><span data-stu-id="1ede2-142">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="1ede2-143">Narrowing</span><span class="sxs-lookup"><span data-stu-id="1ede2-143">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="1ede2-144">Strukturen</span><span class="sxs-lookup"><span data-stu-id="1ede2-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="1ede2-145">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="1ede2-145">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
