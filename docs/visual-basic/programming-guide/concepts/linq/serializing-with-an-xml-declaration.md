---
title: Serialisieren mit einer XML-Deklaration (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 8726f79e-2bb0-4ba0-969d-197cca591647
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 50707da956df593f176764bed94adfc6aec3dfa5
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="serializing-with-an-xml-declaration-visual-basic"></a><span data-ttu-id="e6eb8-102">Serialisieren mit einer XML-Deklaration (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6eb8-102">Serializing with an XML Declaration (Visual Basic)</span></span>
<span data-ttu-id="e6eb8-103">In diesem Thema wird beschrieben, wie Sie steuern können, ob die Serialisierung eine XML-Deklaration generiert.</span><span class="sxs-lookup"><span data-stu-id="e6eb8-103">This topic describes how to control whether serialization generates an XML declaration.</span></span>  
  
## <a name="xml-declaration-generation"></a><span data-ttu-id="e6eb8-104">Generierung einer XML-Deklaration</span><span class="sxs-lookup"><span data-stu-id="e6eb8-104">XML Declaration Generation</span></span>  
 <span data-ttu-id="e6eb8-105">Beim Serialisieren in eine <xref:System.IO.File>oder ein <xref:System.IO.TextWriter>mithilfe der <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>Methode oder die <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>-Methode generiert eine XML-Deklaration.</xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName> </xref:System.IO.TextWriter> </xref:System.IO.File></span><span class="sxs-lookup"><span data-stu-id="e6eb8-105">Serializing to a <xref:System.IO.File> or a <xref:System.IO.TextWriter> using the <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName> method or the <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName> method generates an XML declaration.</span></span> <span data-ttu-id="e6eb8-106">Beim Serialisieren in eine <xref:System.Xml.XmlWriter>, Einstellungen für den Writer (im angegebenen ein <xref:System.Xml.XmlWriterSettings>Objekt) zu bestimmen, ob eine XML-Deklaration oder nicht generiert wird.</xref:System.Xml.XmlWriterSettings> </xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="e6eb8-106">When you serialize to an <xref:System.Xml.XmlWriter>, the writer settings (specified in an <xref:System.Xml.XmlWriterSettings> object) determine whether an XML declaration is generated or not.</span></span>  
  
 <span data-ttu-id="e6eb8-107">Bei der Serialisierung in eine Zeichenfolge mit der `ToString`-Methode enthält der resultierende XML-Code keine XML-Deklaration.</span><span class="sxs-lookup"><span data-stu-id="e6eb8-107">If you are serializing to a string using the `ToString` method, the resulting XML will not include an XML declaration.</span></span>  
  
### <a name="serializing-with-an-xml-declaration"></a><span data-ttu-id="e6eb8-108">Serialisieren mit einer XML-Deklaration</span><span class="sxs-lookup"><span data-stu-id="e6eb8-108">Serializing with an XML Declaration</span></span>  
 <span data-ttu-id="e6eb8-109">Das folgende Beispiel erstellt eine <xref:System.Xml.Linq.XElement>, speichert das Dokument in eine Datei und dann die Datei auf der Konsole ausgegeben:</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="e6eb8-109">The following example creates an <xref:System.Xml.Linq.XElement>, saves the document to a file, and then prints the file to the console:</span></span>  
  
```vb  
Dim root As XElement = <Root>  
                           <Child>child content</Child>  
                       </Root>  
root.Save("Root.xml")  
Dim str As String = File.ReadAllText("Root.xml")  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="e6eb8-110">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="e6eb8-110">This example produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a><span data-ttu-id="e6eb8-111">Serialisieren ohne eine XML-Deklaration</span><span class="sxs-lookup"><span data-stu-id="e6eb8-111">Serializing without an XML Declaration</span></span>  
 <span data-ttu-id="e6eb8-112">Das folgende Beispiel zeigt, wie ein <xref:System.Xml.Linq.XElement>in eine <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.Xml.Linq.XElement> gespeichert</span><span class="sxs-lookup"><span data-stu-id="e6eb8-112">The following example shows how to save an <xref:System.Xml.Linq.XElement> to an <xref:System.Xml.XmlWriter>.</span></span>  
  
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
  
 <span data-ttu-id="e6eb8-113">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="e6eb8-113">This example produces the following output:</span></span>  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6eb8-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6eb8-114">See Also</span></span>  
 [<span data-ttu-id="e6eb8-115">Serialisieren von XML-Strukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6eb8-115">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
