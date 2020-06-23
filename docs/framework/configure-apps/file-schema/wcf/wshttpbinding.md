---
title: <wsHttpBinding>
description: Definiert eine sichere, zuverlässige und interoperable HTTP-Bindung, die für nicht-Duplex Dienstverträge geeignet ist, die WS-zuverlässiges Messaging und WS-Security implementiert.
ms.date: 03/30/2017
helpviewer_keywords:
- wsHttpBinding Element
ms.assetid: 0eee8ced-ad68-427d-b95a-97260e98deed
ms.openlocfilehash: d603f699145622cb1b70ecf99ea542572e841eac
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85243983"
---
# \<wsHttpBinding>
<span data-ttu-id="a2631-102">Definiert eine sichere, zuverlässige und interoperable Bindung für Nicht-Duplexdienstverträge dar.</span><span class="sxs-lookup"><span data-stu-id="a2631-102">Defines a secure, reliable, interoperable binding suitable for non-duplex service contracts.</span></span> <span data-ttu-id="a2631-103">Die Bindung implementiert die folgenden Spezifikationen: WS-Reliable Messaging für Zuverlässigkeit und WS-Security für Nachrichtensicherheit und Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="a2631-103">The binding implements the following specifications: WS-Reliable Messaging for reliability, and WS-Security for message security and authentication.</span></span> <span data-ttu-id="a2631-104">Für den Transport wird HTTP verwendet und für die Nachrichtencodierung Text/XML-Codierung.</span><span class="sxs-lookup"><span data-stu-id="a2631-104">The transport is HTTP, and message encoding is Text/XML encoding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsHttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="a2631-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a2631-105">Syntax</span></span>  
  
```xml  
<wsHttpBinding>
  <binding allowCookies="Boolean"
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
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
               establishSecurityContext="Boolean"
               negotiateServiceCredential="Boolean" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</wsHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2631-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a2631-106">Attributes and Elements</span></span>  
 <span data-ttu-id="a2631-107">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a2631-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2631-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="a2631-108">Attributes</span></span>  
  
|<span data-ttu-id="a2631-109">attribute</span><span class="sxs-lookup"><span data-stu-id="a2631-109">Attribute</span></span>|<span data-ttu-id="a2631-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a2631-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a2631-111">allowCookies</span><span class="sxs-lookup"><span data-stu-id="a2631-111">allowCookies</span></span>|<span data-ttu-id="a2631-112">Ein boolescher Wert, der angibt, ob der Client Cookies akzeptiert und für zukünftige Anfragen propagiert.</span><span class="sxs-lookup"><span data-stu-id="a2631-112">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="a2631-113">Die Standardeinstellung ist „false“.</span><span class="sxs-lookup"><span data-stu-id="a2631-113">The default is false.</span></span><br /><br /> <span data-ttu-id="a2631-114">Sie können diese Eigenschaft verwenden, wenn Sie mit ASMX-Webdiensten interagieren, die Cookies verwenden.</span><span class="sxs-lookup"><span data-stu-id="a2631-114">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="a2631-115">Auf diese Weise können Sie sicherstellen, dass die vom Server zurückgegebenen Cookies automatisch bei allen zukünftigen Clientanforderungen für diesen Dienst kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="a2631-115">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|<span data-ttu-id="a2631-116">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="a2631-116">bypassProxyOnLocal</span></span>|<span data-ttu-id="a2631-117">Ein boolescher Wert, der angibt, ob der Proxyserver bei lokalen Adressen umgangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="a2631-117">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="a2631-118">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="a2631-118">The default is `false`.</span></span>|  
|<span data-ttu-id="a2631-119">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="a2631-119">closeTimeout</span></span>|<span data-ttu-id="a2631-120">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="a2631-120">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="a2631-121">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="a2631-121">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a2631-122">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a2631-122">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="a2631-123">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="a2631-123">hostnameComparisonMode</span></span>|<span data-ttu-id="a2631-124">Gibt den HTTP-Hostnamen-Vergleichsmodus an, der verwendet wird, um URIs zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="a2631-124">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="a2631-125">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HostNameComparisonMode> und gibt an, ob beim Abgleich des URI der Hostname zum Erreichen des Dienstes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a2631-125">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="a2631-126">Der Standardwert lautet <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, wodurch der Hostname beim Abgleich ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="a2631-126">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="a2631-127">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="a2631-127">maxBufferPoolSize</span></span>|<span data-ttu-id="a2631-128">Eine ganze Zahl, die die maximale Pufferpoolgröße für diese Bindung angibt.</span><span class="sxs-lookup"><span data-stu-id="a2631-128">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="a2631-129">Der Standardwert ist 524.288 Byte (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="a2631-129">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="a2631-130">Viele Teile von Windows Communication Foundation (WCF) verwenden Puffer.</span><span class="sxs-lookup"><span data-stu-id="a2631-130">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="a2631-131">Das Erstellen und Zerstören von Puffern bei jeder Verwendung ist kostspielig. Dasselbe gilt für die Garbage Collection für Puffer.</span><span class="sxs-lookup"><span data-stu-id="a2631-131">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="a2631-132">Bei Pufferpools können Sie einen zu verwendenden Puffer aus dem Pool nehmen und ihn nach der Verwendung wieder dem Pool zuführen.</span><span class="sxs-lookup"><span data-stu-id="a2631-132">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="a2631-133">So wird der Aufwand beim Erstellen und Zerstören von Puffern vermieden.</span><span class="sxs-lookup"><span data-stu-id="a2631-133">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="a2631-134">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="a2631-134">maxReceivedMessageSize</span></span>|<span data-ttu-id="a2631-135">Eine positive ganze Zahl, die die maximale Nachrichtengröße in Bytes einschließlich Header angibt, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="a2631-135">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="a2631-136">Der Absender einer Nachricht, die diese Grenze überschreitet, erhält einen SOAP-Fehler.</span><span class="sxs-lookup"><span data-stu-id="a2631-136">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="a2631-137">Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="a2631-137">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="a2631-138">Der Standard ist 65536.</span><span class="sxs-lookup"><span data-stu-id="a2631-138">The default is 65536.</span></span>|  
|<span data-ttu-id="a2631-139">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="a2631-139">messageEncoding</span></span>|<span data-ttu-id="a2631-140">Definiert den Encoder, der verwendet wird, um die SOAP-Nachricht zu codieren.</span><span class="sxs-lookup"><span data-stu-id="a2631-140">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="a2631-141">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="a2631-141">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a2631-142">-Text: Verwenden Sie einen Textnachrichten Encoder.</span><span class="sxs-lookup"><span data-stu-id="a2631-142">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="a2631-143">-MTOM: Verwenden Sie einen MTOM-Encoder (Message Transmission Organization Mechanism 1,0).</span><span class="sxs-lookup"><span data-stu-id="a2631-143">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><span data-ttu-id="a2631-144">-Der Standardwert ist Text.</span><span class="sxs-lookup"><span data-stu-id="a2631-144">-   The default is Text.</span></span><br /><br /> <span data-ttu-id="a2631-145">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="a2631-145">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|<span data-ttu-id="a2631-146">Name</span><span class="sxs-lookup"><span data-stu-id="a2631-146">name</span></span>|<span data-ttu-id="a2631-147">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="a2631-147">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="a2631-148">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a2631-148">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="a2631-149">Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="a2631-149">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="a2631-150">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="a2631-150">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="a2631-151">openTimeout</span><span class="sxs-lookup"><span data-stu-id="a2631-151">openTimeout</span></span>|<span data-ttu-id="a2631-152">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="a2631-152">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="a2631-153">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="a2631-153">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a2631-154">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a2631-154">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="a2631-155">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="a2631-155">proxyAddress</span></span>|<span data-ttu-id="a2631-156">Ein URI, der die Adresse des HTTP-Proxys angibt.</span><span class="sxs-lookup"><span data-stu-id="a2631-156">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="a2631-157">Wenn `useSystemWebProxy``true` ist, muss diese Einstellung `null` lauten.</span><span class="sxs-lookup"><span data-stu-id="a2631-157">If `useSystemWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="a2631-158">Der Standardwert ist `null`.</span><span class="sxs-lookup"><span data-stu-id="a2631-158">The default is `null`.</span></span>|  
|<span data-ttu-id="a2631-159">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="a2631-159">receiveTimeout</span></span>|<span data-ttu-id="a2631-160">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="a2631-160">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="a2631-161">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="a2631-161">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a2631-162">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a2631-162">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="a2631-163">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="a2631-163">sendTimeout</span></span>|<span data-ttu-id="a2631-164">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="a2631-164">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="a2631-165">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="a2631-165">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a2631-166">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a2631-166">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="a2631-167">textEncoding</span><span class="sxs-lookup"><span data-stu-id="a2631-167">textEncoding</span></span>|<span data-ttu-id="a2631-168">Gibt die Zeichensatzcodierung an, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a2631-168">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="a2631-169">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="a2631-169">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a2631-170">-UnicodeFffeTextEncoding: Unicode bigEndian-Codierung.</span><span class="sxs-lookup"><span data-stu-id="a2631-170">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="a2631-171">-Utf16TextEncoding: 16-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="a2631-171">-   Utf16TextEncoding: 16-bit encoding.</span></span><br /><span data-ttu-id="a2631-172">-Utf8TextEncoding: 8-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="a2631-172">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="a2631-173">Der Standardwert ist Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="a2631-173">The default is Utf8TextEncoding.</span></span><br /><br /> <span data-ttu-id="a2631-174">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="a2631-174">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|<span data-ttu-id="a2631-175">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="a2631-175">transactionFlow</span></span>|<span data-ttu-id="a2631-176">Ein boolescher Wert, der angibt, ob die Bindung geleitete WS-Transaktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a2631-176">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="a2631-177">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="a2631-177">The default is `false`.</span></span>|  
|<span data-ttu-id="a2631-178">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="a2631-178">useDefaultWebProxy</span></span>|<span data-ttu-id="a2631-179">Ein boolescher Wert, der angibt, ob der automatisch konfigurierte HTTP-Proxy des Systems verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a2631-179">A Boolean value that specifies whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="a2631-180">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="a2631-180">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a2631-181">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a2631-181">Child Elements</span></span>  
  
|<span data-ttu-id="a2631-182">Element</span><span class="sxs-lookup"><span data-stu-id="a2631-182">Element</span></span>|<span data-ttu-id="a2631-183">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2631-183">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-wshttpbinding.md)|<span data-ttu-id="a2631-184">Definiert die Sicherheitseinstellungen für die Bindung.</span><span class="sxs-lookup"><span data-stu-id="a2631-184">Defines the security settings for the binding.</span></span> <span data-ttu-id="a2631-185">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="a2631-185">This element is of type <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span></span>|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="a2631-186">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="a2631-186">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="a2631-187">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="a2631-187">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="a2631-188">Gibt an, ob zuverlässige Sitzungen zwischen Kanalendpunkten aufgebaut werden.</span><span class="sxs-lookup"><span data-stu-id="a2631-188">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a2631-189">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a2631-189">Parent Elements</span></span>  
  
|<span data-ttu-id="a2631-190">Element</span><span class="sxs-lookup"><span data-stu-id="a2631-190">Element</span></span>|<span data-ttu-id="a2631-191">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2631-191">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="a2631-192">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="a2631-192">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2631-193">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a2631-193">Remarks</span></span>  
 <span data-ttu-id="a2631-194">Die `WSHttpBinding` ist der `BasicHttpBinding` ähnlich, stellt jedoch mehr Webdienstfunktionen bereit.</span><span class="sxs-lookup"><span data-stu-id="a2631-194">The `WSHttpBinding` is similar to the `BasicHttpBinding` but provides more Web service features.</span></span> <span data-ttu-id="a2631-195">Sie verwendet wie BasicHttpBinding den HTTP-Transport und stellt Nachrichtensicherheit bereit, bietet jedoch darüber hinaus Transaktionen, zuverlässiges Messaging und WS-Adressierung, entweder standardmäßig aktiviert oder über ein einziges Steuerelement verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a2631-195">It uses the HTTP transport and provides message security, as does BasicHttpBinding, but it also provides transactions, reliable messaging, and WS-Addressing, either enabled by default or available through a single control setting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2631-196">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a2631-196">Example</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <wsHttpBinding>
        <binding closeTimeout="00:00:10"
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
  
## <a name="see-also"></a><span data-ttu-id="a2631-197">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a2631-197">See also</span></span>

- <xref:System.ServiceModel.WSHttpBinding>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement>
- [<span data-ttu-id="a2631-198">Bindungen</span><span class="sxs-lookup"><span data-stu-id="a2631-198">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a2631-199">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="a2631-199">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a2631-200">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="a2631-200">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
