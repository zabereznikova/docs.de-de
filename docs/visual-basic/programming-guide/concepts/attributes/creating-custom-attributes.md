---
title: Erstellen von benutzerdefinierten Attributen (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c9ef584-6c7c-496b-92a9-6e42f8d9ca28
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7a24553ae4cc2186e805d76ddb37f38c0322aeac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="creating-custom-attributes-visual-basic"></a><span data-ttu-id="872ea-102">Erstellen von benutzerdefinierten Attributen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="872ea-102">Creating Custom Attributes (Visual Basic)</span></span>
<span data-ttu-id="872ea-103">Sie können eigene benutzerdefinierte Attribute erstellen, indem Sie eine Attributklasse definieren. Dies ist eine Klasse, die direkt oder indirekt von <xref:System.Attribute> abgeleitet wird, was es einfach macht, schnell Attributdefinitionen in Metadaten zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="872ea-103">You can create your own custom attributes by defining an attribute class, a class that derives directly or indirectly from <xref:System.Attribute>, which makes identifying attribute definitions in metadata fast and easy.</span></span> <span data-ttu-id="872ea-104">Angenommen, Sie möchten Typen mit dem Namen des Programmierers markieren, der den Typ geschrieben hat.</span><span class="sxs-lookup"><span data-stu-id="872ea-104">Suppose you want to tag types with the name of the programmer who wrote the type.</span></span> <span data-ttu-id="872ea-105">Sie definieren möglicherweise eine benutzerdefinierte `Author`-Attributklasse:</span><span class="sxs-lookup"><span data-stu-id="872ea-105">You might define a custom `Author` attribute class:</span></span>  
  
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
  
 <span data-ttu-id="872ea-106">Der Klassenname ist der Attributname, `Author`.</span><span class="sxs-lookup"><span data-stu-id="872ea-106">The class name is the attribute's name, `Author`.</span></span> <span data-ttu-id="872ea-107">Er ist von `System.Attribute` abgeleitet, ist also eine benutzerdefinierte Attributklasse.</span><span class="sxs-lookup"><span data-stu-id="872ea-107">It is derived from `System.Attribute`, so it is a custom attribute class.</span></span> <span data-ttu-id="872ea-108">Die Parameter des Konstruktors sind die Positionsparameter des benutzerdefinierten Attributs.</span><span class="sxs-lookup"><span data-stu-id="872ea-108">The constructor's parameters are the custom attribute's positional parameters.</span></span> <span data-ttu-id="872ea-109">In diesem Beispiel ist `name` ein Positionsparameter.</span><span class="sxs-lookup"><span data-stu-id="872ea-109">In this example, `name` is a positional parameter.</span></span> <span data-ttu-id="872ea-110">Alle öffentlichen Lese-/Schreibfelder oder -Eigenschaften werden Parameter genannt.</span><span class="sxs-lookup"><span data-stu-id="872ea-110">Any public read-write fields or properties are named parameters.</span></span> <span data-ttu-id="872ea-111">In diesem Fall ist `version` der einzige Parameter mit Namen.</span><span class="sxs-lookup"><span data-stu-id="872ea-111">In this case, `version` is the only named parameter.</span></span> <span data-ttu-id="872ea-112">Beachten Sie die Verwendung des `AttributeUsage`-Attributs, um das `Author`-Attribut ausschließlich für Klassen- und `Structure`-Deklarationen gültig zu machen.</span><span class="sxs-lookup"><span data-stu-id="872ea-112">Note the use of the `AttributeUsage` attribute to make the `Author` attribute valid only on class and `Structure` declarations.</span></span>  
  
 <span data-ttu-id="872ea-113">Sie könnten dieses neue Attribut wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="872ea-113">You could use this new attribute as follows:</span></span>  
  
```vb  
<Author("P. Ackerman", Version:=1.1)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
End Class  
```  
  
 <span data-ttu-id="872ea-114">`AttributeUsage` verfügt über einen Parameter, `AllowMultiple`, mit dem Sie ein benutzerdefiniertes Attribut zur einmaligen oder mehrfachen Nutzung erstellen können.</span><span class="sxs-lookup"><span data-stu-id="872ea-114">`AttributeUsage` has a named parameter, `AllowMultiple`, with which you can make a custom attribute single-use or multiuse.</span></span> <span data-ttu-id="872ea-115">Im folgenden Codebeispiel wird ein mehrfach verwendbares Attribut erstellt.</span><span class="sxs-lookup"><span data-stu-id="872ea-115">In the following code example, a multiuse attribute is created.</span></span>  
  
```vb  
' multiuse attribute  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct,   
                       AllowMultiple:=True)>   
Public Class Author  
    Inherits System.Attribute  
```  
  
 <span data-ttu-id="872ea-116">Im folgenden Codebeispiel werden mehrere Attribute desselben Typs auf eine Klasse angewendet.</span><span class="sxs-lookup"><span data-stu-id="872ea-116">In the following code example, multiple attributes of the same type are applied to a class.</span></span>  
  
```vb  
<Author("P. Ackerman", Version:=1.1),   
Author("R. Koch", Version:=1.2)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
    ' R. Koch's code goes here...  
End Class  
```  
  
> [!NOTE]
>  <span data-ttu-id="872ea-117">Wenn die Attributklasse eine Eigenschaft enthält, muss die Eigenschaft Lese- und Schreibberechtigung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="872ea-117">If your attribute class contains a property, that property must be read-write.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="872ea-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="872ea-118">See Also</span></span>  
 <xref:System.Reflection>  
 [<span data-ttu-id="872ea-119">Visual Basic-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="872ea-119">Visual Basic Programming Guide</span></span>](../../../../visual-basic/programming-guide/index.md)  
 [<span data-ttu-id="872ea-120">Verfassen von benutzerdefinierten Attributen</span><span class="sxs-lookup"><span data-stu-id="872ea-120">Writing Custom Attributes</span></span>](../../../../standard/attributes/writing-custom-attributes.md)  
 [<span data-ttu-id="872ea-121">Reflektion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="872ea-121">Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/reflection.md)  
 [<span data-ttu-id="872ea-122">Attribute (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="872ea-122">Attributes (Visual Basic)</span></span>](../../../../visual-basic/language-reference/attributes.md)  
 <span data-ttu-id="872ea-123">[Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) (Zugreifen auf Attribute mithilfe der Reflektion (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="872ea-123">[Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span></span>  
 [<span data-ttu-id="872ea-124">AttributeUsage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="872ea-124">AttributeUsage (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
