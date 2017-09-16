---
title: 'Gewusst wie: Serialisieren eines Objekts als SOAP-codierter XML-Stream'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
ms.assetid: af406e0a-fa3a-46dd-a7ba-c80731eba3a0
caps.latest.revision: 6
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 717bcb6f9f72a728d77e2847096ea558a9c50902
ms.openlocfilehash: 84bdce1e7a877425a38a980ba306d38573add227
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-serialize-an-object-as-a-soap-encoded-xml-stream"></a>Gewusst wie: Serialisieren eines Objekts als SOAP-codierter XML-Stream
  
 Da eine SOAP-Nachricht mithilfe von XML erstellt wird, kann die <xref:System.Xml.Serialization.XmlSerializer>-Klasse zum Serialisieren von Klassen und zum Generieren von codierten SOAP-Nachrichten verwendet werden. Das resultierende XML entspricht [Abschnitt 5 des Dokuments „Simple Object Access Protocol (SOAP) 1.1“ des World Wide Web Consortium](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512). Wenn Sie einen XML-Webdienst erstellen, der durch SOAP-Meldungen kommuniziert, können Sie den XML-Datenstrom anpassen, indem Sie eine Gruppe spezieller SOAP-Attribute auf Klassen und Member von Klassen anwenden. Eine Liste mit Attributen finden Sie unter [Attributes That Control Encoded SOAP Serialization (Attribute zur Steuerung der Serialisierung von codiertem SOAP)](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).  
  
### <a name="to-serialize-an-object-as-a-soap-encoded-xml-stream"></a>So serialisieren Sie ein Objekt als einen durch SOAP codierten XML-Stream  
  
1.  Erstellen Sie die Klasse mit dem [XML Schema Definition-Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).  
  
2.  Wenden Sie eines oder mehrere der speziellen Attribute aus `System.Xml.Serialization` an. Schlagen Sie hierzu in der Liste unter "Attribute für die Steuerung der Serialisierung von codiertem SOAP" nach.  
  
3.  Erstellen Sie ein `XmlTypeMapping`-Objekt, indem Sie eine neue `SoapReflectionImporter`-Klasse erstellen und die `ImportTypeMapping`-Methode mit dem Typ der serialisierten Klasse aufrufen.  
  
     Im folgenden Codebeispiel wird die `ImportTypeMapping`-Methode der Klasse `SoapReflectionImporter` aufgerufen, um ein `XmlTypeMapping`-Objekt zu erstellen.  
  
    ```vb  
    ' Serializes a class named Group as a SOAP message.  
    Dim myTypeMapping As XmlTypeMapping =
        New SoapReflectionImporter().ImportTypeMapping(GetType(Group))  
    ```  
  
    ```csharp  
    // Serializes a class named Group as a SOAP message.  
    XmlTypeMapping myTypeMapping =
        new SoapReflectionImporter().ImportTypeMapping(typeof(Group));
    ```  
  
4.  Erstellen Sie eine Instanz der `XmlSerializer`-Klasse, indem Sie das `XmlTypeMapping`-Objekt an den <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29>-Konstruktor übergeben.  
  
    ```vb  
    Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
    ```  
  
    ```csharp  
    XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
    ```  
  
5.  Rufen Sie die `Serialize`-Methode oder `Deserialize`-Methode auf.  
  
## <a name="example"></a>Beispiel  
  
```vb  
' Serializes a class named Group as a SOAP message.  
Dim myTypeMapping As XmlTypeMapping =
    New SoapReflectionImporter().ImportTypeMapping(GetType(Group))
Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
```  
  
```csharp  
// Serializes a class named Group as a SOAP message.  
XmlTypeMapping myTypeMapping =
    new SoapReflectionImporter().ImportTypeMapping(typeof(Group));
XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
```  
  
## <a name="see-also"></a>Siehe auch  
 [XML and SOAP Serialization (XML- und SOAP-Serialisierung)](../../../docs/standard/serialization/xml-and-soap-serialization.md)   
 [Attributes That Control Encoded SOAP Serialization (Attribute zur Steuerung der Serialisierung von codiertem SOAP)](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md)   
 [XML Serialization with XML Web Services (XML-Serialisierung mit XML-Webdiensten)](../../../docs/standard/serialization/xml-serialization-with-xml-web-services.md)   
 [How to: Serialize an Object (Vorgehensweise: Serialisieren eines Objekts)](../../../docs/standard/serialization/how-to-serialize-an-object.md)   
 [How to: Deserialize an Object (Vorgehensweise: Deserialisieren eines Objekts)](../../../docs/standard/serialization/how-to-deserialize-an-object.md)   
 [Gewusst wie: Überschreiben von codierter SOAP-XML-Serialisierung](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md)

