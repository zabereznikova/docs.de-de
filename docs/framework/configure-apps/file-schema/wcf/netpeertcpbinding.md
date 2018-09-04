---
title: '&lt;netPeerTcpBinding&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- netPeerBinding element
ms.assetid: 2dd77ada-a176-47c7-a740-900b279f1aad
ms.openlocfilehash: 9032372f8e3344e9b1021be19a32230986b328a2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43513279"
---
# <a name="ltnetpeertcpbindinggt"></a><span data-ttu-id="36cad-102">&lt;netPeerTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="36cad-102">&lt;netPeerTcpBinding&gt;</span></span>
<span data-ttu-id="36cad-103">Definiert eine Bindung für Peerkanal-spezifisches TCP-Messaging.</span><span class="sxs-lookup"><span data-stu-id="36cad-103">Defines a binding for peer channel specific TCP messaging.</span></span>  
  
 <span data-ttu-id="36cad-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="36cad-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="36cad-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="36cad-105">\<bindings></span></span>  
<span data-ttu-id="36cad-106">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="36cad-106">\<netPeerTcpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36cad-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="36cad-107">Syntax</span></span>  
  
```xml  
<netPeerBinding>  
    <binding name="string"  
         closeTimeout="TimeSpan"  
         openTimeout="TimeSpan"   
         receiveTimeout="TimeSpan"  
         sendTimeout="TimeSpan"  
         listenIPAddress="String"  
          maxBufferPoolSize="integer"  
         maxReceiveMessageSize="Integer"   
         port="Integer"  
         <security mode="None/Transport/Message/TransportWithMessageCredential">  
            <transport credentialType="Certificate/Password" />  
        </security>  
    </binding>  
</netPeerBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36cad-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="36cad-108">Attributes and Elements</span></span>  
 <span data-ttu-id="36cad-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="36cad-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36cad-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="36cad-110">Attributes</span></span>  
  
|<span data-ttu-id="36cad-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="36cad-111">Attribute</span></span>|<span data-ttu-id="36cad-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="36cad-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="36cad-113">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="36cad-113">closeTimeout</span></span>|<span data-ttu-id="36cad-114">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="36cad-114">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="36cad-115">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="36cad-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="36cad-116">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="36cad-116">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="36cad-117">listenIPAddress</span><span class="sxs-lookup"><span data-stu-id="36cad-117">listenIPAddress</span></span>|<span data-ttu-id="36cad-118">Eine Zeichenfolge mit einer IP-Adresse, die der Peerknoten auf TCP-Nachrichten überwacht.</span><span class="sxs-lookup"><span data-stu-id="36cad-118">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="36cad-119">Die Standardeinstellung ist `null`.</span><span class="sxs-lookup"><span data-stu-id="36cad-119">The default is `null`.</span></span>|  
|<span data-ttu-id="36cad-120">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="36cad-120">maxBufferPoolSize</span></span>|<span data-ttu-id="36cad-121">Eine ganze Zahl, die die maximale Pufferpoolgröße für diese Bindung angibt.</span><span class="sxs-lookup"><span data-stu-id="36cad-121">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="36cad-122">Der Standardwert ist 524.288 Byte (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="36cad-122">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="36cad-123">Viele Teile von Windows Communication Foundation (WCF) verwenden Puffer.</span><span class="sxs-lookup"><span data-stu-id="36cad-123">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="36cad-124">Das Erstellen und Zerstören von Puffern bei jeder Verwendung ist kostspielig. Dasselbe gilt für die Garbage Collection für Puffer.</span><span class="sxs-lookup"><span data-stu-id="36cad-124">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="36cad-125">Bei Pufferpools können Sie einen zu verwendenden Puffer aus dem Pool nehmen und ihn nach der Verwendung wieder dem Pool zuführen.</span><span class="sxs-lookup"><span data-stu-id="36cad-125">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="36cad-126">So wird der Aufwand beim Erstellen und Zerstören von Puffern vermieden.</span><span class="sxs-lookup"><span data-stu-id="36cad-126">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="36cad-127">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="36cad-127">maxReceivedMessageSize</span></span>|<span data-ttu-id="36cad-128">Eine positive ganze Zahl, die die maximale Nachrichtengröße in Bytes einschließlich Header angibt, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="36cad-128">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="36cad-129">Der Absender einer Nachricht, die diese Grenze überschreitet, erhält einen SOAP-Fehler.</span><span class="sxs-lookup"><span data-stu-id="36cad-129">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="36cad-130">Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="36cad-130">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="36cad-131">Der Standard ist 65536.</span><span class="sxs-lookup"><span data-stu-id="36cad-131">The default is 65536.</span></span>|  
|<span data-ttu-id="36cad-132">Name</span><span class="sxs-lookup"><span data-stu-id="36cad-132">name</span></span>|<span data-ttu-id="36cad-133">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="36cad-133">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="36cad-134">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="36cad-134">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="36cad-135">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="36cad-135">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="36cad-136">Weitere Informationen zu Standardkonfiguration und zu namenlosen Bindungen und Verhaltensweisen finden Sie unter [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="36cad-136">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="36cad-137">openTimeout</span><span class="sxs-lookup"><span data-stu-id="36cad-137">openTimeout</span></span>|<span data-ttu-id="36cad-138">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="36cad-138">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="36cad-139">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="36cad-139">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="36cad-140">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="36cad-140">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="36cad-141">Port</span><span class="sxs-lookup"><span data-stu-id="36cad-141">port</span></span>|<span data-ttu-id="36cad-142">Eine ganze Zahl, die den Netzwerk-Schnittstellenanschluss angibt, an dem diese Bindung TCP-Peerkanalnachrichten verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="36cad-142">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="36cad-143">Dabei muss es sich um einen Wert zwischen <xref:System.Net.IPEndPoint.MinPort> und <xref:System.Net.IPEndPoint.MaxPort> handeln.</span><span class="sxs-lookup"><span data-stu-id="36cad-143">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="36cad-144">Der Standard ist 0.</span><span class="sxs-lookup"><span data-stu-id="36cad-144">The default is 0.</span></span>|  
|<span data-ttu-id="36cad-145">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="36cad-145">receiveTimeout</span></span>|<span data-ttu-id="36cad-146">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="36cad-146">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="36cad-147">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="36cad-147">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="36cad-148">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="36cad-148">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="36cad-149">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="36cad-149">sendTimeout</span></span>|<span data-ttu-id="36cad-150">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="36cad-150">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="36cad-151">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="36cad-151">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="36cad-152">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="36cad-152">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36cad-153">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="36cad-153">Child Elements</span></span>  
  
|<span data-ttu-id="36cad-154">Element</span><span class="sxs-lookup"><span data-stu-id="36cad-154">Element</span></span>|<span data-ttu-id="36cad-155">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="36cad-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36cad-156">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="36cad-156">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="36cad-157">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="36cad-157">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="36cad-158">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="36cad-158">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="36cad-159">\<resolver></span><span class="sxs-lookup"><span data-stu-id="36cad-159">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="36cad-160">Gibt einen Peerresolver an, der von dieser Bindung zum Auflösen einer Peermesh-ID in die Endpunkt-IP-Adressen von Knoten innerhalb des Peermesh verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="36cad-160">Specifies a peer resolver used by this binding to resolve a peer mesh ID to the endpoint IP addresses of nodes within the peer mesh.</span></span>|  
|[<span data-ttu-id="36cad-161">\<security></span><span class="sxs-lookup"><span data-stu-id="36cad-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="36cad-162">Definiert die Sicherheitseinstellungen für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="36cad-162">Defines the security settings for the message.</span></span> <span data-ttu-id="36cad-163">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="36cad-163">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="36cad-164">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="36cad-164">Parent Elements</span></span>  
  
|<span data-ttu-id="36cad-165">Element</span><span class="sxs-lookup"><span data-stu-id="36cad-165">Element</span></span>|<span data-ttu-id="36cad-166">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="36cad-166">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36cad-167">\<bindings></span><span class="sxs-lookup"><span data-stu-id="36cad-167">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="36cad-168">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="36cad-168">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36cad-169">Hinweise</span><span class="sxs-lookup"><span data-stu-id="36cad-169">Remarks</span></span>  
 <span data-ttu-id="36cad-170">Diese Bindung bietet Unterstützung für das Erstellen von Peer-to-Peer- oder Mehrparteienanwendungen mithilfe von Peertransport über TCP.</span><span class="sxs-lookup"><span data-stu-id="36cad-170">This binding provides support for the creation of peer-to-peer or multiparty applications using peer transport over TCP.</span></span> <span data-ttu-id="36cad-171">Jeder Peerknoten kann als Host für mehrere mit diesem Bindungstyp definierte Peerkanäle fungieren.</span><span class="sxs-lookup"><span data-stu-id="36cad-171">Each peer node can host multiple peer channels defined with this binding type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36cad-172">Beispiel</span><span class="sxs-lookup"><span data-stu-id="36cad-172">Example</span></span>  
 <span data-ttu-id="36cad-173">Im folgenden Beispiel wird die NetPeerTcpBinding-Bindung veranschaulicht, die Mehrparteienkommunikation über einen Peerkanal ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="36cad-173">The following example demonstrates using the NetPeerTcpBinding binding, which provides multiparty communication using a peer channel.</span></span> <span data-ttu-id="36cad-174">Ein Szenario mit dieser Bindung, finden Sie unter [Net-Peer-TCP](https://msdn.microsoft.com/library/31f4db66-edb2-40a6-b92a-14098e92acae).</span><span class="sxs-lookup"><span data-stu-id="36cad-174">For a detailed scenario of using this binding, see [Net Peer TCP](https://msdn.microsoft.com/library/31f4db66-edb2-40a6-b92a-14098e92acae).</span></span>  
  
```xml  
<configuration>  
<system.ServiceModel>  
<bindings>  
<netPeerBinding>  
    <binding   
         closeTimeout="00:00:10"  
         openTimeout="00:00:20"   
         receiveTimeout="00:00:30"  
         sendTimeout="00:00:40"  
         maxBufferSize="1001"  
         maxConnections="123"   
         maxReceiveMessageSize="1000">  
        <reliableSession ordered="false"  
            inactivityTimeout="00:02:00"  
            enabled="true" />  
        <security mode="TransportWithMessageCredential">  
            <message clientCredentialType="CardSpace" />  
        </security>  
    </binding>  
</netPeerBinding>  
</bindings>  
</system.ServiceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="36cad-175">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36cad-175">See Also</span></span>  
 <xref:System.ServiceModel.NetPeerTcpBinding>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement>  
 [<span data-ttu-id="36cad-176">Bindungen</span><span class="sxs-lookup"><span data-stu-id="36cad-176">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="36cad-177">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="36cad-177">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="36cad-178">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="36cad-178">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="36cad-179">\<binding></span><span class="sxs-lookup"><span data-stu-id="36cad-179">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="36cad-180">NET-Peer-TCP</span><span class="sxs-lookup"><span data-stu-id="36cad-180">Net Peer TCP</span></span>](https://msdn.microsoft.com/library/31f4db66-edb2-40a6-b92a-14098e92acae)  
 [<span data-ttu-id="36cad-181">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="36cad-181">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
