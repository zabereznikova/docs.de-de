---
title: 'Gewusst wie: Erstellen eines Dokuments mit Namespaces (C#) (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 37e63c57-f86d-47ac-88a7-2c2d107def30
ms.openlocfilehash: 0fa19af47847b0d6b804528af3f766c9775e74f3
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863686"
---
# <a name="how-to-create-a-document-with-namespaces-c-linq-to-xml"></a><span data-ttu-id="bd2e0-102">Gewusst wie: Erstellen eines Dokuments mit Namespaces (C#) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="bd2e0-102">How to: Create a Document with Namespaces (C#) (LINQ to XML)</span></span>
<span data-ttu-id="bd2e0-103">In diesem Thema wird das Erstellen von Dokumenten mit Namespaces beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bd2e0-103">This topic shows how to create documents with namespaces.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd2e0-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bd2e0-104">Example</span></span>  
 <span data-ttu-id="bd2e0-105">Wenn Sie ein Element oder Attribut erstellen möchten, das sich in einem Namespace befindet, deklarieren und initialisieren Sie zuerst ein <xref:System.Xml.Linq.XNamespace>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="bd2e0-105">To create an element or an attribute that is in a namespace, you first declare and initialize an <xref:System.Xml.Linq.XNamespace> object.</span></span> <span data-ttu-id="bd2e0-106">Anschließend verwenden Sie die Additionsoperatorüberladung, um den Namespace mit dem lokalen Namen in Form einer Zeichenfolge zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="bd2e0-106">You then use the addition operator overload to combine the namespace with the local name, expressed as a string.</span></span>  
  
 <span data-ttu-id="bd2e0-107">Das folgende Beispiel erstellt ein Dokument mit nur einem Namespace.</span><span class="sxs-lookup"><span data-stu-id="bd2e0-107">The following example creates a document with one namespace.</span></span> <span data-ttu-id="bd2e0-108">Standardmäßig serialisiert [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] dieses Dokument mit einem Standardnamespace.</span><span class="sxs-lookup"><span data-stu-id="bd2e0-108">By default, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] serializes this document with a default namespace.</span></span>  
  
```csharp  
// Create an XML tree in a namespace.  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
    new XElement(aw + "Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="bd2e0-109">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="bd2e0-109">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child>child content</Child>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="bd2e0-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bd2e0-110">Example</span></span>  
 <span data-ttu-id="bd2e0-111">Das folgende Beispiel erstellt ein Dokument mit nur einem Namespace.</span><span class="sxs-lookup"><span data-stu-id="bd2e0-111">The following example creates a document with one namespace.</span></span> <span data-ttu-id="bd2e0-112">Es erstellt auch ein Attribut, das den Namespace mit einem Namespacepräfix deklariert.</span><span class="sxs-lookup"><span data-stu-id="bd2e0-112">It also creates an attribute that declares the namespace with a namespace prefix.</span></span> <span data-ttu-id="bd2e0-113">Gehen Sie zum Erstellen eines Attributs, das einen Namespace mit einem Präfix deklariert, wie folgt vor. Erstellen Sie ein Attribut, bei dem der Name des Attributs das Namespacepräfix darstellt. Dieser Name befindet sich im <xref:System.Xml.Linq.XNamespace.Xmlns%2A>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="bd2e0-113">To create an attribute that declares a namespace with a prefix, you create an attribute where the name of the attribute is the namespace prefix, and this name is in the <xref:System.Xml.Linq.XNamespace.Xmlns%2A> namespace.</span></span> <span data-ttu-id="bd2e0-114">Der Wert dieses Attributs ist der URI des Namespace.</span><span class="sxs-lookup"><span data-stu-id="bd2e0-114">The value of this attribute is the URI of the namespace.</span></span>  
  
```csharp  
// Create an XML tree in a namespace, with a specified prefix  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XElement(aw + "Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="bd2e0-115">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="bd2e0-115">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child>child content</aw:Child>  
</aw:Root>  
```  
  
## <a name="example"></a><span data-ttu-id="bd2e0-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bd2e0-116">Example</span></span>  
 <span data-ttu-id="bd2e0-117">Das folgende Beispiel zeigt das Erstellen eines Dokuments, das zwei Namespaces enthält.</span><span class="sxs-lookup"><span data-stu-id="bd2e0-117">The following example shows the creation of a document that contains two namespaces.</span></span> <span data-ttu-id="bd2e0-118">Einer der Namespaces ist der Standardnamespace.</span><span class="sxs-lookup"><span data-stu-id="bd2e0-118">One is the default namespace.</span></span> <span data-ttu-id="bd2e0-119">Der andere Namespace besitzt ein Präfix.</span><span class="sxs-lookup"><span data-stu-id="bd2e0-119">Another is a namespace with a prefix.</span></span>  
  
 <span data-ttu-id="bd2e0-120">Durch das Aufnehmen von Namespaceattributen in das Stammelement werden die Namespaces so serialisiert, dass `http://www.adventure-works.com` zum Standardnamespace wird und `www.fourthcoffee.com` mit dem Präfix „fc“ serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="bd2e0-120">By including namespace attributes in the root element, the namespaces are serialized so that `http://www.adventure-works.com` is the default namespace, and `www.fourthcoffee.com` is serialized with a prefix of "fc".</span></span> <span data-ttu-id="bd2e0-121">Zum Erstellen eines Attributs, das einen Standardnamespace deklariert, erstellen Sie ein Attribut mit dem Namen  <legacyBold>xmlns</legacyBold> ohne einen Namespace.</span><span class="sxs-lookup"><span data-stu-id="bd2e0-121">To create an attribute that declares a default namespace, you create an attribute with the name "xmlns", without a namespace.</span></span> <span data-ttu-id="bd2e0-122">Der Wert des Attributs ist der Standardnamespace-URI.</span><span class="sxs-lookup"><span data-stu-id="bd2e0-122">The value of the attribute is the default namespace URI.</span></span>  
  
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
  
 <span data-ttu-id="bd2e0-123">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="bd2e0-123">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <DifferentChild>other content</DifferentChild>  
  </fc:Child>  
  <Child2>c2 content</Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="bd2e0-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bd2e0-124">Example</span></span>  
 <span data-ttu-id="bd2e0-125">Das folgende Beispiel erstellt ein Dokument, das zwei Namespaces enthält, die beide ein Namespacepräfix besitzen.</span><span class="sxs-lookup"><span data-stu-id="bd2e0-125">The following example creates a document that contains two namespaces, both with namespace prefixes.</span></span>  
  
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
  
 <span data-ttu-id="bd2e0-126">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="bd2e0-126">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="example"></a><span data-ttu-id="bd2e0-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bd2e0-127">Example</span></span>  
 <span data-ttu-id="bd2e0-128">Dasselbe Ergebnis lässt sich erzielen, indem statt des Deklarierens und Erstellens eines <xref:System.Xml.Linq.XNamespace>-Objekts erweiterte Namen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd2e0-128">Another way to accomplish the same result is to use expanded names instead of declaring and creating an <xref:System.Xml.Linq.XNamespace> object.</span></span>  
  
 <span data-ttu-id="bd2e0-129">Dieser Ansatz wirkt sich aber negativ auf die Leistung aus.</span><span class="sxs-lookup"><span data-stu-id="bd2e0-129">This approach has performance implications.</span></span> <span data-ttu-id="bd2e0-130">Jedes Mal, wenn Sie eine Zeichenfolge, die einen erweiterten Namen enthält, an [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] übergeben, muss [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] den Namen analysieren und nach dem atomisierten Namespace und dem atomisierten Namen suchen.</span><span class="sxs-lookup"><span data-stu-id="bd2e0-130">Each time you pass a string that contains an expanded name to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] must parse the name, find the atomized namespace, and find the atomized name.</span></span> <span data-ttu-id="bd2e0-131">Dieser Prozess nimmt CPU-Zeit in Anspruch.</span><span class="sxs-lookup"><span data-stu-id="bd2e0-131">This process takes CPU time.</span></span> <span data-ttu-id="bd2e0-132">Wenn es auf eine hohe Leistung ankommt, sollten Sie daher explizit ein <xref:System.Xml.Linq.XNamespace>-Objekt deklarieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="bd2e0-132">If performance is important, you might want to declare and use an <xref:System.Xml.Linq.XNamespace> object explicitly.</span></span>  
  
 <span data-ttu-id="bd2e0-133">Wenn die Leistung ein wichtiger Aspekt ist, finden Sie weitere Informationen unter [Pre-Atomization of XName Objects (LINQ to XML) (C#) (Voratomisierung von XName-Objekten (LINQ to XML) (C#))](../../../../csharp/programming-guide/concepts/linq/pre-atomization-of-xname-objects-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="bd2e0-133">If performance is an important issue, see [Pre-Atomization of XName Objects (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/pre-atomization-of-xname-objects-linq-to-xml.md) for more information</span></span>  
  
```csharp  
// Create an XML tree in a namespace, with a specified prefix  
XElement root = new XElement("{http://www.adventure-works.com}Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XElement("{http://www.adventure-works.com}Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="bd2e0-134">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="bd2e0-134">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child>child content</aw:Child>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bd2e0-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd2e0-135">See Also</span></span>

- [<span data-ttu-id="bd2e0-136">Working with XML Namespaces (C#) (Arbeiten mit XML-Namespaces (C#))</span><span class="sxs-lookup"><span data-stu-id="bd2e0-136">Working with XML Namespaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)
