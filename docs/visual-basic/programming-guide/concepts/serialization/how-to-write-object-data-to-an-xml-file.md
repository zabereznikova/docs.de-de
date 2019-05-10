---
title: 'Vorgehensweise: Schreiben von Objektdaten in eine XML-Datei (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: f7966480-5ed2-43ac-9894-33427436de2a
ms.openlocfilehash: 17f8463a4b905028d37a2e005562867f87f4bd2b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624381"
---
# <a name="how-to-write-object-data-to-an-xml-file-visual-basic"></a>Vorgehensweise: Schreiben von Objektdaten in eine XML-Datei (Visual Basic)
Dieses Beispiel verwendet die <xref:System.Xml.Serialization.XmlSerializer>-Klasse, um das Objekt aus einer Klasse in eine XML-Datei zu schreiben.  
  
## <a name="example"></a>Beispiel  
  
```vb  
Public Module XMLWrite  
  
    Sub Main()  
        WriteXML()  
    End Sub  
  
    Public Class Book  
        Public Title As String  
    End Class  
  
    Public Sub WriteXML()  
        Dim overview As New Book  
        overview.Title = "Serialization Overview"  
        Dim writer As New System.Xml.Serialization.XmlSerializer(GetType(Book))  
        Dim file As New System.IO.StreamWriter(  
            "c:\temp\SerializationOverview.xml")  
        writer.Serialize(file, overview)  
        file.Close()  
    End Sub  
End Module  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Die Klasse muss über einen öffentlichen Konstruktor ohne Parameter verfügen.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
- Die zu serialisierende Klasse verfügt nicht über einen öffentlichen, parameterlosen Konstruktor.  
  
- Die Datei ist bereits vorhanden und schreibgeschützt (<xref:System.IO.IOException>).  
  
- Der Pfad ist zu lang (<xref:System.IO.PathTooLongException>).  
  
- Der Datenträger ist voll (<xref:System.IO.IOException>).  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Mit diesem Beispiel wird eine neue Datei erstellt, wenn diese noch nicht vorhanden ist. Wenn eine Anwendung eine Datei erstellen muss, benötigt sie eine `Create`-Berechtigung für den Ordner. Wenn die Datei bereits vorhanden ist, benötigt die Anwendung lediglich die Berechtigung für den `Write`-Zugriff, also eine geringere Berechtigung. Aus Sicherheitsgründen sollte die Datei nach Möglichkeit erst im Verlauf der Bereitstellung erstellt werden. Außerdem sollte nur die `Read`-Berechtigung für eine einzelne Datei erteilt werden (anstatt `Create`-Berechtigungen für den gesamten Ordner zu gewähren).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IO.StreamWriter>
- [Vorgehensweise: Lesen von Objektdaten aus einer XML-Datei (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)
- [Serialisierung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md)
