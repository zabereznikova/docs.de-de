---
title: Serialisieren in Dateien, TextWriters und XmlWriters3
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a0c24df-79ef-41a0-87f5-e6cf79382da9
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f4c5578bc20f91eb35f78355dff0fc4c44e878e2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="serializing-to-files-textwriters-and-xmlwriters"></a>Serialisieren in Dateien, TextWriters und XmlWriters
Sie können XML-Strukturen in eine <xref:System.IO.File>, in einen <xref:System.IO.TextWriter> oder in einen <xref:System.Xml.XmlWriter> serialisieren.  
  
 Mit der <xref:System.Xml.Linq.XDocument>-Methode können Sie jede XML-Komponente, auch <xref:System.Xml.Linq.XElement> und `ToString`, in eine Zeichenfolge serialisieren.  
  
 Wenn Sie beim Serialisieren in eine Zeichenfolge die Formatierung unterdrücken möchten, können Sie die <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType>-Methode verwenden.  
  
 Das Standardverhalten beim Serialisieren in eine Datei besteht darin, dass das resultierende XML-Dokument formatiert (mit Einzügen versehen) wird. Wenn Sie das Dokument mit Einzügen versehen, wird der nicht signifikante Leerraum in der XML-Struktur nicht beibehalten. Wenn Sie eine Serialisierung mit Formatierung vornehmen möchten, verwenden Sie eine der Überladungen der folgenden Methoden, die <xref:System.Xml.Linq.SaveOptions> nicht als Argument akzeptieren.  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
 Wenn Sie möchten, dass keine Einzüge vorgenommen werden und der nicht signifikante Leerraum in der XML-Struktur beibehalten wird, verwenden Sie eine der Überladungen der folgenden Methoden, die <xref:System.Xml.Linq.SaveOptions> als Argument akzeptieren:  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
 Beispiele finden Sie im entsprechenden Referenzthema.  
  
## <a name="see-also"></a>Siehe auch  
 [Serialisieren von XML-Strukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
