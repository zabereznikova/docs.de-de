---
title: <webMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 892ca485-e21a-4a44-8e40-633161ef6796
ms.openlocfilehash: a1d776730053cd6af3c930a33e13582a8906c4d7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940400"
---
# <a name="webmessageencoding"></a><span data-ttu-id="0aed8-101">\<webMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="0aed8-101">\<webMessageEncoding></span></span>
<span data-ttu-id="0aed8-102">Aktiviert Klartext-XML, JavaScript Object Notation (JSON)-Nachrichtencodierungen und unformatierten binären Inhalt, die bei der Verwendung in einer Windows Communication Foundation-Bindung (WCF) gelesen und geschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0aed8-102">Enables plain-text XML, JavaScript Object Notation (JSON) message encodings and "raw" binary content to be read and written when used in a Windows Communication Foundation (WCF) binding.</span></span>  
  
 <span data-ttu-id="0aed8-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0aed8-103">\<system.serviceModel></span></span>  
<span data-ttu-id="0aed8-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="0aed8-104">\<bindings></span></span>  
<span data-ttu-id="0aed8-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="0aed8-105">\<customBinding></span></span>  
<span data-ttu-id="0aed8-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="0aed8-106">\<binding></span></span>  
<span data-ttu-id="0aed8-107">\<webMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="0aed8-107">\<webMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0aed8-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="0aed8-108">Syntax</span></span>  
  
```xml  
<webMessageEncoding maxReadPoolSize="Integer"
                    maxWritePoolSize="Integer"
                    writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0aed8-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0aed8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0aed8-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0aed8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0aed8-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="0aed8-111">Attributes</span></span>  
  
|<span data-ttu-id="0aed8-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="0aed8-112">Attribute</span></span>|<span data-ttu-id="0aed8-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0aed8-113">Description</span></span>|  
|---------------|-----------------|  
|`maxReadPoolSize`|<span data-ttu-id="0aed8-114">Die Anzahl von Nachrichten, die gleichzeitig gelesen werden können, ohne neue Reader zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="0aed8-114">The amount of messages that can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="0aed8-115">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="0aed8-115">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="0aed8-116">Der Standard ist 64 Reader für jeden der inneren Encoder (Text, JSON und "unformatiert").</span><span class="sxs-lookup"><span data-stu-id="0aed8-116">The default is 64 readers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="0aed8-117">Durch das Erhöhen dieser Zahl wird der Speicherverbrauch gesteigert, jedoch wird der Encoder auf einen plötzlichen Anstieg eingehender Nachrichten vorbereitet, da er Reader aus dem Pool verwenden kann, die bereits erstellt wurden, sodass keine neuen Reader erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="0aed8-117">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of incoming messages because it is able to use readers from the pool that are already created instead of creating new ones.</span></span>|  
|`maxWritePoolSize`|<span data-ttu-id="0aed8-118">Die maximale Anzahl von Nachrichten, die gleichzeitig gesendet werden können, ohne neue Writer zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="0aed8-118">The amount of messages that can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="0aed8-119">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="0aed8-119">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="0aed8-120">Der Standard ist 16 Writer für jeden der inneren Encoder (Text, JSON und "unformatiert").</span><span class="sxs-lookup"><span data-stu-id="0aed8-120">The default is 16 writers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="0aed8-121">Durch das Erhöhen dieser Zahl wird der Speicherverbrauch gesteigert, jedoch wird der Encoder auf einen plötzlichen Anstieg ausgehender Nachrichten vorbereitet, da er Writer aus dem Pool verwenden kann, die bereits erstellt wurden, sodass keine neuen Writer erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="0aed8-121">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of outgoing messages because it is able to use writers from the pool that are already created instead of creating new ones.</span></span>|  
|`writeEncoding`|<span data-ttu-id="0aed8-122">Gibt die Zeichensatzcodierung an, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0aed8-122">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="0aed8-123">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="0aed8-123">Valid values are:</span></span><br /><br /> <span data-ttu-id="0aed8-124">UnicodeFffeTextEncoding Unicode Big-codierte Codierung.</span><span class="sxs-lookup"><span data-stu-id="0aed8-124">-   UnicodeFffeTextEncoding: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="0aed8-125">Utf16TextEncoding Unicode-Codierung.</span><span class="sxs-lookup"><span data-stu-id="0aed8-125">-   Utf16TextEncoding: Unicode encoding.</span></span><br /><span data-ttu-id="0aed8-126">Utf8TextEncoding 8-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="0aed8-126">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="0aed8-127">Der Standardwert ist Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="0aed8-127">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="0aed8-128">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="0aed8-128">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0aed8-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0aed8-129">Child Elements</span></span>  
  
|<span data-ttu-id="0aed8-130">Element</span><span class="sxs-lookup"><span data-stu-id="0aed8-130">Element</span></span>|<span data-ttu-id="0aed8-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0aed8-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0aed8-132">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0aed8-132">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="0aed8-133">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="0aed8-133">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="0aed8-134">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="0aed8-134">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0aed8-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0aed8-135">Parent Elements</span></span>  
  
|<span data-ttu-id="0aed8-136">Element</span><span class="sxs-lookup"><span data-stu-id="0aed8-136">Element</span></span>|<span data-ttu-id="0aed8-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0aed8-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0aed8-138">\<binding></span><span class="sxs-lookup"><span data-stu-id="0aed8-138">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="0aed8-139">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="0aed8-139">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0aed8-140">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0aed8-140">Remarks</span></span>  
 <span data-ttu-id="0aed8-141">Beim Codieren wird eine Nachricht in eine Bytefolge transformiert.</span><span class="sxs-lookup"><span data-stu-id="0aed8-141">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="0aed8-142">Beim Decodieren wird dieser Prozess umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="0aed8-142">Decoding is the reverse process.</span></span> <span data-ttu-id="0aed8-143">Diese Vorgänge erfordern die Angabe einer Zeichencodierung.</span><span class="sxs-lookup"><span data-stu-id="0aed8-143">These processes require the specification of a character encoding.</span></span>  
  
 <span data-ttu-id="0aed8-144">Dazu delegiert das `webMessageEncoding`-Element Vorgänge an eine Reihe innerer Encoder, um die Klartext-XML und JSON-Codierungen sowie die unformatierten binären Daten zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0aed8-144">The `webMessageEncoding` element works by delegating to a series of inner encoders to handle the plain-text XML and JSON encodings, and "raw" binary data.</span></span> <span data-ttu-id="0aed8-145">Diese Delegierung wird von einem zusammengesetzten Nachrichtenencoder durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="0aed8-145">This delegation is done by a composite message encoder.</span></span>  
  
 <span data-ttu-id="0aed8-146">Dieses Bindungselement und die zusammengesetzten Encoder werden zur Steuerung der Codierung in Szenarien eingesetzt, in denen keine SOAP-Nachrichten vom `webHttpBinding`-Element verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0aed8-146">This binding element and its composite encoder are used to control the encoding in scenarios that do not use SOAP messaging used by the `webHttpBinding` element.</span></span> <span data-ttu-id="0aed8-147">Zu den Szenarien gehören u.&#160;a. "Plain Old XML" (POX), Representational State Transfer (REST), Really Simple Syndication (RSS) And Atom Syndication sowie Asynchronous JavaScript And XML (AJAX).</span><span class="sxs-lookup"><span data-stu-id="0aed8-147">These scenarios include "Plain Old XML" (POX), Representational State Transfer (REST), Really Simple Syndication (RSS) and Atom syndication, and Asynchronous JavaScript and XML (AJAX).</span></span> <span data-ttu-id="0aed8-148">Der zusammengesetzte Nachrichtenencoder unterstützt SOAP oder WS-Addressing nicht.</span><span class="sxs-lookup"><span data-stu-id="0aed8-148">The composite message encoder does not support SOAP or WS-Addressing.</span></span>  
  
 <span data-ttu-id="0aed8-149">Das Bindungselement kann mit dem `writeEncoding`-Attribut mit einer Schreibzeichencodierung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="0aed8-149">The binding element can be configured with a write character encoding by using the `writeEncoding` attribute.</span></span> <span data-ttu-id="0aed8-150">Der bereitgestellte <xref:System.Text.Encoding>-Wert gibt das Verhalten beim Schreiben für die JSON- und Text-XML-Fälle an.</span><span class="sxs-lookup"><span data-stu-id="0aed8-150">The supplied <xref:System.Text.Encoding> value specifies the behavior on write for the JSON and Textual XML cases.</span></span> <span data-ttu-id="0aed8-151">Beim Lesen wird jede gültige Nachrichtencodierung und Textcodierung interpretiert.</span><span class="sxs-lookup"><span data-stu-id="0aed8-151">On read, any valid message encoding and text encoding is understood.</span></span>  
  
 <span data-ttu-id="0aed8-152">`maxReadPoolSize` und `maxWritePoolSize` können auch zum Festlegen der maximalen Anzahl an jeweils zuzuweisenden Readern und Writern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0aed8-152">`maxReadPoolSize` and `maxWritePoolSize` can also be used to set the maximum number of readers and writers to be allocated respectively.</span></span> <span data-ttu-id="0aed8-153">Standardmäßig werden 64 Reader und 16 Writer zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="0aed8-153">By default 64 readers and 16 writers are allocated.</span></span>  
  
 <span data-ttu-id="0aed8-154">Standard Komplexitäts Einschränkungen werden auch mit dem [ \<Readerkontingenten >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100)) -Element festgelegt, um vor einer Klasse von DOS-Angriffen (Denial of Service) zu schützen, die versuchen, die Nachrichten Komplexität zum Binden von Endpunkt-Verarbeitungs Ressourcen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0aed8-154">Default complexity constraints are also set using the [\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100)) element to protect against a class of denial of service (DOS) attacks that attempt to use message complexity to tie up endpoint processing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0aed8-155">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0aed8-155">Example</span></span>  
  
```xml  
<webMessageEncoding maxReadPoolSize="256"
                    maxWritePoolSize="128"
                    messageVersion="None"
                    textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="0aed8-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0aed8-156">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>
- [<span data-ttu-id="0aed8-157">Nachrichtencodierung</span><span class="sxs-lookup"><span data-stu-id="0aed8-157">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="0aed8-158">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="0aed8-158">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="0aed8-159">Bindungen</span><span class="sxs-lookup"><span data-stu-id="0aed8-159">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0aed8-160">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="0aed8-160">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0aed8-161">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="0aed8-161">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="0aed8-162">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="0aed8-162">\<customBinding></span></span>](custombinding.md)
