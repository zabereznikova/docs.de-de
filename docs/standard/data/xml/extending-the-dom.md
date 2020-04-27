---
title: Erweitern des DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: b5489c96-4afd-439a-a25d-fc82eb4a148d
ms.openlocfilehash: 11c7e8c8d2ea3b49fe73ab4dde4e2ccc8bc917ff
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159675"
---
# <a name="extending-the-dom"></a>Erweitern des DOM

Microsoft .NET Framework enthält einen Basisgruppe an Klassen, die eine Implementierung des XML-DOM (Document Object Model) bereitstellt. Die <xref:System.Xml.XmlNode>-Klasse und deren abgeleitete Klassen stellen Methoden und Eigenschaften zum Navigieren, Abfragen und Ändern des Inhalts und der Struktur von XML-Dokumenten bereit.

Wenn XML-Inhalte mit einem DOM in den Speicher geladen werden, entalten die erstellten Knoten Informationen wie Knotenname, Knotentyp usw. Es kann durchaus vorkommen, dass Sie bestimmte Knoteninformationen benötigen, die von den Basisklassen nicht bereitgestellt werden. Sie möchten beispielsweise eventuell die Zeilennummer und die Position des Knotens wissen. In diesem Fall können Sie von den vorhandenen DOM-Klassen neue Klassen ableiten und zusätzliche Funktionalitäten hinzufügen.

Beim Ableiten von neuen Klassen existieren zwei allgemeine Richtlinien:

- Es wird empfohlen, niemals Klassen von der <xref:System.Xml.XmlNode>-Klasse abzuleiten. Stattdessen wird empfohlen, Klassen von der Klasse abzuleiten, die dem Knotentyp entspricht, an dem Sie interessiert sind. Wenn Sie beispielsweise zusätzliche Informationen über Attributknoten zurückgeben möchten, können Sie Klassen von der <xref:System.Xml.XmlAttribute>-Klasse ableiten.

- Mit Ausnahme der Methoden zur Knotenerstellung wird empfohlen, beim Überschreiben einer Funktion immer die Basisversion der Funktion aufzurufen und erst dann zusätzliche Verarbeitungen hinzuzufügen.

## <a name="creating-your-own-node-instances"></a>Erstellen von eigenen Knoteninstanzen

Die <xref:System.Xml.XmlDocument>-Klasse enthält Methoden zur Knotenerstellung. Beim Laden einer XML-Datei werden diese Methoden zur Erstellung der Knoten aufgerufen. Sie können diese Methoden überschreiben, damit die Knoteninstanzen beim Laden eines Dokuments erstellt werden. Wenn beispielsweise die <xref:System.Xml.XmlElement>-Klasse erweitert wurde, wird die <xref:System.Xml.XmlDocument>-Klasse geerbt und die <xref:System.Xml.XmlDocument.CreateElement%2A>-Methode überschrieben.

Im folgenden Beispiel wird dargestellt, wie die <xref:System.Xml.XmlDocument.CreateElement%2A>-Methode überschrieben werden muss, damit die Implementierung der <xref:System.Xml.XmlElement>-Klasse zurückgegeben wird.

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

## <a name="extending-a-class"></a>Erweitern einer Klasse

Um eine Klasse zu erweitern, leiten Sie die Klasse von einer der vorhandenen DOM-Klassen ab. Anschließend können Sie eine der virtuellen Methoden oder Eigenschaften in der Basisklasse überschreiben oder Ihre eigene Klasse hinzufügen.

Im folgenden Beispiel wird eine neue Klasse erstellt, die die <xref:System.Xml.XmlElement>-Klasse und die <xref:System.Xml.IXmlLineInfo>-Schnittstelle implementiert. Es werden zusätzliche Methoden und Eigenschaften definiert, mit denen Benutzer Zeileninformationen erfassen können.

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

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Anzahl der Elemente in einem XML-Dokument gezählt:

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

#### <a name="input"></a>Eingabe

book.xml

```xml
<!--sample XML fragment-->
<book genre='novel' ISBN='1-861001-57-5' misc='sale-item'>
  <title>The Handmaid's Tale</title>
  <price>14.95</price>
</book>
```

#### <a name="output"></a>Output

```console
Number of elements in book.xml: 3
```

## <a name="node-event-handler"></a>Knotenereignishandler

Die .NET Framework-Implementierung des DOM enthält auch ein Ereignissystem, mit dem Sie Ereignisse empfangen und behandeln können, wenn Knoten in einem XML-Dokument geändert werden. Mit den Klassen <xref:System.Xml.XmlNodeChangedEventHandler> und <xref:System.Xml.XmlNodeChangedEventArgs> können die Ereignisse `NodeChanged`, `NodeChanging`, `NodeInserted`, `NodeInserting`, `NodeRemoved` und `NodeRemoving` aufgezeichnet werden.

Der Prozess der Ereignisbehandlung läuft in den abgeleiteten Klassen genauso ab wie in den urspünglichen DOM-Klassen.

Weitere Informationen zur Ereignisbehandlung bei Knoten finden Sie unter [Ereignisse](../../../../docs/standard/events/index.md) und <xref:System.Xml.XmlNodeChangedEventHandler>.

## <a name="default-attributes-and-the-createelement-method"></a>Standardattribute und die CreateElement-Methode

Wenn Sie die <xref:System.Xml.XmlDocument.CreateElement%2A>-Methode in einer abgeleiteten Klasse überschreiben, werden keine Standardattribute hinzugefügt, wenn Sie während der Bearbeitung des Dokuments neue Elemente erstellen. Dieses Problem besteht nur während der Bearbeitung. Da die <xref:System.Xml.XmlDocument.CreateElement%2A>-Methode für das Hinzufügen von Standardattributen zu einer <xref:System.Xml.XmlDocument>-Klasse verantwortlich ist, müssen Sie die Funktionalität in der <xref:System.Xml.XmlDocument.CreateElement%2A>-Methode codieren. Wenn Sie eine <xref:System.Xml.XmlDocument>-Klasse laden, die Standardattribute enthält, werden diese korrekt behandelt. Weitere Informationen zu Standardattributen finden Sie unter [Erstellen neuer Attribute für Elemente im DOM](creating-new-attributes-for-elements-in-the-dom.md).

## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](xml-document-object-model-dom.md)
