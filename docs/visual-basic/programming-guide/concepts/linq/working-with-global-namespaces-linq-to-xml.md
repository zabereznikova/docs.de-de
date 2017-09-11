---
title: Arbeiten mit globalen Namespaces (Visual Basic) (LINQ to XML) | Microsoft-Dokumentation
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
ms.assetid: 0a8064d5-e02f-4315-ad48-6deaa443a2f0
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
ms.openlocfilehash: 6d92bdf80fa5db0003dfc0c6af7f0e8f6c3b2334
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="working-with-global-namespaces-visual-basic-linq-to-xml"></a><span data-ttu-id="23c56-102">Arbeiten mit globalen Namespaces (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="23c56-102">Working with Global Namespaces (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="23c56-103">Eine der Schlüsselfunktionen von XML-Literalen in Visual Basic ist die Möglichkeit zum Deklarieren von XML-Namespaces mithilfe der `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="23c56-103">One of the key features of XML literals in Visual Basic is the capability to declare XML namespaces by using the `Imports` statement.</span></span> <span data-ttu-id="23c56-104">Mithilfe dieser Funktionen können Sie einen XML-Namespace, der einen Präfix verwendet, oder einen XML-Standardnamespace deklarieren.</span><span class="sxs-lookup"><span data-stu-id="23c56-104">Using this feature, you can declare an XML namespace that uses a prefix, or you can declare a default XML namespace.</span></span>  
  
 <span data-ttu-id="23c56-105">Diese Möglichkeit erweist sich in zwei Situationen als hilfreich:</span><span class="sxs-lookup"><span data-stu-id="23c56-105">This capability is useful in two situations.</span></span> <span data-ttu-id="23c56-106">Zum einen werden in XML-Literalen deklarierte Namespaces nicht in eingebettete Ausdrücke übertragen.</span><span class="sxs-lookup"><span data-stu-id="23c56-106">First, namespaces declared in XML literals do not carry over into embedded expressions.</span></span> <span data-ttu-id="23c56-107">Durch das Deklarieren globaler Namespaces verringert sich der Arbeitsaufwand, der erforderlich ist, wenn Sie eingebettete Ausdrücke mit Namespaces verwenden.</span><span class="sxs-lookup"><span data-stu-id="23c56-107">Declaring global namespaces reduces the amount of work that you have to do to use embedded expressions with namespaces.</span></span> <span data-ttu-id="23c56-108">Zum anderen müssen Sie globale Namespaces deklarieren, um Namespaces mit XML-Eigenschaften zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="23c56-108">Second, you must declare global namespaces in order to use namespaces with XML properties.</span></span>  
  
 <span data-ttu-id="23c56-109">Sie können globale Namespaces auf Projektebene deklarieren.</span><span class="sxs-lookup"><span data-stu-id="23c56-109">You can declare global namespaces at the project level.</span></span> <span data-ttu-id="23c56-110">Globale Namespaces können auch auf der Modulebene deklariert werden, wobei die globalen Namespaces auf Projektebene außer Kraft gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="23c56-110">You can also declare global namespaces at the module level, which overrides the project-level global namespaces.</span></span> <span data-ttu-id="23c56-111">Schließlich ist es auch möglich, globale Namespaces in einem XML-Literal außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="23c56-111">Finally, you can override global namespaces in an XML literal.</span></span>  
  
 <span data-ttu-id="23c56-112">Bei Verwendung von XML-Literalen oder XML-Eigenschaften, die sich in global deklarierten Namespaces befinden, können Sie sich den erweiterten Namen der XML-Literale oder -Eigenschaften anzeigen lassen, indem Sie in Visual Studio mit der Maus darauf zeigen.</span><span class="sxs-lookup"><span data-stu-id="23c56-112">When using XML literals or XML properties that are in globally-declared namespaces, you can see the expanded name of XML literals or properties by hovering over them in Visual Studio.</span></span> <span data-ttu-id="23c56-113">Der erweiterte Name wird dann in einer QuickInfo angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23c56-113">You will see the expanded name in a tooltip.</span></span>  
  
 <span data-ttu-id="23c56-114">Sie erhalten ein <xref:System.Xml.Linq.XNamespace>-Objekt, das einem globalen Namespace entspricht, der `GetXmlNamespace` -Methode.</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="23c56-114">You can get an <xref:System.Xml.Linq.XNamespace> object that corresponds to a global namespace using the `GetXmlNamespace` method.</span></span>  
  
## <a name="examples-of-global-namespaces"></a><span data-ttu-id="23c56-115">Beispiele für globale Namespaces</span><span class="sxs-lookup"><span data-stu-id="23c56-115">Examples of Global Namespaces</span></span>  
 <span data-ttu-id="23c56-116">Das folgende Beispiel deklariert einen globalen Standardnamespace unter Verwendung der `Imports` -Anweisung, und verwendet dann ein XML-literal um Initialisieren einer <xref:System.Xml.Linq.XElement>-Objekt in diesem Namespace:</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="23c56-116">The following example declares a default global namespace by using the `Imports` statement, and then uses an XML literal to initialize an <xref:System.Xml.Linq.XElement> object in that namespace:</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <Root/>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="23c56-117">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="23c56-117">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com" />  
```  
  
 <span data-ttu-id="23c56-118">Das folgende Beispiel deklariert einen globalen Namespace mit einem Präfix und verwendet dann ein XML-Literal, um ein Element zu initialisieren:</span><span class="sxs-lookup"><span data-stu-id="23c56-118">The following example declares a global namespace with a prefix, and then uses an XML literal to initialize an element:</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root/>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="23c56-119">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="23c56-119">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" />  
```  
  
## <a name="global-namespaces-and-embedded-expressions"></a><span data-ttu-id="23c56-120">Globale Namespaces und eingebettete Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="23c56-120">Global Namespaces and Embedded Expressions</span></span>  
 <span data-ttu-id="23c56-121">Namespaces, die in XML-Literalen deklariert werden, werden nicht in eingebettete Ausdrücke übertragen.</span><span class="sxs-lookup"><span data-stu-id="23c56-121">Namespaces that are declared in XML literals do not carry over into embedded expressions.</span></span> <span data-ttu-id="23c56-122">Das folgende Beispiel deklariert einen Standardnamespace.</span><span class="sxs-lookup"><span data-stu-id="23c56-122">The following example declares a default namespace.</span></span> <span data-ttu-id="23c56-123">Anschließend verwendet das Beispiel einen eingebetteten Ausdruck für das `Child`-Element.</span><span class="sxs-lookup"><span data-stu-id="23c56-123">It then uses an embedded expression for the `Child` element.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <%= <Child/> %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="23c56-124">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="23c56-124">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child xmlns="" />  
</Root>  
```  
  
 <span data-ttu-id="23c56-125">Wie Sie sehen, enthalten die sich ergebenden XML-Daten eine Deklaration eines Standardnamespace, sodass sich das `Child`-Element nicht in einem Namespace befindet.</span><span class="sxs-lookup"><span data-stu-id="23c56-125">As you can see, the resulting XML includes a declaration of a default namespace so that the `Child` element is in no namespace.</span></span>  
  
 <span data-ttu-id="23c56-126">Sie können den Namespace im eingebetteten Ausdruck wie folgt neu deklarieren:</span><span class="sxs-lookup"><span data-stu-id="23c56-126">You could re-declare the namespace in the embedded expression, as follows:</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <%= <Child xmlns="http://www.adventure-works.com"/> %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="23c56-127">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="23c56-127">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child xmlns="http://www.adventure-works.com" />  
</Root>  
```  
  
 <span data-ttu-id="23c56-128">Dies ist jedoch umständlicher als die Verwendung des globalen Standardnamespace, der einen besseren Ansatz darstellt.</span><span class="sxs-lookup"><span data-stu-id="23c56-128">However, this is more cumbersome to use than the global default namespace, which is a better approach.</span></span> <span data-ttu-id="23c56-129">Beim globalen Standardnamespace können Sie XML-Literale verwenden, ohne Namespaces zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="23c56-129">With the global default namespace, you can use XML literals without declaring namespaces.</span></span> <span data-ttu-id="23c56-130">Die sich ergebenden XML-Daten befinden sich im global deklarierten Standardnamespace.</span><span class="sxs-lookup"><span data-stu-id="23c56-130">The resulting XML will be in the globally-declared default namespace.</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <Root>  
                                   <%= <Child/> %>  
                               </Root>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="23c56-131">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="23c56-131">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child />  
</Root>  
```  
  
## <a name="using-namespaces-with-xml-properties"></a><span data-ttu-id="23c56-132">Verwenden von Namespaces mit XML-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="23c56-132">Using Namespaces with XML Properties</span></span>  
 <span data-ttu-id="23c56-133">Wenn Sie mit einer XML-Struktur arbeiten, die sich in einem Namespace befindet, und wenn Sie XML-Eigenschaften verwenden, müssen Sie einen globalen Namespace verwenden, damit sich die XML-Eigenschaften ebenfalls im korrekten Namespace befinden.</span><span class="sxs-lookup"><span data-stu-id="23c56-133">If you are working with an XML tree that is in a namespace, and you use XML properties, then you must use a global namespace so that the XML properties will also be in the correct namespace.</span></span> <span data-ttu-id="23c56-134">Das folgende Beispiel deklariert eine XML-Struktur in einem Namespace.</span><span class="sxs-lookup"><span data-stu-id="23c56-134">The following example declares an XML tree in a namespace.</span></span> <span data-ttu-id="23c56-135">Anschließend gibt das Beispiel die Anzahl von `Child`-Elementen aus.</span><span class="sxs-lookup"><span data-stu-id="23c56-135">It then prints the count of `Child` elements.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <Child>content</Child>  
    </Root>  
Console.WriteLine(root.<Child>.Count())  
```  
  
 <span data-ttu-id="23c56-136">Diesem Beispiel zufolge gibt es keine `Child`-Elemente.</span><span class="sxs-lookup"><span data-stu-id="23c56-136">This example indicates that there are no `Child` elements.</span></span> <span data-ttu-id="23c56-137">Es erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="23c56-137">It produces the following output:</span></span>  
  
```  
0  
```  
  
 <span data-ttu-id="23c56-138">Wenn Sie aber einen globalen Standardnamespace deklarieren, befinden sich sowohl das XML-Literal als auch die XML-Eigenschaft im globalen Standardnamespace:</span><span class="sxs-lookup"><span data-stu-id="23c56-138">If, however, you declare a default global namespace, then both the XML literal and the XML property are in the default global namespace:</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child>content</Child>  
            </Root>  
        Console.WriteLine(root.<Child>.Count())  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="23c56-139">Diesem Beispiel zufolge gibt es genau ein `Child`-Element.</span><span class="sxs-lookup"><span data-stu-id="23c56-139">This example indicates that there is one `Child` element.</span></span> <span data-ttu-id="23c56-140">Es erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="23c56-140">It produces the following output:</span></span>  
  
```  
1  
```  
  
 <span data-ttu-id="23c56-141">Wenn Sie einen globalen Namespace deklarieren, der ein Präfix besitzt, können Sie das Präfix sowohl für die XML-Literale als auch für die XML-Eigenschaften verwenden:</span><span class="sxs-lookup"><span data-stu-id="23c56-141">If you declare a global namespace that has a prefix, you can use the prefix for both XML literals and XML properties:</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child>content</aw:Child>  
            </aw:Root>  
        Console.WriteLine(root.<aw:Child>.Count())  
    End Sub  
End Module  
```  
  
## <a name="xnamespace-and-global-namespaces"></a><span data-ttu-id="23c56-142">XNamespace und globale Namespaces</span><span class="sxs-lookup"><span data-stu-id="23c56-142">XNamespace and Global Namespaces</span></span>  
 <span data-ttu-id="23c56-143">Sie erhalten ein <xref:System.Xml.Linq.XNamespace>Objekt mithilfe der `GetXmlNamespace` Methode:</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="23c56-143">You can get an <xref:System.Xml.Linq.XNamespace> object by using the `GetXmlNamespace` method:</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root/>  
        Dim xn As XNamespace = GetXmlNamespace(aw)  
        Console.WriteLine(xn)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="23c56-144">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="23c56-144">This example produces the following output:</span></span>  
  
```  
http://www.adventure-works.com  
```  
  
## <a name="see-also"></a><span data-ttu-id="23c56-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23c56-145">See Also</span></span>  
 [<span data-ttu-id="23c56-146">Arbeiten mit XML-Namespaces (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23c56-146">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
