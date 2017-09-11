---
title: Erstellen von benutzerdefinierten Attributen (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 5c9ef584-6c7c-496b-92a9-6e42f8d9ca28
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
ms.openlocfilehash: fbfc3f84f6287d233d475f01869dab63b937a521
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="creating-custom-attributes-visual-basic"></a><span data-ttu-id="67a56-102">Erstellen von benutzerdefinierten Attributen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67a56-102">Creating Custom Attributes (Visual Basic)</span></span>
<span data-ttu-id="67a56-103">Sie können eigene benutzerdefinierte Attribute erstellen, durch die Definition einer Attributklasse, die eine Klasse, die direkt oder indirekt abgeleitet <xref:System.Attribute>, welche identifizieren Attributdefinitionen, die in den Metadaten, die schnell und einfach macht.</xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="67a56-103">You can create your own custom attributes by defining an attribute class, a class that derives directly or indirectly from <xref:System.Attribute>, which makes identifying attribute definitions in metadata fast and easy.</span></span> <span data-ttu-id="67a56-104">Angenommen Sie, Sie Tagtypen mit dem Namen des Programmierers, die den Typ erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="67a56-104">Suppose you want to tag types with the name of the programmer who wrote the type.</span></span> <span data-ttu-id="67a56-105">Sie definieren eine benutzerdefinierte `Author` Attributklasse:</span><span class="sxs-lookup"><span data-stu-id="67a56-105">You might define a custom `Author` attribute class:</span></span>  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct)>   
Public Class Author  
    Inherits System.Attribute  
    Private name As String  
    Public version As Double  
    Sub New(ByVal authorName As String)  
        name = authorName  
        version = 1.0  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="67a56-106">Der Klassenname ist der Attributname `Author`.</span><span class="sxs-lookup"><span data-stu-id="67a56-106">The class name is the attribute's name, `Author`.</span></span> <span data-ttu-id="67a56-107">Sie ist abgeleitet von `System.Attribute`, sodass eine benutzerdefinierte Attributklasse.</span><span class="sxs-lookup"><span data-stu-id="67a56-107">It is derived from `System.Attribute`, so it is a custom attribute class.</span></span> <span data-ttu-id="67a56-108">Die Parameter des Konstruktors sind Positionsparameter des benutzerdefinierten Attributs.</span><span class="sxs-lookup"><span data-stu-id="67a56-108">The constructor's parameters are the custom attribute's positional parameters.</span></span> <span data-ttu-id="67a56-109">In diesem Beispiel `name` ist ein Positionsparameter.</span><span class="sxs-lookup"><span data-stu-id="67a56-109">In this example, `name` is a positional parameter.</span></span> <span data-ttu-id="67a56-110">Alle öffentlichen Schreib-Lese-Felder oder Eigenschaften sind benannte Parameter.</span><span class="sxs-lookup"><span data-stu-id="67a56-110">Any public read-write fields or properties are named parameters.</span></span> <span data-ttu-id="67a56-111">In diesem Fall `version` ist der einzige benannte Parameter.</span><span class="sxs-lookup"><span data-stu-id="67a56-111">In this case, `version` is the only named parameter.</span></span> <span data-ttu-id="67a56-112">Beachten Sie, dass die `AttributeUsage` -Attribut der `Author` Attribut gilt nur für die Klasse und `Structure` Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="67a56-112">Note the use of the `AttributeUsage` attribute to make the `Author` attribute valid only on class and `Structure` declarations.</span></span>  
  
 <span data-ttu-id="67a56-113">Sie könnten dieses neue Attribut wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="67a56-113">You could use this new attribute as follows:</span></span>  
  
```vb  
<Author("P. Ackerman", Version:=1.1)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
End Class  
```  
  
 <span data-ttu-id="67a56-114">`AttributeUsage`hat einen benannten Parameter, `AllowMultiple`, mit denen Sie ein benutzerdefiniertes Attribut einfache oder mehrfache Verwendung konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="67a56-114">`AttributeUsage` has a named parameter, `AllowMultiple`, with which you can make a custom attribute single-use or multiuse.</span></span> <span data-ttu-id="67a56-115">Im folgenden Codebeispiel wird ein mehrfach verwendbares Attribut erstellt.</span><span class="sxs-lookup"><span data-stu-id="67a56-115">In the following code example, a multiuse attribute is created.</span></span>  
  
```vb  
' multiuse attribute  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct,   
                       AllowMultiple:=True)>   
Public Class Author  
    Inherits System.Attribute  
```  
  
 <span data-ttu-id="67a56-116">Im folgenden Codebeispiel werden mehrere Attribute desselben Typs auf eine Klasse angewendet.</span><span class="sxs-lookup"><span data-stu-id="67a56-116">In the following code example, multiple attributes of the same type are applied to a class.</span></span>  
  
```vb  
<Author("P. Ackerman", Version:=1.1),   
Author("R. Koch", Version:=1.2)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
    ' R. Koch's code goes here...  
End Class  
```  
  
> [!NOTE]
>  <span data-ttu-id="67a56-117">Wenn die Attributklasse eine Eigenschaft enthält, muss die Eigenschaft Lese-/ Schreibzugriff sein.</span><span class="sxs-lookup"><span data-stu-id="67a56-117">If your attribute class contains a property, that property must be read-write.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67a56-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67a56-118">See Also</span></span>  
 <span data-ttu-id="67a56-119"><xref:System.Reflection></xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="67a56-119"><xref:System.Reflection></span></span>   
<span data-ttu-id="67a56-120"> [Visual Basic-Programmierhandbuch](../../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="67a56-120"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="67a56-121"> [Verfassen von benutzerdefinierten Attributen](http://msdn.microsoft.com/library/97216f69-bde8-49fd-ac40-f18c500ef5dc) </span><span class="sxs-lookup"><span data-stu-id="67a56-121"> [Writing Custom Attributes](http://msdn.microsoft.com/library/97216f69-bde8-49fd-ac40-f18c500ef5dc) </span></span>  
<span data-ttu-id="67a56-122"> [Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="67a56-122"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span></span>  
<span data-ttu-id="67a56-123"> [Attribute (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span><span class="sxs-lookup"><span data-stu-id="67a56-123"> [Attributes (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span></span>  
<span data-ttu-id="67a56-124"> [Zugriff auf Attribute mit Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) </span><span class="sxs-lookup"><span data-stu-id="67a56-124"> [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) </span></span>  
<span data-ttu-id="67a56-125"> [AttributeUsage (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)</span><span class="sxs-lookup"><span data-stu-id="67a56-125"> [AttributeUsage (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)</span></span>
