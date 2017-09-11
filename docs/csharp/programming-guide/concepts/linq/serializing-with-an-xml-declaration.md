---
title: Serialisieren mit einer XML-Deklaration (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: c237fa4a-a042-40fd-886f-17b54c66bb75
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 36ffb8ddd584785c660896ca77707d504638852f
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="serializing-with-an-xml-declaration-c"></a><span data-ttu-id="5d85c-102">Serialisieren mit einer XML-Deklaration (C#)</span><span class="sxs-lookup"><span data-stu-id="5d85c-102">Serializing with an XML Declaration (C#)</span></span>
<span data-ttu-id="5d85c-103">In diesem Thema wird beschrieben, wie Sie steuern können, ob die Serialisierung eine XML-Deklaration generiert.</span><span class="sxs-lookup"><span data-stu-id="5d85c-103">This topic describes how to control whether serialization generates an XML declaration.</span></span>  
  
## <a name="xml-declaration-generation"></a><span data-ttu-id="5d85c-104">Generierung einer XML-Deklaration</span><span class="sxs-lookup"><span data-stu-id="5d85c-104">XML Declaration Generation</span></span>  
 <span data-ttu-id="5d85c-105">Beim Serialisieren in ein <xref:System.IO.File>- oder <xref:System.IO.TextWriter>-Objekt führt die Verwendung der <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>- oder <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>-Methode zur Generierung einer XML-Deklaration.</span><span class="sxs-lookup"><span data-stu-id="5d85c-105">Serializing to a <xref:System.IO.File> or a <xref:System.IO.TextWriter> using the <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName> method or the <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName> method generates an XML declaration.</span></span> <span data-ttu-id="5d85c-106">Beim Serialisieren in einen <xref:System.Xml.XmlWriter> bestimmen die (in einem <xref:System.Xml.XmlWriterSettings>-Objekt angegebenen) Writer-Einstellungen, ob eine XML-Deklaration generiert wird.</span><span class="sxs-lookup"><span data-stu-id="5d85c-106">When you serialize to an <xref:System.Xml.XmlWriter>, the writer settings (specified in an <xref:System.Xml.XmlWriterSettings> object) determine whether an XML declaration is generated or not.</span></span>  
  
 <span data-ttu-id="5d85c-107">Bei der Serialisierung in eine Zeichenfolge mit der `ToString`-Methode enthält der resultierende XML-Code keine XML-Deklaration.</span><span class="sxs-lookup"><span data-stu-id="5d85c-107">If you are serializing to a string using the `ToString` method, the resulting XML will not include an XML declaration.</span></span>  
  
### <a name="serializing-with-an-xml-declaration"></a><span data-ttu-id="5d85c-108">Serialisieren mit einer XML-Deklaration</span><span class="sxs-lookup"><span data-stu-id="5d85c-108">Serializing with an XML Declaration</span></span>  
 <span data-ttu-id="5d85c-109">Das folgende Beispiel erstellt ein <xref:System.Xml.Linq.XElement>, speichert das Dokument in einer Datei und gibt die Datei dann auf der Konsole aus:</span><span class="sxs-lookup"><span data-stu-id="5d85c-109">The following example creates an <xref:System.Xml.Linq.XElement>, saves the document to a file, and then prints the file to the console:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child", "child content")  
);  
root.Save("Root.xml");  
string str = File.ReadAllText("Root.xml");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="5d85c-110">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="5d85c-110">This example produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a><span data-ttu-id="5d85c-111">Serialisieren ohne eine XML-Deklaration</span><span class="sxs-lookup"><span data-stu-id="5d85c-111">Serializing without an XML Declaration</span></span>  
 <span data-ttu-id="5d85c-112">Das folgende Beispiel zeigt die Vorgehensweise beim Speichern eines <xref:System.Xml.Linq.XElement> in einem <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="5d85c-112">The following example shows how to save an <xref:System.Xml.Linq.XElement> to an <xref:System.Xml.XmlWriter>.</span></span>  
  
```csharp  
StringBuilder sb = new StringBuilder();  
XmlWriterSettings xws = new XmlWriterSettings();  
xws.OmitXmlDeclaration = true;  
  
using (XmlWriter xw = XmlWriter.Create(sb, xws)) {  
    XElement root = new XElement("Root",  
        new XElement("Child", "child content")  
    );  
    root.Save(xw);  
}  
Console.WriteLine(sb.ToString());  
```  
  
 <span data-ttu-id="5d85c-113">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="5d85c-113">This example produces the following output:</span></span>  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5d85c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d85c-114">See Also</span></span>  
 [<span data-ttu-id="5d85c-115">Serialisieren von XML-Strukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="5d85c-115">Serializing XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)

