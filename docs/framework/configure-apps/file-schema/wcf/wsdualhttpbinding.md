---
title: <wsDualHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsDualHttpBinding Element
ms.assetid: fd8ac4e2-5641-473b-9115-73f14ab1c065
ms.openlocfilehash: 3e32539900893297d2bac232138f9940a8ab100b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557644"
---
# \<wsDualHttpBinding>
<span data-ttu-id="c84f4-101">Definiert eine sichere und interoperable Bindung, die für Duplexdienstverträge oder für die Kommunikation über SOAP-Vermittler geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="c84f4-101">Defines a secure, reliable and interoperable binding that is suitable for duplex service contracts or communication through SOAP intermediaries.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsDualHttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="c84f4-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="c84f4-102">Syntax</span></span>  
  
```xml  
<wsDualHttpBinding>
  <binding name="String"
          closeTimeout="TimeSpan"
          openTimeout="TimeSpan"
          receiveTimeout="TimeSpan"
          sendTimeout="TimeSpan"
          bypassProxyOnLocal="Boolean"
          clientBaseAddress="URI"
          transactionFlow="Boolean"
          hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
          maxBufferPoolSize="integer"
          maxReceivedMessageSize="Integer"
          messageEncoding="Text/Mtom"
          proxyAddress="URI"
          textEncoding="Unicode/BigEndianUnicode/UTF8"
          useDefaultWebProxy="Boolean">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan" />
    <security mode="None/Message">
      <message clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</wsDualHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c84f4-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c84f4-103">Attributes and Elements</span></span>  
 <span data-ttu-id="c84f4-104">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c84f4-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c84f4-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="c84f4-105">Attributes</span></span>  
  
|<span data-ttu-id="c84f4-106">attribute</span><span class="sxs-lookup"><span data-stu-id="c84f4-106">Attribute</span></span>|<span data-ttu-id="c84f4-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c84f4-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c84f4-108">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="c84f4-108">bypassProxyOnLocal</span></span>|<span data-ttu-id="c84f4-109">Ein boolescher Wert, der angibt, ob der Proxyserver bei lokalen Adressen umgangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="c84f4-109">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="c84f4-110">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="c84f4-110">The default is `false`.</span></span>|  
|<span data-ttu-id="c84f4-111">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="c84f4-111">clientBaseAddress</span></span>|<span data-ttu-id="c84f4-112">Ein URI, der die Basisadresse festlegt, die vom Client auf Antwortnachrichten vom Dienst überwacht wird.</span><span class="sxs-lookup"><span data-stu-id="c84f4-112">A URI that sets the base address that the client listens to for response messages from the service.</span></span> <span data-ttu-id="c84f4-113">Wenn dies angegeben wurde, wird diese Adresse (einschließlich der kanalspezifischen GUIDs) zur Überwachung verwendet.</span><span class="sxs-lookup"><span data-stu-id="c84f4-113">If specified, this address (plus a per-channelGUID) is used for listening.</span></span> <span data-ttu-id="c84f4-114">Wenn kein Wert angegeben wurde, wird die Basisadresse des Clients je nach Transport generiert.</span><span class="sxs-lookup"><span data-stu-id="c84f4-114">If the value is not specified, the client base address is generated in a transport-specific manner.</span></span> <span data-ttu-id="c84f4-115">Der Standardwert ist `null`.</span><span class="sxs-lookup"><span data-stu-id="c84f4-115">The default is `null`.</span></span>|  
|<span data-ttu-id="c84f4-116">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="c84f4-116">closeTimeout</span></span>|<span data-ttu-id="c84f4-117">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="c84f4-117">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="c84f4-118">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="c84f4-118">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c84f4-119">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="c84f4-119">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="c84f4-120">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="c84f4-120">hostnameComparisonMode</span></span>|<span data-ttu-id="c84f4-121">Gibt den HTTP-Hostnamen-Vergleichsmodus an, der verwendet wird, um URIs zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="c84f4-121">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="c84f4-122">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HostNameComparisonMode> und gibt an, ob beim Abgleich des URI der Hostname zum Erreichen des Dienstes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c84f4-122">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="c84f4-123">Der Standardwert lautet <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, wodurch der Hostname beim Abgleich ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="c84f4-123">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="c84f4-124">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="c84f4-124">maxBufferPoolSize</span></span>|<span data-ttu-id="c84f4-125">Eine ganze Zahl, die die maximale Pufferpoolgröße für diese Bindung angibt.</span><span class="sxs-lookup"><span data-stu-id="c84f4-125">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="c84f4-126">Der Standardwert ist 524.288 Byte (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="c84f4-126">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="c84f4-127">Viele Teile von Windows Communication Foundation (WCF) verwenden Puffer.</span><span class="sxs-lookup"><span data-stu-id="c84f4-127">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="c84f4-128">Das Erstellen und Zerstören von Puffern bei jeder Verwendung ist kostspielig. Dasselbe gilt für die Garbage Collection für Puffer.</span><span class="sxs-lookup"><span data-stu-id="c84f4-128">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="c84f4-129">Bei Pufferpools können Sie einen zu verwendenden Puffer aus dem Pool nehmen und ihn nach der Verwendung wieder dem Pool zuführen.</span><span class="sxs-lookup"><span data-stu-id="c84f4-129">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="c84f4-130">So wird der Aufwand beim Erstellen und Zerstören von Puffern vermieden.</span><span class="sxs-lookup"><span data-stu-id="c84f4-130">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="c84f4-131">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="c84f4-131">maxReceivedMessageSize</span></span>|<span data-ttu-id="c84f4-132">Eine positive ganze Zahl, die die maximale Nachrichtengröße in Bytes einschließlich Header angibt, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="c84f4-132">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="c84f4-133">Der Absender einer Nachricht, die diese Grenze überschreitet, erhält einen SOAP-Fehler.</span><span class="sxs-lookup"><span data-stu-id="c84f4-133">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="c84f4-134">Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="c84f4-134">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="c84f4-135">Der Standard ist 65536.</span><span class="sxs-lookup"><span data-stu-id="c84f4-135">The default is 65536.</span></span>|  
|<span data-ttu-id="c84f4-136">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="c84f4-136">messageEncoding</span></span>|<span data-ttu-id="c84f4-137">Definiert den Encoder, der verwendet wird, um die SOAP-Nachricht zu codieren.</span><span class="sxs-lookup"><span data-stu-id="c84f4-137">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="c84f4-138">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="c84f4-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c84f4-139">-Text: Verwenden Sie einen Textnachrichten Encoder.</span><span class="sxs-lookup"><span data-stu-id="c84f4-139">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="c84f4-140">-MTOM: Verwenden Sie einen MTOM-Encoder (Message Transmission Organization Mechanism 1,0).</span><span class="sxs-lookup"><span data-stu-id="c84f4-140">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><span data-ttu-id="c84f4-141">-Der Standardwert ist Text.</span><span class="sxs-lookup"><span data-stu-id="c84f4-141">-   The default is Text.</span></span><br /><br /> <span data-ttu-id="c84f4-142">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="c84f4-142">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|<span data-ttu-id="c84f4-143">name</span><span class="sxs-lookup"><span data-stu-id="c84f4-143">name</span></span>|<span data-ttu-id="c84f4-144">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="c84f4-144">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="c84f4-145">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c84f4-145">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="c84f4-146">Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="c84f4-146">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="c84f4-147">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="c84f4-147">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="c84f4-148">openTimeout</span><span class="sxs-lookup"><span data-stu-id="c84f4-148">openTimeout</span></span>|<span data-ttu-id="c84f4-149">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="c84f4-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="c84f4-150">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="c84f4-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c84f4-151">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="c84f4-151">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="c84f4-152">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="c84f4-152">proxyAddress</span></span>|<span data-ttu-id="c84f4-153">Ein URI, der die Adresse des HTTP-Proxys angibt.</span><span class="sxs-lookup"><span data-stu-id="c84f4-153">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="c84f4-154">Wenn `useDefaultWebProxy``true` ist, muss diese Einstellung `null` lauten.</span><span class="sxs-lookup"><span data-stu-id="c84f4-154">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="c84f4-155">Der Standardwert ist `null`.</span><span class="sxs-lookup"><span data-stu-id="c84f4-155">The default is `null`.</span></span>|  
|<span data-ttu-id="c84f4-156">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="c84f4-156">receiveTimeout</span></span>|<span data-ttu-id="c84f4-157">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="c84f4-157">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="c84f4-158">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="c84f4-158">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c84f4-159">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="c84f4-159">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="c84f4-160">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="c84f4-160">sendTimeout</span></span>|<span data-ttu-id="c84f4-161">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="c84f4-161">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="c84f4-162">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="c84f4-162">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c84f4-163">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="c84f4-163">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="c84f4-164">textEncoding</span><span class="sxs-lookup"><span data-stu-id="c84f4-164">textEncoding</span></span>|<span data-ttu-id="c84f4-165">Legt die Zeichensatzkodierung fest, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c84f4-165">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="c84f4-166">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="c84f4-166">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c84f4-167">-BigEndianUnicode: Unicode bigEndian-Codierung.</span><span class="sxs-lookup"><span data-stu-id="c84f4-167">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="c84f4-168">-Unicode: 16-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="c84f4-168">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="c84f4-169">-UTF8:8-Bit-Codierung</span><span class="sxs-lookup"><span data-stu-id="c84f4-169">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="c84f4-170">Der Standardwert ist UTF8.</span><span class="sxs-lookup"><span data-stu-id="c84f4-170">The default is UTF8.</span></span> <span data-ttu-id="c84f4-171">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="c84f4-171">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|<span data-ttu-id="c84f4-172">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="c84f4-172">transactionFlow</span></span>|<span data-ttu-id="c84f4-173">Ein boolescher Wert, der angibt, ob die Bindung geleitete WS-Transaktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c84f4-173">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="c84f4-174">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="c84f4-174">The default is `false`.</span></span>|  
|<span data-ttu-id="c84f4-175">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="c84f4-175">useDefaultWebProxy</span></span>|<span data-ttu-id="c84f4-176">Ein boolescher Wert, der angibt, ob der automatisch konfigurierte HTTP-Proxy des Systems verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c84f4-176">A Boolean value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="c84f4-177">Die Proxyadresse muss `null` sein (das heißt, sie ist nicht festgelegt), wenn dieses Attribut den Wert `true` hat.</span><span class="sxs-lookup"><span data-stu-id="c84f4-177">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="c84f4-178">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="c84f4-178">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c84f4-179">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c84f4-179">Child Elements</span></span>  
  
|<span data-ttu-id="c84f4-180">Element</span><span class="sxs-lookup"><span data-stu-id="c84f4-180">Element</span></span>|<span data-ttu-id="c84f4-181">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c84f4-181">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-wsdualhttpbinding.md)|<span data-ttu-id="c84f4-182">Definiert die Sicherheitseinstellungen für die Bindung.</span><span class="sxs-lookup"><span data-stu-id="c84f4-182">Defines the security settings for the binding.</span></span> <span data-ttu-id="c84f4-183">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WSDualHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="c84f4-183">This element is of type <xref:System.ServiceModel.Configuration.WSDualHttpSecurityElement>.</span></span>|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="c84f4-184">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="c84f4-184">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="c84f4-185">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="c84f4-185">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<reliableSession>](/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="c84f4-186">Gibt an, ob zuverlässige Sitzungen zwischen Kanalendpunkten aufgebaut werden.</span><span class="sxs-lookup"><span data-stu-id="c84f4-186">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c84f4-187">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c84f4-187">Parent Elements</span></span>  
  
|<span data-ttu-id="c84f4-188">Element</span><span class="sxs-lookup"><span data-stu-id="c84f4-188">Element</span></span>|<span data-ttu-id="c84f4-189">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c84f4-189">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="c84f4-190">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="c84f4-190">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c84f4-191">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c84f4-191">Remarks</span></span>  
 <span data-ttu-id="c84f4-192">Die `WSDualHttpBinding` bietet die gleiche Unterstützung für Webdienstprotokolle wie die `WSHttpBinding`, jedoch für die Verwendung mit Duplexverträgen.</span><span class="sxs-lookup"><span data-stu-id="c84f4-192">The `WSDualHttpBinding` provides the same support for Web Service protocols as the `WSHttpBinding`, but for use with duplex contracts.</span></span> <span data-ttu-id="c84f4-193">`WSDualHttpBinding` unterstützt ausschließlich SOAP-Sicherheit und erfordert zuverlässiges Messaging.</span><span class="sxs-lookup"><span data-stu-id="c84f4-193">`WSDualHttpBinding` only supports SOAP security and requires reliable messaging.</span></span> <span data-ttu-id="c84f4-194">Diese Bindung macht es erforderlich, dass der Client einen öffentlichen URI aufweist, der einen Rückrufendpunkt für den Dienst bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="c84f4-194">This binding requires that the client has a public URI that provides a callback endpoint for the service.</span></span> <span data-ttu-id="c84f4-195">Dies wird vom `clientBaseAddress`-Attribut zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="c84f4-195">This is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="c84f4-196">Eine Dualbindung macht die IP-Adresse des Clients für den Dienst verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c84f4-196">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="c84f4-197">Der Client sollte Sicherheitseinstellungen verwenden, um sicherzustellen, dass nur Verbindungen zu vertrauenswürdigen Diensten hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c84f4-197">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
 <span data-ttu-id="c84f4-198">Diese Bindung kann zur zuverlässigen Kommunikation über einen oder mehrere SOAP-Vermittler verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c84f4-198">This binding can be used to communicate reliably through one or more SOAP intermediaries.</span></span>  
  
 <span data-ttu-id="c84f4-199">Diese Bindung generiert standardmäßig einen Laufzeitstapel mit WS-ReliableMessaging für die Zuverlässigkeit, WS-Security für die Nachrichtensicherheit und –authentifizierung, HTTP für die Nachrichtenübertragung und Kodierung von Text-/XML-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="c84f4-199">By default, this binding generates a runtime stack with WS-ReliableMessaging for reliability, WS-Security for message security and authentication, HTTP for message delivery, and a Text/XML message encoding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c84f4-200">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c84f4-200">Example</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <wsDualHttpBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 bypassProxyOnLocal="false"
                 clientBaseAddress="http://localhost:8001/client/"
                 transactionFlow="true"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://foo/bar"
                 textEncoding="utf-16"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00" />
          <security mode="None">
            <message clientCredentialType="None"
                     negotiateServiceCredential="false"
                     algorithmSuite="Aes128" />
          </security>
        </binding>
      </wsDualHttpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="c84f4-201">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c84f4-201">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpBinding>
- <xref:System.ServiceModel.Configuration.WSDualHttpBindingElement>
- [<span data-ttu-id="c84f4-202">Bindungen</span><span class="sxs-lookup"><span data-stu-id="c84f4-202">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c84f4-203">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="c84f4-203">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="c84f4-204">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="c84f4-204">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
