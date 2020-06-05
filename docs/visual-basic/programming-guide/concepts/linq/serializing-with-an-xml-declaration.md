---
title: Serialisieren mit einer XML-Deklaration
ms.date: 07/20/2015
ms.assetid: 8726f79e-2bb0-4ba0-969d-197cca591647
ms.openlocfilehash: cd303a800efe42d3fa99d601f25d54320570bed3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411796"
---
# <a name="serializing-with-an-xml-declaration-visual-basic"></a><span data-ttu-id="0f64a-102">Serialisieren mit einer XML-Deklaration (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f64a-102">Serializing with an XML Declaration (Visual Basic)</span></span>
<span data-ttu-id="0f64a-103">In diesem Thema wird beschrieben, wie Sie steuern können, ob die Serialisierung eine XML-Deklaration generiert.</span><span class="sxs-lookup"><span data-stu-id="0f64a-103">This topic describes how to control whether serialization generates an XML declaration.</span></span>  
  
## <a name="xml-declaration-generation"></a><span data-ttu-id="0f64a-104">Generierung einer XML-Deklaration</span><span class="sxs-lookup"><span data-stu-id="0f64a-104">XML Declaration Generation</span></span>  
 <span data-ttu-id="0f64a-105">Beim Serialisieren in ein <xref:System.IO.File>- oder <xref:System.IO.TextWriter>-Objekt führt die Verwendung der <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>- oder <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>-Methode zur Generierung einer XML-Deklaration.</span><span class="sxs-lookup"><span data-stu-id="0f64a-105">Serializing to a <xref:System.IO.File> or a <xref:System.IO.TextWriter> using the <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> method or the <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> method generates an XML declaration.</span></span> <span data-ttu-id="0f64a-106">Beim Serialisieren in einen <xref:System.Xml.XmlWriter> bestimmen die (in einem <xref:System.Xml.XmlWriterSettings>-Objekt angegebenen) Writer-Einstellungen, ob eine XML-Deklaration generiert wird.</span><span class="sxs-lookup"><span data-stu-id="0f64a-106">When you serialize to an <xref:System.Xml.XmlWriter>, the writer settings (specified in an <xref:System.Xml.XmlWriterSettings> object) determine whether an XML declaration is generated or not.</span></span>  
  
 <span data-ttu-id="0f64a-107">Bei der Serialisierung in eine Zeichenfolge mit der `ToString`-Methode enthält der resultierende XML-Code keine XML-Deklaration.</span><span class="sxs-lookup"><span data-stu-id="0f64a-107">If you are serializing to a string using the `ToString` method, the resulting XML will not include an XML declaration.</span></span>  
  
### <a name="serializing-with-an-xml-declaration"></a><span data-ttu-id="0f64a-108">Serialisieren mit einer XML-Deklaration</span><span class="sxs-lookup"><span data-stu-id="0f64a-108">Serializing with an XML Declaration</span></span>  
 <span data-ttu-id="0f64a-109">Das folgende Beispiel erstellt ein <xref:System.Xml.Linq.XElement>, speichert das Dokument in einer Datei und gibt die Datei dann auf der Konsole aus:</span><span class="sxs-lookup"><span data-stu-id="0f64a-109">The following example creates an <xref:System.Xml.Linq.XElement>, saves the document to a file, and then prints the file to the console:</span></span>  
  
```vb  
Dim root As XElement = <Root>  
                           <Child>child content</Child>  
                       </Root>  
root.Save("Root.xml")  
Dim str As String = File.ReadAllText("Root.xml")  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="0f64a-110">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="0f64a-110">This example produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a><span data-ttu-id="0f64a-111">Serialisieren ohne eine XML-Deklaration</span><span class="sxs-lookup"><span data-stu-id="0f64a-111">Serializing without an XML Declaration</span></span>  
 <span data-ttu-id="0f64a-112">Das folgende Beispiel zeigt die Vorgehensweise beim Speichern eines <xref:System.Xml.Linq.XElement> in einem <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="0f64a-112">The following example shows how to save an <xref:System.Xml.Linq.XElement> to an <xref:System.Xml.XmlWriter>.</span></span>  
  
```vb  
Dim sb As StringBuilder = New StringBuilder()  
Dim xws As XmlWriterSettings = New XmlWriterSettings()  
xws.OmitXmlDeclaration = True  
  
Using xw As XmlWriter = XmlWriter.Create(sb, xws)  
    Dim root = <Root>  
                   <Child>child content</Child>  
               </Root>  
    root.Save(xw)  
End Using  
Console.WriteLine(sb.ToString())  
```  
  
 <span data-ttu-id="0f64a-113">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="0f64a-113">This example produces the following output:</span></span>  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f64a-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0f64a-114">See also</span></span>

- [<span data-ttu-id="0f64a-115">Serialisieren von XML-Strukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f64a-115">Serializing XML Trees (Visual Basic)</span></span>](serializing-xml-trees.md)
