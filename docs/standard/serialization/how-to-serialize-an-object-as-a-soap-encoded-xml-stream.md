---
title: 'Vorgehensweise: Serialisieren eines Objekts als einen durch SOAP codierten XML-Stream'
description: Erfahren Sie, wie Sie ein Objekt als SOAP-codierten XML-Stream serialisieren. Die XmlSerializer-Klasse kann zum Serialisieren von Klassen und zum Generieren von codierten SOAP-Nachrichten verwendet werden.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
ms.assetid: af406e0a-fa3a-46dd-a7ba-c80731eba3a0
ms.openlocfilehash: 1d38c4e334439ef41b4d4429e52cff04c6463573
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "84291564"
---
# <a name="how-to-serialize-an-object-as-a-soap-encoded-xml-stream"></a>Vorgehensweise: Serialisieren eines Objekts als einen durch SOAP codierten XML-Stream
  
 Da eine SOAP-Nachricht mithilfe von XML erstellt wird, kann die <xref:System.Xml.Serialization.XmlSerializer>-Klasse zum Serialisieren von Klassen und zum Generieren von codierten SOAP-Nachrichten verwendet werden. Das resultierende XML entspricht [Abschnitt 5 des Dokuments „Simple Object Access Protocol (SOAP) 1.1“ des World Wide Web Consortium](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512). Wenn Sie einen XML-Webdienst erstellen, der durch SOAP-Meldungen kommuniziert, können Sie den XML-Datenstrom anpassen, indem Sie eine Gruppe spezieller SOAP-Attribute auf Klassen und Member von Klassen anwenden. Eine Liste mit Attributen finden Sie unter [Attributes That Control Encoded SOAP Serialization (Attribute zur Steuerung der Serialisierung von codiertem SOAP)](attributes-that-control-encoded-soap-serialization.md).  
  
### <a name="to-serialize-an-object-as-a-soap-encoded-xml-stream"></a>So serialisieren Sie ein Objekt als einen durch SOAP codierten XML-Stream  
  
1. Erstellen Sie die Klasse mit dem [XML Schema Definition-Tool (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md).  
  
2. Wenden Sie eines oder mehrere der speziellen Attribute aus `System.Xml.Serialization` an. Schlagen Sie hierzu in der Liste unter "Attribute für die Steuerung der Serialisierung von codiertem SOAP" nach.  
  
3. Erstellen Sie ein `XmlTypeMapping`-Objekt, indem Sie eine neue `SoapReflectionImporter`-Klasse erstellen und die `ImportTypeMapping`-Methode mit dem Typ der serialisierten Klasse aufrufen.  
  
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
  
4. Erstellen Sie eine Instanz der `XmlSerializer`-Klasse, indem Sie das `XmlTypeMapping`-Objekt an den <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29>-Konstruktor übergeben.  
  
    ```vb  
    Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
    ```  
  
    ```csharp  
    XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
    ```  
  
5. Rufen Sie die `Serialize`-Methode oder `Deserialize`-Methode auf.  
  
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

- [XML- und SOAP-Serialisierung](xml-and-soap-serialization.md)
- [Attribute zur Steuerung der Serialisierung von codiertem SOAP](attributes-that-control-encoded-soap-serialization.md)
- [XML-Serialisierung mit XML-Webdiensten](xml-serialization-with-xml-web-services.md)
- [How to: Serialisieren eines Objekts](how-to-serialize-an-object.md).
- [How to: Deserialisieren eines Objekts](how-to-deserialize-an-object.md)
- [How to: Überschreiben von codierter SOAP-XML-Serialisierung](how-to-override-encoded-soap-xml-serialization.md)
