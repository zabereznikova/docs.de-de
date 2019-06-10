---
title: 'Vorgehensweise: Serialisieren mit der XmlSerializer-Klasse (C#)'
ms.date: 07/20/2015
ms.assetid: 2e0a0bbc-c548-4fe2-8741-be5a9ccd0cbb
ms.openlocfilehash: 2a9d51bbae905a128d6d5846423a5c02fe1d67d0
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66484881"
---
# <a name="how-to-serialize-using-xmlserializer-c"></a><span data-ttu-id="11b07-102">Vorgehensweise: Serialisieren mit der XmlSerializer-Klasse (C#)</span><span class="sxs-lookup"><span data-stu-id="11b07-102">How to: Serialize Using XmlSerializer (C#)</span></span>
<span data-ttu-id="11b07-103">Dieses Thema enthält ein Beispiel, das zum Serialisieren und Deserialisieren <xref:System.Xml.Serialization.XmlSerializer> verwendet.</span><span class="sxs-lookup"><span data-stu-id="11b07-103">This topic shows an example that serializes and deserializes using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11b07-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="11b07-104">Example</span></span>  
 <span data-ttu-id="11b07-105">Im folgenden Beispiel wird eine Reihe von Objekten erstellt, die <xref:System.Xml.Linq.XElement>-Objekte enthalten.</span><span class="sxs-lookup"><span data-stu-id="11b07-105">The following example creates a number of objects that contain <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="11b07-106">Anschließend serialisiert das Beispiel diese Objekte in einen Speicherstream und deserialisiert sie von dort wieder:</span><span class="sxs-lookup"><span data-stu-id="11b07-106">It then serializes them to a memory stream, and then deserializes them from the memory stream.</span></span>  
  
```csharp  
using System;  
using System.IO;  
using System.Linq;  
using System.Xml;  
using System.Xml.Serialization;  
using System.Xml.Linq;  
  
public class XElementContainer  
{  
    public XElement member;  
  
    public XElementContainer()  
    {  
        member = XLinqTest.CreateXElement();  
    }  
  
    public override string ToString()  
    {  
        return member.ToString();  
    }  
}  
  
public class XElementNullContainer  
{  
    public XElement member;  
  
    public XElementNullContainer()  
    {  
    }  
}  
  
class XLinqTest  
{  
    static void Main(string[] args)  
    {  
        Test<XElementNullContainer>(new XElementNullContainer());  
        Test<XElement>(CreateXElement());  
        Test<XElementContainer>(new XElementContainer());  
    }  
  
    public static XElement CreateXElement()  
    {  
        XNamespace ns = "http://www.adventure-works.com";  
        return new XElement(ns + "aw");  
    }  
  
    static void Test<T>(T obj)  
    {  
        using (MemoryStream stream = new MemoryStream())  
        {  
            XmlSerializer s = new XmlSerializer(typeof(T));  
            Console.WriteLine("Testing for type: {0}", typeof(T));  
            s.Serialize(XmlWriter.Create(stream), obj);  
            stream.Flush();  
            stream.Seek(0, SeekOrigin.Begin);  
            object o = s.Deserialize(XmlReader.Create(stream));  
            Console.WriteLine("  Deserialized type: {0}", o.GetType());  
        }  
    }  
}  
```  
  
 <span data-ttu-id="11b07-107">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="11b07-107">This example produces the following output:</span></span>  
  
```  
Testing for type: XElementNullContainer  
  Deserialized type: XElementNullContainer  
Testing for type: System.Xml.Linq.XElement  
  Deserialized type: System.Xml.Linq.XElement  
Testing for type: XElementContainer  
  Deserialized type: XElementContainer  
```  
