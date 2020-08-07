---
title: Programmieren mit Knoten (C#)
description: Erfahren Sie mehr über das Programmieren mit Knoten. Hiermit können Entwickler Programme schreiben, die auf detaillierterer Ebene arbeiten, als Elemente und Attribute bieten können.
ms.date: 07/20/2015
ms.assetid: c38df0f2-c805-431a-93ff-9103a4284c2f
ms.openlocfilehash: 8a31d6459ab644a682d480239cabc3d88fd7dc14
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301683"
---
# <a name="programming-with-nodes-c"></a><span data-ttu-id="55db3-104">Programmieren mit Knoten (C#)</span><span class="sxs-lookup"><span data-stu-id="55db3-104">Programming with Nodes (C#)</span></span>
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="55db3-105">-Entwickler, die Programme, wie einen XML-Editor, ein Transformationssystem oder einen Berichts-Generator schreiben müssen, müssen häufig Programme schreiben, die auf einer detaillierteren Ebene als Elemente und Attribute arbeiten.</span><span class="sxs-lookup"><span data-stu-id="55db3-105">developers who need to write programs such as an XML editor, a transform system, or a report writer often need to write programs that work at a finer level of granularity than elements and attributes.</span></span> <span data-ttu-id="55db3-106">Sie müssen oft auf der Ebene der Knoten arbeiten und dabei Textknoten, Verarbeitungsanweisungen und Kommentare bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="55db3-106">They often need to work at the node level, manipulating text nodes, processing instructions, and comments.</span></span> <span data-ttu-id="55db3-107">Dieses Thema beschäftigt sich mit einigen Aspekten des Programmierens auf Knotenebene.</span><span class="sxs-lookup"><span data-stu-id="55db3-107">This topic provides some details about programming at the node level.</span></span>  
  
## <a name="node-details"></a><span data-ttu-id="55db3-108">Knotendetails</span><span class="sxs-lookup"><span data-stu-id="55db3-108">Node Details</span></span>  
 <span data-ttu-id="55db3-109">Es gibt eine Reihe von Programmierdetails, die ein auf der Knotenebene arbeitender Programmierer kennen sollte.</span><span class="sxs-lookup"><span data-stu-id="55db3-109">There are a number of details of programming that a programmer working at the node level should know.</span></span>  
  
### <a name="parent-property-of-children-nodes-of-xdocument-is-set-to-null"></a><span data-ttu-id="55db3-110">Übergeordnete Eigenschaft der untergeordneten XDocument-Knoten ist gleich NULL</span><span class="sxs-lookup"><span data-stu-id="55db3-110">Parent Property of Children Nodes of XDocument is Set to Null</span></span>  
 <span data-ttu-id="55db3-111">Die <xref:System.Xml.Linq.XObject.Parent%2A>-Eigenschaft enthält das übergeordnete <xref:System.Xml.Linq.XElement>, nicht den übergeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="55db3-111">The <xref:System.Xml.Linq.XObject.Parent%2A> property contains the parent <xref:System.Xml.Linq.XElement>, not the parent node.</span></span> <span data-ttu-id="55db3-112">Für untergeordnete Knoten von <xref:System.Xml.Linq.XDocument> gibt es kein übergeordnetes <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="55db3-112">Child nodes of <xref:System.Xml.Linq.XDocument> have no parent <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="55db3-113">Ihr übergeordnetes Element ist das Dokument, weshalb die <xref:System.Xml.Linq.XObject.Parent%2A>-Eigenschaft dieser Knoten gleich NULL ist.</span><span class="sxs-lookup"><span data-stu-id="55db3-113">Their parent is the document, so the <xref:System.Xml.Linq.XObject.Parent%2A> property for those nodes is set to null.</span></span>  
  
 <span data-ttu-id="55db3-114">Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="55db3-114">The following example demonstrates this:</span></span>  
  
```csharp  
XDocument doc = XDocument.Parse(@"<!-- a comment --><Root/>");  
Console.WriteLine(doc.Nodes().OfType<XComment>().First().Parent == null);  
Console.WriteLine(doc.Root.Parent == null);  
```  
  
 <span data-ttu-id="55db3-115">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="55db3-115">This example produces the following output:</span></span>  
  
```output  
True  
True  
```  
  
### <a name="adjacent-text-nodes-are-possible"></a><span data-ttu-id="55db3-116">Textknoten können nebeneinander liegen</span><span class="sxs-lookup"><span data-stu-id="55db3-116">Adjacent Text Nodes are Possible</span></span>  
 <span data-ttu-id="55db3-117">In einer Reihe von XML-Programmiermodellen werden nebeneinander liegende Textknoten immer zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="55db3-117">In a number of XML programming models, adjacent text nodes are always merged.</span></span> <span data-ttu-id="55db3-118">Dies wird mitunter als Normalisierung von Textknoten bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="55db3-118">This is sometimes called normalization of text nodes.</span></span> <span data-ttu-id="55db3-119">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] findet keine Normalisierung von Textknoten statt.</span><span class="sxs-lookup"><span data-stu-id="55db3-119">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] does not normalize text nodes.</span></span> <span data-ttu-id="55db3-120">Wenn Sie einem Element zwei Textknoten hinzufügen, erhalten Sie zwei nebeneinander liegende Textknoten.</span><span class="sxs-lookup"><span data-stu-id="55db3-120">If you add two text nodes to the same element, it will result in adjacent text nodes.</span></span> <span data-ttu-id="55db3-121">Wird jedoch Inhalt in Form einer Zeichenfolge statt als <xref:System.Xml.Linq.XText>-Knoten hinzugefügt, kann [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] die Zeichenfolge mit einem angrenzenden Textknoten zusammenführen.</span><span class="sxs-lookup"><span data-stu-id="55db3-121">However, if you add content specified as a string rather than as an <xref:System.Xml.Linq.XText> node, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] might merge the string with an adjacent text node.</span></span>  
  
 <span data-ttu-id="55db3-122">Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="55db3-122">The following example demonstrates this:</span></span>  
  
```csharp  
XElement xmlTree = new XElement("Root", "Content");  
  
Console.WriteLine(xmlTree.Nodes().OfType<XText>().Count());  
  
// this does not add a new text node  
xmlTree.Add("new content");  
Console.WriteLine(xmlTree.Nodes().OfType<XText>().Count());  
  
// this does add a new, adjacent text node  
xmlTree.Add(new XText("more text"));  
Console.WriteLine(xmlTree.Nodes().OfType<XText>().Count());  
```  
  
 <span data-ttu-id="55db3-123">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="55db3-123">This example produces the following output:</span></span>  
  
```output  
1  
1  
2  
```  
  
### <a name="empty-text-nodes-are-possible"></a><span data-ttu-id="55db3-124">Textknoten können leer sein</span><span class="sxs-lookup"><span data-stu-id="55db3-124">Empty Text Nodes are Possible</span></span>  
 <span data-ttu-id="55db3-125">In einigen XML-Programmiermodellen ist garantiert, dass Textknoten keine leere Zeichenfolge enthalten.</span><span class="sxs-lookup"><span data-stu-id="55db3-125">In some XML programming models, text nodes are guaranteed to not contain the empty string.</span></span> <span data-ttu-id="55db3-126">Der Grund dafür ist, dass ein Textknoten keine Auswirkungen auf die Serialisierung des XML-Codes haben.</span><span class="sxs-lookup"><span data-stu-id="55db3-126">The reasoning is that such a text node has no impact on serialization of the XML.</span></span> <span data-ttu-id="55db3-127">Aber aus demselben Grund, aus dem Textknoten nebeneinander liegen können, wird der Textknoten auch nicht gelöscht, wenn Sie den Text aus ihm entfernen, indem Sie eine leere Zeichenfolge als Wert für den Textknoten festlegen.</span><span class="sxs-lookup"><span data-stu-id="55db3-127">However, for the same reason that adjacent text nodes are possible, if you remove the text from a text node by setting its value to the empty string, the text node itself will not be deleted.</span></span>  
  
```csharp  
XElement xmlTree = new XElement("Root", "Content");  
XText textNode = xmlTree.Nodes().OfType<XText>().First();  
  
// the following line does not cause the removal of the text node.  
textNode.Value = "";  
  
XText textNode2 = xmlTree.Nodes().OfType<XText>().First();  
Console.WriteLine(">>{0}<<", textNode2);
```  
  
 <span data-ttu-id="55db3-128">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="55db3-128">This example produces the following output:</span></span>  
  
```output  
>><<  
```  
  
### <a name="an-empty-text-node-impacts-serialization"></a><span data-ttu-id="55db3-129">Ein leerer Textknoten wirkt sich auf die Serialisierung aus</span><span class="sxs-lookup"><span data-stu-id="55db3-129">An Empty Text Node Impacts Serialization</span></span>  
 <span data-ttu-id="55db3-130">Wenn ein Element nur einen untergeordneten Textknoten enthält, der leer ist, wird es mit der langen Tagsyntax serialisiert: `<Child></Child>`.</span><span class="sxs-lookup"><span data-stu-id="55db3-130">If an element contains only a child text node that is empty, it is serialized with the long tag syntax: `<Child></Child>`.</span></span> <span data-ttu-id="55db3-131">Wenn ein Element überhaupt keine untergeordneten Knoten enthält, wird es mit der kurzen Tagsyntax serialisiert: `<Child />`.</span><span class="sxs-lookup"><span data-stu-id="55db3-131">If an element contains no child nodes whatsoever, it is serialized with the short tag syntax: `<Child />`.</span></span>  
  
```csharp  
XElement child1 = new XElement("Child1",  
    new XText("")  
);  
XElement child2 = new XElement("Child2");  
Console.WriteLine(child1);  
Console.WriteLine(child2);
```  
  
 <span data-ttu-id="55db3-132">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="55db3-132">This example produces the following output:</span></span>  
  
```xml  
<Child1></Child1>  
<Child2 />  
```  
  
### <a name="namespaces-are-attributes-in-the-linq-to-xml-tree"></a><span data-ttu-id="55db3-133">Namespaces sind Attribute in der LINQ to XML-Struktur</span><span class="sxs-lookup"><span data-stu-id="55db3-133">Namespaces are Attributes in the LINQ to XML Tree</span></span>  
 <span data-ttu-id="55db3-134">Auch wenn Namespacedeklarationen dieselbe Syntax wie Attribute haben, werden Namespacedeklarationen in einigen Programmierschnittstellen, wie XSLT und XPath, nicht als Attribute betrachtet.</span><span class="sxs-lookup"><span data-stu-id="55db3-134">Even though namespace declarations have identical syntax to attributes, in some programming interfaces, such as XSLT and XPath, namespace declarations are not considered to be attributes.</span></span> <span data-ttu-id="55db3-135">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] werden Namespaces jedoch als <xref:System.Xml.Linq.XAttribute>-Objekte in der XML-Struktur gespeichert.</span><span class="sxs-lookup"><span data-stu-id="55db3-135">However, in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], namespaces are stored as <xref:System.Xml.Linq.XAttribute> objects in the XML tree.</span></span> <span data-ttu-id="55db3-136">Wenn Sie die Attribute für ein Element durchlaufen, das eine Namespacedeklaration enthält, wird die Namespacedeklaration als eines der Elemente in der zurückgegebenen Auflistung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="55db3-136">If you iterate through the attributes for an element that contains a namespace declaration, you will see the namespace declaration as one of the items in the returned collection.</span></span>  
  
 <span data-ttu-id="55db3-137">Die <xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A>-Eigenschaft gibt an, ob ein Attribut eine Namespacedeklaration ist.</span><span class="sxs-lookup"><span data-stu-id="55db3-137">The <xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A> property indicates whether an attribute is a namespace declaration.</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root  
    xmlns='http://www.adventure-works.com'  
    xmlns:fc='www.fourthcoffee.com'  
    AnAttribute='abc'/>");  
foreach (XAttribute att in root.Attributes())  
    Console.WriteLine("{0}  IsNamespaceDeclaration:{1}", att, att.IsNamespaceDeclaration);  
```  
  
 <span data-ttu-id="55db3-138">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="55db3-138">This example produces the following output:</span></span>  
  
```output  
xmlns="http://www.adventure-works.com"  IsNamespaceDeclaration:True  
xmlns:fc="www.fourthcoffee.com"  IsNamespaceDeclaration:True  
AnAttribute="abc"  IsNamespaceDeclaration:False  
```  
  
### <a name="xpath-axis-methods-do-not-return-child-white-space-of-xdocument"></a><span data-ttu-id="55db3-139">XPath-Achsenmethoden geben keinen untergeordneten XDocument-Leerraum zurück</span><span class="sxs-lookup"><span data-stu-id="55db3-139">XPath Axis Methods Do Not Return Child White Space of XDocument</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="55db3-140">ermöglicht untergeordnete Textknoten eines <xref:System.Xml.Linq.XDocument>, solange die Textknoten nur Leerraum enthalten.</span><span class="sxs-lookup"><span data-stu-id="55db3-140">allows for child text nodes of an <xref:System.Xml.Linq.XDocument>, as long as the text nodes contain only white space.</span></span> <span data-ttu-id="55db3-141">Das XPath-Objektmodell sieht jedoch keinen Leerraum als untergeordnete Knoten eines Dokuments vor. Das hat zur Folge, dass beim Durchlaufen der untergeordneten Elemente eines <xref:System.Xml.Linq.XDocument> mit der <xref:System.Xml.Linq.XContainer.Nodes%2A>-Achse Leerraumtextknoten zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="55db3-141">However, the XPath object model does not include white space as child nodes of a document, so when you iterate through the children of an <xref:System.Xml.Linq.XDocument> using the <xref:System.Xml.Linq.XContainer.Nodes%2A> axis, white-space text nodes will be returned.</span></span> <span data-ttu-id="55db3-142">Werden dagegen die untergeordneten Elemente eines <xref:System.Xml.Linq.XDocument> mit den XPath-Achsenmethoden durchlaufen, erfolgt keine Rückgabe von Leerraumtextknoten.</span><span class="sxs-lookup"><span data-stu-id="55db3-142">However, when you iterate through the children of an <xref:System.Xml.Linq.XDocument> using the XPath axis methods, white-space text nodes will not be returned.</span></span>  
  
```csharp  
// Create a document with some white-space child nodes of the document.  
XDocument root = XDocument.Parse(  
@"<?xml version='1.0' encoding='utf-8' standalone='yes'?>  
  
<Root/>  
  
<!--a comment-->  
", LoadOptions.PreserveWhitespace);  
  
// count the white-space child nodes using LINQ to XML  
Console.WriteLine(root.Nodes().OfType<XText>().Count());  
  
// count the white-space child nodes using XPathEvaluate  
Console.WriteLine(((IEnumerable)root.XPathEvaluate("text()")).OfType<XText>().Count());
```  
  
 <span data-ttu-id="55db3-143">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="55db3-143">This example produces the following output:</span></span>  
  
```output  
3  
0  
```  
  
### <a name="xdeclaration-objects-are-not-nodes"></a><span data-ttu-id="55db3-144">XDeclaration-Objekte sind keine Knoten</span><span class="sxs-lookup"><span data-stu-id="55db3-144">XDeclaration Objects are not Nodes</span></span>  
 <span data-ttu-id="55db3-145">Wenn Sie die untergeordneten Elemente eines <xref:System.Xml.Linq.XDocument>-Objekts durchlaufen, wird das XML-Deklarationsobjekt nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="55db3-145">When you iterate through the children nodes of an <xref:System.Xml.Linq.XDocument>, you will not see the XML declaration object.</span></span> <span data-ttu-id="55db3-146">Es ist kein untergeordneter Knoten des Dokuments, sondern eine seiner Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="55db3-146">It is a property of the document, not a child node of it.</span></span>  
  
```csharp  
XDocument doc = new XDocument(  
    new XDeclaration("1.0", "utf-8", "yes"),  
    new XElement("Root")  
);  
doc.Save("Temp.xml");  
Console.WriteLine(File.ReadAllText("Temp.xml"));  
  
// this shows that there is only one child node of the document  
Console.WriteLine(doc.Nodes().Count());  
```  
  
 <span data-ttu-id="55db3-147">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="55db3-147">This example produces the following output:</span></span>  
  
```output  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<Root />  
1  
```  
  