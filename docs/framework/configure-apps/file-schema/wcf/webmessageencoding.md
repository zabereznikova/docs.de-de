---
title: '&lt;webMessageEncoding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 892ca485-e21a-4a44-8e40-633161ef6796
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e9629ecbe744ac1f4bbd44e22ac42a3e81fff27a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltwebmessageencodinggt"></a><span data-ttu-id="99e74-102">&lt;webMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="99e74-102">&lt;webMessageEncoding&gt;</span></span>
<span data-ttu-id="99e74-103">Aktiviert Klartext-XML, JavaScript Object Notation (JSON)-Nachrichtencodierungen und unformatierten binären Inhalt, die bei der Verwendung in einer [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Bindung gelesen und geschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="99e74-103">Enables plain-text XML, JavaScript Object Notation (JSON) message encodings and "raw" binary content to be read and written when used in a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] binding.</span></span>  
  
 <span data-ttu-id="99e74-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="99e74-104">\<system.serviceModel></span></span>  
<span data-ttu-id="99e74-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="99e74-105">\<bindings></span></span>  
<span data-ttu-id="99e74-106">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="99e74-106">\<customBinding></span></span>  
<span data-ttu-id="99e74-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="99e74-107">\<binding></span></span>  
<span data-ttu-id="99e74-108">\<WebMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="99e74-108">\<webMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99e74-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="99e74-109">Syntax</span></span>  
  
```xml  
<webMessageEncoding   
      maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
  
writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99e74-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="99e74-110">Attributes and Elements</span></span>  
 <span data-ttu-id="99e74-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="99e74-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99e74-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="99e74-112">Attributes</span></span>  
  
|<span data-ttu-id="99e74-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="99e74-113">Attribute</span></span>|<span data-ttu-id="99e74-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99e74-114">Description</span></span>|  
|---------------|-----------------|  
|`maxReadPoolSize`|<span data-ttu-id="99e74-115">Die Anzahl von Nachrichten, die gleichzeitig gelesen werden können, ohne neue Reader zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="99e74-115">The amount of messages that can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="99e74-116">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="99e74-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="99e74-117">Der Standard ist 64 Reader für jeden der inneren Encoder (Text, JSON und "unformatiert").</span><span class="sxs-lookup"><span data-stu-id="99e74-117">The default is 64 readers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="99e74-118">Durch das Erhöhen dieser Zahl wird der Speicherverbrauch gesteigert, jedoch wird der Encoder auf einen plötzlichen Anstieg eingehender Nachrichten vorbereitet, da er Reader aus dem Pool verwenden kann, die bereits erstellt wurden, sodass keine neuen Reader erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="99e74-118">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of incoming messages because it is able to use readers from the pool that are already created instead of creating new ones.</span></span>|  
|`maxWritePoolSize`|<span data-ttu-id="99e74-119">Die maximale Anzahl von Nachrichten, die gleichzeitig gesendet werden können, ohne neue Writer zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="99e74-119">The amount of messages that can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="99e74-120">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="99e74-120">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="99e74-121">Der Standard ist 16 Writer für jeden der inneren Encoder (Text, JSON und "unformatiert").</span><span class="sxs-lookup"><span data-stu-id="99e74-121">The default is 16 writers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="99e74-122">Durch das Erhöhen dieser Zahl wird der Speicherverbrauch gesteigert, jedoch wird der Encoder auf einen plötzlichen Anstieg ausgehender Nachrichten vorbereitet, da er Writer aus dem Pool verwenden kann, die bereits erstellt wurden, sodass keine neuen Writer erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="99e74-122">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of outgoing messages because it is able to use writers from the pool that are already created instead of creating new ones.</span></span>|  
|`writeEncoding`|<span data-ttu-id="99e74-123">Gibt die Zeichensatzcodierung an, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="99e74-123">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="99e74-124">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="99e74-124">Valid values are:</span></span><br /><br /> <span data-ttu-id="99e74-125">-UnicodeFffeTextEncoding: Unicode bigEndian-Codierung.</span><span class="sxs-lookup"><span data-stu-id="99e74-125">-   UnicodeFffeTextEncoding: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="99e74-126">-Utf16TextEncoding: Unicode-Codierung.</span><span class="sxs-lookup"><span data-stu-id="99e74-126">-   Utf16TextEncoding: Unicode encoding.</span></span><br /><span data-ttu-id="99e74-127">-Utf8TextEncoding: 8-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="99e74-127">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="99e74-128">Der Standardwert ist Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="99e74-128">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="99e74-129">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="99e74-129">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99e74-130">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="99e74-130">Child Elements</span></span>  
  
|<span data-ttu-id="99e74-131">Element</span><span class="sxs-lookup"><span data-stu-id="99e74-131">Element</span></span>|<span data-ttu-id="99e74-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99e74-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99e74-133">\<ReaderQuotas ></span><span class="sxs-lookup"><span data-stu-id="99e74-133">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="99e74-134">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="99e74-134">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="99e74-135">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="99e74-135">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="99e74-136">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="99e74-136">Parent Elements</span></span>  
  
|<span data-ttu-id="99e74-137">Element</span><span class="sxs-lookup"><span data-stu-id="99e74-137">Element</span></span>|<span data-ttu-id="99e74-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99e74-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99e74-139">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="99e74-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="99e74-140">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="99e74-140">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99e74-141">Hinweise</span><span class="sxs-lookup"><span data-stu-id="99e74-141">Remarks</span></span>  
 <span data-ttu-id="99e74-142">Beim Codieren wird eine Nachricht in eine Bytefolge transformiert.</span><span class="sxs-lookup"><span data-stu-id="99e74-142">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="99e74-143">Beim Decodieren wird dieser Prozess umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="99e74-143">Decoding is the reverse process.</span></span> <span data-ttu-id="99e74-144">Diese Vorgänge erfordern die Angabe einer Zeichencodierung.</span><span class="sxs-lookup"><span data-stu-id="99e74-144">These processes require the specification of a character encoding.</span></span>  
  
 <span data-ttu-id="99e74-145">Dazu delegiert das `webMessageEncoding`-Element Vorgänge an eine Reihe innerer Encoder, um die Klartext-XML und JSON-Codierungen sowie die unformatierten binären Daten zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="99e74-145">The `webMessageEncoding` element works by delegating to a series of inner encoders to handle the plain-text XML and JSON encodings, and "raw" binary data.</span></span> <span data-ttu-id="99e74-146">Diese Delegierung wird von einem zusammengesetzten Nachrichtenencoder durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="99e74-146">This delegation is done by a composite message encoder.</span></span>  
  
 <span data-ttu-id="99e74-147">Dieses Bindungselement und die zusammengesetzten Encoder werden zur Steuerung der Codierung in Szenarien eingesetzt, in denen keine SOAP-Nachrichten vom `webHttpBinding`-Element verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="99e74-147">This binding element and its composite encoder are used to control the encoding in scenarios that do not use SOAP messaging used by the `webHttpBinding` element.</span></span> <span data-ttu-id="99e74-148">Zu den Szenarien gehören u.&#160;a. "Plain Old XML" (POX), Representational State Transfer (REST), Really Simple Syndication (RSS) And Atom Syndication sowie Asynchronous JavaScript And XML (AJAX).</span><span class="sxs-lookup"><span data-stu-id="99e74-148">These scenarios include "Plain Old XML" (POX), Representational State Transfer (REST), Really Simple Syndication (RSS) and Atom syndication, and Asynchronous JavaScript and XML (AJAX).</span></span> <span data-ttu-id="99e74-149">Der zusammengesetzte Nachrichtenencoder unterstützt SOAP oder WS-Addressing nicht.</span><span class="sxs-lookup"><span data-stu-id="99e74-149">The composite message encoder does not support SOAP or WS-Addressing.</span></span>  
  
 <span data-ttu-id="99e74-150">Das Bindungselement kann mit dem `writeEncoding`-Attribut mit einer Schreibzeichencodierung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="99e74-150">The binding element can be configured with a write character encoding by using the `writeEncoding` attribute.</span></span> <span data-ttu-id="99e74-151">Der bereitgestellte <xref:System.Text.Encoding>-Wert gibt das Verhalten beim Schreiben für die JSON- und Text-XML-Fälle an.</span><span class="sxs-lookup"><span data-stu-id="99e74-151">The supplied <xref:System.Text.Encoding> value specifies the behavior on write for the JSON and Textual XML cases.</span></span> <span data-ttu-id="99e74-152">Beim Lesen wird jede gültige Nachrichtencodierung und Textcodierung interpretiert.</span><span class="sxs-lookup"><span data-stu-id="99e74-152">On read, any valid message encoding and text encoding is understood.</span></span>  
  
 <span data-ttu-id="99e74-153">`maxReadPoolSize` und `maxWritePoolSize` können auch zum Festlegen der maximalen Anzahl an jeweils zuzuweisenden Readern und Writern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="99e74-153">`maxReadPoolSize` and `maxWritePoolSize` can also be used to set the maximum number of readers and writers to be allocated respectively.</span></span> <span data-ttu-id="99e74-154">Standardmäßig werden 64 Reader und 16 Writer zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="99e74-154">By default 64 readers and 16 writers are allocated.</span></span>  
  
 <span data-ttu-id="99e74-155">Standardkomplexitätseinschränkungen festgelegt werden, werden auch die [ \<ReaderQuotas >](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd) Element zum Schutz vor einer Klasse von Denial-of-Service (DOS)-Angriffe, die versuchen, die nachrichtenkomplexität zum Binden von Endpunkt-Verarbeitung Verarbeitungsressourcen Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="99e74-155">Default complexity constraints are also set using the [\<readerQuotas>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd) element to protect against a class of denial of service (DOS) attacks that attempt to use message complexity to tie up endpoint processing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99e74-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="99e74-156">Example</span></span>  
  
```xml  
<webMessageEncoding   
    maxReadPoolSize="256"  
    maxWritePoolSize="128"  
    messageVersion="None"  
    textEncoding="utf-8"   
/>  
```  
  
## <a name="see-also"></a><span data-ttu-id="99e74-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99e74-157">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>  
 [<span data-ttu-id="99e74-158">Nachrichtencodierung</span><span class="sxs-lookup"><span data-stu-id="99e74-158">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="99e74-159">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="99e74-159">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="99e74-160">Bindungen</span><span class="sxs-lookup"><span data-stu-id="99e74-160">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="99e74-161">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="99e74-161">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="99e74-162">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="99e74-162">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="99e74-163">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="99e74-163">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
