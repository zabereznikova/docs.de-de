---
title: "Vorgehensweise: Serialisieren eines Objekts als SOAP-codierter XML-Stream | Microsoft Docs"
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
  - "Serialisierung, SOAP"
  - "SOAP, XML-Serialisierung"
  - "XML-Serialisierung, SOAP"
ms.assetid: af406e0a-fa3a-46dd-a7ba-c80731eba3a0
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Vorgehensweise: Serialisieren eines Objekts als SOAP-codierter XML-Stream
[Codebeispiel](#cpconxmlserializationusingsoapprotocolanchor1)  
  
 Da eine SOAP\-Nachricht mithilfe von XML erstellt wird, kann die [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)\-Klasse zum Serialisieren von Klassen und zum Generieren von codierten SOAP\-Nachrichten verwendet werden.Das resultierende XML entspricht Abschnitt 5 des Dokuments "Simple Object Access Protocol \(SOAP\) 1.1" des World Wide Web Consortium \(www.w3.org\).Wenn Sie einen XML\-Webdienst erstellen, der durch SOAP\-Meldungen kommuniziert, können Sie den XML\-Datenstrom anpassen, indem Sie eine Gruppe spezieller SOAP\-Attribute auf Klassen und Member von Klassen anwenden.Eine Liste der Attribute finden Sie unter [Attribute zur Steuerung der Serialisierung von codiertem SOAP](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md).  
  
### So serialisieren Sie ein Objekt als einen durch SOAP codierten XML\-Stream  
  
1.  Erstellen Sie die Klasse mit dem [XML Schema Definition\-Tool \(Xsd.exe\)](../../../docs/framework/serialization/xml-schema-definition-tool-xsd-exe.md).  
  
2.  Wenden Sie eines oder mehrere der speziellen Attribute aus **System.Xml.Serialization** an.Schlagen Sie hierzu in der Liste unter "Attribute für die Steuerung der Serialisierung von codiertem SOAP" nach.  
  
3.  Erstellen Sie ein **XmlTypeMapping**\-Objekt, indem Sie eine neue **SoapReflectionImporter**\-Klasse erstellen und die **ImportTypeMapping**\-Methode mit dem Typ der serialisierten Klasse aufrufen.  
  
     Im folgenden Codebeispiel wird die **ImportTypeMapping**\-Methode der **SoapReflectionImporter**\-Klasse aufgerufen, um ein **XmlTypeMapping**\-Objekt zu erstellen.  
  
    ```vb  
    ' Serializes a class named Group as a SOAP message.  
    Dim myTypeMapping As XmlTypeMapping = (New SoapReflectionImporter(). _  
    ImportTypeMapping(GetType(Group))  
  
    ```  
  
    ```csharp  
    // Serializes a class named Group as a SOAP message.  
    XmlTypeMapping myTypeMapping = (new SoapReflectionImporter().  
    ImportTypeMapping(typeof(Group));  
    ```  
  
4.  Erstellen Sie eine Instanz der **XmlSerializer**\-Klasse, indem Sie das **XmlTypeMapping**\-Objekt an den <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29>\-Konstruktor übergeben.  
  
    ```vb  
    Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
  
    ```  
  
    ```csharp  
    XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
    ```  
  
5.  Rufen Sie die **Serialize**\-Methode oder **Deserialize**\-Methode auf.  
  
## Beispiel  
  
```vb  
' Serializes a class named Group as a SOAP message.  
Dim myTypeMapping As XmlTypeMapping = (New SoapReflectionImporter(). _  
ImportTypeMapping(GetType(Group))  
Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
  
```  
  
```csharp  
// Serializes a class named Group as a SOAP message.  
XmlTypeMapping myTypeMapping = (new SoapReflectionImporter().ImportTypeMapping(typeof(Group));  
XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
```  
  
## Siehe auch  
 [XML\- und SOAP\-Serialisierung](../../../docs/framework/serialization/xml-and-soap-serialization.md)   
 [Attribute zur Steuerung der Serialisierung von codiertem SOAP](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md)   
 [XML\-Serialisierung mit XML\-Webdiensten](../../../docs/framework/serialization/xml-serialization-with-xml-web-services.md)   
 [Vorgehensweise: Serialisieren eines Objekts](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [Vorgehensweise: Deserialisieren eines Objekts](../../../docs/framework/serialization/how-to-deserialize-an-object.md)   
 [Vorgehensweise: Überschreiben von codierter SOAP\-XML\-Serialisierung](../../../docs/framework/serialization/how-to-override-encoded-soap-xml-serialization.md)