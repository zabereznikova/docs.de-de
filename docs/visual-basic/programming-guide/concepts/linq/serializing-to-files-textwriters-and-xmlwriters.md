---
title: Beim Serialisieren in Dateien, TextWriters und XmlWriters3 | Microsoft-Dokumentation
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
ms.assetid: 7a0c24df-79ef-41a0-87f5-e6cf79382da9
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 98662b8d84459ed051d048084c2755fa7aaf8247
ms.lasthandoff: 03/13/2017

---
# <a name="serializing-to-files-textwriters-and-xmlwriters"></a>Serialisieren in Dateien, TextWriters und XmlWriters
Sie können XML-Strukturen zu serialisieren einer <xref:System.IO.File>, <xref:System.IO.TextWriter>, oder eine <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.IO.TextWriter> </xref:System.IO.File>  
  
 Sie können jede XML-Komponente, serialisieren einschließlich <xref:System.Xml.Linq.XDocument>und <xref:System.Xml.Linq.XElement>, in eine Zeichenfolge mit der `ToString` -Methode.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument>  
  
 Wenn Sie beim Serialisieren in eine Zeichenfolge die Formatierung unterdrücken möchten, können Sie mithilfe der <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=fullName>-Methode.</xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=fullName>  
  
 Thedefault-Verhalten beim Serialisieren in eine Datei wird (Einzug) das resultierende XML-Dokument formatiert. Wenn Sie das Dokument mit Einzügen versehen, wird der nicht signifikante Leerraum in der XML-Struktur nicht beibehalten. Um mit Formatierung serialisieren, verwenden Sie eine der Überladungen der folgenden Methoden, die kein <xref:System.Xml.Linq.SaveOptions>als Argument:</xref:System.Xml.Linq.SaveOptions>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>  
  
 Wenn Sie die Option nicht für den Einzug und der nicht signifikante Leerraum in der XML-Struktur beibehalten möchten, verwenden Sie eine der Überladungen der folgenden Methoden, die akzeptiert <xref:System.Xml.Linq.SaveOptions>als Argument:</xref:System.Xml.Linq.SaveOptions>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>  
  
 Beispiele finden Sie im entsprechenden Referenzthema.  
  
## <a name="see-also"></a>Siehe auch  
 [Serialisieren von XML-Strukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
