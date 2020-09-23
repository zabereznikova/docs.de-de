---
title: 'Vorgehensweise: Bestimmen des Bezugs zwischen zwei Objekten'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: b33815d58b0ef40f7f75a6a41bb4b1eeef591859
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072222"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a><span data-ttu-id="417ee-102">Gewusst wie: Bestimmen des Bezugs zwischen zwei Objekten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="417ee-102">How to: Determine Whether Two Objects Are Related (Visual Basic)</span></span>

<span data-ttu-id="417ee-103">Sie können zwei-Objekte vergleichen, um die Beziehung (sofern vorhanden) zwischen den Klassen zu bestimmen, von denen Sie erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="417ee-103">You can compare two objects to determine the relationship, if any, between the classes from which they are created.</span></span> <span data-ttu-id="417ee-104">Die- <xref:System.Type.IsInstanceOfType%2A> Methode der- <xref:System.Type?displayProperty=nameWithType> Klasse gibt zurück `True` , wenn die angegebene Klasse von der aktuellen Klasse erbt, oder, wenn der aktuelle Typ eine Schnittstelle ist, die von der angegebenen Klasse unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="417ee-104">The <xref:System.Type.IsInstanceOfType%2A> method of the <xref:System.Type?displayProperty=nameWithType> class returns `True` if the specified class inherits from the current class, or if the current type is an interface supported by the specified class.</span></span>

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a><span data-ttu-id="417ee-105">So bestimmen Sie, ob ein Objekt von der Klasse oder Schnittstelle eines anderen Objekts erbt</span><span class="sxs-lookup"><span data-stu-id="417ee-105">To determine if one object inherits from another object's class or interface</span></span>

1. <span data-ttu-id="417ee-106">Rufen Sie für das Objekt, das Sie als Basistyp betrachten können, die- <xref:System.Object.GetType%2A> Methode auf.</span><span class="sxs-lookup"><span data-stu-id="417ee-106">On the object you think might be of the base type, invoke the <xref:System.Object.GetType%2A> method.</span></span>

2. <span data-ttu-id="417ee-107">Rufen Sie für das <xref:System.Type?displayProperty=nameWithType> von zurückgegebene-Objekt <xref:System.Object.GetType%2A> die-Methode auf <xref:System.Type.IsInstanceOfType%2A> .</span><span class="sxs-lookup"><span data-stu-id="417ee-107">On the <xref:System.Type?displayProperty=nameWithType> object returned by <xref:System.Object.GetType%2A>, invoke the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>

3. <span data-ttu-id="417ee-108">Geben Sie in der Argumentliste für <xref:System.Type.IsInstanceOfType%2A> das Objekt an, das Sie möglicherweise vom abgeleiteten Typ haben.</span><span class="sxs-lookup"><span data-stu-id="417ee-108">In the argument list for <xref:System.Type.IsInstanceOfType%2A>, specify the object you think might be of the derived type.</span></span>

    <span data-ttu-id="417ee-109"><xref:System.Type.IsInstanceOfType%2A> Gibt zurück, `True` Wenn der Argumenttyp vom <xref:System.Type?displayProperty=nameWithType> Objekttyp erbt.</span><span class="sxs-lookup"><span data-stu-id="417ee-109"><xref:System.Type.IsInstanceOfType%2A> returns `True` if its argument type inherits from the <xref:System.Type?displayProperty=nameWithType> object type.</span></span>

## <a name="example"></a><span data-ttu-id="417ee-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="417ee-110">Example</span></span>

 <span data-ttu-id="417ee-111">Im folgenden Beispiel wird bestimmt, ob ein-Objekt eine Klasse darstellt, die von der Klasse eines anderen Objekts abgeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="417ee-111">The following example determines whether one object represents a class derived from another object's class.</span></span>

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

<span data-ttu-id="417ee-112">Beachten Sie die unerwartete Platzierung der beiden Objektvariablen im-Befehl <xref:System.Type.IsInstanceOfType%2A> .</span><span class="sxs-lookup"><span data-stu-id="417ee-112">Note the unexpected placement of the two object variables in the call to <xref:System.Type.IsInstanceOfType%2A>.</span></span> <span data-ttu-id="417ee-113">Der vermeintliche Basistyp wird verwendet, um die <xref:System.Type?displayProperty=nameWithType> -Klasse zu generieren, und der vermeintliche abgeleitete Typ wird als Argument an die-Methode übermittelt <xref:System.Type.IsInstanceOfType%2A> .</span><span class="sxs-lookup"><span data-stu-id="417ee-113">The supposed base type is used to generate the <xref:System.Type?displayProperty=nameWithType> class, and the supposed derived type is passed as an argument to the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>

## <a name="see-also"></a><span data-ttu-id="417ee-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="417ee-114">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [<span data-ttu-id="417ee-115">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="417ee-115">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="417ee-116">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="417ee-116">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="417ee-117">Werte von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="417ee-117">Object Variable Values</span></span>](object-variable-values.md)
- [<span data-ttu-id="417ee-118">Vorgehensweise: Bestimmen der Gleichheit zweier Objekte</span><span class="sxs-lookup"><span data-stu-id="417ee-118">How to: Determine Whether Two Objects Are Identical</span></span>](how-to-determine-whether-two-objects-are-identical.md)
