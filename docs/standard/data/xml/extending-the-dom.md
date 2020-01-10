---
title: Erweitern des DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: b5489c96-4afd-439a-a25d-fc82eb4a148d
ms.openlocfilehash: 41b6959843e866b89da46a9cedfb54a2f5ed001a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710881"
---
# <a name="extending-the-dom"></a><span data-ttu-id="8ec95-102">Erweitern des DOM</span><span class="sxs-lookup"><span data-stu-id="8ec95-102">Extending the DOM</span></span>

<span data-ttu-id="8ec95-103">Microsoft .NET Framework enthält einen Basisgruppe an Klassen, die eine Implementierung des XML-DOM (Document Object Model) bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="8ec95-103">The Microsoft .NET Framework includes a base set of classes that provides an implementation of the XML Document Object Model (DOM).</span></span> <span data-ttu-id="8ec95-104">Die <xref:System.Xml.XmlNode>-Klasse und deren abgeleitete Klassen stellen Methoden und Eigenschaften zum Navigieren, Abfragen und Ändern des Inhalts und der Struktur von XML-Dokumenten bereit.</span><span class="sxs-lookup"><span data-stu-id="8ec95-104">The <xref:System.Xml.XmlNode>, and its derived classes, provides methods and properties that allow you to navigate, query, and modify the content and structure of an XML document.</span></span>

<span data-ttu-id="8ec95-105">Wenn XML-Inhalte mit einem DOM in den Speicher geladen werden, entalten die erstellten Knoten Informationen wie Knotenname, Knotentyp usw.</span><span class="sxs-lookup"><span data-stu-id="8ec95-105">When XML content is loaded into memory using the DOM, the nodes created contain information such as node name, node type, and so on.</span></span> <span data-ttu-id="8ec95-106">Es kann durchaus vorkommen, dass Sie bestimmte Knoteninformationen benötigen, die von den Basisklassen nicht bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8ec95-106">There may be occasions where you require specific node information that the base classes do not provide.</span></span> <span data-ttu-id="8ec95-107">Sie möchten beispielsweise eventuell die Zeilennummer und die Position des Knotens wissen.</span><span class="sxs-lookup"><span data-stu-id="8ec95-107">For example, you may want to see the line number and position of the node.</span></span> <span data-ttu-id="8ec95-108">In diesem Fall können Sie von den vorhandenen DOM-Klassen neue Klassen ableiten und zusätzliche Funktionalitäten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8ec95-108">In this case, you can derive new classes from the existing DOM classes and add additional functionality.</span></span>

<span data-ttu-id="8ec95-109">Beim Ableiten von neuen Klassen existieren zwei allgemeine Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="8ec95-109">There are two general guidelines when deriving new classes:</span></span>

- <span data-ttu-id="8ec95-110">Es wird empfohlen, niemals Klassen von der <xref:System.Xml.XmlNode>-Klasse abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="8ec95-110">It is recommended that you never derive from the <xref:System.Xml.XmlNode> class.</span></span> <span data-ttu-id="8ec95-111">Stattdessen wird empfohlen, Klassen von der Klasse abzuleiten, die dem Knotentyp entspricht, an dem Sie interessiert sind.</span><span class="sxs-lookup"><span data-stu-id="8ec95-111">Instead, it is recommended that you derive classes from the class corresponding to the node type that you are interested in.</span></span> <span data-ttu-id="8ec95-112">Wenn Sie beispielsweise zusätzliche Informationen über Attributknoten zurückgeben möchten, können Sie Klassen von der <xref:System.Xml.XmlAttribute>-Klasse ableiten.</span><span class="sxs-lookup"><span data-stu-id="8ec95-112">For example, if you want to return additional information on attribute nodes, you can derive from the <xref:System.Xml.XmlAttribute> class.</span></span>

- <span data-ttu-id="8ec95-113">Mit Ausnahme der Methoden zur Knotenerstellung wird empfohlen, beim Überschreiben einer Funktion immer die Basisversion der Funktion aufzurufen und erst dann zusätzliche Verarbeitungen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="8ec95-113">Except for the node creation methods, it is recommended that when overriding a function, you should always call the base version of the function and then add any additional processing.</span></span>

## <a name="creating-your-own-node-instances"></a><span data-ttu-id="8ec95-114">Erstellen von eigenen Knoteninstanzen</span><span class="sxs-lookup"><span data-stu-id="8ec95-114">Creating Your Own Node Instances</span></span>

<span data-ttu-id="8ec95-115">Die <xref:System.Xml.XmlDocument>-Klasse enthält Methoden zur Knotenerstellung.</span><span class="sxs-lookup"><span data-stu-id="8ec95-115">The <xref:System.Xml.XmlDocument> class contains node creation methods.</span></span> <span data-ttu-id="8ec95-116">Beim Laden einer XML-Datei werden diese Methoden zur Erstellung der Knoten aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8ec95-116">When an XML file is loaded, these methods are called to create the nodes.</span></span> <span data-ttu-id="8ec95-117">Sie können diese Methoden überschreiben, damit die Knoteninstanzen beim Laden eines Dokuments erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="8ec95-117">You can override these methods so that your node instances are created when a document is loaded.</span></span> <span data-ttu-id="8ec95-118">Wenn beispielsweise die <xref:System.Xml.XmlElement>-Klasse erweitert wurde, wird die <xref:System.Xml.XmlDocument>-Klasse geerbt und die <xref:System.Xml.XmlDocument.CreateElement%2A>-Methode überschrieben.</span><span class="sxs-lookup"><span data-stu-id="8ec95-118">For example, if you have extended the <xref:System.Xml.XmlElement> class, you would inherit the <xref:System.Xml.XmlDocument> class and override the <xref:System.Xml.XmlDocument.CreateElement%2A> method.</span></span>

<span data-ttu-id="8ec95-119">Im folgenden Beispiel wird dargestellt, wie die <xref:System.Xml.XmlDocument.CreateElement%2A>-Methode überschrieben werden muss, damit die Implementierung der <xref:System.Xml.XmlElement>-Klasse zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8ec95-119">The following example shows how to override the <xref:System.Xml.XmlDocument.CreateElement%2A> method to return your implementation of the <xref:System.Xml.XmlElement> class.</span></span>

```vb
Class LineInfoDocument
    Inherits XmlDocument
        Public Overrides Function CreateElement(prefix As String, localname As String, nsURI As String) As XmlElement
        Dim elem As New LineInfoElement(prefix, localname, nsURI, Me)
        Return elem
    End Function 'CreateElement
End Class 'LineInfoDocument
```

```csharp
class LineInfoDocument : XmlDocument 
{
    public override XmlElement CreateElement(string prefix, string localname, string nsURI) 
    {
        LineInfoElement elem = new LineInfoElement(prefix, localname, nsURI, this);
        return elem;
    }
}
```

## <a name="extending-a-class"></a><span data-ttu-id="8ec95-120">Erweitern einer Klasse</span><span class="sxs-lookup"><span data-stu-id="8ec95-120">Extending a Class</span></span>

<span data-ttu-id="8ec95-121">Um eine Klasse zu erweitern, leiten Sie die Klasse von einer der vorhandenen DOM-Klassen ab.</span><span class="sxs-lookup"><span data-stu-id="8ec95-121">To extend a class, derive your class from one of the existing DOM classes.</span></span> <span data-ttu-id="8ec95-122">Anschließend können Sie eine der virtuellen Methoden oder Eigenschaften in der Basisklasse überschreiben oder Ihre eigene Klasse hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8ec95-122">You can then override any of the virtual methods or properties in the base class, or add your own.</span></span>

<span data-ttu-id="8ec95-123">Im folgenden Beispiel wird eine neue Klasse erstellt, die die <xref:System.Xml.XmlElement>-Klasse und die <xref:System.Xml.IXmlLineInfo>-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="8ec95-123">In the following example, a new class is created, which implements the <xref:System.Xml.XmlElement> class and the <xref:System.Xml.IXmlLineInfo> interface.</span></span> <span data-ttu-id="8ec95-124">Es werden zusätzliche Methoden und Eigenschaften definiert, mit denen Benutzer Zeileninformationen erfassen können.</span><span class="sxs-lookup"><span data-stu-id="8ec95-124">Additional methods and properties are defined which allows users to gather line information.</span></span>

```vb
Class LineInfoElement
   Inherits XmlElement
   Implements IXmlLineInfo
   Private lineNumber As Integer = 0
   Private linePosition As Integer = 0

   Friend Sub New(prefix As String, localname As String, nsURI As String, doc As XmlDocument)
      MyBase.New(prefix, localname, nsURI, doc)
      CType(doc, LineInfoDocument).IncrementElementCount()
   End Sub

   Public Sub SetLineInfo(linenum As Integer, linepos As Integer)
      lineNumber = linenum
      linePosition = linepos
   End Sub

   Public ReadOnly Property LineNumber() As Integer
      Get
         Return lineNumber
      End Get
   End Property

   Public ReadOnly Property LinePosition() As Integer
      Get
         Return linePosition
      End Get
   End Property

   Public Function HasLineInfo() As Boolean
      Return True
   End Function
End Class ' End LineInfoElement class.
```

```csharp
class LineInfoElement : XmlElement, IXmlLineInfo {
   int lineNumber = 0;
   int linePosition = 0;
   internal LineInfoElement( string prefix, string localname, string nsURI, XmlDocument doc ) : base( prefix, localname, nsURI, doc ) {
       ( (LineInfoDocument)doc ).IncrementElementCount();
  }
  public void SetLineInfo( int linenum, int linepos ) {
      lineNumber = linenum;
      linePosition = linepos;
  }
  public int LineNumber {
     get {
       return lineNumber;
     }
  }
  public int LinePosition {
      get {
        return linePosition;
      }
  }
  public bool HasLineInfo() {
    return true;
  }
} // End LineInfoElement class.
```

### <a name="example"></a><span data-ttu-id="8ec95-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8ec95-125">Example</span></span>

<span data-ttu-id="8ec95-126">Im folgenden Beispiel wird die Anzahl der Elemente in einem XML-Dokument gezählt:</span><span class="sxs-lookup"><span data-stu-id="8ec95-126">The following example counts the number of elements in an XML document:</span></span>

```vb
Imports System.Xml
Imports System.IO

Class LineInfoDocument
   Inherits XmlDocument

   Private elementCount As Integer

   Friend Sub New()
      elementCount = 0
   End Sub

   Public Overrides Function CreateElement(prefix As String, localname As String, nsURI As String) As XmlElement
      Dim elem As New LineInfoElement(prefix, localname, nsURI, Me)
      Return elem
   End Function

   Public Sub IncrementElementCount()
      elementCount += 1
   End Sub

   Public Function GetCount() As Integer
      Return elementCount
   End Function
End Class 'End LineInfoDocument class.

Class LineInfoElement
   Inherits XmlElement

   Friend Sub New(prefix As String, localname As String, nsURI As String, doc As XmlDocument)
      MyBase.New(prefix, localname, nsURI, doc)
      CType(doc, LineInfoDocument).IncrementElementCount()
   End Sub 'New
End Class 'LineInfoElement
 _ 'End LineInfoElement class.

Public Class Test

   Private filename As [String] = "book.xml"

   Public Shared Sub Main()

      Dim doc As New LineInfoDocument()
      doc.Load(filename)
      Console.WriteLine("Number of elements in {0}: {1}", filename, doc.GetCount())
   End Sub
End Class
```

```csharp
using System;
using System.Xml;
using System.IO;

class LineInfoDocument : XmlDocument {

  int elementCount;
  internal LineInfoDocument():base() {
    elementCount = 0;
  }

  public override XmlElement CreateElement( string prefix, string localname, string nsURI) {
    LineInfoElement elem = new LineInfoElement(prefix, localname, nsURI, this );
    return elem;
  }

  public void IncrementElementCount() {
     elementCount++;
  }

  public int GetCount() {
     return elementCount;
  }
} // End LineInfoDocument class.

class LineInfoElement:XmlElement {

    internal LineInfoElement( string prefix, string localname, string nsURI, XmlDocument doc ):base( prefix,localname,nsURI, doc ){
      ((LineInfoDocument)doc).IncrementElementCount();
    }
} // End LineInfoElement class.

public class Test {

  const String filename = "book.xml";
  public static void Main() {

     LineInfoDocument doc =new LineInfoDocument();
     doc.Load(filename);
     Console.WriteLine("Number of elements in {0}: {1}", filename, doc.GetCount());

  }
}
```

#### <a name="input"></a><span data-ttu-id="8ec95-127">Input</span><span class="sxs-lookup"><span data-stu-id="8ec95-127">Input</span></span>

<span data-ttu-id="8ec95-128">book.xml</span><span class="sxs-lookup"><span data-stu-id="8ec95-128">book.xml</span></span>

```xml
<!--sample XML fragment-->
<book genre='novel' ISBN='1-861001-57-5' misc='sale-item'>
  <title>The Handmaid's Tale</title>
  <price>14.95</price>
</book>
```

#### <a name="output"></a><span data-ttu-id="8ec95-129">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="8ec95-129">Output</span></span>

```console
Number of elements in book.xml: 3
```

## <a name="node-event-handler"></a><span data-ttu-id="8ec95-130">Knotenereignishandler</span><span class="sxs-lookup"><span data-stu-id="8ec95-130">Node Event Handler</span></span>

<span data-ttu-id="8ec95-131">Die .NET Framework-Implementierung des DOM enthält auch ein Ereignissystem, mit dem Sie Ereignisse empfangen und behandeln können, wenn Knoten in einem XML-Dokument geändert werden.</span><span class="sxs-lookup"><span data-stu-id="8ec95-131">The .NET Framework implementation of the DOM also includes an event system that enables you to receive and handle events when nodes in an XML document change.</span></span> <span data-ttu-id="8ec95-132">Mit den Klassen <xref:System.Xml.XmlNodeChangedEventHandler> und <xref:System.Xml.XmlNodeChangedEventArgs> können die Ereignisse `NodeChanged`, `NodeChanging`, `NodeInserted`, `NodeInserting`, `NodeRemoved` und `NodeRemoving` aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="8ec95-132">Using the <xref:System.Xml.XmlNodeChangedEventHandler> and <xref:System.Xml.XmlNodeChangedEventArgs> classes, you can capture `NodeChanged`, `NodeChanging`, `NodeInserted`, `NodeInserting`, `NodeRemoved`, and `NodeRemoving` events.</span></span>

<span data-ttu-id="8ec95-133">Der Prozess der Ereignisbehandlung läuft in den abgeleiteten Klassen genauso ab wie in den urspünglichen DOM-Klassen.</span><span class="sxs-lookup"><span data-stu-id="8ec95-133">The event-handling process works exactly the same in derived classes as it would in the original DOM classes.</span></span>

<span data-ttu-id="8ec95-134">Weitere Informationen zur Ereignisbehandlung bei Knoten finden Sie unter [Ereignisse](../../../../docs/standard/events/index.md) und <xref:System.Xml.XmlNodeChangedEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="8ec95-134">For more information regarding node event handling, see [Events](../../../../docs/standard/events/index.md) and <xref:System.Xml.XmlNodeChangedEventHandler>.</span></span>

## <a name="default-attributes-and-the-createelement-method"></a><span data-ttu-id="8ec95-135">Standardattribute und die CreateElement-Methode</span><span class="sxs-lookup"><span data-stu-id="8ec95-135">Default Attributes and the CreateElement Method</span></span>

<span data-ttu-id="8ec95-136">Wenn Sie die <xref:System.Xml.XmlDocument.CreateElement%2A>-Methode in einer abgeleiteten Klasse überschreiben, werden keine Standardattribute hinzugefügt, wenn Sie während der Bearbeitung des Dokuments neue Elemente erstellen.</span><span class="sxs-lookup"><span data-stu-id="8ec95-136">If you are overriding the <xref:System.Xml.XmlDocument.CreateElement%2A> method in a derived class, default attributes are not added when you are creating new elements while editing the document.</span></span> <span data-ttu-id="8ec95-137">Dieses Problem besteht nur während der Bearbeitung.</span><span class="sxs-lookup"><span data-stu-id="8ec95-137">This is only an issue while editing.</span></span> <span data-ttu-id="8ec95-138">Da die <xref:System.Xml.XmlDocument.CreateElement%2A>-Methode für das Hinzufügen von Standardattributen zu einer <xref:System.Xml.XmlDocument>-Klasse verantwortlich ist, müssen Sie die Funktionalität in der <xref:System.Xml.XmlDocument.CreateElement%2A>-Methode codieren.</span><span class="sxs-lookup"><span data-stu-id="8ec95-138">Because the <xref:System.Xml.XmlDocument.CreateElement%2A> method is responsible for adding default attributes to an <xref:System.Xml.XmlDocument>, you must code this functionality in the <xref:System.Xml.XmlDocument.CreateElement%2A> method.</span></span> <span data-ttu-id="8ec95-139">Wenn Sie eine <xref:System.Xml.XmlDocument>-Klasse laden, die Standardattribute enthält, werden diese korrekt behandelt.</span><span class="sxs-lookup"><span data-stu-id="8ec95-139">If you are loading an <xref:System.Xml.XmlDocument> that includes default attributes, they will be handled correctly.</span></span> <span data-ttu-id="8ec95-140">Weitere Informationen zu Standardattributen finden Sie unter [Erstellen neuer Attribute für Elemente im DOM](creating-new-attributes-for-elements-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="8ec95-140">For more information on default attributes, see [Creating New Attributes for Elements in the DOM](creating-new-attributes-for-elements-in-the-dom.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8ec95-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ec95-141">See also</span></span>

- [<span data-ttu-id="8ec95-142">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="8ec95-142">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
