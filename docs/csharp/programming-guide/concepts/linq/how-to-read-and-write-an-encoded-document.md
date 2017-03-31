---
title: 'Vorgehensweise: Lesen und Schreiben eines codierten Dokuments (C#) | Microsoft-Dokumentation'
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
ms.assetid: 84f64e71-39a6-42c6-ad68-f052bb158a03
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6f599d279e804372ef8779514939f14cee15c5e3
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-read-and-write-an-encoded-document-c"></a>Vorgehensweise: Lesen und Schreiben eines codierten Dokuments (C#)
Fügen Sie der XML-Struktur zum Erstellen eines codierten XML-Dokuments eine <xref:System.Xml.Linq.XDeclaration> hinzu, die die Codierung auf den gewünschten Codeseitennamen festlegt.  
  
 Jeder von <xref:System.Text.Encoding.WebName%2A> zurückgegebene Wert ist ein gültiger Wert.  
  
 Wenn Sie ein codiertes Dokument lesen, wird die Eigenschaft <xref:System.Xml.Linq.XDeclaration.Encoding%2A> auf den Codeseitennamen festgelegt werden.  
  
 Wenn Sie <xref:System.Xml.Linq.XDeclaration.Encoding%2A> auf einen gültigen Codeseitennamen festlegen, verwendet [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] zum Serialisieren die angegebene Codierung.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt zwei Dokumente: eines mit UTF-8-Codierung und eines mit UTF-16-Codierung. Anschließend werden die Dokumente geladen, und die Codierung wird auf der Konsole ausgegeben.  
  
```csharp  
Console.WriteLine("Creating a document with utf-8 encoding");  
XDocument encodedDoc8 = new XDocument(  
    new XDeclaration("1.0", "utf-8", "yes"),  
    new XElement("Root", "Content")  
);  
encodedDoc8.Save("EncodedUtf8.xml");  
Console.WriteLine("Encoding is:{0}", encodedDoc8.Declaration.Encoding);  
Console.WriteLine();  
  
Console.WriteLine("Creating a document with utf-16 encoding");  
XDocument encodedDoc16 = new XDocument(  
    new XDeclaration("1.0", "utf-16", "yes"),  
    new XElement("Root", "Content")  
);  
encodedDoc16.Save("EncodedUtf16.xml");  
Console.WriteLine("Encoding is:{0}", encodedDoc16.Declaration.Encoding);  
Console.WriteLine();  
  
XDocument newDoc8 = XDocument.Load("EncodedUtf8.xml");  
Console.WriteLine("Encoded document:");  
Console.WriteLine(File.ReadAllText("EncodedUtf8.xml"));  
Console.WriteLine();  
Console.WriteLine("Encoding of loaded document is:{0}", newDoc8.Declaration.Encoding);  
Console.WriteLine();  
  
XDocument newDoc16 = XDocument.Load("EncodedUtf16.xml");  
Console.WriteLine("Encoded document:");  
Console.WriteLine(File.ReadAllText("EncodedUtf16.xml"));  
Console.WriteLine();  
Console.WriteLine("Encoding of loaded document is:{0}", newDoc16.Declaration.Encoding);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XDeclaration.Encoding%2A?displayProperty=fullName>   
 [Advanced LINQ to XML Programming (C#) (Erweiterte LINQ to XML-Programmierung (C#))](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
