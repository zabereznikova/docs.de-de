---
title: 'Vorgehensweise: Steuern der Serialisierung abgeleiteter Klassen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: caa92596-9e15-4d91-acbe-56911ef47a84
ms.openlocfilehash: af19981fd7cfeda3e8e985fa991fd7fdf2476b42
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159922"
---
# <a name="how-to-control-serialization-of-derived-classes"></a><span data-ttu-id="502ae-102">Vorgehensweise: Steuern der Serialisierung abgeleiteter Klassen</span><span class="sxs-lookup"><span data-stu-id="502ae-102">How to: Control Serialization of Derived Classes</span></span>
<span data-ttu-id="502ae-103">Neben der Verwendung des **XmlElementAttribute**-Attributs zum Ändern eines XML-Elementnamens lässt sich die Objektserialisierung auch auf andere Weise anpassen.</span><span class="sxs-lookup"><span data-stu-id="502ae-103">Using the **XmlElementAttribute** attribute to change the name of an XML element is not the only way to customize object serialization.</span></span> <span data-ttu-id="502ae-104">Sie können den XML-Stream ebenfalls anpassen, indem Sie von einer vorhandenen Klasse ableiten und die <xref:System.Xml.Serialization.XmlSerializer>-Instanz anweisen, wie die neue Klasse serialisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="502ae-104">You can also customize the XML stream by deriving from an existing class and instructing the <xref:System.Xml.Serialization.XmlSerializer> instance how to serialize the new class.</span></span>  
  
 <span data-ttu-id="502ae-105">Beispielsweise können Sie im Fall einer `Book`-Klasse von dieser Klasse ableiten und eine `ExpandedBook`-Klasse erstellen, die über zusätzliche Eigenschaften verfügt.</span><span class="sxs-lookup"><span data-stu-id="502ae-105">For example, given a `Book` class, you can derive from it and create an `ExpandedBook` class that has a few more properties.</span></span> <span data-ttu-id="502ae-106">Sie müssen **XmlSerializer** jedoch anweisen, den abgeleiteten Typ beim Serialisieren oder Deserialisieren zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="502ae-106">However, you must instruct the **XmlSerializer** to accept the derived type when serializing or deserializing.</span></span> <span data-ttu-id="502ae-107">Erstellen Sie hierzu eine <xref:System.Xml.Serialization.XmlElementAttribute>-Instanz, und legen Sie deren **Typ**-Eigenschaft auf den Typ der abgeleiteten Klasse fest.</span><span class="sxs-lookup"><span data-stu-id="502ae-107">This can be done by creating a <xref:System.Xml.Serialization.XmlElementAttribute> instance and setting its **Type** property to the derived class type.</span></span> <span data-ttu-id="502ae-108">Fügen Sie **XmlElementAttribute** zu einer <xref:System.Xml.Serialization.XmlAttributes>-Instanz hinzu.</span><span class="sxs-lookup"><span data-stu-id="502ae-108">Add the **XmlElementAttribute** to a <xref:System.Xml.Serialization.XmlAttributes> instance.</span></span> <span data-ttu-id="502ae-109">Fügen Sie dann **XmlAttributes** zu einer <xref:System.Xml.Serialization.XmlAttributeOverrides>-Instanz hinzu, und geben Sie dabei sowohl den Typ des zu überschreibenden Objekts als auch den Namen des Members an, der die abgeleitete Klasse akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="502ae-109">Then add the **XmlAttributes** to a <xref:System.Xml.Serialization.XmlAttributeOverrides> instance, specifying the type being overridden and the name of the member that accepts the derived class.</span></span> <span data-ttu-id="502ae-110">Dies wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="502ae-110">This is shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="502ae-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="502ae-111">Example</span></span>  
  
```vb  
Public Class Orders  
    public Books() As Book  
End Class
  
Public Class Book  
    public ISBN As String
End Class  
  
Public Class ExpandedBook  
    Inherits Book  
    public NewEdition As Boolean  
End Class  
  
Public Class Run  
    Shared Sub Main()  
        Dim t As Run = New Run()  
        t.SerializeObject("Book.xml")  
        t.DeserializeObject("Book.xml")  
    End Sub  
  
    Public Sub SerializeObject(filename As String)  
        ' Each overridden field, property, or type requires
        ' an XmlAttributes instance.
        Dim attrs As XmlAttributes = New XmlAttributes()  
  
        ' Creates an XmlElementAttribute instance to override the
        ' field that returns Book objects. The overridden field  
        ' returns Expanded objects instead.  
        Dim attr As XmlElementAttribute = _  
        New XmlElementAttribute()  
        attr.ElementName = "NewBook"  
        attr.Type = GetType(ExpandedBook)  
  
        ' Adds the element to the collection of elements.  
        attrs.XmlElements.Add(attr)  
  
        ' Creates the XmlAttributeOverrides.  
        Dim attrOverrides As XmlAttributeOverrides = _  
        New XmlAttributeOverrides()  
  
        ' Adds the type of the class that contains the overridden
        ' member, as well as the XmlAttributes instance to override it
        ' with, to the XmlAttributeOverrides instance.
        attrOverrides.Add(GetType(Orders), "Books", attrs)  
  
        ' Creates the XmlSerializer using the XmlAttributeOverrides.  
        Dim s As XmlSerializer  = _  
        New XmlSerializer(GetType(Orders), attrOverrides)  
  
        ' Writing the file requires a TextWriter instance.  
        Dim writer As TextWriter = New StreamWriter(filename)  
  
        ' Creates the object to be serialized.  
        Dim myOrders As Orders = New Orders()  
  
        ' Creates an object of the derived type.  
        Dim b As ExpandedBook = New ExpandedBook()  
        b.ISBN= "123456789"  
        b.NewEdition = True  
        myOrders.Books = New ExpandedBook(){b}  
  
        ' Serializes the object.  
        s.Serialize(writer,myOrders)  
        writer.Close()  
    End Sub  
  
    Public Sub DeserializeObject(filename As String)  
        Dim attrOverrides As XmlAttributeOverrides = _  
        New XmlAttributeOverrides()  
        Dim attrs As XmlAttributes = New XmlAttributes()  
  
        ' Creates an XmlElementAttribute to override the
        ' field that returns Book objects. The overridden field  
        ' returns Expanded objects instead.
        Dim attr As XmlElementAttribute = _  
        New XmlElementAttribute()  
        attr.ElementName = "NewBook"  
        attr.Type = GetType(ExpandedBook)  
  
        ' Adds the XmlElementAttribute to the collection of objects.  
        attrs.XmlElements.Add(attr)  
  
        attrOverrides.Add(GetType(Orders), "Books", attrs)  
  
        ' Creates the XmlSerializer using the XmlAttributeOverrides.  
        Dim s As XmlSerializer = _  
        New XmlSerializer(GetType(Orders), attrOverrides)  
  
        Dim fs As FileStream = New FileStream(filename, FileMode.Open)  
        Dim myOrders As Orders = CType( s.Deserialize(fs), Orders)  
        Console.WriteLine("ExpandedBook:")  
  
        ' The difference between deserializing the overridden
        ' XML document and serializing it is this: To read the derived
        ' object values, you must declare an object of the derived type
        ' and cast the returned object to it.
        Dim expanded As ExpandedBook
        Dim b As Book  
        for each b  in myOrders.Books  
            expanded = CType(b, ExpandedBook)  
            Console.WriteLine(expanded.ISBN)  
            Console.WriteLine(expanded.NewEdition)  
        Next  
    End Sub  
End Class  
```  
  
```csharp  
public class Orders  
{  
    public Book[] Books;  
}
  
public class Book  
{  
    public string ISBN;  
}  
  
public class ExpandedBook:Book  
{  
    public bool NewEdition;  
}  
  
public class Run  
{  
    public void SerializeObject(string filename)  
    {  
        // Each overridden field, property, or type requires
        // an XmlAttributes instance.  
        XmlAttributes attrs = new XmlAttributes();  
  
        // Creates an XmlElementAttribute instance to override the
        // field that returns Book objects. The overridden field  
        // returns Expanded objects instead.  
        XmlElementAttribute attr = new XmlElementAttribute();  
        attr.ElementName = "NewBook";  
        attr.Type = typeof(ExpandedBook);  
  
        // Adds the element to the collection of elements.  
        attrs.XmlElements.Add(attr);  
  
        // Creates the XmlAttributeOverrides instance.  
        XmlAttributeOverrides attrOverrides = new XmlAttributeOverrides();  
  
        // Adds the type of the class that contains the overridden
        // member, as well as the XmlAttributes instance to override it
        // with, to the XmlAttributeOverrides.  
        attrOverrides.Add(typeof(Orders), "Books", attrs);  
  
        // Creates the XmlSerializer using the XmlAttributeOverrides.  
        XmlSerializer s =
        new XmlSerializer(typeof(Orders), attrOverrides);  
  
        // Writing the file requires a TextWriter instance.  
        TextWriter writer = new StreamWriter(filename);  
  
        // Creates the object to be serialized.  
        Orders myOrders = new Orders();  
  
        // Creates an object of the derived type.  
        ExpandedBook b = new ExpandedBook();  
        b.ISBN= "123456789";  
        b.NewEdition = true;  
        myOrders.Books = new ExpandedBook[]{b};  
  
        // Serializes the object.  
        s.Serialize(writer,myOrders);  
        writer.Close();  
    }  
  
    public void DeserializeObject(string filename)  
    {  
        XmlAttributeOverrides attrOverrides =
            new XmlAttributeOverrides();  
        XmlAttributes attrs = new XmlAttributes();  
  
        // Creates an XmlElementAttribute to override the
        // field that returns Book objects. The overridden field  
        // returns Expanded objects instead.  
        XmlElementAttribute attr = new XmlElementAttribute();  
        attr.ElementName = "NewBook";  
        attr.Type = typeof(ExpandedBook);  
  
        // Adds the XmlElementAttribute to the collection of objects.  
        attrs.XmlElements.Add(attr);  
  
        attrOverrides.Add(typeof(Orders), "Books", attrs);  
  
        // Creates the XmlSerializer using the XmlAttributeOverrides.  
        XmlSerializer s =
        new XmlSerializer(typeof(Orders), attrOverrides);  
  
        FileStream fs = new FileStream(filename, FileMode.Open);  
        Orders myOrders = (Orders) s.Deserialize(fs);  
        Console.WriteLine("ExpandedBook:");  
  
        // The difference between deserializing the overridden
        // XML document and serializing it is this: To read the derived
        // object values, you must declare an object of the derived type
        // and cast the returned object to it.  
        ExpandedBook expanded;  
        foreach(Book b in myOrders.Books)
        {  
            expanded = (ExpandedBook)b;  
            Console.WriteLine(  
            expanded.ISBN + "\n" +
            expanded.NewEdition);  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="502ae-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="502ae-112">See also</span></span>

- <xref:System.Xml.Serialization.XmlSerializer>
- <xref:System.Xml.Serialization.XmlElementAttribute>
- <xref:System.Xml.Serialization.XmlAttributes>
- <xref:System.Xml.Serialization.XmlAttributeOverrides>
- [<span data-ttu-id="502ae-113">XML- und SOAP-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="502ae-113">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
- [<span data-ttu-id="502ae-114">How to: Serialisieren eines Objekts</span><span class="sxs-lookup"><span data-stu-id="502ae-114">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [<span data-ttu-id="502ae-115">How to: Angeben eines alternativen Elementnamens für einen XML-Stream</span><span class="sxs-lookup"><span data-stu-id="502ae-115">How to: Specify an Alternate Element Name for an XML Stream</span></span>](../../../docs/standard/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md)
