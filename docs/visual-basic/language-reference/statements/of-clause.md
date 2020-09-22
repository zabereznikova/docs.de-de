---
title: Of-Klausel
ms.date: 07/20/2015
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
ms.openlocfilehash: 0595356fb75fc0ac73a49622d71fe1d28fa7b648
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90865907"
---
# <a name="of-clause-visual-basic"></a><span data-ttu-id="862bc-102">Of-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="862bc-102">Of Clause (Visual Basic)</span></span>

<span data-ttu-id="862bc-103">Führt eine- `Of` Klausel ein, die einen *Typparameter* für eine *generische* Klasse, Struktur, Schnittstelle, einen Delegaten oder eine Prozedur bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="862bc-103">Introduces an `Of` clause, which identifies a *type parameter* on a *generic* class, structure, interface, delegate, or procedure.</span></span> <span data-ttu-id="862bc-104">Informationen zu generischen Typen finden Sie unter [generische Typen in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="862bc-104">For information on generic types, see [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).</span></span>  
  
## <a name="using-the-of-keyword"></a><span data-ttu-id="862bc-105">Verwenden des of-Schlüssel Worts</span><span class="sxs-lookup"><span data-stu-id="862bc-105">Using the Of Keyword</span></span>  

 <span data-ttu-id="862bc-106">Im folgenden Codebeispiel wird das- `Of` Schlüsselwort verwendet, um die Gliederung einer Klasse zu definieren, die zwei Typparameter annimmt.</span><span class="sxs-lookup"><span data-stu-id="862bc-106">The following code example uses the `Of` keyword to define the outline of a class that takes two type parameters.</span></span> <span data-ttu-id="862bc-107">Der *constrains* - `keyType` Parameter wird von der- <xref:System.IComparable> Schnittstelle eingeschränkt, was bedeutet, dass der verarbeitende Code ein Typargument bereitstellen muss, das implementiert <xref:System.IComparable> .</span><span class="sxs-lookup"><span data-stu-id="862bc-107">It *constrains* the `keyType` parameter by the <xref:System.IComparable> interface, which means the consuming code must supply a type argument that implements <xref:System.IComparable>.</span></span> <span data-ttu-id="862bc-108">Dies ist erforderlich, damit die- `add` Prozedur die-Methode aufgerufen werden kann <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="862bc-108">This is necessary so that the `add` procedure can call the <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="862bc-109">Weitere Informationen über Einschränkungen finden Sie unter [Type List](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="862bc-109">For more information on constraints, see [Type List](type-list.md).</span></span>  
  
```vb  
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
  
 <span data-ttu-id="862bc-110">Wenn Sie die vorherige Klassendefinition Fertigstellen, können Sie eine Vielzahl von `dictionary` Klassen daraus erstellen.</span><span class="sxs-lookup"><span data-stu-id="862bc-110">If you complete the preceding class definition, you can construct a variety of `dictionary` classes from it.</span></span> <span data-ttu-id="862bc-111">Die Typen, die Sie angeben, `entryType` und `keyType` bestimmen, welche Art von Eintrag die Klasse enthält und welche Art von Schlüssel Sie den einzelnen Einträgen zuordnet.</span><span class="sxs-lookup"><span data-stu-id="862bc-111">The types you supply to `entryType` and `keyType` determine what type of entry the class holds and what type of key it associates with each entry.</span></span> <span data-ttu-id="862bc-112">Aufgrund der-Einschränkung müssen Sie `keyType` einen Typ angeben, der implementiert <xref:System.IComparable> .</span><span class="sxs-lookup"><span data-stu-id="862bc-112">Because of the constraint, you must supply to `keyType` a type that implements <xref:System.IComparable>.</span></span>  
  
 <span data-ttu-id="862bc-113">Im folgenden Codebeispiel wird ein-Objekt erstellt, das `String` -Einträge enthält und `Integer` jedem jeweils einen Schlüssel zuordnet.</span><span class="sxs-lookup"><span data-stu-id="862bc-113">The following code example creates an object that holds `String` entries and associates an `Integer` key with each one.</span></span> <span data-ttu-id="862bc-114">`Integer` implementiert <xref:System.IComparable> und erfüllt daher die Einschränkung für `keyType` .</span><span class="sxs-lookup"><span data-stu-id="862bc-114">`Integer` implements <xref:System.IComparable> and therefore satisfies the constraint on `keyType`.</span></span>  
  
```vb  
Dim d As New dictionary(Of String, Integer)  
```  
  
 <span data-ttu-id="862bc-115">Das `Of`-Schlüsselwort kann in den folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="862bc-115">The `Of` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="862bc-116">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="862bc-116">Class Statement</span></span>](class-statement.md)  
  
 [<span data-ttu-id="862bc-117">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="862bc-117">Delegate Statement</span></span>](delegate-statement.md)  
  
 [<span data-ttu-id="862bc-118">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="862bc-118">Function Statement</span></span>](function-statement.md)  
  
 [<span data-ttu-id="862bc-119">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="862bc-119">Interface Statement</span></span>](interface-statement.md)  
  
 [<span data-ttu-id="862bc-120">Structure Statement</span><span class="sxs-lookup"><span data-stu-id="862bc-120">Structure Statement</span></span>](structure-statement.md)  
  
 [<span data-ttu-id="862bc-121">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="862bc-121">Sub Statement</span></span>](sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="862bc-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="862bc-122">See also</span></span>

- <xref:System.IComparable>
- [<span data-ttu-id="862bc-123">Type List</span><span class="sxs-lookup"><span data-stu-id="862bc-123">Type List</span></span>](type-list.md)
- [<span data-ttu-id="862bc-124">Generische Typen in Visual Basic (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="862bc-124">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="862bc-125">In</span><span class="sxs-lookup"><span data-stu-id="862bc-125">In</span></span>](../modifiers/in-generic-modifier.md)
- [<span data-ttu-id="862bc-126">aus</span><span class="sxs-lookup"><span data-stu-id="862bc-126">Out</span></span>](../modifiers/out-generic-modifier.md)
