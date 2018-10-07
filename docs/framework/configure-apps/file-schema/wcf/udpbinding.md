---
title: '&lt;udpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: fa291901-8340-45c6-9c44-5d9281c70bc3
ms.openlocfilehash: 62752ca74c7e5332c025a42d87608bb4c7f725ae
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2018
ms.locfileid: "48846200"
---
# <a name="ltudpbindinggt"></a><span data-ttu-id="478f1-102">&lt;udpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="478f1-102">&lt;udpBinding&gt;</span></span>
<span data-ttu-id="478f1-103">Ein Konfigurationselement, das zum Konfigurieren der <xref:System.ServiceModel.UdpBinding>-Bindung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="478f1-103">A configuration element used to configure the <xref:System.ServiceModel.UdpBinding> binding.</span></span>  
  
 <span data-ttu-id="478f1-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="478f1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="478f1-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="478f1-105">\<bindings></span></span>  
<span data-ttu-id="478f1-106">\<udpBinding></span><span class="sxs-lookup"><span data-stu-id="478f1-106">\<udpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="478f1-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="478f1-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="478f1-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="478f1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="478f1-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="478f1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="478f1-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="478f1-110">Attributes</span></span>  
  
|<span data-ttu-id="478f1-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="478f1-111">Attribute</span></span>|<span data-ttu-id="478f1-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="478f1-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="478f1-113">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="478f1-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="478f1-114">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="478f1-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="478f1-115">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="478f1-115">The default is 00:01:00.</span></span>|  
|`duplicateMessageHistoryLength`|<span data-ttu-id="478f1-116">Ein ganzzahliger Wert, der die doppelte Nachrichtenverlaufslänge angibt.</span><span class="sxs-lookup"><span data-stu-id="478f1-116">An integer value that specifies the duplicate message history length.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="478f1-117">Eine ganze Zahl, die die maximale Speicherkapazität der Nachrichtenpuffer angibt, die Nachrichten aus dem Kanal empfangen.</span><span class="sxs-lookup"><span data-stu-id="478f1-117">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="478f1-118">Der Standardwert ist 524288 (0x80000) Bytes.</span><span class="sxs-lookup"><span data-stu-id="478f1-118">The default value is 524288 (0x80000) bytes.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="478f1-119">Eine ganze Zahl, die die maximale Größe eines Puffers in Bytes angibt, in dem Nachrichten gespeichert werden, während sie für einen mit dieser Bindung konfigurierten Endpunkt verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="478f1-119">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="478f1-120">Der Standardwert ist 65.536 Bytes.</span><span class="sxs-lookup"><span data-stu-id="478f1-120">The default value is 65,536 bytes.</span></span>|  
|`maxPendingMessagesTotalSize`|<span data-ttu-id="478f1-121">Ein ganzzahliger Wert, der die maximale Anzahl von Nachrichten angibt, die empfangen, jedoch noch nicht aus der Eingangswarteschlange für eine einzelne Kanalinstanz entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="478f1-121">An integer value that specifies the maximum number of messages that are received but not yet removed from the input queue for an individual channel instance.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="478f1-122">Eine positive ganze Zahl, die die maximale Nachrichtengröße in Bytes einschließlich Header definiert, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="478f1-122">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="478f1-123">Der Absender erhält einen SOAP-Fehler, wenn die Nachricht zu groß für den Empfänger ist.</span><span class="sxs-lookup"><span data-stu-id="478f1-123">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="478f1-124">Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="478f1-124">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="478f1-125">Der Standardwert beträgt 65.536 Bytes.</span><span class="sxs-lookup"><span data-stu-id="478f1-125">The default is 65,536 bytes.</span></span>|  
|`maxRetransmitCount`|<span data-ttu-id="478f1-126">Ein ganzzahliger Wert, der die maximale Anzahl neu zu übermittelnder Nachrichten angibt.</span><span class="sxs-lookup"><span data-stu-id="478f1-126">An integer value that specifies the maximum number of retransmit messages.</span></span>|  
|`multicastInterfaceId`|<span data-ttu-id="478f1-127">Ein ganzzahliger Wert, der die ID der Multicastschnittstelle angibt.</span><span class="sxs-lookup"><span data-stu-id="478f1-127">An integer value that specifies the multicast interface ID.</span></span>|  
|`name`|<span data-ttu-id="478f1-128">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="478f1-128">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="478f1-129">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="478f1-129">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="478f1-130">Jede Bindung hat ein `name`-Attribut und ein `namespace`-Attribut, die die Bindung in den Metadaten des Diensts eindeutig identifizieren.</span><span class="sxs-lookup"><span data-stu-id="478f1-130">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="478f1-131">Außerdem kommt dieser Name bei den Bindungen eines Typs nur einmal vor.</span><span class="sxs-lookup"><span data-stu-id="478f1-131">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="478f1-132">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="478f1-132">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="478f1-133">Weitere Informationen zu Standardkonfiguration und zu namenlosen Bindungen und Verhaltensweisen finden Sie unter [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="478f1-133">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="478f1-134">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="478f1-134">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="478f1-135">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="478f1-135">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="478f1-136">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="478f1-136">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="478f1-137">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="478f1-137">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="478f1-138">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="478f1-138">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="478f1-139">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="478f1-139">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="478f1-140">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="478f1-140">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="478f1-141">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="478f1-141">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="478f1-142">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="478f1-142">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="478f1-143">Legt die Zeichensatzkodierung fest, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="478f1-143">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="478f1-144">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="478f1-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="478f1-145">-BigEndianUnicode: Unicode BigEndian-Codierung.</span><span class="sxs-lookup"><span data-stu-id="478f1-145">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="478f1-146">– Unicode: 16-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="478f1-146">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="478f1-147">– UTF8: 8-Bit-Codierung</span><span class="sxs-lookup"><span data-stu-id="478f1-147">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="478f1-148">Der Standard ist UTF8.</span><span class="sxs-lookup"><span data-stu-id="478f1-148">The default is UTF8.</span></span> <span data-ttu-id="478f1-149">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="478f1-149">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`timeToLive`|<span data-ttu-id="478f1-150">Ein Timespan-Wert, der die Gültigkeitsdauer für die Bindung angibt.</span><span class="sxs-lookup"><span data-stu-id="478f1-150">A timespan value that specifies the time to live for the binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="478f1-151">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="478f1-151">Child Elements</span></span>  
  
|<span data-ttu-id="478f1-152">Element</span><span class="sxs-lookup"><span data-stu-id="478f1-152">Element</span></span>|<span data-ttu-id="478f1-153">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="478f1-153">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="478f1-154">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="478f1-154">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="478f1-155">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="478f1-155">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="478f1-156">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="478f1-156">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="478f1-157">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="478f1-157">Parent Elements</span></span>  
  
|<span data-ttu-id="478f1-158">Element</span><span class="sxs-lookup"><span data-stu-id="478f1-158">Element</span></span>|<span data-ttu-id="478f1-159">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="478f1-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="478f1-160">\<bindings></span><span class="sxs-lookup"><span data-stu-id="478f1-160">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="478f1-161">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="478f1-161">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="478f1-162">Hinweise</span><span class="sxs-lookup"><span data-stu-id="478f1-162">Remarks</span></span>  
 <span data-ttu-id="478f1-163">UdpBinding ermöglicht WCF-Diensten die Kommunikation über den UDP-Transport.</span><span class="sxs-lookup"><span data-stu-id="478f1-163">The UdpBinding allows WCF services to communicate over the UDP transport.</span></span> <span data-ttu-id="478f1-164">Sie können für "fire and forget" Nachrichtenaustausch, in denen ein Client sendet eine Nachricht an einen Dienst, und keine Rückantwort erwartet.</span><span class="sxs-lookup"><span data-stu-id="478f1-164">It allows for "fire and forget" message exchanges where a client sends a message to a service and expects no response back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="478f1-165">Beispiel</span><span class="sxs-lookup"><span data-stu-id="478f1-165">Example</span></span>  
 <span data-ttu-id="478f1-166">Das folgende Beispiel zeigt, wie <xref:System.ServiceModel.UdpBinding> mithilfe des <`udpBinding`>-Elements konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="478f1-166">The following example shows how to configure the <xref:System.ServiceModel.UdpBinding> using the <`udpBinding`> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="478f1-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="478f1-167">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="478f1-168">Bindungen</span><span class="sxs-lookup"><span data-stu-id="478f1-168">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="478f1-169">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="478f1-169">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="478f1-170">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="478f1-170">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="478f1-171">\<binding></span><span class="sxs-lookup"><span data-stu-id="478f1-171">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
