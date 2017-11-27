---
title: Of-Klausel (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- Of
- vb.Of
- vb.of
helpviewer_keywords:
- Of keyword [Visual Basic]
- arguments [Visual Basic], data types
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
ms.assetid: 0db8f65c-65af-4089-ab7f-6fcfecb60444
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5ef3ac4ac88727b1dcae50fa14abde03f29a16fb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="of-clause-visual-basic"></a><span data-ttu-id="3299b-102">Of-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3299b-102">Of Clause (Visual Basic)</span></span>
<span data-ttu-id="3299b-103">Führt eine `Of` -Klausel, die identifiziert eine *Typparameter* auf eine *generischen* -Klasse, Struktur, Schnittstelle, Delegat oder Prozedur.</span><span class="sxs-lookup"><span data-stu-id="3299b-103">Introduces an `Of` clause, which identifies a *type parameter* on a *generic* class, structure, interface, delegate, or procedure.</span></span> <span data-ttu-id="3299b-104">Informationen zu generischen Typen finden Sie unter [generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="3299b-104">For information on generic types, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span>  
  
## <a name="using-the-of-keyword"></a><span data-ttu-id="3299b-105">Mit dem Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="3299b-105">Using the Of Keyword</span></span>  
 <span data-ttu-id="3299b-106">Im folgenden Codebeispiel wird mit der `Of` Schlüsselwort, um den Umriss einer Klasse definieren, die zwei Typparameter erhält.</span><span class="sxs-lookup"><span data-stu-id="3299b-106">The following code example uses the `Of` keyword to define the outline of a class that takes two type parameters.</span></span> <span data-ttu-id="3299b-107">Es *schränkt* der `keyType` Parameters, indem die <xref:System.IComparable> -Schnittstelle, d. h., der verwendete Code ein Typargument, das implementiert angeben muss <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="3299b-107">It *constrains* the `keyType` parameter by the <xref:System.IComparable> interface, which means the consuming code must supply a type argument that implements <xref:System.IComparable>.</span></span> <span data-ttu-id="3299b-108">Dies ist erforderlich, damit die `add` Prozeduraufruf können die <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="3299b-108">This is necessary so that the `add` procedure can call the <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="3299b-109">Weitere Informationen zu Einschränkungen finden Sie unter [Typliste](../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="3299b-109">For more information on constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
```  
Public Class Dictionary(Of entryType, keyType As IComparable)  
    Public Sub add(ByVal e As entryType, ByVal k As keyType)  
        Dim dk As keyType  
        If k.CompareTo(dk) = 0 Then  
        End If  
    End Sub  
    Public Function find(ByVal k As keyType) As entryType  
    End Function  
End Class  
```  
  
 <span data-ttu-id="3299b-110">Wenn Sie die vorangehende Klassendefinition abgeschlossen haben, können Sie eine Vielzahl von erstellen `dictionary` Klassen daraus.</span><span class="sxs-lookup"><span data-stu-id="3299b-110">If you complete the preceding class definition, you can construct a variety of `dictionary` classes from it.</span></span> <span data-ttu-id="3299b-111">Die Typen, die Sie, um angeben `entryType` und `keyType` zu bestimmen, welche Art des Eintrags die Klasse enthält, und welche Art von Schlüssel dieser mit jeder Eintrag verknüpft.</span><span class="sxs-lookup"><span data-stu-id="3299b-111">The types you supply to `entryType` and `keyType` determine what type of entry the class holds and what type of key it associates with each entry.</span></span> <span data-ttu-id="3299b-112">Aufgrund der Einschränkung müssen Sie angeben `keyType` ein Typ, der implementiert <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="3299b-112">Because of the constraint, you must supply to `keyType` a type that implements <xref:System.IComparable>.</span></span>  
  
 <span data-ttu-id="3299b-113">Das folgende Codebeispiel erstellt ein Objekt, das enthält `String` Einträge und ordnet eine `Integer` mit den einzelnen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="3299b-113">The following code example creates an object that holds `String` entries and associates an `Integer` key with each one.</span></span> <span data-ttu-id="3299b-114">`Integer`implementiert <xref:System.IComparable> und erfüllt daher die Einschränkung auf `keyType`.</span><span class="sxs-lookup"><span data-stu-id="3299b-114">`Integer` implements <xref:System.IComparable> and therefore satisfies the constraint on `keyType`.</span></span>  
  
```  
Dim d As New dictionary(Of String, Integer)  
```  
  
 <span data-ttu-id="3299b-115">Das `Of`-Schlüsselwort kann in den folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="3299b-115">The `Of` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="3299b-116">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3299b-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="3299b-117">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3299b-117">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="3299b-118">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3299b-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="3299b-119">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3299b-119">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="3299b-120">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3299b-120">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="3299b-121">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3299b-121">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="3299b-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3299b-122">See Also</span></span>  
 <xref:System.IComparable>  
 [<span data-ttu-id="3299b-123">Typliste</span><span class="sxs-lookup"><span data-stu-id="3299b-123">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="3299b-124">Generische Typen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3299b-124">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="3299b-125">In</span><span class="sxs-lookup"><span data-stu-id="3299b-125">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [<span data-ttu-id="3299b-126">Out</span><span class="sxs-lookup"><span data-stu-id="3299b-126">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
