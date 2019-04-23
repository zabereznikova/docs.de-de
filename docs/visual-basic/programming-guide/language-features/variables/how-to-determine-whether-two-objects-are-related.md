---
title: 'Vorgehensweise: Bestimmen, ob zwei Objekten zwischen Bezugs (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: f59e00d80d28fc4bf24874d25b5c12643649c834
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342101"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a><span data-ttu-id="9bffc-102">Vorgehensweise: Bestimmen, ob zwei Objekten zwischen Bezugs (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9bffc-102">How to: Determine Whether Two Objects Are Related (Visual Basic)</span></span>
<span data-ttu-id="9bffc-103">Sie können vergleichen zwei Objekte, um die Beziehung zwischen den Klassen ggf. zu bestimmen, von dem sie erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9bffc-103">You can compare two objects to determine the relationship, if any, between the classes from which they are created.</span></span> <span data-ttu-id="9bffc-104">Die <xref:System.Type.IsInstanceOfType%2A> Methode der <xref:System.Type?displayProperty=nameWithType> -Klasse gibt `True` , wenn die angegebene Klasse von der aktuellen Klasse erbt oder der aktuelle Typ eine Schnittstelle, unterstützt durch die angegebene Klasse ist.</span><span class="sxs-lookup"><span data-stu-id="9bffc-104">The <xref:System.Type.IsInstanceOfType%2A> method of the <xref:System.Type?displayProperty=nameWithType> class returns `True` if the specified class inherits from the current class, or if the current type is an interface supported by the specified class.</span></span>  
  
### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a><span data-ttu-id="9bffc-105">Um festzustellen, ob ein Objekt von einem anderen Objekt der Klasse oder Schnittstelle erbt</span><span class="sxs-lookup"><span data-stu-id="9bffc-105">To determine if one object inherits from another object's class or interface</span></span>  
  
1. <span data-ttu-id="9bffc-106">Für das Objekt, das Sie denken des Basistyps, rufen Sie die <xref:System.Object.GetType%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="9bffc-106">On the object you think might be of the base type, invoke the <xref:System.Object.GetType%2A> method.</span></span>  
  
2. <span data-ttu-id="9bffc-107">Auf der <xref:System.Type?displayProperty=nameWithType> zurückgegebenes Objekt <xref:System.Object.GetType%2A>, rufen Sie die <xref:System.Type.IsInstanceOfType%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="9bffc-107">On the <xref:System.Type?displayProperty=nameWithType> object returned by <xref:System.Object.GetType%2A>, invoke the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>  
  
3. <span data-ttu-id="9bffc-108">In der Argumentliste für <xref:System.Type.IsInstanceOfType%2A>, geben Sie das Objekt, das Sie denken möglicherweise des abgeleiteten Typs.</span><span class="sxs-lookup"><span data-stu-id="9bffc-108">In the argument list for <xref:System.Type.IsInstanceOfType%2A>, specify the object you think might be of the derived type.</span></span>  
  
     <span data-ttu-id="9bffc-109"><xref:System.Type.IsInstanceOfType%2A> Gibt `True` Falls Argumenttyps erbt die <xref:System.Type?displayProperty=nameWithType> Objekttyp.</span><span class="sxs-lookup"><span data-stu-id="9bffc-109"><xref:System.Type.IsInstanceOfType%2A> returns `True` if its argument type inherits from the <xref:System.Type?displayProperty=nameWithType> object type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bffc-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9bffc-110">Example</span></span>  
 <span data-ttu-id="9bffc-111">Im folgende Beispiel wird bestimmt, ob ein Objekt eine von einer anderen Klasse abgeleitete Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="9bffc-111">The following example determines whether one object represents a class derived from another object's class.</span></span>  
  
```  
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
  
 <span data-ttu-id="9bffc-112">Beachten Sie die unerwartete Platzierung der zwei Variablen im Aufruf von <xref:System.Type.IsInstanceOfType%2A>.</span><span class="sxs-lookup"><span data-stu-id="9bffc-112">Note the unexpected placement of the two object variables in the call to <xref:System.Type.IsInstanceOfType%2A>.</span></span> <span data-ttu-id="9bffc-113">Der angenommene Basistyp dient zum Generieren der <xref:System.Type?displayProperty=nameWithType> -Klasse, und der angenommene abgeleitete Typ wird als Argument für das Übergeben der <xref:System.Type.IsInstanceOfType%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="9bffc-113">The supposed base type is used to generate the <xref:System.Type?displayProperty=nameWithType> class, and the supposed derived type is passed as an argument to the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bffc-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9bffc-114">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [<span data-ttu-id="9bffc-115">Object-Datentyp</span><span class="sxs-lookup"><span data-stu-id="9bffc-115">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="9bffc-116">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="9bffc-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="9bffc-117">Werte von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="9bffc-117">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="9bffc-118">Vorgehensweise: Bestimmt, ob zwei Objekte identisch sind.</span><span class="sxs-lookup"><span data-stu-id="9bffc-118">How to: Determine Whether Two Objects Are Identical</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
