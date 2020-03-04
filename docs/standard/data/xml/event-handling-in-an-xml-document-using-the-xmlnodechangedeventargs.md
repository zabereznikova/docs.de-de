---
title: Ereignisbehandlung in einem XML-Dokument mit "XmlNodeChangedEventArgs"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 0fe844e3-5b6f-4fe7-ad15-22459501738b
ms.openlocfilehash: b27c51572b1ba83480d90eba4add7f930715a4e5
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156529"
---
# <a name="event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs"></a>Ereignisbehandlung in einem XML-Dokument mit "XmlNodeChangedEventArgs"
**XmlNodeChangedEventArgs** kapselt die Argumente, die den beim **XmlDocument**-Objekt zur Verarbeitung von Ereignissen registrierten Ereignishandlern übergeben werden. Die folgende Tabelle enthält die Ereignisse und eine Beschreibung der Situation, in der sie ausgelöst werden.  
  
|event|Wird ausgelöst|  
|-----------|-----------|  
|<xref:System.Xml.XmlDocument.NodeInserting>|Wenn ein Knoten, der zum aktuellen Dokument gehört, gerade in einen anderen Knoten eingefügt wird.|  
|<xref:System.Xml.XmlDocument.NodeInserted>|Wenn ein Knoten, der zum aktuellen Dokument gehört, gerade in einen anderen Knoten eingefügt wurde.|  
|<xref:System.Xml.XmlDocument.NodeRemoving>|Wenn ein Knoten, der zum aktuellen Dokument gehört, gerade aus dem Dokument entfernt wird.|  
|<xref:System.Xml.XmlDocument.NodeRemoved>|Wenn ein Knoten, der zum aktuellen Dokument gehört, aus dem übergeordneten Knoten entfernt wurde.|  
|<xref:System.Xml.XmlDocument.NodeChanging>|Wenn der Wert eines Knotens gerade geändert wird.|  
|<xref:System.Xml.XmlDocument.NodeChanged>|Wenn der Wert eines Knotens geändert wurde.|  
  
> [!NOTE]
> Wenn die Speicherauslastung von **XmlDataDocument** vollständig für die **DataSet**-Speicherung optimiert ist, wird durch **XmlDataDocument** bei Änderungen des zugrunde liegenden **DataSet** möglicherweise keines der oben aufgeführten Ereignisse ausgelöst. Wenn diese Ereignisse benötigt werden, muss das ganze **XmlDocument** einmal durchlaufen werden, damit die Speicherauslastung nicht vollständig optimiert wird.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie ein Ereignishandler definiert und dann einem Ereignis hinzugefügt wird.  
  
```vb  
' Attach the event handler, NodeInsertedHandler, to the NodeInserted  
' event.  
Dim doc as XmlDocument = new XmlDocument()  
Dim XmlNodeChgEHdlr as XmlNodeChangedEventHandler = new XmlNodeChangedEventHandler(addressof MyNodeChangedEvent)
AddHandler doc.NodeInserted, XmlNodeChgEHdlr
  
Dim n as XmlNode = doc.CreateElement( "element" )  
Console.WriteLine( "Before Event Inserting" )
  
' This is the point where the new node is being inserted in the tree,  
' and this is the point where the NodeInserted event is raised.  
doc.AppendChild( n )  
Console.WriteLine( "After Event Inserting" )
  
' Define the event handler that handles the NodeInserted event.  
sub NodeInsertedHandler(src as Object, args as XmlNodeChangedEventArgs)  
    Console.WriteLine("Node " + args.Node.Name + " inserted!!")  
end sub  
```  
  
```csharp  
// Attach the event handler, NodeInsertedHandler, to the NodeInserted  
// event.  
XmlDocument doc = new XmlDocument();  
doc.NodeInserted += new XmlNodeChangedEventHandler(NodeInsertedHandler);  
XmlNode n = doc.CreateElement( "element" );  
Console.WriteLine( "Before Event Inserting" );  
  
// This is the point where the new node is being inserted in the tree,  
// and this is the point where the NodeInserted event is raised.  
doc.AppendChild( n );  
Console.WriteLine( "After Event Inserting" );
  
// Define the event handler that handles the NodeInserted event.  
void NodeInsertedHandler(Object src, XmlNodeChangedEventArgs args)  
{  
    Console.WriteLine("Node " + args.Node.Name + " inserted!!");  
}  
```  
  
 Manche DOM-Operationen sind Verbundoperationen, die mehrere Ereignisse auslösen können. **AppendChild** muss den gerade angefügten Knoten möglicherweise auch aus dem übergeordneten Element entfernen. In diesem Fall wird zuerst ein **NodeRemoved**-Ereignis und dann ein **NodeInserted**-Ereignis ausgelöst. Vorgänge (z.B. das Festlegen von **InnerXml**) können zu mehreren Ereignissen führen.  
  
 Im folgenden Codebeispiel wird das Erstellen des Ereignishandlers und die Behandlung des **NodeInserted**-Ereignisses veranschaulicht.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports Microsoft.VisualBasic  
  
Public Class Sample  
  
    Private Const filename As String = "books.xml"  
  
    Shared Sub Main()  
        Dim mySample As Sample = New Sample()  
        mySample.Run(filename)  
    End Sub  
  
    Public Sub Run(ByVal args As String)  
        ' Create and load the XML document.  
        Console.WriteLine("Loading file 0 ...", args)  
        Dim doc As XmlDocument = New XmlDocument()  
        doc.Load(args)  
  
        ' Create the event handlers.  
        Dim XmlNodeChgEHdlr As XmlNodeChangedEventHandler = New XmlNodeChangedEventHandler(AddressOf MyNodeChangedEvent)  
        Dim XmlNodeInsrtEHdlr As XmlNodeChangedEventHandler = New XmlNodeChangedEventHandler(AddressOf MyNodeInsertedEvent)  
        AddHandler doc.NodeChanged, XmlNodeChgEHdlr  
        AddHandler doc.NodeInserted, XmlNodeInsrtEHdlr  
  
        ' Change the book price.  
        doc.DocumentElement.LastChild.InnerText = "5.95"  
  
        ' Add a new element.  
        Dim newElem As XmlElement = doc.CreateElement("style")  
        newElem.InnerText = "hardcover"  
        doc.DocumentElement.AppendChild(newElem)  
  
        Console.WriteLine(Chr(13) + Chr(10) + "Display the modified XML...")  
        Console.WriteLine(doc.OuterXml)  
    End Sub  
  
    ' Handle the NodeChanged event.  
    Public Sub MyNodeChangedEvent(ByVal src As Object, ByVal args As XmlNodeChangedEventArgs)  
        Console.Write("Node Changed Event: <0> changed", args.Node.Name)  
        If Not (args.Node.Value Is Nothing) Then  
            Console.WriteLine(" with value  0", args.Node.Value)  
        Else  
            Console.WriteLine("")  
        End If  
    End Sub  
  
    ' Handle the NodeInserted event.  
    Public Sub MyNodeInsertedEvent(ByVal src As Object, ByVal args As XmlNodeChangedEventArgs)  
        Console.Write("Node Inserted Event: <0> inserted", args.Node.Name)  
        If Not (args.Node.Value Is Nothing) Then  
            Console.WriteLine(" with value 0", args.Node.Value)  
        Else  
            Console.WriteLine("")  
        End If  
    End Sub  
  
End Class        ' End class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
  private const String filename = "books.xml";  
  
  public static void Main()  
  {  
     Sample mySample = new Sample();  
     mySample.Run(filename);  
  }  
  
  public void Run(String args)  
  {  
  
     // Create and load the XML document.  
     Console.WriteLine ("Loading file {0} ...", args);  
     XmlDocument doc = new XmlDocument();  
     doc.Load (args);  
  
     // Create the event handlers.  
     doc.NodeChanged += new XmlNodeChangedEventHandler(this.MyNodeChangedEvent);  
     doc.NodeInserted += new XmlNodeChangedEventHandler(this.MyNodeInsertedEvent);  
  
     // Change the book price.  
     doc.DocumentElement.LastChild.InnerText = "5.95";  
  
     // Add a new element.  
     XmlElement newElem = doc.CreateElement("style");  
     newElem.InnerText = "hardcover";  
     doc.DocumentElement.AppendChild(newElem);  
  
     Console.WriteLine("\r\nDisplay the modified XML...");  
     Console.WriteLine(doc.OuterXml);
  
  }  
  
  // Handle the NodeChanged event.  
  public void MyNodeChangedEvent(Object src, XmlNodeChangedEventArgs args)  
  {  
     Console.Write("Node Changed Event: <{0}> changed", args.Node.Name);  
     if (args.Node.Value != null)  
     {  
        Console.WriteLine(" with value  {0}", args.Node.Value);  
     }  
     else  
       Console.WriteLine("");  
  }  
  
  // Handle the NodeInserted event.  
  public void MyNodeInsertedEvent(Object src, XmlNodeChangedEventArgs args)  
  {  
     Console.Write("Node Inserted Event: <{0}> inserted", args.Node.Name);  
     if (args.Node.Value != null)  
     {  
        Console.WriteLine(" with value {0}", args.Node.Value);  
     }  
     else  
        Console.WriteLine("");  
  }  
  
} // End class
```  
  
 Weitere Informationen finden Sie unter <xref:System.Xml.XmlNodeChangedEventArgs> und <xref:System.Xml.XmlNodeChangedEventHandler>.  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
