---
title: 'Vorgehensweise: Serialisieren eines Objekts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.assetid: a1207d05-32b2-4953-8582-959607991227
ms.openlocfilehash: 3e24d890d47747c51086214530073fc551321079
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159883"
---
# <a name="how-to-serialize-an-object"></a>Vorgehensweise: Serialisieren eines Objekts
Wenn Sie ein Objekt serialisieren möchten, erstellen Sie zuerst das zu serialisierende Objekt und legen dann dessen öffentliche Eigenschaften und Felder fest. Dazu müssen Sie das Transportformat angeben, in dem der XML-Stream gespeichert werden soll: als Stream oder als Datei. Wenn der XML-Stream beispielsweise in einer permanenten Form gespeichert werden muss, erstellen Sie ein <xref:System.IO.FileStream>-Objekt.  
  
> [!NOTE]
> Weitere Beispiele zur XML-Serialisierung finden Sie unter [Examples of XML Serialization (Beispiele für die XML-Serialisierung)](../../../docs/standard/serialization/examples-of-xml-serialization.md).  
  
### <a name="to-serialize-an-object"></a>So serialisieren Sie ein Objekt  
  
1. Erstellen Sie das Objekt, und legen Sie seine öffentlichen Felder und Eigenschaften fest.  
  
2. Erstellen Sie unter Verwendung des Objekttyps ein <xref:System.Xml.Serialization.XmlSerializer>-Objekt. Weitere Informationen hierzu finden Sie in den Ausführungen zu den <xref:System.Xml.Serialization.XmlSerializer>-Klassenkonstruktoren.  
  
3. Rufen Sie die <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A>-Methode auf, um einen XML-Stream oder eine Darstellung in Dateiform der öffentlichen Eigenschaften und Felder des Objekts zu generieren. Im folgenden Beispiel wird eine Datei erstellt.  
  
    ```vb  
    Dim myObject As MySerializableClass = New MySerializableClass()  
    ' Insert code to set properties and fields of the object.  
    Dim mySerializer As XmlSerializer = New XmlSerializer(GetType(MySerializableClass))  
    ' To write to a file, create a StreamWriter object.  
    Dim myWriter As StreamWriter = New StreamWriter("myFileName.xml")  
    mySerializer.Serialize(myWriter, myObject)  
    myWriter.Close()  
    ```  
  
    ```csharp  
    MySerializableClass myObject = new MySerializableClass();  
    // Insert code to set properties and fields of the object.  
    XmlSerializer mySerializer = new
    XmlSerializer(typeof(MySerializableClass));  
    // To write to a file, create a StreamWriter object.  
    StreamWriter myWriter = new StreamWriter("myFileName.xml");  
    mySerializer.Serialize(myWriter, myObject);  
    myWriter.Close();  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in die XML-Serialisierung](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [How to: Deserialisieren eines Objekts](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
