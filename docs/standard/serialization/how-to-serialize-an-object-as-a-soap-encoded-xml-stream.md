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
# <a name="how-to-serialize-an-object-as-a-soap-encoded-xml-stream"></a><span data-ttu-id="3dd4a-104">Vorgehensweise: Serialisieren eines Objekts als einen durch SOAP codierten XML-Stream</span><span class="sxs-lookup"><span data-stu-id="3dd4a-104">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>
  
 <span data-ttu-id="3dd4a-105">Da eine SOAP-Nachricht mithilfe von XML erstellt wird, kann die <xref:System.Xml.Serialization.XmlSerializer>-Klasse zum Serialisieren von Klassen und zum Generieren von codierten SOAP-Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3dd4a-105">Because a SOAP message is built using XML, the <xref:System.Xml.Serialization.XmlSerializer> class can be used to serialize classes and generate encoded SOAP messages.</span></span> <span data-ttu-id="3dd4a-106">Das resultierende XML entspricht [Abschnitt 5 des Dokuments „Simple Object Access Protocol (SOAP) 1.1“ des World Wide Web Consortium](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512).</span><span class="sxs-lookup"><span data-stu-id="3dd4a-106">The resulting XML conforms to [section 5 of the World Wide Web Consortium document "Simple Object Access Protocol (SOAP) 1.1"](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512).</span></span> <span data-ttu-id="3dd4a-107">Wenn Sie einen XML-Webdienst erstellen, der durch SOAP-Meldungen kommuniziert, können Sie den XML-Datenstrom anpassen, indem Sie eine Gruppe spezieller SOAP-Attribute auf Klassen und Member von Klassen anwenden.</span><span class="sxs-lookup"><span data-stu-id="3dd4a-107">When you are creating an XML Web service that communicates through SOAP messages, you can customize the XML stream by applying a set of special SOAP attributes to classes and members of classes.</span></span> <span data-ttu-id="3dd4a-108">Eine Liste mit Attributen finden Sie unter [Attributes That Control Encoded SOAP Serialization (Attribute zur Steuerung der Serialisierung von codiertem SOAP)](attributes-that-control-encoded-soap-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="3dd4a-108">For a list of attributes, see [Attributes That Control Encoded SOAP Serialization](attributes-that-control-encoded-soap-serialization.md).</span></span>  
  
### <a name="to-serialize-an-object-as-a-soap-encoded-xml-stream"></a><span data-ttu-id="3dd4a-109">So serialisieren Sie ein Objekt als einen durch SOAP codierten XML-Stream</span><span class="sxs-lookup"><span data-stu-id="3dd4a-109">To serialize an object as a SOAP-encoded XML stream</span></span>  
  
1. <span data-ttu-id="3dd4a-110">Erstellen Sie die Klasse mit dem [XML Schema Definition-Tool (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md).</span><span class="sxs-lookup"><span data-stu-id="3dd4a-110">Create the class using the [XML Schema Definition Tool (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md).</span></span>  
  
2. <span data-ttu-id="3dd4a-111">Wenden Sie eines oder mehrere der speziellen Attribute aus `System.Xml.Serialization` an.</span><span class="sxs-lookup"><span data-stu-id="3dd4a-111">Apply one or more of the special attributes found in `System.Xml.Serialization`.</span></span> <span data-ttu-id="3dd4a-112">Schlagen Sie hierzu in der Liste unter "Attribute für die Steuerung der Serialisierung von codiertem SOAP" nach.</span><span class="sxs-lookup"><span data-stu-id="3dd4a-112">See the list in "Attributes That Control Encoded SOAP Serialization."</span></span>  
  
3. <span data-ttu-id="3dd4a-113">Erstellen Sie ein `XmlTypeMapping`-Objekt, indem Sie eine neue `SoapReflectionImporter`-Klasse erstellen und die `ImportTypeMapping`-Methode mit dem Typ der serialisierten Klasse aufrufen.</span><span class="sxs-lookup"><span data-stu-id="3dd4a-113">Create an `XmlTypeMapping` by creating a new `SoapReflectionImporter`, and invoking the `ImportTypeMapping` method with the type of the serialized class.</span></span>  
  
     <span data-ttu-id="3dd4a-114">Im folgenden Codebeispiel wird die `ImportTypeMapping`-Methode der Klasse `SoapReflectionImporter` aufgerufen, um ein `XmlTypeMapping`-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3dd4a-114">The following code example calls the `ImportTypeMapping` method of the `SoapReflectionImporter` class to create an `XmlTypeMapping`.</span></span>  
  
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
  
4. <span data-ttu-id="3dd4a-115">Erstellen Sie eine Instanz der `XmlSerializer`-Klasse, indem Sie das `XmlTypeMapping`-Objekt an den <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29>-Konstruktor übergeben.</span><span class="sxs-lookup"><span data-stu-id="3dd4a-115">Create an instance of the `XmlSerializer` class by passing the `XmlTypeMapping` to the <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29> constructor.</span></span>  
  
    ```vb  
    Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
    ```  
  
    ```csharp  
    XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
    ```  
  
5. <span data-ttu-id="3dd4a-116">Rufen Sie die `Serialize`-Methode oder `Deserialize`-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="3dd4a-116">Call the `Serialize` or `Deserialize` method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3dd4a-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3dd4a-117">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3dd4a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3dd4a-118">See also</span></span>

- [<span data-ttu-id="3dd4a-119">XML- und SOAP-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="3dd4a-119">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
- [<span data-ttu-id="3dd4a-120">Attribute zur Steuerung der Serialisierung von codiertem SOAP</span><span class="sxs-lookup"><span data-stu-id="3dd4a-120">Attributes That Control Encoded SOAP Serialization</span></span>](attributes-that-control-encoded-soap-serialization.md)
- [<span data-ttu-id="3dd4a-121">XML-Serialisierung mit XML-Webdiensten</span><span class="sxs-lookup"><span data-stu-id="3dd4a-121">XML Serialization with XML Web Services</span></span>](xml-serialization-with-xml-web-services.md)
- <span data-ttu-id="3dd4a-122">[How to: Serialisieren eines Objekts](how-to-serialize-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="3dd4a-122">[How to: Serialize an Object](how-to-serialize-an-object.md)</span></span>
- [<span data-ttu-id="3dd4a-123">How to: Deserialisieren eines Objekts</span><span class="sxs-lookup"><span data-stu-id="3dd4a-123">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)
- [<span data-ttu-id="3dd4a-124">How to: Überschreiben von codierter SOAP-XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="3dd4a-124">How to: Override Encoded SOAP XML Serialization</span></span>](how-to-override-encoded-soap-xml-serialization.md)
