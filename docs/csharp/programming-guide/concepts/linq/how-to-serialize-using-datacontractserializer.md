---
title: 'Vorgehensweise: Serialisieren mit der DataContractSerializer-Klasse (C#)'
ms.date: 07/20/2015
ms.assetid: 3320ecbf-cdbe-480e-979c-2c14bbef9988
ms.openlocfilehash: 7175b5051d318e7f214b4c2f7d96d44acf7a0a48
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66484917"
---
# <a name="how-to-serialize-using-datacontractserializer-c"></a><span data-ttu-id="ec85a-102">Vorgehensweise: Serialisieren mit der DataContractSerializer-Klasse (C#)</span><span class="sxs-lookup"><span data-stu-id="ec85a-102">How to: Serialize Using DataContractSerializer (C#)</span></span>
<span data-ttu-id="ec85a-103">Dieses Thema enthält ein Beispiel, das zum Serialisieren und Deserialisieren <xref:System.Runtime.Serialization.DataContractSerializer> verwendet.</span><span class="sxs-lookup"><span data-stu-id="ec85a-103">This topic shows an example that serializes and deserializes using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec85a-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ec85a-104">Example</span></span>  
 <span data-ttu-id="ec85a-105">Im folgenden Beispiel wird eine Reihe von Objekten erstellt, die <xref:System.Xml.Linq.XElement>-Objekte enthalten.</span><span class="sxs-lookup"><span data-stu-id="ec85a-105">The following example creates a number of objects that contain <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="ec85a-106">Anschließend werden diese Objekte in Textdateien serialisiert und dann aus den Textdateien wieder deserialisiert.</span><span class="sxs-lookup"><span data-stu-id="ec85a-106">It then serializes them to text files, and then deserializes them from the text files.</span></span>  
  
```csharp  
using System;  
using System.Xml;  
using System.Xml.Linq;  
using System.IO;  
using System.Runtime.Serialization;  
  
public class XLinqTest  
{  
    public static void Main()  
    {  
        Test<XElement>(CreateXElement());  
        Test<XElementContainer>(new XElementContainer());  
        Test<XElementNullContainer>(new XElementNullContainer());  
    }  
  
    public static void Test<T>(T obj)  
    {  
        DataContractSerializer s = new DataContractSerializer(typeof(T));  
        using (FileStream fs = File.Open("test" + typeof(T).Name + ".xml", FileMode.Create))  
        {  
            Console.WriteLine("Testing for type: {0}", typeof(T));   
            s.WriteObject(fs, obj);  
        }  
        using (FileStream fs = File.Open("test" + typeof(T).Name + ".xml", FileMode.Open))  
        {  
            object s2 = s.ReadObject(fs);  
            if (s2 == null)  
                Console.WriteLine("  Deserialized object is null (Nothing in VB)");  
            else  
                Console.WriteLine("  Deserialized type: {0}", s2.GetType());  
        }  
    }  
  
    public static XElement CreateXElement()  
    {  
        return new XElement(XName.Get("NameInNamespace", "http://www.adventure-works.org"));  
    }  
}  
  
[DataContract]  
public class XElementContainer  
{  
    [DataMember]  
    public XElement member;  
  
    public XElementContainer()  
    {  
        member = XLinqTest.CreateXElement();  
    }  
}  
  
[DataContract]  
public class XElementNullContainer  
{  
    [DataMember]  
    public XElement member;  
  
    public XElementNullContainer()  
    {  
        member = null;  
    }  
}  
```  
  
 <span data-ttu-id="ec85a-107">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="ec85a-107">This example produces the following output:</span></span>  
  
```  
Testing for type: System.Xml.Linq.XElement  
  Deserialized type: System.Xml.Linq.XElement  
Testing for type: XElementContainer  
  Deserialized type: XElementContainer  
Testing for type: XElementNullContainer  
  Deserialized type: XElementNullContainer  
```  
  