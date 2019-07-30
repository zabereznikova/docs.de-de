---
title: 'Vorgehensweise: Bestimmen, ob zwei Objekte verwandt sind (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: 2b17be4ef5a7dabfc4779ab6f5675cc2baec9c3c
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626558"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a><span data-ttu-id="d20ac-102">Vorgehensweise: Bestimmen, ob zwei Objekte verwandt sind (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d20ac-102">How to: Determine Whether Two Objects Are Related (Visual Basic)</span></span>

<span data-ttu-id="d20ac-103">Sie können zwei-Objekte vergleichen, um die Beziehung (sofern vorhanden) zwischen den Klassen zu bestimmen, von denen Sie erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d20ac-103">You can compare two objects to determine the relationship, if any, between the classes from which they are created.</span></span> <span data-ttu-id="d20ac-104">Die <xref:System.Type.IsInstanceOfType%2A> -Methode <xref:System.Type?displayProperty=nameWithType> der-Klasse `True` gibt zurück, wenn die angegebene Klasse von der aktuellen Klasse erbt, oder, wenn der aktuelle Typ eine Schnittstelle ist, die von der angegebenen Klasse unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="d20ac-104">The <xref:System.Type.IsInstanceOfType%2A> method of the <xref:System.Type?displayProperty=nameWithType> class returns `True` if the specified class inherits from the current class, or if the current type is an interface supported by the specified class.</span></span>

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a><span data-ttu-id="d20ac-105">So bestimmen Sie, ob ein Objekt von der Klasse oder Schnittstelle eines anderen Objekts erbt</span><span class="sxs-lookup"><span data-stu-id="d20ac-105">To determine if one object inherits from another object's class or interface</span></span>

1. <span data-ttu-id="d20ac-106">Rufen Sie für das Objekt, das Sie als Basistyp betrachten können, <xref:System.Object.GetType%2A> die-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="d20ac-106">On the object you think might be of the base type, invoke the <xref:System.Object.GetType%2A> method.</span></span>

2. <span data-ttu-id="d20ac-107">Rufen Sie <xref:System.Type?displayProperty=nameWithType> für das von <xref:System.Object.GetType%2A>zurückgegebene- <xref:System.Type.IsInstanceOfType%2A> Objekt die-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="d20ac-107">On the <xref:System.Type?displayProperty=nameWithType> object returned by <xref:System.Object.GetType%2A>, invoke the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>

3. <span data-ttu-id="d20ac-108">Geben Sie in der Argument <xref:System.Type.IsInstanceOfType%2A>Liste für das Objekt an, das Sie möglicherweise vom abgeleiteten Typ haben.</span><span class="sxs-lookup"><span data-stu-id="d20ac-108">In the argument list for <xref:System.Type.IsInstanceOfType%2A>, specify the object you think might be of the derived type.</span></span>

    <span data-ttu-id="d20ac-109"><xref:System.Type.IsInstanceOfType%2A>gibt `True` zurück, wenn der <xref:System.Type?displayProperty=nameWithType> Argumenttyp vom Objekttyp erbt.</span><span class="sxs-lookup"><span data-stu-id="d20ac-109"><xref:System.Type.IsInstanceOfType%2A> returns `True` if its argument type inherits from the <xref:System.Type?displayProperty=nameWithType> object type.</span></span>

## <a name="example"></a><span data-ttu-id="d20ac-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d20ac-110">Example</span></span>
 <span data-ttu-id="d20ac-111">Im folgenden Beispiel wird bestimmt, ob ein-Objekt eine Klasse darstellt, die von der Klasse eines anderen Objekts abgeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="d20ac-111">The following example determines whether one object represents a class derived from another object's class.</span></span>

```vb
Public Class baseClass
End Class
Public Class derivedClass : Inherits baseClass
End Class
Public Class testTheseClasses
    Public Sub seeIfRelated()
        Dim baseObj As Object = New baseClass()
        Dim derivedObj As Object = New derivedClass()
        Dim related As Boolean
        related = baseObj.GetType().IsInstanceOfType(derivedObj)
        MsgBox(CStr(related))
    End Sub
End Class
```

<span data-ttu-id="d20ac-112">Beachten Sie die unerwartete Platzierung der beiden Objektvariablen im <xref:System.Type.IsInstanceOfType%2A>-Befehl.</span><span class="sxs-lookup"><span data-stu-id="d20ac-112">Note the unexpected placement of the two object variables in the call to <xref:System.Type.IsInstanceOfType%2A>.</span></span> <span data-ttu-id="d20ac-113">Der vermeintliche Basistyp wird verwendet, um die <xref:System.Type?displayProperty=nameWithType> -Klasse zu generieren, und der vermeintliche abgeleitete Typ wird als Argument <xref:System.Type.IsInstanceOfType%2A> an die-Methode übermittelt.</span><span class="sxs-lookup"><span data-stu-id="d20ac-113">The supposed base type is used to generate the <xref:System.Type?displayProperty=nameWithType> class, and the supposed derived type is passed as an argument to the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>

## <a name="see-also"></a><span data-ttu-id="d20ac-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d20ac-114">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [<span data-ttu-id="d20ac-115">Object-Datentyp</span><span class="sxs-lookup"><span data-stu-id="d20ac-115">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="d20ac-116">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="d20ac-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="d20ac-117">Werte von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="d20ac-117">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="d20ac-118">Vorgehensweise: Bestimmen, ob zwei Objekte identisch sind</span><span class="sxs-lookup"><span data-stu-id="d20ac-118">How to: Determine Whether Two Objects Are Identical</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
