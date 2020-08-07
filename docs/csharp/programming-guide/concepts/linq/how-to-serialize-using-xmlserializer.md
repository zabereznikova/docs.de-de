---
title: 'Vorgehensweise: Serialisieren mit XmlSerializer (C#)'
description: Erfahren Sie, wie Sie Objekte mit XmlSerializer serialisieren. Hier finden Sie ein Beispiel, das Objekte erstellt, in einen Arbeitsspeicherstream serialisiert und dann wieder deserialisiert.
ms.date: 07/20/2015
ms.assetid: 2e0a0bbc-c548-4fe2-8741-be5a9ccd0cbb
ms.openlocfilehash: 29c8c7170af8a24292892862dc89cfe101d24f15
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301514"
---
# <a name="how-to-serialize-using-xmlserializer-c"></a><span data-ttu-id="3fb2f-104">Vorgehensweise: Serialisieren mit XmlSerializer (C#)</span><span class="sxs-lookup"><span data-stu-id="3fb2f-104">How to serialize using XmlSerializer (C#)</span></span>
<span data-ttu-id="3fb2f-105">Dieses Thema enthält ein Beispiel, das zum Serialisieren und Deserialisieren <xref:System.Xml.Serialization.XmlSerializer> verwendet.</span><span class="sxs-lookup"><span data-stu-id="3fb2f-105">This topic shows an example that serializes and deserializes using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fb2f-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3fb2f-106">Example</span></span>  
 <span data-ttu-id="3fb2f-107">Im folgenden Beispiel wird eine Reihe von Objekten erstellt, die <xref:System.Xml.Linq.XElement>-Objekte enthalten.</span><span class="sxs-lookup"><span data-stu-id="3fb2f-107">The following example creates a number of objects that contain <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="3fb2f-108">Anschließend serialisiert das Beispiel diese Objekte in einen Speicherstream und deserialisiert sie von dort wieder:</span><span class="sxs-lookup"><span data-stu-id="3fb2f-108">It then serializes them to a memory stream, and then deserializes them from the memory stream.</span></span>  
  
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
  
 <span data-ttu-id="3fb2f-109">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3fb2f-109">This example produces the following output:</span></span>  
  
```output  
Testing for type: XElementNullContainer  
  Deserialized type: XElementNullContainer  
Testing for type: System.Xml.Linq.XElement  
  Deserialized type: System.Xml.Linq.XElement  
Testing for type: XElementContainer  
  Deserialized type: XElementContainer  
```  
