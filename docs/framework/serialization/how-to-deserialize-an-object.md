---
title: "Vorgehensweise: Deserialisieren eines Objekts | Microsoft Docs"
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
  - "Deserialisieren von Objekten"
  - "Objekte, Deserialisieren von Schritten"
ms.assetid: 287129c8-035a-4fea-b7b3-4790057ca076
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Vorgehensweise: Deserialisieren eines Objekts
Beim Deserialisieren eines Objekts wird durch das Transportformat festgelegt, ob ein Stream\- oder ein Dateiobjekt erstellt wird.Nachdem das Transportformat festgelegt wurde, können Sie je nach Bedarf die <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A>\-Methode oder <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A>\-Methode aufrufen.  
  
### So deserialisieren Sie ein Objekt  
  
1.  Erstellen Sie ein <xref:System.Xml.Serialization.XmlSerializer>\-Objekt unter Verwendung des zu deserialisierenden Objekttyps.  
  
2.  Rufen Sie die <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A>\-Methode auf, um ein Replikat des Objekts zu erzeugen.Beim Deserialisieren müssen Sie das zurückgegebene Objekt in den ursprünglichen Objekttyp umwandeln. Dies wird im folgenden Beispiel gezeigt, in dem das Objekt in eine Datei deserialisiert wird \(es könnte aber auch in einen Stream deserialsiert werden\).  
  
    ```vb  
    Dim myObject As MySerializableClass  
    ' Construct an instance of the XmlSerializer with the type  
    ' of object that is being deserialized.  
    Dim mySerializer As XmlSerializer = New XmlSerializer(GetType(MySerializableClass))  
    ' To read the file, create a FileStream.  
    Dim myFileStream As FileStream = _  
    New FileStream("myFileName.xml", FileMode.Open)  
    ' Call the Deserialize method and cast to the object type.  
    myObject = CType( _  
    mySerializer.Deserialize(myFileStream), MySerializableClass)  
  
    ```  
  
    ```csharp  
    MySerializableClass myObject;  
    // Construct an instance of the XmlSerializer with the type  
    // of object that is being deserialized.  
    XmlSerializer mySerializer =   
    new XmlSerializer(typeof(MySerializableClass));  
    // To read the file, create a FileStream.  
    FileStream myFileStream =   
    new FileStream("myFileName.xml", FileMode.Open);  
    // Call the Deserialize method and cast to the object type.  
    myObject = (MySerializableClass)   
    mySerializer.Deserialize(myFileStream)  
    ```  
  
## Siehe auch  
 [Einführung in die XML\-Serialisierung](../../../docs/framework/serialization/introducing-xml-serialization.md)   
 [Vorgehensweise: Serialisieren eines Objekts](../../../docs/framework/serialization/how-to-serialize-an-object.md)