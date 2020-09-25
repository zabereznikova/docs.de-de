---
title: <webMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 892ca485-e21a-4a44-8e40-633161ef6796
ms.openlocfilehash: b250b64e1f073e00e4047ab6931a00d0b93b55b5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177877"
---
# \<webMessageEncoding>

<span data-ttu-id="339f5-101">Aktiviert Klartext-XML, JavaScript Object Notation (JSON)-Nachrichtencodierungen und unformatierten binären Inhalt, die bei der Verwendung in einer Windows Communication Foundation-Bindung (WCF) gelesen und geschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="339f5-101">Enables plain-text XML, JavaScript Object Notation (JSON) message encodings and "raw" binary content to be read and written when used in a Windows Communication Foundation (WCF) binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="339f5-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="339f5-102">Syntax</span></span>  
  
```xml  
<webMessageEncoding maxReadPoolSize="Integer"
                    maxWritePoolSize="Integer"
                    writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="339f5-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="339f5-103">Attributes and Elements</span></span>  

 <span data-ttu-id="339f5-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="339f5-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="339f5-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="339f5-105">Attributes</span></span>  
  
|<span data-ttu-id="339f5-106">attribute</span><span class="sxs-lookup"><span data-stu-id="339f5-106">Attribute</span></span>|<span data-ttu-id="339f5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="339f5-107">Description</span></span>|  
|---------------|-----------------|  
|`maxReadPoolSize`|<span data-ttu-id="339f5-108">Die Anzahl von Nachrichten, die gleichzeitig gelesen werden können, ohne neue Reader zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="339f5-108">The amount of messages that can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="339f5-109">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="339f5-109">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="339f5-110">Der Standard ist 64 Reader für jeden der inneren Encoder (Text, JSON und "unformatiert").</span><span class="sxs-lookup"><span data-stu-id="339f5-110">The default is 64 readers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="339f5-111">Durch das Erhöhen dieser Zahl wird der Speicherverbrauch gesteigert, jedoch wird der Encoder auf einen plötzlichen Anstieg eingehender Nachrichten vorbereitet, da er Reader aus dem Pool verwenden kann, die bereits erstellt wurden, sodass keine neuen Reader erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="339f5-111">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of incoming messages because it is able to use readers from the pool that are already created instead of creating new ones.</span></span>|  
|`maxWritePoolSize`|<span data-ttu-id="339f5-112">Die maximale Anzahl von Nachrichten, die gleichzeitig gesendet werden können, ohne neue Writer zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="339f5-112">The amount of messages that can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="339f5-113">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="339f5-113">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="339f5-114">Der Standard ist 16 Writer für jeden der inneren Encoder (Text, JSON und "unformatiert").</span><span class="sxs-lookup"><span data-stu-id="339f5-114">The default is 16 writers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="339f5-115">Durch das Erhöhen dieser Zahl wird der Speicherverbrauch gesteigert, jedoch wird der Encoder auf einen plötzlichen Anstieg ausgehender Nachrichten vorbereitet, da er Writer aus dem Pool verwenden kann, die bereits erstellt wurden, sodass keine neuen Writer erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="339f5-115">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of outgoing messages because it is able to use writers from the pool that are already created instead of creating new ones.</span></span>|  
|`writeEncoding`|<span data-ttu-id="339f5-116">Gibt die Zeichensatzcodierung an, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="339f5-116">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="339f5-117">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="339f5-117">Valid values are:</span></span><br /><br /> <span data-ttu-id="339f5-118">-UnicodeFffeTextEncoding: Unicode Big-codierte Codierung.</span><span class="sxs-lookup"><span data-stu-id="339f5-118">-   UnicodeFffeTextEncoding: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="339f5-119">-Utf16TextEncoding: Unicode-Codierung.</span><span class="sxs-lookup"><span data-stu-id="339f5-119">-   Utf16TextEncoding: Unicode encoding.</span></span><br /><span data-ttu-id="339f5-120">-Utf8TextEncoding: 8-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="339f5-120">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="339f5-121">Der Standardwert ist Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="339f5-121">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="339f5-122">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="339f5-122">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="339f5-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="339f5-123">Child Elements</span></span>  
  
|<span data-ttu-id="339f5-124">Element</span><span class="sxs-lookup"><span data-stu-id="339f5-124">Element</span></span>|<span data-ttu-id="339f5-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="339f5-125">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="339f5-126">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="339f5-126">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="339f5-127">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="339f5-127">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="339f5-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="339f5-128">Parent Elements</span></span>  
  
|<span data-ttu-id="339f5-129">Element</span><span class="sxs-lookup"><span data-stu-id="339f5-129">Element</span></span>|<span data-ttu-id="339f5-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="339f5-130">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="339f5-131">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="339f5-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="339f5-132">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="339f5-132">Remarks</span></span>  

 <span data-ttu-id="339f5-133">Beim Codieren wird eine Nachricht in eine Bytefolge transformiert.</span><span class="sxs-lookup"><span data-stu-id="339f5-133">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="339f5-134">Beim Decodieren wird dieser Prozess umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="339f5-134">Decoding is the reverse process.</span></span> <span data-ttu-id="339f5-135">Diese Vorgänge erfordern die Angabe einer Zeichencodierung.</span><span class="sxs-lookup"><span data-stu-id="339f5-135">These processes require the specification of a character encoding.</span></span>  
  
 <span data-ttu-id="339f5-136">Dazu delegiert das `webMessageEncoding`-Element Vorgänge an eine Reihe innerer Encoder, um die Klartext-XML und JSON-Codierungen sowie die unformatierten binären Daten zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="339f5-136">The `webMessageEncoding` element works by delegating to a series of inner encoders to handle the plain-text XML and JSON encodings, and "raw" binary data.</span></span> <span data-ttu-id="339f5-137">Diese Delegierung wird von einem zusammengesetzten Nachrichtenencoder durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="339f5-137">This delegation is done by a composite message encoder.</span></span>  
  
 <span data-ttu-id="339f5-138">Dieses Bindungselement und die zusammengesetzten Encoder werden zur Steuerung der Codierung in Szenarien eingesetzt, in denen keine SOAP-Nachrichten vom `webHttpBinding`-Element verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="339f5-138">This binding element and its composite encoder are used to control the encoding in scenarios that do not use SOAP messaging used by the `webHttpBinding` element.</span></span> <span data-ttu-id="339f5-139">Zu den Szenarien gehören u.&#160;a. "Plain Old XML" (POX), Representational State Transfer (REST), Really Simple Syndication (RSS) And Atom Syndication sowie Asynchronous JavaScript And XML (AJAX).</span><span class="sxs-lookup"><span data-stu-id="339f5-139">These scenarios include "Plain Old XML" (POX), Representational State Transfer (REST), Really Simple Syndication (RSS) and Atom syndication, and Asynchronous JavaScript and XML (AJAX).</span></span> <span data-ttu-id="339f5-140">Der zusammengesetzte Nachrichtenencoder unterstützt SOAP oder WS-Addressing nicht.</span><span class="sxs-lookup"><span data-stu-id="339f5-140">The composite message encoder does not support SOAP or WS-Addressing.</span></span>  
  
 <span data-ttu-id="339f5-141">Das Bindungselement kann mit dem `writeEncoding`-Attribut mit einer Schreibzeichencodierung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="339f5-141">The binding element can be configured with a write character encoding by using the `writeEncoding` attribute.</span></span> <span data-ttu-id="339f5-142">Der bereitgestellte <xref:System.Text.Encoding>-Wert gibt das Verhalten beim Schreiben für die JSON- und Text-XML-Fälle an.</span><span class="sxs-lookup"><span data-stu-id="339f5-142">The supplied <xref:System.Text.Encoding> value specifies the behavior on write for the JSON and Textual XML cases.</span></span> <span data-ttu-id="339f5-143">Beim Lesen wird jede gültige Nachrichtencodierung und Textcodierung interpretiert.</span><span class="sxs-lookup"><span data-stu-id="339f5-143">On read, any valid message encoding and text encoding is understood.</span></span>  
  
 <span data-ttu-id="339f5-144">`maxReadPoolSize` und `maxWritePoolSize` können auch zum Festlegen der maximalen Anzahl an jeweils zuzuweisenden Readern und Writern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="339f5-144">`maxReadPoolSize` and `maxWritePoolSize` can also be used to set the maximum number of readers and writers to be allocated respectively.</span></span> <span data-ttu-id="339f5-145">Standardmäßig werden 64 Reader und 16 Writer zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="339f5-145">By default 64 readers and 16 writers are allocated.</span></span>  
  
 <span data-ttu-id="339f5-146">Standard Komplexitäts Einschränkungen werden auch mit dem-Element festgelegt [\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100)) , um vor einer Klasse von DOS-Angriffen (Denial of Service) zu schützen, die versuchen, die Nachrichten Komplexität zum Binden von Endpunkt-Verarbeitungs Ressourcen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="339f5-146">Default complexity constraints are also set using the [\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100)) element to protect against a class of denial of service (DOS) attacks that attempt to use message complexity to tie up endpoint processing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="339f5-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="339f5-147">Example</span></span>  
  
```xml  
<webMessageEncoding maxReadPoolSize="256"
                    maxWritePoolSize="128"
                    messageVersion="None"
                    textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="339f5-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="339f5-148">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>
- [<span data-ttu-id="339f5-149">Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="339f5-149">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="339f5-150">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="339f5-150">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="339f5-151">Bindungen</span><span class="sxs-lookup"><span data-stu-id="339f5-151">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="339f5-152">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="339f5-152">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="339f5-153">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="339f5-153">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
