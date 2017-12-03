---
title: '&lt;udpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa291901-8340-45c6-9c44-5d9281c70bc3
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 26ed0c9dd2c895d4a01536a5715c6235ff65df7b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltudpbindinggt"></a><span data-ttu-id="ef076-102">&lt;udpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="ef076-102">&lt;udpBinding&gt;</span></span>
<span data-ttu-id="ef076-103">Ein Konfigurationselement, das zum Konfigurieren der <xref:System.ServiceModel.UdpBinding>-Bindung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ef076-103">A configuration element used to configure the <xref:System.ServiceModel.UdpBinding> binding.</span></span>  
  
 <span data-ttu-id="ef076-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ef076-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ef076-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="ef076-105">\<bindings></span></span>  
<span data-ttu-id="ef076-106">\<UdpBinding ></span><span class="sxs-lookup"><span data-stu-id="ef076-106">\<udpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef076-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef076-107">Syntax</span></span>  
  
```xml  
<udpBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       duplicateMessageHistoryLength="Integer"  
       maxBufferPoolSize="Integer"  
       maxBufferSize="Integer"       maxPendingMessagesTotalSize="Integer"  
       maxReceivedMessageSize="Integer"       maxRetransmitCount="Integer"  
       multicastInterfaceId="Integer"  
              name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan"  
       textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
       timeToLive="TimeSpan">  
       <readerQuotas   
            maxArrayLength="Integer"  
            maxBytesPerRead="Integer"  
            maxDepth="Integer"             maxNameTableCharCount="Integer"                maxStringContentLength="Integer" />  
   </binding>  
</basicHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef076-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ef076-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ef076-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ef076-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef076-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="ef076-110">Attributes</span></span>  
  
|<span data-ttu-id="ef076-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="ef076-111">Attribute</span></span>|<span data-ttu-id="ef076-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef076-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="ef076-113">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="ef076-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="ef076-114">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="ef076-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ef076-115">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ef076-115">The default is 00:01:00.</span></span>|  
|`duplicateMessageHistoryLength`|<span data-ttu-id="ef076-116">Ein ganzzahliger Wert, der die doppelte Nachrichtenverlaufslänge angibt.</span><span class="sxs-lookup"><span data-stu-id="ef076-116">An integer value that specifies the duplicate message history length.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="ef076-117">Eine ganze Zahl, die die maximale Speicherkapazität der Nachrichtenpuffer angibt, die Nachrichten aus dem Kanal empfangen.</span><span class="sxs-lookup"><span data-stu-id="ef076-117">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="ef076-118">Der Standardwert ist 524288 (0x80000) Bytes.</span><span class="sxs-lookup"><span data-stu-id="ef076-118">The default value is 524288 (0x80000) bytes.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="ef076-119">Eine ganze Zahl, die die maximale Größe eines Puffers in Bytes angibt, in dem Nachrichten gespeichert werden, während sie für einen mit dieser Bindung konfigurierten Endpunkt verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="ef076-119">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="ef076-120">Der Standardwert ist 65.536 Bytes.</span><span class="sxs-lookup"><span data-stu-id="ef076-120">The default value is 65,536 bytes.</span></span>|  
|`maxPendingMessagesTotalSize`|<span data-ttu-id="ef076-121">Ein ganzzahliger Wert, der die maximale Anzahl von Nachrichten angibt, die empfangen, jedoch noch nicht aus der Eingangswarteschlange für eine einzelne Kanalinstanz entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="ef076-121">An integer value that specifies the maximum number of messages that are received but not yet removed from the input queue for an individual channel instance.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="ef076-122">Eine positive ganze Zahl, die die maximale Nachrichtengröße in Bytes einschließlich Header definiert, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="ef076-122">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="ef076-123">Der Absender erhält einen SOAP-Fehler, wenn die Nachricht zu groß für den Empfänger ist.</span><span class="sxs-lookup"><span data-stu-id="ef076-123">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="ef076-124">Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="ef076-124">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="ef076-125">Der Standardwert beträgt 65.536 Bytes.</span><span class="sxs-lookup"><span data-stu-id="ef076-125">The default is 65,536 bytes.</span></span>|  
|`maxRetransmitCount`|<span data-ttu-id="ef076-126">Ein ganzzahliger Wert, der die maximale Anzahl neu zu übermittelnder Nachrichten angibt.</span><span class="sxs-lookup"><span data-stu-id="ef076-126">An integer value that specifies the maximum number of retransmit messages.</span></span>|  
|`multicastInterfaceId`|<span data-ttu-id="ef076-127">Ein ganzzahliger Wert, der die ID der Multicastschnittstelle angibt.</span><span class="sxs-lookup"><span data-stu-id="ef076-127">An integer value that specifies the multicast interface ID.</span></span>|  
|`name`|<span data-ttu-id="ef076-128">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="ef076-128">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="ef076-129">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ef076-129">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="ef076-130">Jede Bindung hat ein `name`-Attribut und ein `namespace`-Attribut, die die Bindung in den Metadaten des Diensts eindeutig identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ef076-130">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="ef076-131">Außerdem kommt dieser Name bei den Bindungen eines Typs nur einmal vor.</span><span class="sxs-lookup"><span data-stu-id="ef076-131">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="ef076-132">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ef076-132">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="ef076-133">Weitere Informationen zur Standardkonfiguration und namenlos Bindungen und Verhaltensweisen finden Sie unter [vereinfachte Konfiguration](../../../../../docs/framework/wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="ef076-133">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="ef076-134">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="ef076-134">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="ef076-135">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="ef076-135">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ef076-136">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ef076-136">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="ef076-137">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="ef076-137">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="ef076-138">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="ef076-138">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ef076-139">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="ef076-139">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="ef076-140">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="ef076-140">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="ef076-141">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="ef076-141">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ef076-142">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ef076-142">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="ef076-143">Legt die Zeichensatzkodierung fest, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ef076-143">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="ef076-144">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="ef076-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ef076-145">-BigEndianUnicode: Unicode BigEndian-Codierung.</span><span class="sxs-lookup"><span data-stu-id="ef076-145">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="ef076-146">– Unicode: 16-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="ef076-146">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="ef076-147">-UTF8: 8-Bit-Codierung</span><span class="sxs-lookup"><span data-stu-id="ef076-147">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="ef076-148">Der Standard ist UTF8.</span><span class="sxs-lookup"><span data-stu-id="ef076-148">The default is UTF8.</span></span> <span data-ttu-id="ef076-149">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="ef076-149">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`timeToLive`|<span data-ttu-id="ef076-150">Ein Timespan-Wert, der die Gültigkeitsdauer für die Bindung angibt.</span><span class="sxs-lookup"><span data-stu-id="ef076-150">A timespan value that specifies the time to live for the binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ef076-151">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ef076-151">Child Elements</span></span>  
  
|<span data-ttu-id="ef076-152">Element</span><span class="sxs-lookup"><span data-stu-id="ef076-152">Element</span></span>|<span data-ttu-id="ef076-153">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef076-153">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef076-154">\<ReaderQuotas ></span><span class="sxs-lookup"><span data-stu-id="ef076-154">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="ef076-155">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="ef076-155">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="ef076-156">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="ef076-156">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ef076-157">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ef076-157">Parent Elements</span></span>  
  
|<span data-ttu-id="ef076-158">Element</span><span class="sxs-lookup"><span data-stu-id="ef076-158">Element</span></span>|<span data-ttu-id="ef076-159">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef076-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef076-160">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="ef076-160">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="ef076-161">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="ef076-161">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef076-162">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ef076-162">Remarks</span></span>  
 <span data-ttu-id="ef076-163">UdpBinding ermöglicht WCF-Diensten die Kommunikation über den UDP-Transport.</span><span class="sxs-lookup"><span data-stu-id="ef076-163">The UdpBinding allows WCF services to communicate over the UDP transport.</span></span> <span data-ttu-id="ef076-164">Sie können für den Nachrichtenaustausch "fire and forget", in denen ein Client sendet eine Nachricht an einen Dienst, und keine Rückantwort erwartet.</span><span class="sxs-lookup"><span data-stu-id="ef076-164">It allows for "fire and forget" message exchanges where a client sends a message to a service and expects no response back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef076-165">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ef076-165">Example</span></span>  
 <span data-ttu-id="ef076-166">Das folgende Beispiel zeigt, wie <xref:System.ServiceModel.UdpBinding> mithilfe des <`udpBinding`>-Elements konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="ef076-166">The following example shows how to configure the <xref:System.ServiceModel.UdpBinding> using the <`udpBinding`> element.</span></span>  
  
```xml  
<udpBinding>  
        <binding  closeTimeout="00:10:00"  
                   duplicateMessageHistoryLength="100"  
                   maxBufferPoolSize="100"  
                   maxPendingMessagesTotalSize="100000"  
                   maxReceivedMessageSize="65536"  
                    maxRetransmitCount="10"  
                   multicastInterfaceId="00000"  
                   name="myUdpBinding"  
                   openTimeout="00:10:00"  
                   receiveTimeout="00:10:00"  
                   sendTimeout="00:10:00"  
                   textEncoding="utf-8"  
                   timeToLive="00:10:00"  
          <readerQuotas/>   
        </binding>  
      </udpBinding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef076-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef076-167">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="ef076-168">Bindungen</span><span class="sxs-lookup"><span data-stu-id="ef076-168">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="ef076-169">Konfigurieren der vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="ef076-169">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="ef076-170">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="ef076-170">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="ef076-171">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="ef076-171">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
