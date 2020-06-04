---
title: Benutzerdefinierter Datentyp
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
ms.openlocfilehash: fbd9536a54d7fb471d6cb2e130b14a84e40a4940
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415491"
---
# <a name="user-defined-data-type"></a><span data-ttu-id="6ca66-102">Benutzerdefinierter Datentyp</span><span class="sxs-lookup"><span data-stu-id="6ca66-102">User-Defined Data Type</span></span>

<span data-ttu-id="6ca66-103">Enthält Daten in einem Format, das Sie definieren.</span><span class="sxs-lookup"><span data-stu-id="6ca66-103">Holds data in a format you define.</span></span> <span data-ttu-id="6ca66-104">Die- `Structure` Anweisung definiert das Format.</span><span class="sxs-lookup"><span data-stu-id="6ca66-104">The `Structure` statement defines the format.</span></span>

<span data-ttu-id="6ca66-105">In früheren Versionen von Visual Basic wird der benutzerdefinierte Typ (User-Defined Type, UDT) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6ca66-105">Previous versions of Visual Basic support the user-defined type (UDT).</span></span> <span data-ttu-id="6ca66-106">Die aktuelle Version erweitert den UDT in eine- *Struktur*.</span><span class="sxs-lookup"><span data-stu-id="6ca66-106">The current version expands the UDT to a *structure*.</span></span> <span data-ttu-id="6ca66-107">Eine Struktur ist eine Verkettung von einem *oder mehreren Membern verschiedener Daten* Typen.</span><span class="sxs-lookup"><span data-stu-id="6ca66-107">A structure is a concatenation of one or more *members* of various data types.</span></span> <span data-ttu-id="6ca66-108">Visual Basic behandelt eine Struktur als eine Einheit, obwohl Sie auch einzeln auf die Member zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="6ca66-108">Visual Basic treats a structure as a single unit, although you can also access its members individually.</span></span>

## <a name="remarks"></a><span data-ttu-id="6ca66-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6ca66-109">Remarks</span></span>

<span data-ttu-id="6ca66-110">Definieren und verwenden Sie einen Structure-Datentyp, wenn Sie verschiedene Datentypen in einer einzelnen Einheit kombinieren müssen, oder wenn keiner der elementaren Datentypen Ihren Anforderungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="6ca66-110">Define and use a structure data type when you need to combine various data types into a single unit, or when none of the elementary data types serve your needs.</span></span>

<span data-ttu-id="6ca66-111">Der Standardwert eines Structure-Datentyps besteht aus der Kombination der Standardwerte der einzelnen Member.</span><span class="sxs-lookup"><span data-stu-id="6ca66-111">The default value of a structure data type consists of the combination of the default values of each of its members.</span></span>

## <a name="declaration-format"></a><span data-ttu-id="6ca66-112">Deklarations Format</span><span class="sxs-lookup"><span data-stu-id="6ca66-112">Declaration Format</span></span>

<span data-ttu-id="6ca66-113">Eine Struktur Deklaration beginnt mit der [Structure-Anweisung](../statements/structure-statement.md) und endet mit der- `End Structure` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="6ca66-113">A structure declaration starts with the [Structure Statement](../statements/structure-statement.md) and ends with the `End Structure` statement.</span></span> <span data-ttu-id="6ca66-114">Die- `Structure` Anweisung gibt den Namen der Struktur an, die auch der Bezeichner des Datentyps ist, den die Struktur definiert.</span><span class="sxs-lookup"><span data-stu-id="6ca66-114">The `Structure` statement supplies the name of the structure, which is also the identifier of the data type the structure is defining.</span></span> <span data-ttu-id="6ca66-115">Andere Teile des Codes können diesen Bezeichner verwenden, um Variablen, Parameter und Funktions Rückgabewerte für den Datentyp dieser Struktur zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="6ca66-115">Other parts of the code can use this identifier to declare variables, parameters, and function return values to be of this structure's data type.</span></span>

<span data-ttu-id="6ca66-116">Die Deklarationen zwischen der `Structure` -Anweisung und der- `End Structure` Anweisung definieren die Member der-Struktur.</span><span class="sxs-lookup"><span data-stu-id="6ca66-116">The declarations between the `Structure` and `End Structure` statements define the members of the structure.</span></span>

## <a name="member-access-levels"></a><span data-ttu-id="6ca66-117">Mitglieds Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="6ca66-117">Member Access Levels</span></span>

<span data-ttu-id="6ca66-118">Sie müssen jeden Member mithilfe einer [Dim-Anweisung](../statements/dim-statement.md) oder einer-Anweisung, die die Zugriffsebene angibt, wie z. b. [Public](../modifiers/public.md), [Friend](../modifiers/friend.md)oder [private](../modifiers/private.md), deklarieren.</span><span class="sxs-lookup"><span data-stu-id="6ca66-118">You must declare every member using a [Dim Statement](../statements/dim-statement.md) or a statement that specifies access level, such as [Public](../modifiers/public.md), [Friend](../modifiers/friend.md), or [Private](../modifiers/private.md).</span></span> <span data-ttu-id="6ca66-119">Wenn Sie eine- `Dim` Anweisung verwenden, ist die Zugriffsebene standardmäßig auf Public eingestellt.</span><span class="sxs-lookup"><span data-stu-id="6ca66-119">If you use a `Dim` statement, the access level defaults to public.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="6ca66-120">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="6ca66-120">Programming Tips</span></span>

- <span data-ttu-id="6ca66-121">**Arbeitsspeicher Nutzung.**</span><span class="sxs-lookup"><span data-stu-id="6ca66-121">**Memory Consumption.**</span></span> <span data-ttu-id="6ca66-122">Wie bei allen zusammengesetzten Datentypen können Sie den gesamten Speicherverbrauch auch bei Strukturen nicht dadurch zuverlässig berechnen, indem Sie die nominalen Speicherbelegungen ihrer Member addieren.</span><span class="sxs-lookup"><span data-stu-id="6ca66-122">As with all composite data types, you cannot safely calculate the total memory consumption of a structure by adding together the nominal storage allocations of its members.</span></span> <span data-ttu-id="6ca66-123">Darüber hinaus können Sie nicht davon ausgehen, dass die Member im Speicher in derselben Reihenfolge wie in der Deklaration angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="6ca66-123">Furthermore, you cannot safely assume that the order of storage in memory is the same as your order of declaration.</span></span> <span data-ttu-id="6ca66-124">Wenn Sie das Speicherlayout einer Struktur steuern müssen, können Sie das <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut auf die `Structure`-Anweisung anwenden.</span><span class="sxs-lookup"><span data-stu-id="6ca66-124">If you need to control the storage layout of a structure, you can apply the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute to the `Structure` statement.</span></span>

- <span data-ttu-id="6ca66-125">**Interop-Überlegungen.**</span><span class="sxs-lookup"><span data-stu-id="6ca66-125">**Interop Considerations.**</span></span> <span data-ttu-id="6ca66-126">Wenn Sie mit Komponenten verbunden sind, die nicht für die .NET Framework geschrieben wurden (z. b. Automatisierungs-oder COM-Objekte), beachten Sie, dass benutzerdefinierte Typen in anderen Umgebungen nicht mit Visual Basic Strukturtypen kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="6ca66-126">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that user-defined types in other environments are not compatible with Visual Basic structure types.</span></span>

- <span data-ttu-id="6ca66-127">**Tet.**</span><span class="sxs-lookup"><span data-stu-id="6ca66-127">**Widening.**</span></span> <span data-ttu-id="6ca66-128">Es gibt keine automatische Konvertierung in oder aus einem Struktur Datentyp.</span><span class="sxs-lookup"><span data-stu-id="6ca66-128">There is no automatic conversion to or from any structure data type.</span></span> <span data-ttu-id="6ca66-129">Mithilfe der [Operator-Anweisung](../statements/operator-statement.md)können Sie Konvertierungs Operatoren für die Struktur definieren, und Sie können jeden Konvertierungs Operator als oder deklarieren `Widening` `Narrowing` .</span><span class="sxs-lookup"><span data-stu-id="6ca66-129">You can define conversion operators on your structure using the [Operator Statement](../statements/operator-statement.md), and you can declare each conversion operator to be `Widening` or `Narrowing`.</span></span>

- <span data-ttu-id="6ca66-130">**Geben Sie Zeichen ein.**</span><span class="sxs-lookup"><span data-stu-id="6ca66-130">**Type Characters.**</span></span> <span data-ttu-id="6ca66-131">Struktur Datentypen haben kein Literaltyp Zeichen oder Bezeichnertyp Zeichen.</span><span class="sxs-lookup"><span data-stu-id="6ca66-131">Structure data types have no literal type character or identifier type character.</span></span>

- <span data-ttu-id="6ca66-132">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="6ca66-132">**Framework Type.**</span></span> <span data-ttu-id="6ca66-133">In der .NET Framework ist kein entsprechender Typ vorhanden.</span><span class="sxs-lookup"><span data-stu-id="6ca66-133">There is no corresponding type in the .NET Framework.</span></span> <span data-ttu-id="6ca66-134">Alle-Strukturen erben von der .NET Framework-Klasse <xref:System.ValueType?displayProperty=nameWithType> , aber keine einzelne Struktur entspricht <xref:System.ValueType?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="6ca66-134">All structures inherit from the .NET Framework class <xref:System.ValueType?displayProperty=nameWithType>, but no individual structure corresponds to <xref:System.ValueType?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="6ca66-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6ca66-135">Example</span></span>

<span data-ttu-id="6ca66-136">Das folgende Paradigma zeigt den Umriss der Deklaration einer-Struktur.</span><span class="sxs-lookup"><span data-stu-id="6ca66-136">The following paradigm shows the outline of the declaration of a structure.</span></span>

```vb
[Public | Protected | Friend | Protected Friend | Private] Structure structname
    {Dim | Public | Friend | Private} member1 As datatype1
    ' ...
    {Dim | Public | Friend | Private} memberN As datatypeN
End Structure
```

## <a name="see-also"></a><span data-ttu-id="6ca66-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6ca66-137">See also</span></span>

- <xref:System.ValueType>
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- [<span data-ttu-id="6ca66-138">Datentypen</span><span class="sxs-lookup"><span data-stu-id="6ca66-138">Data Types</span></span>](index.md)
- [<span data-ttu-id="6ca66-139">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="6ca66-139">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="6ca66-140">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="6ca66-140">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="6ca66-141">Structure Statement</span><span class="sxs-lookup"><span data-stu-id="6ca66-141">Structure Statement</span></span>](../statements/structure-statement.md)
- [<span data-ttu-id="6ca66-142">Widening</span><span class="sxs-lookup"><span data-stu-id="6ca66-142">Widening</span></span>](../modifiers/widening.md)
- [<span data-ttu-id="6ca66-143">Narrowing</span><span class="sxs-lookup"><span data-stu-id="6ca66-143">Narrowing</span></span>](../modifiers/narrowing.md)
- [<span data-ttu-id="6ca66-144">Strukturen</span><span class="sxs-lookup"><span data-stu-id="6ca66-144">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="6ca66-145">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="6ca66-145">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
