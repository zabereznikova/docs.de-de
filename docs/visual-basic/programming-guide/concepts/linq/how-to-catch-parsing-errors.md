---
title: 'Gewusst wie: Auffangen von Parsingfehlern'
ms.date: 07/20/2015
ms.assetid: 22e9068e-ea58-447b-816e-cd1852c11787
ms.openlocfilehash: 14c4f76c5f10616f9346084cda276e2862b2b41d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353345"
---
# <a name="how-to-catch-parsing-errors-visual-basic"></a>Gewusst wie: Auffangen von Parsing-Fehlern (Visual Basic)
In diesem Thema wird gezeigt, wie nicht wohlgeformter oder ungültiger XML-Code erkannt werden kann.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] wird mithilfe von <xref:System.Xml.XmlReader> implementiert. Wenn nicht wohlgeformter oder ungültiger XML-Code an [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] übergeben wird, löst die zugrunde liegende <xref:System.Xml.XmlReader>-Klasse eine Ausnahme aus. Die verschiedenen Methoden, die XML analysieren, z.B. <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, fangen die Ausnahme nicht ab. Die Ausnahme kann dann von Ihrer Anwendung abgefangen werden.  
  
 Beachten Sie, dass Sie bei Verwendung von XML-Literalen keine Analysefehler abrufen können. Der Visual Basic-Compiler fängt Fehler von nicht wohlgeformtem oder ungültigem XML ab.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code versucht, ungültiges XML zu analysieren:  
  
```vb  
Try  
    Dim contacts As XElement = XElement.Parse("<Contacts>" & vbCrLf & _  
        "    <Contact>" & vbCrLf & _  
        "        <Name>Jim Wilson</Name>" & vbCrLf & _  
        "    </Contact>" & vbCrLf & _  
        "</Contcts>")  
  
    Console.WriteLine(contacts)  
Catch e As System.Xml.XmlException  
    Console.WriteLine(e.Message)  
End Try  
```  
  
 Wenn Sie diesen Code ausführen, wird die folgende Ausnahme ausgelöst:  
  
```console  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 Weitere Informationen zu den Ausnahmen, von denen Sie ausgehen können, dass sie von den Methoden <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> und <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> ausgelöst werden, finden Sie in der <xref:System.Xml.XmlReader>-Dokumentation.  
  
## <a name="see-also"></a>Siehe auch

- [XML-Datei (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
