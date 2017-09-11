---
title: 'Gewusst wie: Lesen und schreiben ein codiertes Dokuments (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: 159d868f-5ac8-40f2-95ca-07dd925f35c6
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
ms.openlocfilehash: 5bfc825ca32aaa365b7cc2d0347834a796d3598b
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="how-to-read-and-write-an-encoded-document-visual-basic"></a><span data-ttu-id="753c1-102">Gewusst wie: Lesen und schreiben ein codiertes Dokuments (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="753c1-102">How to: Read and Write an Encoded Document (Visual Basic)</span></span>
<span data-ttu-id="753c1-103">Zum Erstellen eines codierten XML-Dokuments fügen Sie eine <xref:System.Xml.Linq.XDeclaration>der XML-Struktur, die Codierung auf den gewünschten Codeseitennamen festlegt.</xref:System.Xml.Linq.XDeclaration></span><span class="sxs-lookup"><span data-stu-id="753c1-103">To create an encoded XML document, you add an <xref:System.Xml.Linq.XDeclaration> to the XML tree, setting the encoding to the desired code page name.</span></span>  
  
 <span data-ttu-id="753c1-104">Zurückgegebenen Wert <xref:System.Text.Encoding.WebName%2A>ist ein gültiger Wert.</xref:System.Text.Encoding.WebName%2A></span><span class="sxs-lookup"><span data-stu-id="753c1-104">Any value returned by <xref:System.Text.Encoding.WebName%2A> is a valid value.</span></span>  
  
 <span data-ttu-id="753c1-105">Wenn Sie eines codiertes Dokuments Lesen der <xref:System.Xml.Linq.XDeclaration.Encoding%2A>-Eigenschaft wird auf den Codeseitennamen festgelegt werden.</xref:System.Xml.Linq.XDeclaration.Encoding%2A></span><span class="sxs-lookup"><span data-stu-id="753c1-105">If you read an encoded document, the <xref:System.Xml.Linq.XDeclaration.Encoding%2A> property will be set to the code page name.</span></span>  
  
 <span data-ttu-id="753c1-106">Wenn Sie festlegen, <xref:System.Xml.Linq.XDeclaration.Encoding%2A>auf einen gültigen Codeseitennamen [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] mit der angegebenen Codierung serialisiert.</xref:System.Xml.Linq.XDeclaration.Encoding%2A></span><span class="sxs-lookup"><span data-stu-id="753c1-106">If you set <xref:System.Xml.Linq.XDeclaration.Encoding%2A> to a valid code page name, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] will serialize with the specified encoding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="753c1-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="753c1-107">Example</span></span>  
 <span data-ttu-id="753c1-108">Das folgende Beispiel erstellt zwei Dokumente: eines mit UTF-8-Codierung und eines mit UTF-16-Codierung.</span><span class="sxs-lookup"><span data-stu-id="753c1-108">The following example creates two documents, one with utf-8 encoding, and one with utf-16 encoding.</span></span> <span data-ttu-id="753c1-109">Anschließend werden die Dokumente geladen, und die Codierung wird auf der Konsole ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="753c1-109">It then loads the documents and prints the encoding to the console.</span></span>  
  
```vb  
Console.WriteLine("Creating a document with utf-8 encoding")  
Dim encodedDoc8 As XDocument = _  
        <?xml version='1.0' encoding='utf-8' standalone='yes'?>  
        <Root>Content</Root>   
  
encodedDoc8.Save("EncodedUtf8.xml")  
Console.WriteLine("Encoding is:{0}", encodedDoc8.Declaration.Encoding)  
Console.WriteLine()  
  
Console.WriteLine("Creating a document with utf-16 encoding")  
Dim encodedDoc16 As XDocument = _  
        <?xml version='1.0' encoding='utf-16' standalone='yes'?>  
        <Root>Content</Root>  
  
encodedDoc16.Save("EncodedUtf16.xml")  
Console.WriteLine("Encoding is:{0}", encodedDoc16.Declaration.Encoding)  
Console.WriteLine()  
  
Dim newDoc8 As XDocument = XDocument.Load("EncodedUtf8.xml")  
Console.WriteLine("Encoded document:")  
Console.WriteLine(File.ReadAllText("EncodedUtf8.xml"))  
Console.WriteLine()  
Console.WriteLine("Encoding of loaded document is:{0}", newDoc8.Declaration.Encoding)  
Console.WriteLine()  
  
Dim newDoc16 As XDocument = XDocument.Load("EncodedUtf16.xml")  
Console.WriteLine("Encoded document:")  
Console.WriteLine(File.ReadAllText("EncodedUtf16.xml"))  
Console.WriteLine()  
Console.WriteLine("Encoding of loaded document is:{0}", newDoc16.Declaration.Encoding)  
```  
  
 <span data-ttu-id="753c1-110">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="753c1-110">This example produces the following output:</span></span>  
  
```  
Creating a document with utf-8 encoding  
Encoding is:utf-8  
  
Creating a document with utf-16 encoding  
Encoding is:utf-16  
  
Encoded document:  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<Root>Content</Root>  
  
Encoding of loaded document is:utf-8  
  
Encoded document:  
<?xml version="1.0" encoding="utf-16" standalone="yes"?>  
<Root>Content</Root>  
  
Encoding of loaded document is:utf-16  
```  
  
## <a name="see-also"></a><span data-ttu-id="753c1-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="753c1-111">See Also</span></span>  
 <span data-ttu-id="753c1-112"><xref:System.Xml.Linq.XDeclaration.Encoding%2A?displayProperty=fullName></xref:System.Xml.Linq.XDeclaration.Encoding%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="753c1-112"><xref:System.Xml.Linq.XDeclaration.Encoding%2A?displayProperty=fullName></span></span>   
<span data-ttu-id="753c1-113"> [Erweiterte LINQ to XML-Programmierung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)</span><span class="sxs-lookup"><span data-stu-id="753c1-113"> [Advanced LINQ to XML Programming (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)</span></span>
