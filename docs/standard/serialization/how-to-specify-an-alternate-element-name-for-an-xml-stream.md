---
title: 'Gewusst wie: Angeben eines alternativen Elementnamens für einen XML-Stream'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XML serialization, overriding
- serialization, overriding
- XML stream, specifying alternate element name for
- overriding XML serialization
- classes, overriding
- overriding classes
ms.assetid: 5cc1c0b0-f94b-4525-9a41-88a582cd6668
ms.openlocfilehash: 6aaff20e2955fc9f121b3e60b14c0bbcf7515660
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159857"
---
# <a name="how-to-specify-an-alternate-element-name-for-an-xml-stream"></a>Gewusst wie: Angeben eines alternativen Elementnamens für einen XML-Stream
  
Mit <xref:System.Xml.Serialization.XmlSerializer> können Sie mehr als einen XML-Stream mit der gleichen Gruppe von Klassen generieren. Dies ist beispielsweise dann sinnvoll, wenn zwei verschiedene XML-Webdienste die gleichen grundlegenden Informationen benötigen, die sich nur in wenigen Details unterscheiden. Stellen Sie sich beispielsweise vor, zwei XML-Webdienste, die Buchbestellungen verarbeiten, erfordern die Angabe von ISBN-Nummern. Ein Dienst verwendet das Tag \<ISBN>, während der zweite das Tag \<BookID> verwendet. Sie verfügen über eine Klasse mit dem Namen von `Book`, die ein Feld namens `ISBN` enthält. In der Standardeinstellung wird beim Serialisieren einer Instanz der `Book`-Klasse der Membername (ISBN) als Name des XML-Elements verwendet. Für den ersten XML-Webdienst entspricht dies dem erwarteten Verhalten. Wenn der XML-Stream jedoch an den zweiten XML-Webdienst gesendet werden soll, muss die Serialisierung überschrieben werden, damit der Elementname des Tags `BookID` lautet.  
  
## <a name="to-create-an-xml-stream-with-an-alternate-element-name"></a>So erstellen Sie einen XML-Stream mit einem alternativen Elementnamen  
  
1. Erstellen Sie eine Instanz der <xref:System.Xml.Serialization.XmlElementAttribute>-Klasse.  
  
2. Legen Sie die <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A>-Eigenschaft des <xref:System.Xml.Serialization.XmlElementAttribute>-Objekts auf "BookID" fest.  
  
3. Erstellen Sie eine Instanz der <xref:System.Xml.Serialization.XmlAttributes>-Klasse.  
  
4. Fügen Sie das `XmlElementAttribute`-Objekt der Sammlung hinzu, auf die über die <xref:System.Xml.Serialization.XmlAttributes.XmlElements%2A>-Eigenschaft von <xref:System.Xml.Serialization.XmlAttributes> zugegriffen wird.  
  
5. Erstellen Sie eine Instanz der <xref:System.Xml.Serialization.XmlAttributeOverrides>-Klasse.  
  
6. Fügen Sie das `XmlAttributes`-Objekt dem <xref:System.Xml.Serialization.XmlAttributeOverrides>-Objekt hinzu, und geben Sie dabei sowohl den Typ des zu überschreibenden Objekts als auch den Namen des Members an, das überschrieben wird.  
  
7. Erstellen Sie eine Instanz der `XmlSerializer`-Klasse mit `XmlAttributeOverrides`.  
  
8. Erstellen Sie eine Instanz der `Book`-Klasse, und serialisieren oder deserialisieren Sie diese Instanz.  
  
## <a name="example"></a>Beispiel  
  
```vb  
Public Class SerializeOverride()  
    ' Creates an XmlElementAttribute with the alternate name.  
    Dim myElementAttribute As XmlElementAttribute = _  
    New XmlElementAttribute()  
    myElementAttribute.ElementName = "BookID"  
    Dim myAttributes As XmlAttributes = New XmlAttributes()  
    myAttributes.XmlElements.Add(myElementAttribute)  
    Dim myOverrides As XmlAttributeOverrides = New XmlAttributeOverrides()  
    myOverrides.Add(typeof(Book), "ISBN", myAttributes)  
    Dim mySerializer As XmlSerializer = _  
    New XmlSerializer(GetType(Book), myOverrides)  
    Dim b As Book = New Book()  
    b.ISBN = "123456789"  
    ' Creates a StreamWriter to write the XML stream to.  
    Dim writer As StreamWriter = New StreamWriter("Book.xml")  
    mySerializer.Serialize(writer, b);  
End Class  
```  
  
```csharp  
public class SerializeOverride()  
{  
    // Creates an XmlElementAttribute with the alternate name.  
    XmlElementAttribute myElementAttribute = new XmlElementAttribute();  
    myElementAttribute.ElementName = "BookID";  
    XmlAttributes myAttributes = new XmlAttributes();  
    myAttributes.XmlElements.Add(myElementAttribute);  
    XmlAttributeOverrides myOverrides = new XmlAttributeOverrides();  
    myOverrides.Add(typeof(Book), "ISBN", myAttributes);  
    XmlSerializer mySerializer =
    new XmlSerializer(typeof(Book), myOverrides)  
    Book b = new Book();  
    b.ISBN = "123456789"  
    // Creates a StreamWriter to write the XML stream to.  
    StreamWriter writer = new StreamWriter("Book.xml");  
    mySerializer.Serialize(writer, b);  
}  
```  
  
 Der XML-Stream könnte wie folgt aussehen.  
  
```xml  
<Book>  
    <BookID>123456789</BookID>  
</Book>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Serialization.XmlElementAttribute>
- <xref:System.Xml.Serialization.XmlAttributes>
- <xref:System.Xml.Serialization.XmlAttributeOverrides>
- [XML- und SOAP-Serialisierung](../../../docs/standard/serialization/xml-and-soap-serialization.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [Vorgehensweise: Serialisieren eines Objekts](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [Vorgehensweise: Deserialisieren eines Objekts](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
