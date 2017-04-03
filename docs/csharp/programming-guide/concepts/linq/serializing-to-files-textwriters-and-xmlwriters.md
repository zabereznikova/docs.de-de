---
title: Serialisieren in Dateien, TextWriters und XmlWriters1 | Microsoft-Dokumentation
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
ms.assetid: bd3ea6f7-895b-4ff4-a625-fe2bb55b1886
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
ms.openlocfilehash: f61324395e81509e5800e99b654a8c669d4397f0
ms.lasthandoff: 03/13/2017

---
# <a name="serializing-to-files-textwriters-and-xmlwriters"></a>Serialisieren in Dateien, TextWriters und XmlWriters
Sie können XML Strukturen zu <xref:System.IO.File>, <xref:System.IO.TextWriter> oder <xref:System.Xml.XmlWriter> serialisieren.  
  
 Sie können jede XML-Komponente, darunter <xref:System.Xml.Linq.XDocument> und <xref:System.Xml.Linq.XElement>, mithilfe der `ToString`-Methode in eine Zeichenfolge serialisieren.  
  
 Wenn Sie beim Serialisieren in eine Zeichenfolge die Formatierung unterdrücken möchten, können Sie die Methode <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=fullName> verwenden.  
  
 Das Standardverhalten beim Serialisieren in eine Datei besteht darin, dass das resultierende XML-Dokument formatiert (mit Einzügen versehen) wird. Wenn Sie das Dokument mit Einzügen versehen, wird der nicht signifikante Leerraum in der XML-Struktur nicht beibehalten. Wenn Sie eine Serialisierung mit Formatierung vornehmen möchten, verwenden Sie eine der Überladungen der folgenden Methoden, die <xref:System.Xml.Linq.SaveOptions> nicht als Argument akzeptieren:  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>  
  
 Wenn Sie möchten, dass keine Einzüge vorgenommen werden und der nicht signifikante Leerraum in der XML-Struktur beibehalten wird, verwenden Sie eine der Überladungen der folgenden Methoden, die <xref:System.Xml.Linq.SaveOptions> als Argument akzeptieren:  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>  
  
 Beispiele finden Sie im entsprechenden Referenzthema.  
  
## <a name="see-also"></a>Siehe auch  
 [Serializing XML Trees (C#) (Serialisieren von XML-Strukturen (C#))](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)
