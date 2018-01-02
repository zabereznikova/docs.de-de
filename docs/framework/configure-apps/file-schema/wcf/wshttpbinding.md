---
title: '&lt;wsHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: wsHttpBinding Element
ms.assetid: 0eee8ced-ad68-427d-b95a-97260e98deed
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f4b453392e21079fe1042f3f07bd895bbcdad888
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltwshttpbindinggt"></a><span data-ttu-id="07264-102">&lt;wsHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="07264-102">&lt;wsHttpBinding&gt;</span></span>
<span data-ttu-id="07264-103">Definiert eine sichere, zuverlässige und interoperable Bindung für Nicht-Duplexdienstverträge dar.</span><span class="sxs-lookup"><span data-stu-id="07264-103">Defines a secure, reliable, interoperable binding suitable for non-duplex service contracts.</span></span> <span data-ttu-id="07264-104">Die Bindung implementiert die folgenden Spezifikationen: WS-Reliable Messaging für Zuverlässigkeit und WS-Security für Nachrichtensicherheit und Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="07264-104">The binding implements the following specifications: WS-Reliable Messaging for reliability, and WS-Security for message security and authentication.</span></span> <span data-ttu-id="07264-105">Für den Transport wird HTTP verwendet und für die Nachrichtencodierung Text/XML-Codierung.</span><span class="sxs-lookup"><span data-stu-id="07264-105">The transport is HTTP, and message encoding is Text/XML encoding.</span></span>  
  
 <span data-ttu-id="07264-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="07264-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="07264-107">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="07264-107">\<bindings></span></span>  
<span data-ttu-id="07264-108">\<WsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="07264-108">\<wsHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07264-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="07264-109">Syntax</span></span>  
  
```xml  
<wsHttpBinding>  
    <binding   
        allowCookies="Boolean"  
        bypassProxyOnLocal="Boolean"  
        closeTimeout="TimeSpan"  
        hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"  
        maxBufferPoolSize="integer"  
        maxReceivedMessageSize="Integer"  
        messageEncoding="Text/Mtom"   
                name="string"  
        openTimeout="TimeSpan"   
        proxyAddress="URI"  
        receiveTimeout="TimeSpan"  
        sendTimeout="TimeSpan"  
                textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
        transactionFlow="Boolean"  
        useDefaultWebProxy="Boolean">  
        <reliableSession ordered="Boolean"  
           inactivityTimeout="TimeSpan"  
           enabled="Boolean" />  
        <security mode="Message/None/Transport/TransportWithCredential">  
           <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
                proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
                realm="string" />  
          <message   
             algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
                          clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
             establishSecurityContext="Boolean"  
             negotiateServiceCredential="Boolean" />  
        </security>  
       <readerQuotas             maxArrayLength="Integer"            maxBytesPerRead="Integer"            maxDepth="Integer"             maxNameTableCharCount="Integer"                     maxStringContentLength="Integer" />  
    </binding>  
</wsHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07264-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="07264-110">Attributes and Elements</span></span>  
 <span data-ttu-id="07264-111">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="07264-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07264-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="07264-112">Attributes</span></span>  
  
|<span data-ttu-id="07264-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="07264-113">Attribute</span></span>|<span data-ttu-id="07264-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07264-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="07264-115">allowCookies</span><span class="sxs-lookup"><span data-stu-id="07264-115">allowCookies</span></span>|<span data-ttu-id="07264-116">Ein boolescher Wert, der angibt, ob der Client Cookies akzeptiert und für zukünftige Anfragen propagiert.</span><span class="sxs-lookup"><span data-stu-id="07264-116">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="07264-117">Der Standardwert ist false.</span><span class="sxs-lookup"><span data-stu-id="07264-117">The default is false.</span></span><br /><br /> <span data-ttu-id="07264-118">Sie können diese Eigenschaft verwenden, wenn Sie mit ASMX-Webdiensten interagieren, die Cookies verwenden.</span><span class="sxs-lookup"><span data-stu-id="07264-118">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="07264-119">Auf diese Weise können Sie sicherstellen, dass die vom Server zurückgegebenen Cookies automatisch bei allen zukünftigen Clientanforderungen für diesen Dienst kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="07264-119">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|<span data-ttu-id="07264-120">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="07264-120">bypassProxyOnLocal</span></span>|<span data-ttu-id="07264-121">Ein boolescher Wert, der angibt, ob der Proxyserver bei lokalen Adressen umgangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="07264-121">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="07264-122">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="07264-122">The default is `false`.</span></span>|  
|<span data-ttu-id="07264-123">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="07264-123">closeTimeout</span></span>|<span data-ttu-id="07264-124">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="07264-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="07264-125">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="07264-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="07264-126">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="07264-126">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="07264-127">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="07264-127">hostnameComparisonMode</span></span>|<span data-ttu-id="07264-128">Gibt den HTTP-Hostnamen-Vergleichsmodus an, der verwendet wird, um URIs zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="07264-128">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="07264-129">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HostNameComparisonMode> und gibt an, ob beim Abgleich des URI der Hostname zum Erreichen des Dienstes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="07264-129">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="07264-130">Der Standardwert lautet <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, wodurch der Hostname beim Abgleich ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="07264-130">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="07264-131">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="07264-131">maxBufferPoolSize</span></span>|<span data-ttu-id="07264-132">Eine ganze Zahl, die die maximale Pufferpoolgröße für diese Bindung angibt.</span><span class="sxs-lookup"><span data-stu-id="07264-132">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="07264-133">Der Standardwert ist 524.288 Byte (512 * 1024).</span><span class="sxs-lookup"><span data-stu-id="07264-133">The default is 524,288 bytes (512 * 1024).</span></span> <span data-ttu-id="07264-134">Viele Teile von Windows Communication Foundation (WCF) verwenden Puffer.</span><span class="sxs-lookup"><span data-stu-id="07264-134">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="07264-135">Das Erstellen und Zerstören von Puffern bei jeder Verwendung ist kostspielig. Dasselbe gilt für die Garbage Collection für Puffer.</span><span class="sxs-lookup"><span data-stu-id="07264-135">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="07264-136">Bei Pufferpools können Sie einen zu verwendenden Puffer aus dem Pool nehmen und ihn nach der Verwendung wieder dem Pool zuführen.</span><span class="sxs-lookup"><span data-stu-id="07264-136">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="07264-137">So wird der Aufwand beim Erstellen und Zerstören von Puffern vermieden.</span><span class="sxs-lookup"><span data-stu-id="07264-137">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="07264-138">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="07264-138">maxReceivedMessageSize</span></span>|<span data-ttu-id="07264-139">Eine positive ganze Zahl, die die maximale Nachrichtengröße in Bytes einschließlich Header angibt, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="07264-139">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="07264-140">Der Absender einer Nachricht, die diese Grenze überschreitet, erhält einen SOAP-Fehler.</span><span class="sxs-lookup"><span data-stu-id="07264-140">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="07264-141">Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="07264-141">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="07264-142">Der Standard ist 65536.</span><span class="sxs-lookup"><span data-stu-id="07264-142">The default is 65536.</span></span>|  
|<span data-ttu-id="07264-143">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="07264-143">messageEncoding</span></span>|<span data-ttu-id="07264-144">Definiert den Encoder, der verwendet wird, um die SOAP-Nachricht zu codieren.</span><span class="sxs-lookup"><span data-stu-id="07264-144">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="07264-145">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="07264-145">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="07264-146">-Text: Verwenden Sie einen textnachrichtenencoder.</span><span class="sxs-lookup"><span data-stu-id="07264-146">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="07264-147">-Mtom: Verwendung eines Encoders Message Transmission Organisation Mechanism 1.0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="07264-147">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><span data-ttu-id="07264-148">– Der Standardwert ist Text.</span><span class="sxs-lookup"><span data-stu-id="07264-148">-   The default is Text.</span></span><br /><br /> <span data-ttu-id="07264-149">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="07264-149">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|<span data-ttu-id="07264-150">Name</span><span class="sxs-lookup"><span data-stu-id="07264-150">name</span></span>|<span data-ttu-id="07264-151">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="07264-151">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="07264-152">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="07264-152">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="07264-153">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="07264-153">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="07264-154">Weitere Informationen zur Standardkonfiguration und namenlos Bindungen und Verhaltensweisen finden Sie unter [vereinfachte Konfiguration](../../../../../docs/framework/wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="07264-154">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="07264-155">openTimeout</span><span class="sxs-lookup"><span data-stu-id="07264-155">openTimeout</span></span>|<span data-ttu-id="07264-156">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="07264-156">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="07264-157">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="07264-157">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="07264-158">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="07264-158">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="07264-159">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="07264-159">proxyAddress</span></span>|<span data-ttu-id="07264-160">Ein URI, der die Adresse des HTTP-Proxys angibt.</span><span class="sxs-lookup"><span data-stu-id="07264-160">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="07264-161">Wenn `useSystemWebProxy` `true` ist, muss diese Einstellung `null` lauten.</span><span class="sxs-lookup"><span data-stu-id="07264-161">If `useSystemWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="07264-162">Die Standardeinstellung ist `null`.</span><span class="sxs-lookup"><span data-stu-id="07264-162">The default is `null`.</span></span>|  
|<span data-ttu-id="07264-163">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="07264-163">receiveTimeout</span></span>|<span data-ttu-id="07264-164">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="07264-164">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="07264-165">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="07264-165">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="07264-166">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="07264-166">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="07264-167">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="07264-167">sendTimeout</span></span>|<span data-ttu-id="07264-168">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="07264-168">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="07264-169">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="07264-169">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="07264-170">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="07264-170">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="07264-171">textEncoding</span><span class="sxs-lookup"><span data-stu-id="07264-171">textEncoding</span></span>|<span data-ttu-id="07264-172">Gibt die Zeichensatzcodierung an, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="07264-172">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="07264-173">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="07264-173">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="07264-174">-UnicodeFffeTextEncoding: Unicode BigEndian-Codierung.</span><span class="sxs-lookup"><span data-stu-id="07264-174">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="07264-175">-Utf16TextEncoding: 16-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="07264-175">-   Utf16TextEncoding: 16-bit encoding.</span></span><br /><span data-ttu-id="07264-176">-Utf8TextEncoding: 8-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="07264-176">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="07264-177">Der Standardwert ist Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="07264-177">The default is Utf8TextEncoding.</span></span><br /><br /> <span data-ttu-id="07264-178">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="07264-178">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|<span data-ttu-id="07264-179">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="07264-179">transactionFlow</span></span>|<span data-ttu-id="07264-180">Ein boolescher Wert, der angibt, ob die Bindung geleitete WS-Transaktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="07264-180">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="07264-181">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="07264-181">The default is `false`.</span></span>|  
|<span data-ttu-id="07264-182">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="07264-182">useDefaultWebProxy</span></span>|<span data-ttu-id="07264-183">Ein boolescher Wert, der angibt, ob der automatisch konfigurierte HTTP-Proxy des Systems verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="07264-183">A Boolean value that specifies whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="07264-184">Die Standardeinstellung ist `true`.</span><span class="sxs-lookup"><span data-stu-id="07264-184">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="07264-185">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="07264-185">Child Elements</span></span>  
  
|<span data-ttu-id="07264-186">Element</span><span class="sxs-lookup"><span data-stu-id="07264-186">Element</span></span>|<span data-ttu-id="07264-187">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07264-187">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07264-188">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="07264-188">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|<span data-ttu-id="07264-189">Definiert die Sicherheitseinstellungen für die Bindung.</span><span class="sxs-lookup"><span data-stu-id="07264-189">Defines the security settings for the binding.</span></span> <span data-ttu-id="07264-190">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="07264-190">This element is of type <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span></span>|  
|[<span data-ttu-id="07264-191">\<ReaderQuotas ></span><span class="sxs-lookup"><span data-stu-id="07264-191">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="07264-192">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="07264-192">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="07264-193">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="07264-193">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="07264-194">reliableSession</span><span class="sxs-lookup"><span data-stu-id="07264-194">reliableSession</span></span>](http://msdn.microsoft.com/en-us/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)|<span data-ttu-id="07264-195">Gibt an, ob zuverlässige Sitzungen zwischen Kanalendpunkten aufgebaut werden.</span><span class="sxs-lookup"><span data-stu-id="07264-195">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="07264-196">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="07264-196">Parent Elements</span></span>  
  
|<span data-ttu-id="07264-197">Element</span><span class="sxs-lookup"><span data-stu-id="07264-197">Element</span></span>|<span data-ttu-id="07264-198">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07264-198">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07264-199">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="07264-199">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="07264-200">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="07264-200">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07264-201">Hinweise</span><span class="sxs-lookup"><span data-stu-id="07264-201">Remarks</span></span>  
 <span data-ttu-id="07264-202">Die `WSHttpBinding` ist der `BasicHttpBinding` ähnlich, stellt jedoch mehr Webdienstfunktionen bereit.</span><span class="sxs-lookup"><span data-stu-id="07264-202">The `WSHttpBinding` is similar to the `BasicHttpBinding` but provides more Web service features.</span></span> <span data-ttu-id="07264-203">Sie verwendet wie BasicHttpBinding den HTTP-Transport und stellt Nachrichtensicherheit bereit, bietet jedoch darüber hinaus Transaktionen, zuverlässiges Messaging und WS-Adressierung, entweder standardmäßig aktiviert oder über ein einziges Steuerelement verfügbar.</span><span class="sxs-lookup"><span data-stu-id="07264-203">It uses the HTTP transport and provides message security, as does BasicHttpBinding, but it also provides transactions, reliable messaging, and WS-Addressing, either enabled by default or available through a single control setting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07264-204">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07264-204">Example</span></span>  
  
```xml  
<configuration>  
    <system.ServiceModel>  
        <bindings>  
            <wsHttpBinding>  
                <binding   
                    closeTimeout="00:00:10"  
                    openTimeout="00:00:20"   
                    receiveTimeout="00:00:30"  
                    sendTimeout="00:00:40"  
                    bypassProxyOnLocal="false"  
                    transactionFlow="false"   
                    hostNameComparisonMode="WeakWildcard"  
                    maxReceivedMessageSize="1000"  
                    messageEncoding="Mtom"   
                    proxyAddress="http://foo/bar"  
                    textEncoding="utf-16"  
                    useDefaultWebProxy="false">  
                    <reliableSession ordered="false"  
                         inactivityTimeout="00:02:00"  
                         enabled="true" />  
                    <security mode="Transport">  
                         <transport clientCredentialType="Digest"  
                            proxyCredentialType="None"  
                            realm="someRealm" />  
                         <message clientCredentialType="Windows"  
                            negotiateServiceCredential="false"  
                            algorithmSuite="Aes128"   
                            defaultProtectionLevel="None" />  
                    </security>  
                </binding>  
           </wsHttpBinding>  
        </bindings>  
    </system.ServiceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="07264-205">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07264-205">See Also</span></span>  
 <xref:System.ServiceModel.WSHttpBinding>  
 <xref:System.ServiceModel.Configuration.WSHttpBindingElement>  
 [<span data-ttu-id="07264-206">Bindungen</span><span class="sxs-lookup"><span data-stu-id="07264-206">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="07264-207">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="07264-207">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="07264-208">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="07264-208">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="07264-209">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="07264-209">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
