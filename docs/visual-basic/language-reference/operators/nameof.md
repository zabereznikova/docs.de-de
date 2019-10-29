---
title: Nameof-Operator-Visual Basic
description: Erfahren Sie, wie Sie den nameof-Operator in Visual Basic
ms.date: 10/27/2019
helpviewer_keywords:
- NameOf operator [Visual Basic]
ms.openlocfilehash: 8416bb1a1715c1c37b62cac6a9e0b427a9c72547
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73041352"
---
# <a name="nameof-operator---visual-basic"></a><span data-ttu-id="ea862-103">Nameof-Operator-Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ea862-103">NameOf operator - Visual Basic</span></span>

<span data-ttu-id="ea862-104">Der Operator `NameOf` ruft den Namen einer Variablen, eines Typs oder eines Members als Zeichenfolgenkonstante ab:</span><span class="sxs-lookup"><span data-stu-id="ea862-104">The `NameOf` operator obtains the name of a variable, type, or member as the string constant:</span></span>

```vb
Console.WriteLine(NameOf(System.Collections.Generic))  ' output: Generic
Console.WriteLine(NameOf(List(Of Integer)))  ' output: List
Console.WriteLine(NameOf(List(Of Integer).Count))  ' output: Count
Console.WriteLine(NameOf(List(Of Integer).Add))  ' output: Add

Dim numbers As New List(Of Integer) From { 1, 2, 3 }
Console.WriteLine(NameOf(numbers))  ' output: numbers
Console.WriteLine(NameOf(numbers.Count))  ' output: Count
Console.WriteLine(NameOf(numbers.Add))  ' output: Add
```

<span data-ttu-id="ea862-105">Im Falle eines Typs und eines Namespace ist der erzeugte Name in der Regel nicht [vollqualifiziert](~/_csharplang/spec/basic-concepts.md#fully-qualified-names), wie im obigen Beispiel zu sehen.</span><span class="sxs-lookup"><span data-stu-id="ea862-105">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="ea862-106">Der Operator `NameOf` wird zur Kompilierzeit ausgewertet und hat zur Laufzeit keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="ea862-106">The `NameOf` operator is evaluated at compile time, and has no effect at run time.</span></span>

<span data-ttu-id="ea862-107">Der Operator `NameOf` kann zur besseren Verwaltbarkeit des Argumentüberprüfungscodes beitragen:</span><span class="sxs-lookup"><span data-stu-id="ea862-107">You can use the `NameOf` operator to make the argument-checking code more maintainable:</span></span>

```vb
Private _name As String

Public Property Name As String
    Get
        Return _name
    End Get
    Set
        If value Is Nothing Then
            Throw New ArgumentNullException(NameOf(value), $"{NameOf(name)} cannot be null.")
        End If
    End Set
End Property
```

<span data-ttu-id="ea862-108">Der `NameOf`-Operator ist in Visual Basic 14 und höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ea862-108">The `NameOf` operator is available in Visual Basic 14 and later.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea862-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea862-109">See also</span></span>

- [<span data-ttu-id="ea862-110">Sprachreferenz zu Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ea862-110">Visual Basic Language Reference</span></span>](../index.md)
- [<span data-ttu-id="ea862-111">Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea862-111">Operators (Visual Basic)</span></span>](index.md)
