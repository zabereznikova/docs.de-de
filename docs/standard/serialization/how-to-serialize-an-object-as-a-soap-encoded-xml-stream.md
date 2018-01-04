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
- csharp
- vb
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
ms.assetid: af406e0a-fa3a-46dd-a7ba-c80731eba3a0
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 863c79b36cd51b2e1e747169fd15a2358a1e6fee
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-serialize-an-object-as-a-soap-encoded-xml-stream"></a><span data-ttu-id="833ac-102">Gewusst wie: Serialisieren eines Objekts als SOAP-codierter XML-Stream</span><span class="sxs-lookup"><span data-stu-id="833ac-102">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>
  
 <span data-ttu-id="833ac-103">Da eine SOAP-Nachricht mithilfe von XML erstellt wird, kann die <xref:System.Xml.Serialization.XmlSerializer>-Klasse zum Serialisieren von Klassen und zum Generieren von codierten SOAP-Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="833ac-103">Because a SOAP message is built using XML, the <xref:System.Xml.Serialization.XmlSerializer> class can be used to serialize classes and generate encoded SOAP messages.</span></span> <span data-ttu-id="833ac-104">Das resultierende XML entspricht [Abschnitt 5 des Dokuments „Simple Object Access Protocol (SOAP) 1.1“ des World Wide Web Consortium](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512).</span><span class="sxs-lookup"><span data-stu-id="833ac-104">The resulting XML conforms to [section 5 of the World Wide Web Consortium document "Simple Object Access Protocol (SOAP) 1.1"](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512).</span></span> <span data-ttu-id="833ac-105">Wenn Sie einen XML-Webdienst erstellen, der durch SOAP-Meldungen kommuniziert, können Sie den XML-Datenstrom anpassen, indem Sie eine Gruppe spezieller SOAP-Attribute auf Klassen und Member von Klassen anwenden.</span><span class="sxs-lookup"><span data-stu-id="833ac-105">When you are creating an XML Web service that communicates through SOAP messages, you can customize the XML stream by applying a set of special SOAP attributes to classes and members of classes.</span></span> <span data-ttu-id="833ac-106">Eine Liste mit Attributen finden Sie unter [Attributes That Control Encoded SOAP Serialization (Attribute zur Steuerung der Serialisierung von codiertem SOAP)](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="833ac-106">For a list of attributes, see [Attributes That Control Encoded SOAP Serialization](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).</span></span>  
  
### <a name="to-serialize-an-object-as-a-soap-encoded-xml-stream"></a><span data-ttu-id="833ac-107">So serialisieren Sie ein Objekt als einen durch SOAP codierten XML-Stream</span><span class="sxs-lookup"><span data-stu-id="833ac-107">To serialize an object as a SOAP-encoded XML stream</span></span>  
  
1.  <span data-ttu-id="833ac-108">Erstellen Sie die Klasse mit dem [XML Schema Definition-Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).</span><span class="sxs-lookup"><span data-stu-id="833ac-108">Create the class using the [XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).</span></span>  
  
2.  <span data-ttu-id="833ac-109">Wenden Sie eines oder mehrere der speziellen Attribute aus `System.Xml.Serialization` an.</span><span class="sxs-lookup"><span data-stu-id="833ac-109">Apply one or more of the special attributes found in `System.Xml.Serialization`.</span></span> <span data-ttu-id="833ac-110">Schlagen Sie hierzu in der Liste unter "Attribute für die Steuerung der Serialisierung von codiertem SOAP" nach.</span><span class="sxs-lookup"><span data-stu-id="833ac-110">See the list in "Attributes That Control Encoded SOAP Serialization."</span></span>  
  
3.  <span data-ttu-id="833ac-111">Erstellen Sie ein `XmlTypeMapping`-Objekt, indem Sie eine neue `SoapReflectionImporter`-Klasse erstellen und die `ImportTypeMapping`-Methode mit dem Typ der serialisierten Klasse aufrufen.</span><span class="sxs-lookup"><span data-stu-id="833ac-111">Create an `XmlTypeMapping` by creating a new `SoapReflectionImporter`, and invoking the `ImportTypeMapping` method with the type of the serialized class.</span></span>  
  
     <span data-ttu-id="833ac-112">Im folgenden Codebeispiel wird die `ImportTypeMapping`-Methode der Klasse `SoapReflectionImporter` aufgerufen, um ein `XmlTypeMapping`-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="833ac-112">The following code example calls the `ImportTypeMapping` method of the `SoapReflectionImporter` class to create an `XmlTypeMapping`.</span></span>  
  
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
  
4.  <span data-ttu-id="833ac-113">Erstellen Sie eine Instanz der `XmlSerializer`-Klasse, indem Sie das `XmlTypeMapping`-Objekt an den <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29>-Konstruktor übergeben.</span><span class="sxs-lookup"><span data-stu-id="833ac-113">Create an instance of the `XmlSerializer` class by passing the `XmlTypeMapping` to the <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29> constructor.</span></span>  
  
    ```vb  
    Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
    ```  
  
    ```csharp  
    XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
    ```  
  
5.  <span data-ttu-id="833ac-114">Rufen Sie die `Serialize`-Methode oder `Deserialize`-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="833ac-114">Call the `Serialize` or `Deserialize` method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="833ac-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="833ac-115">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="833ac-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="833ac-116">See Also</span></span>  
 [<span data-ttu-id="833ac-117">XML- und SOAP-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="833ac-117">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
 [<span data-ttu-id="833ac-118">Attribute zur Steuerung der Serialisierung von codiertem SOAP</span><span class="sxs-lookup"><span data-stu-id="833ac-118">Attributes That Control Encoded SOAP Serialization</span></span>](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md)  
 [<span data-ttu-id="833ac-119">XML-Serialisierung mit XML-Webdiensten</span><span class="sxs-lookup"><span data-stu-id="833ac-119">XML Serialization with XML Web Services</span></span>](../../../docs/standard/serialization/xml-serialization-with-xml-web-services.md)  
 [<span data-ttu-id="833ac-120">Vorgehensweise: Serialisieren eines Objekts</span><span class="sxs-lookup"><span data-stu-id="833ac-120">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)  
 [<span data-ttu-id="833ac-121">Vorgehensweise: Deserialisieren eines Objekts</span><span class="sxs-lookup"><span data-stu-id="833ac-121">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)  
 [<span data-ttu-id="833ac-122">Gewusst wie: Überschreiben von codierter SOAP-XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="833ac-122">How to: Override Encoded SOAP XML Serialization</span></span>](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md)
