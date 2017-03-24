---
title: 'Gewusst wie: Streamen von XML-Fragmenten aus einem XmlReader (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: f67ce598-4a12-4dcb-9a07-24deca02a111
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
ms.openlocfilehash: c9c60bb4730ef6569390f76f63c40a2cbd1c9524
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-visual-basic"></a>Gewusst wie: Streamen von XML-Fragmenten aus einem XmlReader (Visual Basic)
Wenn Sie große XML-Dateien verarbeiten müssen, kann u. U. nicht die gesamte XML-Struktur in den Arbeitsspeicher geladen werden. In diesem Thema veranschaulicht, wie mithilfe einer <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> Fragmente Streamen  
  
 Eine der effektivsten Methoden verwenden ein <xref:System.Xml.XmlReader>Lesen <xref:System.Xml.Linq.XElement>Objekten ist eine eigene benutzerdefinierte Achsenmethode schreiben.</xref:System.Xml.Linq.XElement> </xref:System.Xml.XmlReader> Achsenmethode gibt in der Regel eine Auflistung wie z. B. <xref:System.Collections.Generic.IEnumerable%601>von <xref:System.Xml.Linq.XElement>, wie im Beispiel in diesem Thema gezeigt.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> In der benutzerdefinierten Achsenmethode, nach der Erstellung von XML-Fragment durch Aufrufen der <xref:System.Xml.Linq.XNode.ReadFrom%2A>-Methode zurückgegeben wird, die Auflistung mit `yield return`.</xref:System.Xml.Linq.XNode.ReadFrom%2A> Auf diese Weise versehen Sie Ihre benutzerdefinierte Achsenmethode mit der Semantik für eine verzögerte Ausführung.  
  
 Beim Erstellen einer XML-Struktur aus einem <xref:System.Xml.XmlReader>-Objekt, das <xref:System.Xml.XmlReader>muss auf einem Element positioniert werden.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader> Die <xref:System.Xml.Linq.XNode.ReadFrom%2A>Methode gibt keinen zurück, bis sie das Endtag des Elements gelesen hat.</xref:System.Xml.Linq.XNode.ReadFrom%2A>  
  
 Wenn Sie eine Teilstruktur erstellen möchten, instanziieren Sie ein <xref:System.Xml.XmlReader>, positionieren Sie den Reader auf dem Knoten, die Sie zum konvertieren möchten eine <xref:System.Xml.Linq.XElement>Struktur, und erstellen Sie die <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement> </xref:System.Xml.XmlReader>  
  
 Das Thema [How to: Stream XML-Fragmenten mit Zugriff auf Headerinformationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md) enthält Informationen und ein Beispiel dafür, wie komplexere Dokumente gestreamt.  
  
 Das Thema [Gewusst wie: Ausführen Streaming Transformieren von großen XML-Dokumenten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md) enthält ein Beispiel der Verwendung von LINQ to XML extrem große XML-Dokumente zu transformieren, Beibehaltung einer geringen speicherbeanspruchung.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel erstellt eine benutzerdefinierte Achsenmethode. Zum Abfragen kann eine [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Abfrage verwendet werden. Die benutzerdefinierte Achsenmethode `StreamRootChildDoc` eignet sich vor allem zum Lesen eines Dokuments, das ein sich wiederholendes `Child`-Element enthält.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 In diesem Beispiel ist das Quelldokument sehr klein. Dieses Beispiel würde aber auch dann wenig Speicher beanspruchen, wenn das Quelldokument Millionen `Child`-Elemente enthielte.  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Implementieren von IEnumerable(Of T) in Visual Basic](../../../../visual-basic/programming-guide/language-features/control-flow/walkthrough-implementing-ienumerable-of-t.md)   
 [Analysieren von XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
