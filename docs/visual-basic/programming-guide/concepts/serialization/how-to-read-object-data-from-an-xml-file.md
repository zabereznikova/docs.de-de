---
title: 'Vorgehensweise: Lesen von Objektdaten aus einer XML-Datei (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 1e1423bf-74a4-4dde-a3bb-ae1bfc0a68ed
ms.openlocfilehash: f6233fc7ce74cbd39237bab07cfd2ed22b9c2240
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834893"
---
# <a name="how-to-read-object-data-from-an-xml-file-visual-basic"></a>Vorgehensweise: Lesen von Objektdaten aus einer XML-Datei (Visual Basic)
In diesem Beispiel werden Objektdaten gelesen, die zuvor mithilfe der <xref:System.Xml.Serialization.XmlSerializer>-Klasse in eine XML-Datei geschrieben wurden.  
  
## <a name="example"></a>Beispiel  
  
```vb  
Public Class Book  
    Public Title As String  
End Class  
  
Public Sub ReadXML()  
    Dim reader As New System.Xml.Serialization.XmlSerializer(GetType(Book))  
    Dim file As New System.IO.StreamReader(  
        "c:\temp\SerializationOverview.xml")  
    Dim overview As Book  
    overview = CType(reader.Deserialize(file), Book)  
    Console.WriteLine(overview.Title)  
End Sub  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Ersetzen Sie den Dateinamen „c:\temp\SerializationOverview.xml“ durch den Namen der Datei, die die serialisierten Daten enthält. Weitere Informationen zum Serialisieren von Daten finden Sie unter [Vorgehensweise: Schreiben von Objektdaten in eine XML-Datei (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).  
  
 Die Klasse muss über einen öffentlichen Konstruktor ohne Parameter verfügen.  
  
 Nur die öffentlichen Eigenschaften und Felder werden deserialisiert.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Die zu serialisierende Klasse verfügt nicht über einen öffentlichen, parameterlosen Konstruktor.  
  
-   Die Daten in der Datei stellen keine Daten aus der zu deserialisierenden Klasse dar.  
  
-   Die Datei ist nicht vorhanden (<xref:System.IO.IOException>).  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Überprüfen Sie immer die Eingaben, und deserialisieren Sie keine Daten aus einer nicht vertrauenswürdigen Quelle. Das neu erstellte Objekt wird auf einem lokalen Computer mit den Berechtigungen des Codes ausgeführt, der es deserialisiert hat. Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IO.StreamWriter>
- [Vorgehensweise: Schreiben von Objektdaten in eine XML-Datei (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)
- [Serialisierung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md)
- [Visual Basic-Programmierhandbuch](../../../../visual-basic/programming-guide/index.md)
