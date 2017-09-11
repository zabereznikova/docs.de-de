---
title: AttributeUsage (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 48757216-c21d-4051-86d5-8a3e03c39d2c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c91f2686a03d2590e1aaf166d27c49744bb13c9b
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="attributeusage-visual-basic"></a><span data-ttu-id="bb758-102">AttributeUsage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb758-102">AttributeUsage (Visual Basic)</span></span>
<span data-ttu-id="bb758-103">Bestimmt, wie eine benutzerdefinierte Attributklasse verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="bb758-103">Determines how a custom attribute class can be used.</span></span> <span data-ttu-id="bb758-104">`AttributeUsage`ist ein Attribut, die angewendet werden kann, um benutzerdefinierte Attributdefinitionen zu steuern, wie das neue Attribut angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="bb758-104">`AttributeUsage` is an attribute that can be applied to custom attribute definitions to control how the new attribute can be applied.</span></span> <span data-ttu-id="bb758-105">Die Standardeinstellungen aussehen wie folgt, wenn Sie explizit angewendet:</span><span class="sxs-lookup"><span data-stu-id="bb758-105">The default settings look like this when applied explicitly:</span></span>  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.All,   
                   AllowMultiple:=False,   
                   Inherited:=True)>   
Class NewAttribute  
    Inherits System.Attribute  
End Class  
```  
  
 <span data-ttu-id="bb758-106">In diesem Beispiel die `NewAttribute` -Klasse kann auf jede Codeentität Attribut kann angewendet, aber kann nur einmal für jede Entität angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="bb758-106">In this example, the `NewAttribute` class can be applied to any attribute-able code entity, but can be applied only once to each entity.</span></span> <span data-ttu-id="bb758-107">Es wird von abgeleiteten Klassen bei Anwendung auf eine Basisklasse geerbt.</span><span class="sxs-lookup"><span data-stu-id="bb758-107">It is inherited by derived classes when applied to a base class.</span></span>  
  
 <span data-ttu-id="bb758-108">Die `AllowMultiple` und `Inherited` Argumente sind optional, damit dieser Code die gleiche Wirkung hat:</span><span class="sxs-lookup"><span data-stu-id="bb758-108">The `AllowMultiple` and `Inherited` arguments are optional, so this code has the same effect:</span></span>  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.All)>   
Class NewAttribute  
    Inherits System.Attribute  
End Class  
```  
  
 <span data-ttu-id="bb758-109">Die erste `AttributeUsage` Argument muss ein oder mehrere Elemente von der <xref:System.AttributeTargets>-Enumeration.</xref:System.AttributeTargets></span><span class="sxs-lookup"><span data-stu-id="bb758-109">The first `AttributeUsage` argument must be one or more elements of the <xref:System.AttributeTargets> enumeration.</span></span> <span data-ttu-id="bb758-110">Mehrere Zieltypen können zusammen mit dem OR-Operator, wie folgt verknüpft:</span><span class="sxs-lookup"><span data-stu-id="bb758-110">Multiple target types can be linked together with the OR operator, like this:</span></span>  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Property Or AttributeTargets.Field)>   
Class NewPropertyOrFieldAttribute  
    Inherits Attribute  
End Class  
```  
  
 <span data-ttu-id="bb758-111">Wenn die `AllowMultiple` Argument auf festgelegt ist `true`, und klicken Sie dann das resultierende Attribut mehr als einmal kann, können Sie für eine einzelne Entität, wie folgt angewendet werden:</span><span class="sxs-lookup"><span data-stu-id="bb758-111">If the `AllowMultiple` argument is set to `true`, then the resulting attribute can be applied more than once to a single entity, like this:</span></span>  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Class, AllowMultiple:=True)>   
Class MultiUseAttr  
    Inherits Attribute  
End Class  
  
<MultiUseAttr(), MultiUseAttr()>   
Class Class1  
End Class  
```  
  
 <span data-ttu-id="bb758-112">In diesem Fall `MultiUseAttr` kann mehrmals angewendet werden, da `AllowMultiple` Wert `true`.</span><span class="sxs-lookup"><span data-stu-id="bb758-112">In this case `MultiUseAttr` can be applied repeatedly because `AllowMultiple` is set to `true`.</span></span> <span data-ttu-id="bb758-113">Beide Formate wie für das Anwenden von mehreren Attributen sind gültig.</span><span class="sxs-lookup"><span data-stu-id="bb758-113">Both formats shown for applying multiple attributes are valid.</span></span>  
  
 <span data-ttu-id="bb758-114">Wenn `Inherited` Wert `false`, und klicken Sie dann das Attribut nicht von Klassen geerbt wird, die von einer Klasse abgeleitet werden, die zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="bb758-114">If `Inherited` is set to `false`, then the attribute is not inherited by classes that are derived from a class that is attributed.</span></span> <span data-ttu-id="bb758-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bb758-115">For example:</span></span>  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Class, Inherited:=False)>   
Class Attr1  
    Inherits Attribute  
End Class  
  
<Attr1()>   
Class BClass  
  
End Class    
  
Class DClass  
    Inherits BClass  
End Class  
```  
  
 <span data-ttu-id="bb758-116">In diesem Fall `Attr1` gilt nicht für `DClass` über Vererbung.</span><span class="sxs-lookup"><span data-stu-id="bb758-116">In this case `Attr1` is not applied to `DClass` via inheritance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb758-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bb758-117">Remarks</span></span>  
 <span data-ttu-id="bb758-118">Das `AttributeUsage` -Attribut ist ein Attribut – es kann nicht auf die gleiche Klasse mehr als einmal angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="bb758-118">The `AttributeUsage` attribute is a single-use attribute--it cannot be applied more than once to the same class.</span></span> <span data-ttu-id="bb758-119">`AttributeUsage`ist ein Alias für <xref:System.AttributeUsageAttribute>.</xref:System.AttributeUsageAttribute></span><span class="sxs-lookup"><span data-stu-id="bb758-119">`AttributeUsage` is an alias for <xref:System.AttributeUsageAttribute>.</span></span>  
  
 <span data-ttu-id="bb758-120">Weitere Informationen finden Sie unter [Zugriff auf Attribute mithilfe von Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="bb758-120">For more information, see [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb758-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bb758-121">Example</span></span>  
 <span data-ttu-id="bb758-122">Das folgende Beispiel zeigt die Auswirkung der `Inherited` und `AllowMultiple` Argumente für die `AttributeUsage` -Attribut, und wie die benutzerdefinierten Attribute auf eine Klasse angewendet aufgelistet werden können.</span><span class="sxs-lookup"><span data-stu-id="bb758-122">The following example demonstrates the effect of the `Inherited` and `AllowMultiple` arguments to the `AttributeUsage` attribute, and how the custom attributes applied to a class can be enumerated.</span></span>  
  
```vb  
Imports System  
```  
  
```vb  
' Create some custom attributes:  
<AttributeUsage(System.AttributeTargets.Class, Inherited:=False)>   
Class A1  
    Inherits System.Attribute  
End Class  
  
<AttributeUsage(System.AttributeTargets.Class)>   
Class A2  
    Inherits System.Attribute  
End Class      
  
<AttributeUsage(System.AttributeTargets.Class, AllowMultiple:=True)>   
Class A3  
    Inherits System.Attribute  
End Class  
  
' Apply custom attributes to classes:  
<A1(), A2()>   
Class BaseClass  
  
End Class  
  
<A3(), A3()>   
Class DerivedClass  
    Inherits BaseClass  
End Class  
  
Public Class TestAttributeUsage  
    Sub Main()  
        Dim b As New BaseClass  
        Dim d As New DerivedClass  
        ' Display custom attributes for each class.  
        Console.WriteLine("Attributes on Base Class:")  
        Dim attrs() As Object = b.GetType().GetCustomAttributes(True)  
  
        For Each attr In attrs  
            Console.WriteLine(attr)  
        Next  
  
        Console.WriteLine("Attributes on Derived Class:")  
        attrs = d.GetType().GetCustomAttributes(True)  
        For Each attr In attrs  
            Console.WriteLine(attr)  
        Next              
    End Sub  
End Class  
```  
  
## <a name="sample-output"></a><span data-ttu-id="bb758-123">Beispielausgabe</span><span class="sxs-lookup"><span data-stu-id="bb758-123">Sample Output</span></span>  
  
```  
Attributes on Base Class:  
A1  
A2  
Attributes on Derived Class:  
A3  
A3  
A2  
```  
  
## <a name="see-also"></a><span data-ttu-id="bb758-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb758-124">See Also</span></span>  
 <span data-ttu-id="bb758-125"><xref:System.Attribute></xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="bb758-125"><xref:System.Attribute></span></span>   
 <span data-ttu-id="bb758-126"><xref:System.Reflection></xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="bb758-126"><xref:System.Reflection></span></span>   
<span data-ttu-id="bb758-127"> [Visual Basic-Programmierhandbuch](../../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bb758-127"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="bb758-128"> [Attribute](https://msdn.microsoft.com/library/5x6cd29c) </span><span class="sxs-lookup"><span data-stu-id="bb758-128"> [Attributes](https://msdn.microsoft.com/library/5x6cd29c) </span></span>  
<span data-ttu-id="bb758-129"> [Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="bb758-129"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span></span>  
<span data-ttu-id="bb758-130"> [Attribute (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span><span class="sxs-lookup"><span data-stu-id="bb758-130"> [Attributes (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span></span>  
<span data-ttu-id="bb758-131"> [Erstellen von benutzerdefinierten Attributen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="bb758-131"> [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) </span></span>  
<span data-ttu-id="bb758-132"> [Zugriff auf Attribute mit Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span><span class="sxs-lookup"><span data-stu-id="bb758-132"> [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span></span>
