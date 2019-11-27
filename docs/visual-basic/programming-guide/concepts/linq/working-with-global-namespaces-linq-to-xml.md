---
title: Arbeiten mit globalen Namespaces (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 0a8064d5-e02f-4315-ad48-6deaa443a2f0
ms.openlocfilehash: 80510e370e0a9c7ab27cb5177d9b547ead82715c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350993"
---
# <a name="working-with-global-namespaces-visual-basic-linq-to-xml"></a><span data-ttu-id="669a5-102">Arbeiten mit globalen Namespaces (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="669a5-102">Working with Global Namespaces (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="669a5-103">Eines der wichtigsten Features von XML-Literalen in Visual Basic ist die Funktion zum Deklarieren von XML-Namespaces mithilfe der `Imports`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="669a5-103">One of the key features of XML literals in Visual Basic is the capability to declare XML namespaces by using the `Imports` statement.</span></span> <span data-ttu-id="669a5-104">Mithilfe dieser Funktionen können Sie einen XML-Namespace, der einen Präfix verwendet, oder einen XML-Standardnamespace deklarieren.</span><span class="sxs-lookup"><span data-stu-id="669a5-104">Using this feature, you can declare an XML namespace that uses a prefix, or you can declare a default XML namespace.</span></span>  
  
 <span data-ttu-id="669a5-105">Diese Möglichkeit erweist sich in zwei Situationen als hilfreich:</span><span class="sxs-lookup"><span data-stu-id="669a5-105">This capability is useful in two situations.</span></span> <span data-ttu-id="669a5-106">Zum einen werden in XML-Literalen deklarierte Namespaces nicht in eingebettete Ausdrücke übertragen.</span><span class="sxs-lookup"><span data-stu-id="669a5-106">First, namespaces declared in XML literals do not carry over into embedded expressions.</span></span> <span data-ttu-id="669a5-107">Durch das Deklarieren globaler Namespaces verringert sich der Arbeitsaufwand, der erforderlich ist, wenn Sie eingebettete Ausdrücke mit Namespaces verwenden.</span><span class="sxs-lookup"><span data-stu-id="669a5-107">Declaring global namespaces reduces the amount of work that you have to do to use embedded expressions with namespaces.</span></span> <span data-ttu-id="669a5-108">Zum anderen müssen Sie globale Namespaces deklarieren, um Namespaces mit XML-Eigenschaften zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="669a5-108">Second, you must declare global namespaces in order to use namespaces with XML properties.</span></span>  
  
 <span data-ttu-id="669a5-109">Sie können globale Namespaces auf Projektebene deklarieren.</span><span class="sxs-lookup"><span data-stu-id="669a5-109">You can declare global namespaces at the project level.</span></span> <span data-ttu-id="669a5-110">Globale Namespaces können auch auf der Modulebene deklariert werden, wobei die globalen Namespaces auf Projektebene außer Kraft gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="669a5-110">You can also declare global namespaces at the module level, which overrides the project-level global namespaces.</span></span> <span data-ttu-id="669a5-111">Schließlich ist es auch möglich, globale Namespaces in einem XML-Literal außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="669a5-111">Finally, you can override global namespaces in an XML literal.</span></span>  
  
 <span data-ttu-id="669a5-112">Bei Verwendung von XML-Literalen oder XML-Eigenschaften, die sich in global deklarierten Namespaces befinden, können Sie sich den erweiterten Namen der XML-Literale oder -Eigenschaften anzeigen lassen, indem Sie in Visual Studio mit der Maus darauf zeigen.</span><span class="sxs-lookup"><span data-stu-id="669a5-112">When using XML literals or XML properties that are in globally-declared namespaces, you can see the expanded name of XML literals or properties by hovering over them in Visual Studio.</span></span> <span data-ttu-id="669a5-113">Der erweiterte Name wird dann in einer QuickInfo angezeigt.</span><span class="sxs-lookup"><span data-stu-id="669a5-113">You will see the expanded name in a tooltip.</span></span>  
  
 <span data-ttu-id="669a5-114">Mit der <xref:System.Xml.Linq.XNamespace>-Methode können Sie ein `GetXmlNamespace`-Objekt abrufen, das einem globalen Namespace entspricht.</span><span class="sxs-lookup"><span data-stu-id="669a5-114">You can get an <xref:System.Xml.Linq.XNamespace> object that corresponds to a global namespace using the `GetXmlNamespace` method.</span></span>  
  
## <a name="examples-of-global-namespaces"></a><span data-ttu-id="669a5-115">Beispiele für globale Namespaces</span><span class="sxs-lookup"><span data-stu-id="669a5-115">Examples of Global Namespaces</span></span>  
 <span data-ttu-id="669a5-116">Das folgende Beispiel deklariert einen globalen Standardnamespace unter Verwendung der `Imports`-Anweisung und verwendet dann ein XML-Literal, um ein <xref:System.Xml.Linq.XElement>-Objekt in diesem Namespace zu deklarieren:</span><span class="sxs-lookup"><span data-stu-id="669a5-116">The following example declares a default global namespace by using the `Imports` statement, and then uses an XML literal to initialize an <xref:System.Xml.Linq.XElement> object in that namespace:</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <Root/>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="669a5-117">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="669a5-117">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com" />  
```  
  
 <span data-ttu-id="669a5-118">Das folgende Beispiel deklariert einen globalen Namespace mit einem Präfix und verwendet dann ein XML-Literal, um ein Element zu initialisieren:</span><span class="sxs-lookup"><span data-stu-id="669a5-118">The following example declares a global namespace with a prefix, and then uses an XML literal to initialize an element:</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root/>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="669a5-119">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="669a5-119">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" />  
```  
  
## <a name="global-namespaces-and-embedded-expressions"></a><span data-ttu-id="669a5-120">Globale Namespaces und eingebettete Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="669a5-120">Global Namespaces and Embedded Expressions</span></span>  
 <span data-ttu-id="669a5-121">Namespaces, die in XML-Literalen deklariert werden, werden nicht in eingebettete Ausdrücke übertragen.</span><span class="sxs-lookup"><span data-stu-id="669a5-121">Namespaces that are declared in XML literals do not carry over into embedded expressions.</span></span> <span data-ttu-id="669a5-122">Das folgende Beispiel deklariert einen Standardnamespace.</span><span class="sxs-lookup"><span data-stu-id="669a5-122">The following example declares a default namespace.</span></span> <span data-ttu-id="669a5-123">Anschließend verwendet das Beispiel einen eingebetteten Ausdruck für das `Child`-Element.</span><span class="sxs-lookup"><span data-stu-id="669a5-123">It then uses an embedded expression for the `Child` element.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <%= <Child/> %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="669a5-124">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="669a5-124">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child xmlns="" />  
</Root>  
```  
  
 <span data-ttu-id="669a5-125">Wie Sie sehen, enthalten die sich ergebenden XML-Daten eine Deklaration eines Standardnamespace, sodass sich das `Child`-Element nicht in einem Namespace befindet.</span><span class="sxs-lookup"><span data-stu-id="669a5-125">As you can see, the resulting XML includes a declaration of a default namespace so that the `Child` element is in no namespace.</span></span>  
  
 <span data-ttu-id="669a5-126">Sie können den Namespace im eingebetteten Ausdruck wie folgt neu deklarieren:</span><span class="sxs-lookup"><span data-stu-id="669a5-126">You could re-declare the namespace in the embedded expression, as follows:</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <%= <Child xmlns="http://www.adventure-works.com"/> %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="669a5-127">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="669a5-127">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child xmlns="http://www.adventure-works.com" />  
</Root>  
```  
  
 <span data-ttu-id="669a5-128">Dies ist jedoch umständlicher als die Verwendung des globalen Standardnamespace, der einen besseren Ansatz darstellt.</span><span class="sxs-lookup"><span data-stu-id="669a5-128">However, this is more cumbersome to use than the global default namespace, which is a better approach.</span></span> <span data-ttu-id="669a5-129">Beim globalen Standardnamespace können Sie XML-Literale verwenden, ohne Namespaces zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="669a5-129">With the global default namespace, you can use XML literals without declaring namespaces.</span></span> <span data-ttu-id="669a5-130">Die sich ergebenden XML-Daten befinden sich im global deklarierten Standardnamespace.</span><span class="sxs-lookup"><span data-stu-id="669a5-130">The resulting XML will be in the globally-declared default namespace.</span></span>  
  
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
  
 <span data-ttu-id="669a5-131">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="669a5-131">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child />  
</Root>  
```  
  
## <a name="using-namespaces-with-xml-properties"></a><span data-ttu-id="669a5-132">Verwenden von Namespaces mit XML-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="669a5-132">Using Namespaces with XML Properties</span></span>  
 <span data-ttu-id="669a5-133">Wenn Sie mit einer XML-Struktur arbeiten, die sich in einem Namespace befindet, und wenn Sie XML-Eigenschaften verwenden, müssen Sie einen globalen Namespace verwenden, damit sich die XML-Eigenschaften ebenfalls im korrekten Namespace befinden.</span><span class="sxs-lookup"><span data-stu-id="669a5-133">If you are working with an XML tree that is in a namespace, and you use XML properties, then you must use a global namespace so that the XML properties will also be in the correct namespace.</span></span> <span data-ttu-id="669a5-134">Das folgende Beispiel deklariert eine XML-Struktur in einem Namespace.</span><span class="sxs-lookup"><span data-stu-id="669a5-134">The following example declares an XML tree in a namespace.</span></span> <span data-ttu-id="669a5-135">Anschließend gibt das Beispiel die Anzahl von `Child`-Elementen aus.</span><span class="sxs-lookup"><span data-stu-id="669a5-135">It then prints the count of `Child` elements.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <Child>content</Child>  
    </Root>  
Console.WriteLine(root.<Child>.Count())  
```  
  
 <span data-ttu-id="669a5-136">Diesem Beispiel zufolge gibt es keine `Child`-Elemente.</span><span class="sxs-lookup"><span data-stu-id="669a5-136">This example indicates that there are no `Child` elements.</span></span> <span data-ttu-id="669a5-137">Es erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="669a5-137">It produces the following output:</span></span>  
  
```console  
0  
```  
  
 <span data-ttu-id="669a5-138">Wenn Sie aber einen globalen Standardnamespace deklarieren, befinden sich sowohl das XML-Literal als auch die XML-Eigenschaft im globalen Standardnamespace:</span><span class="sxs-lookup"><span data-stu-id="669a5-138">If, however, you declare a default global namespace, then both the XML literal and the XML property are in the default global namespace:</span></span>  
  
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
  
 <span data-ttu-id="669a5-139">Diesem Beispiel zufolge gibt es genau ein `Child`-Element.</span><span class="sxs-lookup"><span data-stu-id="669a5-139">This example indicates that there is one `Child` element.</span></span> <span data-ttu-id="669a5-140">Es erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="669a5-140">It produces the following output:</span></span>  
  
```console  
1  
```  
  
 <span data-ttu-id="669a5-141">Wenn Sie einen globalen Namespace deklarieren, der ein Präfix besitzt, können Sie das Präfix sowohl für die XML-Literale als auch für die XML-Eigenschaften verwenden:</span><span class="sxs-lookup"><span data-stu-id="669a5-141">If you declare a global namespace that has a prefix, you can use the prefix for both XML literals and XML properties:</span></span>  
  
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
  
## <a name="xnamespace-and-global-namespaces"></a><span data-ttu-id="669a5-142">XNamespace und globale Namespaces</span><span class="sxs-lookup"><span data-stu-id="669a5-142">XNamespace and Global Namespaces</span></span>  
 <span data-ttu-id="669a5-143">Mit der <xref:System.Xml.Linq.XNamespace>-Methode können Sie ein `GetXmlNamespace`-Objekt abrufen:</span><span class="sxs-lookup"><span data-stu-id="669a5-143">You can get an <xref:System.Xml.Linq.XNamespace> object by using the `GetXmlNamespace` method:</span></span>  
  
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
  
 <span data-ttu-id="669a5-144">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="669a5-144">This example produces the following output:</span></span>  
  
```console  
http://www.adventure-works.com  
```  
  
## <a name="see-also"></a><span data-ttu-id="669a5-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="669a5-145">See also</span></span>

- [<span data-ttu-id="669a5-146">Übersicht über Namespaces (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="669a5-146">Namespaces Overview (LINQ to XML) (Visual Basic)</span></span>](namespaces-overview-linq-to-xml.md)
