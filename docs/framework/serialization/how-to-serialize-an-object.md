---
title: "Vorgehensweise: Serialisieren eines Objekts | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Objekte, Serialisieren von Schritten"
  - "Serialisieren von Objekten"
ms.assetid: a1207d05-32b2-4953-8582-959607991227
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Vorgehensweise: Serialisieren eines Objekts
Wenn Sie ein Objekt serialisieren möchten, erstellen Sie zuerst das zu serialisierende Objekt, und legen Sie dann dessen öffentliche Eigenschaften und Felder fest.Dazu müssen Sie das Transportformat angeben, in dem der XML\-Stream gespeichert werden soll: als Stream oder als Datei.Wenn der XML\-Stream beispielsweise in einer permanenten Form gespeichert werden muss, erstellen Sie ein [FileStream](frlrfSystemIOFileStreamClassTopic)\-Objekt.  
  
> [!NOTE]
>  Weitere Beispiele zur XML\-Serialisierung finden Sie unter [Beispiele für die XML\-Serialisierung](../../../docs/framework/serialization/examples-of-xml-serialization.md).  
  
### So serialisieren Sie ein Objekt  
  
1.  Erstellen Sie das Objekt, und legen Sie seine öffentlichen Felder und Eigenschaften fest.  
  
2.  Erstellen Sie unter Verwendung des Objekttyps ein <xref:System.Xml.Serialization.XmlSerializer>\-Objekt.Weitere Informationen hierzu finden Sie in den Ausführungen zu den <xref:System.Xml.Serialization.XmlSerializer>\-Klassenkonstruktoren.  
  
3.  Rufen Sie die <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A>\-Methode auf, um einen XML\-Stream oder eine Darstellung in Dateiform der öffentlichen Eigenschaften und Felder des Objekts zu generieren.Im folgenden Beispiel wird eine Datei erstellt.  
  
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
  
## Siehe auch  
 [Einführung in die XML\-Serialisierung](../../../docs/framework/serialization/introducing-xml-serialization.md)   
 [Vorgehensweise: Deserialisieren eines Objekts](../../../docs/framework/serialization/how-to-deserialize-an-object.md)