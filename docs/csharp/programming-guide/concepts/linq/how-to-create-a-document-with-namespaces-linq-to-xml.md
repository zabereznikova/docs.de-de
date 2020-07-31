---
title: 'Vorgehensweise: Erstellen eines Dokuments mit Namespaces (C#) (LINQ to XML)'
description: In diesem Artikel erfahren Sie, wie Sie ein Dokument mit einem Namespace in LINQ to XML in C# erstellen, indem Sie ein XNamespace-Objekt verwenden, um den Namespace mit dem lokalen Namen zu kombinieren.
ms.date: 07/20/2015
ms.assetid: 37e63c57-f86d-47ac-88a7-2c2d107def30
ms.openlocfilehash: 6472baefc73285af1c6dca0bfe7d874003940fc4
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103394"
---
# <a name="how-to-create-a-document-with-namespaces-c-linq-to-xml"></a><span data-ttu-id="f687b-103">Vorgehensweise: Erstellen eines Dokuments mit Namespaces (C#) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="f687b-103">How to create a document with namespaces (C#) (LINQ to XML)</span></span>
<span data-ttu-id="f687b-104">In diesem Thema wird das Erstellen von Dokumenten mit Namespaces beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f687b-104">This topic shows how to create documents with namespaces.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f687b-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f687b-105">Example</span></span>  
 <span data-ttu-id="f687b-106">Wenn Sie ein Element oder Attribut erstellen möchten, das sich in einem Namespace befindet, deklarieren und initialisieren Sie zuerst ein <xref:System.Xml.Linq.XNamespace>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="f687b-106">To create an element or an attribute that is in a namespace, you first declare and initialize an <xref:System.Xml.Linq.XNamespace> object.</span></span> <span data-ttu-id="f687b-107">Anschließend verwenden Sie die Additionsoperatorüberladung, um den Namespace mit dem lokalen Namen in Form einer Zeichenfolge zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="f687b-107">You then use the addition operator overload to combine the namespace with the local name, expressed as a string.</span></span>  
  
 <span data-ttu-id="f687b-108">Das folgende Beispiel erstellt ein Dokument mit nur einem Namespace.</span><span class="sxs-lookup"><span data-stu-id="f687b-108">The following example creates a document with one namespace.</span></span> <span data-ttu-id="f687b-109">Standardmäßig serialisiert [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] dieses Dokument mit einem Standardnamespace.</span><span class="sxs-lookup"><span data-stu-id="f687b-109">By default, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] serializes this document with a default namespace.</span></span>  
  
```csharp  
// Create an XML tree in a namespace.  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
    new XElement(aw + "Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="f687b-110">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="f687b-110">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child>child content</Child>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="f687b-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f687b-111">Example</span></span>  
 <span data-ttu-id="f687b-112">Das folgende Beispiel erstellt ein Dokument mit nur einem Namespace.</span><span class="sxs-lookup"><span data-stu-id="f687b-112">The following example creates a document with one namespace.</span></span> <span data-ttu-id="f687b-113">Es erstellt auch ein Attribut, das den Namespace mit einem Namespacepräfix deklariert.</span><span class="sxs-lookup"><span data-stu-id="f687b-113">It also creates an attribute that declares the namespace with a namespace prefix.</span></span> <span data-ttu-id="f687b-114">Gehen Sie zum Erstellen eines Attributs, das einen Namespace mit einem Präfix deklariert, wie folgt vor. Erstellen Sie ein Attribut, bei dem der Name des Attributs das Namespacepräfix darstellt. Dieser Name befindet sich im <xref:System.Xml.Linq.XNamespace.Xmlns%2A>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="f687b-114">To create an attribute that declares a namespace with a prefix, you create an attribute where the name of the attribute is the namespace prefix, and this name is in the <xref:System.Xml.Linq.XNamespace.Xmlns%2A> namespace.</span></span> <span data-ttu-id="f687b-115">Der Wert dieses Attributs ist der URI des Namespace.</span><span class="sxs-lookup"><span data-stu-id="f687b-115">The value of this attribute is the URI of the namespace.</span></span>  
  
```csharp  
// Create an XML tree in a namespace, with a specified prefix  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XElement(aw + "Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="f687b-116">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="f687b-116">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child>child content</aw:Child>  
</aw:Root>  
```  
  
## <a name="example"></a><span data-ttu-id="f687b-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f687b-117">Example</span></span>  
 <span data-ttu-id="f687b-118">Das folgende Beispiel zeigt das Erstellen eines Dokuments, das zwei Namespaces enthält.</span><span class="sxs-lookup"><span data-stu-id="f687b-118">The following example shows the creation of a document that contains two namespaces.</span></span> <span data-ttu-id="f687b-119">Einer der Namespaces ist der Standardnamespace.</span><span class="sxs-lookup"><span data-stu-id="f687b-119">One is the default namespace.</span></span> <span data-ttu-id="f687b-120">Der andere Namespace besitzt ein Präfix.</span><span class="sxs-lookup"><span data-stu-id="f687b-120">Another is a namespace with a prefix.</span></span>  
  
 <span data-ttu-id="f687b-121">Durch das Aufnehmen von Namespaceattributen in das Stammelement werden die Namespaces so serialisiert, dass `http://www.adventure-works.com` zum Standardnamespace wird und `www.fourthcoffee.com` mit dem Präfix „fc“ serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="f687b-121">By including namespace attributes in the root element, the namespaces are serialized so that `http://www.adventure-works.com` is the default namespace, and `www.fourthcoffee.com` is serialized with a prefix of "fc".</span></span> <span data-ttu-id="f687b-122">Zum Erstellen eines Attributs, das einen Standardnamespace deklariert, erstellen Sie ein Attribut mit dem Namen  <legacyBold>xmlns</legacyBold> ohne einen Namespace.</span><span class="sxs-lookup"><span data-stu-id="f687b-122">To create an attribute that declares a default namespace, you create an attribute with the name "xmlns", without a namespace.</span></span> <span data-ttu-id="f687b-123">Der Wert des Attributs ist der Standardnamespace-URI.</span><span class="sxs-lookup"><span data-stu-id="f687b-123">The value of the attribute is the default namespace URI.</span></span>  
  
```csharp  
// The http://www.adventure-works.com namespace is forced to be the default namespace.  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute("xmlns", "http://www.adventure-works.com"),  
    new XAttribute(XNamespace.Xmlns + "fc", "www.fourthcoffee.com"),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="f687b-124">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="f687b-124">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <DifferentChild>other content</DifferentChild>  
  </fc:Child>  
  <Child2>c2 content</Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="f687b-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f687b-125">Example</span></span>  
 <span data-ttu-id="f687b-126">Das folgende Beispiel erstellt ein Dokument, das zwei Namespaces enthält, die beide ein Namespacepräfix besitzen.</span><span class="sxs-lookup"><span data-stu-id="f687b-126">The following example creates a document that contains two namespaces, both with namespace prefixes.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", aw.NamespaceName),  
    new XAttribute(XNamespace.Xmlns + "fc", fc.NamespaceName),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="f687b-127">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="f687b-127">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="example"></a><span data-ttu-id="f687b-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f687b-128">Example</span></span>  
 <span data-ttu-id="f687b-129">Dasselbe Ergebnis lässt sich erzielen, indem statt des Deklarierens und Erstellens eines <xref:System.Xml.Linq.XNamespace>-Objekts erweiterte Namen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f687b-129">Another way to accomplish the same result is to use expanded names instead of declaring and creating an <xref:System.Xml.Linq.XNamespace> object.</span></span>  
  
 <span data-ttu-id="f687b-130">Dieser Ansatz wirkt sich aber negativ auf die Leistung aus.</span><span class="sxs-lookup"><span data-stu-id="f687b-130">This approach has performance implications.</span></span> <span data-ttu-id="f687b-131">Jedes Mal, wenn Sie eine Zeichenfolge, die einen erweiterten Namen enthält, an [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] übergeben, muss [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] den Namen analysieren und nach dem atomisierten Namespace und dem atomisierten Namen suchen.</span><span class="sxs-lookup"><span data-stu-id="f687b-131">Each time you pass a string that contains an expanded name to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] must parse the name, find the atomized namespace, and find the atomized name.</span></span> <span data-ttu-id="f687b-132">Dieser Prozess nimmt CPU-Zeit in Anspruch.</span><span class="sxs-lookup"><span data-stu-id="f687b-132">This process takes CPU time.</span></span> <span data-ttu-id="f687b-133">Wenn es auf eine hohe Leistung ankommt, sollten Sie daher explizit ein <xref:System.Xml.Linq.XNamespace>-Objekt deklarieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="f687b-133">If performance is important, you might want to declare and use an <xref:System.Xml.Linq.XNamespace> object explicitly.</span></span>  
  
 <span data-ttu-id="f687b-134">Wenn die Leistung ein wichtiger Aspekt ist, finden Sie weitere Informationen unter [Pre-Atomization of XName Objects (LINQ to XML) (C#) (Voratomisierung von XName-Objekten (LINQ to XML) (C#))](./pre-atomization-of-xname-objects-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f687b-134">If performance is an important issue, see [Pre-Atomization of XName Objects (LINQ to XML) (C#)](./pre-atomization-of-xname-objects-linq-to-xml.md) for more information</span></span>  
  
```csharp  
// Create an XML tree in a namespace, with a specified prefix  
XElement root = new XElement("{http://www.adventure-works.com}Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XElement("{http://www.adventure-works.com}Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="f687b-135">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="f687b-135">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child>child content</aw:Child>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f687b-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f687b-136">See also</span></span>

- [<span data-ttu-id="f687b-137">Namespaces: Übersicht (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="f687b-137">Namespaces Overview (LINQ to XML) (C#)</span></span>](namespaces-overview-linq-to-xml.md)
