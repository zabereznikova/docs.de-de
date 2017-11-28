---
title: 'Vorgehensweise: Lesen von Objektdaten aus einer XML-Datei (C#)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 6ad60d96-a4d9-48e6-a8b0-d7f6f803cafa
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6a3389de2f3272a546a7380ef386f5d88666e6d1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-object-data-from-an-xml-file-c"></a>Vorgehensweise: Lesen von Objektdaten aus einer XML-Datei (C#)
In diesem Beispiel werden Objektdaten gelesen, die zuvor mithilfe der <xref:System.Xml.Serialization.XmlSerializer>-Klasse in eine XML-Datei geschrieben wurden.  
  
## <a name="example"></a>Beispiel  
  
```csharp  
public class Book  
{  
    public String title;  
}         
  
public void ReadXML()  
{  
    // First write something so that there is something to read ...  
    var b = new Book { title = "Serialization Overview" };  
    var writer = new System.Xml.Serialization.XmlSerializer(typeof(Book));  
    var wfile = new System.IO.StreamWriter(@"c:\temp\SerializationOverview.xml");  
    writer.Serialize(wfile, b);  
    wfile.Close();  
  
    // Now we can read the serialized book ...  
    System.Xml.Serialization.XmlSerializer reader =   
        new System.Xml.Serialization.XmlSerializer(typeof(Book));  
    System.IO.StreamReader file = new System.IO.StreamReader(  
        @"c:\temp\SerializationOverview.xml");  
    Book overview =  (Book)reader.Deserialize(file);  
    file.Close();  
  
    Console.WriteLine(overview.title);  
  
}  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Ersetzen Sie den Dateinamen „c:\temp\SerializationOverview.xml“ durch den Namen der Datei, die die serialisierten Daten enthält. Weitere Informationen zum Serialisieren von Daten finden Sie unter [Vorgehensweise: Schreiben von Objektdaten in eine XML-Datei (C#)](../../../../csharp/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).  
  
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
 <xref:System.IO.StreamWriter>  
 [How to: Write Object Data to an XML File (C#)](../../../../csharp/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md) (Vorgehensweise: Schreiben von Objektdaten in eine XML-Datei (C#))  
 [Serialisierung (C#)](../../../../csharp/programming-guide/concepts/serialization/index.md)  
 [C#-Programmierhandbuch](../../../../csharp/programming-guide/index.md)
