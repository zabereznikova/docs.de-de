---
title: <netTcpBinding>
description: Stellt eine sichere, zuverlässige und optimierte Bindung dar, die nur für die Computer übergreifende WCF-Kommunikation mit TCP vorgesehen ist. Zuverlässiges Messaging ist standardmäßig deaktiviert.
ms.date: 03/30/2017
helpviewer_keywords:
- netTcpBinding Element
ms.assetid: 5c5104a7-8754-4335-8233-46a45322503e
ms.openlocfilehash: a366b26d87c8796822e4fbbb2001823c116f2629
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556127"
---
# \<netTcpBinding>

<span data-ttu-id="3c22a-103">Gibt eine sichere, zuverlässige und optimierte Bindung an, die computerübergreifende Kommunikation unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3c22a-103">Specifies a secure, reliable, optimized binding suitable for cross-machine communication.</span></span> <span data-ttu-id="3c22a-104">Diese Bindung generiert standardmäßig einen Laufzeitkommunikationsstapel mit Windows-Sicherheit für die Nachrichtensicherheit und die Authentifizierung, TCP für die Nachrichtenübermittlung sowie binäre Nachrichtencodierung.</span><span class="sxs-lookup"><span data-stu-id="3c22a-104">By default, it generates a runtime communication stack with Windows Security for message security and authentication, TCP for message delivery, and binary message encoding.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netTcpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="3c22a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3c22a-105">Syntax</span></span>  
  
```xml  
<netTcpBinding>
  <binding closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           listenBacklog="Integer"
           maxBufferPoolSize="integer"
           maxBufferSize="Integer"
           maxConnections="Integer"
           maxReceivedMessageSize="Integer"
           name="string"
           openTimeout="TimeSpan"
           portSharingEnabled="Boolean"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           transactionFlow="Boolean"
           transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <security mode="None/Transport/Message/Both">
      <message clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" />
      <transport clientCredentialType="None/Windows/Certificate"
                 protectionLevel="None/Sign/EncryptAndSign" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c22a-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3c22a-106">Attributes and elements</span></span>

<span data-ttu-id="3c22a-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3c22a-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c22a-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="3c22a-108">Attributes</span></span>  
  
|<span data-ttu-id="3c22a-109">attribute</span><span class="sxs-lookup"><span data-stu-id="3c22a-109">Attribute</span></span>|<span data-ttu-id="3c22a-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3c22a-110">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="3c22a-111">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="3c22a-111">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="3c22a-112">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="3c22a-112">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3c22a-113">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="3c22a-113">The default is 00:01:00.</span></span>|  
|`hostNameComparisonMode`|<span data-ttu-id="3c22a-114">Gibt den HTTP-Hostnamen-Vergleichsmodus an, der verwendet wird, um URIs zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="3c22a-114">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="3c22a-115">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HostNameComparisonMode> und gibt an, ob beim Abgleich des URI der Hostname zum Erreichen des Dienstes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3c22a-115">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="3c22a-116">Der Standardwert lautet <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, wodurch der Hostname beim Abgleich ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="3c22a-116">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`listenBacklog`|<span data-ttu-id="3c22a-117">Eine positive ganze Zahl, die die maximale Anzahl an Kanälen angibt, die im Listener darauf warten, akzeptiert zu werden.</span><span class="sxs-lookup"><span data-stu-id="3c22a-117">A positive integer that specifies the maximum number of channels waiting to be accepted on the listener.</span></span> <span data-ttu-id="3c22a-118">Verbindungen oberhalb des Limits werden in die Warteschlange gestellt, bis unterhalb des Limits Speicherplatz verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="3c22a-118">Connections in excess of this limit are queued until space below the limit becomes available.</span></span> <span data-ttu-id="3c22a-119">Das `connectionTimeout`-Attribut beschränkt die Zeit, die ein Client wartet, bevor eine Verbindungsausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="3c22a-119">The `connectionTimeout` attribute limits the time a client will wait to be connected before throwing a connection exception.</span></span> <span data-ttu-id="3c22a-120">Der Standardwert ist 10.</span><span class="sxs-lookup"><span data-stu-id="3c22a-120">The default is 10.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="3c22a-121">Eine ganze Zahl, die die maximale Pufferpoolgröße für diese Bindung angibt.</span><span class="sxs-lookup"><span data-stu-id="3c22a-121">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="3c22a-122">Der Standardwert ist 512 \* 1024 Bytes.</span><span class="sxs-lookup"><span data-stu-id="3c22a-122">The default is 512 \* 1024 bytes.</span></span> <span data-ttu-id="3c22a-123">Viele Teile von Windows Communication Foundation (WCF) verwenden Puffer.</span><span class="sxs-lookup"><span data-stu-id="3c22a-123">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="3c22a-124">Das Erstellen und Zerstören von Puffern bei jeder Verwendung ist kostspielig. Dasselbe gilt für die Garbage Collection für Puffer.</span><span class="sxs-lookup"><span data-stu-id="3c22a-124">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="3c22a-125">Bei Pufferpools können Sie einen zu verwendenden Puffer aus dem Pool nehmen und ihn nach der Verwendung wieder dem Pool zuführen.</span><span class="sxs-lookup"><span data-stu-id="3c22a-125">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="3c22a-126">So wird der Aufwand beim Erstellen und Zerstören von Puffern vermieden.</span><span class="sxs-lookup"><span data-stu-id="3c22a-126">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="3c22a-127">Eine positive ganze Zahl, die die maximale Größe des Puffers in Bytes angibt, der zum Speichern von Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3c22a-127">A positive integer that specifies the maximum size, in bytes, of the buffer used to store messages in memory.</span></span><br /><br /> <span data-ttu-id="3c22a-128">Wenn das `transferMode`-Attribut auf `Buffered` festgelegt ist, sollte dieses Attribut auf den `maxReceivedMessageSize`-Attributwert festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="3c22a-128">If the `transferMode` attribute equals to `Buffered`, this attribute should be equal to the `maxReceivedMessageSize` attribute value.</span></span><br /><br /> <span data-ttu-id="3c22a-129">Wenn das `transferMode`-Attribut auf `Streamed` festgelegt ist, darf dieses Attribut den `maxReceivedMessageSize`-Attributwert nicht überschreiten und sollte mindestens auf die Größe des Headers festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="3c22a-129">If the `transferMode` attribute equals to `Streamed`, this attribute cannot be more than the `maxReceivedMessageSize` attribute value, and should be at least the size of the headers.</span></span><br /><br /> <span data-ttu-id="3c22a-130">Der Standard ist 65536.</span><span class="sxs-lookup"><span data-stu-id="3c22a-130">The default is 65536.</span></span> <span data-ttu-id="3c22a-131">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span><span class="sxs-lookup"><span data-stu-id="3c22a-131">For more information, see <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span></span>|  
|`maxConnections`|<span data-ttu-id="3c22a-132">Eine ganze Zahl, die die maximale Anzahl ausgehender und eingehender Verbindungen angibt, die der Dienst erstellt bzw. akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="3c22a-132">An integer that specifies the maximum number of outbound and inbound connections the service will create/accept.</span></span> <span data-ttu-id="3c22a-133">Eingehende und ausgehende Verbindungen werden mit einem separaten, von diesem Attribut angegebenen Grenzwert verglichen.</span><span class="sxs-lookup"><span data-stu-id="3c22a-133">Incoming and outgoing connections are counted against a separate limit specified by this attribute.</span></span><br /><br /> <span data-ttu-id="3c22a-134">Eingehende Verbindungen, die diesen Grenzwert überschreiten, werden in die Warteschlange gestellt, bis wieder Speicherplatz verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="3c22a-134">Inbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="3c22a-135">Ausgehende Verbindungen, die diesen Grenzwert überschreiten, werden in die Warteschlange gestellt, bis wieder Speicherplatz verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="3c22a-135">Outbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="3c22a-136">Der Standardwert ist 10.</span><span class="sxs-lookup"><span data-stu-id="3c22a-136">The default is 10.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="3c22a-137">Eine positive ganze Zahl, die die maximale Nachrichtengröße in Bytes einschließlich Header angibt, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="3c22a-137">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="3c22a-138">Der Absender einer Nachricht, die diese Grenze überschreitet, erhält einen SOAP-Fehler.</span><span class="sxs-lookup"><span data-stu-id="3c22a-138">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="3c22a-139">Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="3c22a-139">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="3c22a-140">Der Standard ist 65536.</span><span class="sxs-lookup"><span data-stu-id="3c22a-140">The default is 65536.</span></span>|  
|`name`|<span data-ttu-id="3c22a-141">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="3c22a-141">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="3c22a-142">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3c22a-142">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="3c22a-143">Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="3c22a-143">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="3c22a-144">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="3c22a-144">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="3c22a-145">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="3c22a-145">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="3c22a-146">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="3c22a-146">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3c22a-147">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="3c22a-147">The default is 00:01:00.</span></span>|  
|`portSharingEnabled`|<span data-ttu-id="3c22a-148">Ein boolescher Wert, der angibt, ob die TCP-Anschlussfreigabe für diese Verbindung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="3c22a-148">A Boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span> <span data-ttu-id="3c22a-149">Wenn dies `false` ist, verwendet jede Bindung ihren eigenen Anschluss.</span><span class="sxs-lookup"><span data-stu-id="3c22a-149">If this is `false`, each binding uses its own exclusive port.</span></span> <span data-ttu-id="3c22a-150">Diese Einstellung ist nur für Dienste relevant, da Clients nicht betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="3c22a-150">This setting is relevant only to services, because clients are not affected.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="3c22a-151">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="3c22a-151">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="3c22a-152">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="3c22a-152">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3c22a-153">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="3c22a-153">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="3c22a-154">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="3c22a-154">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="3c22a-155">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="3c22a-155">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3c22a-156">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="3c22a-156">The default is 00:01:00.</span></span>|  
|`transactionFlow`|<span data-ttu-id="3c22a-157">Ein boolescher Wert, der angibt, ob die Bindung geleitete WS-Transaktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3c22a-157">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="3c22a-158">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="3c22a-158">The default is `false`.</span></span>|  
|`transactionProtocol`|<span data-ttu-id="3c22a-159">Gibt das Transaktionsprotokoll an, das mit dieser Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3c22a-159">Specifies the transaction protocol to be used with this binding.</span></span> <span data-ttu-id="3c22a-160">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="3c22a-160">Valid values are</span></span><br /><br /> <span data-ttu-id="3c22a-161">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="3c22a-161">-   OleTransactions</span></span><br /><span data-ttu-id="3c22a-162">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="3c22a-162">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="3c22a-163">Der Standardwert ist OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="3c22a-163">The default is OleTransactions.</span></span> <span data-ttu-id="3c22a-164">Dieses Attribut ist vom Typ <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="3c22a-164">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
|`transferMode`|<span data-ttu-id="3c22a-165">Ein <xref:System.ServiceModel.TransferMode>-Wert, der angibt, ob Nachrichten bei einer Anforderung oder Antwort gepuffert oder per Stream übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="3c22a-165">A <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed or a request or response.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3c22a-166">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3c22a-166">Child elements</span></span>  
  
|<span data-ttu-id="3c22a-167">Element</span><span class="sxs-lookup"><span data-stu-id="3c22a-167">Element</span></span>|<span data-ttu-id="3c22a-168">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3c22a-168">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nettcpbinding.md)|<span data-ttu-id="3c22a-169">Definiert die Sicherheitseinstellungen für die Bindung.</span><span class="sxs-lookup"><span data-stu-id="3c22a-169">Defines the security settings for the binding.</span></span> <span data-ttu-id="3c22a-170">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="3c22a-170">This element is of type <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>.</span></span>|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="3c22a-171">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="3c22a-171">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="3c22a-172">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="3c22a-172">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<reliableSession>](/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="3c22a-173">Gibt an, ob zuverlässige Sitzungen zwischen Kanalendpunkten aufgebaut werden.</span><span class="sxs-lookup"><span data-stu-id="3c22a-173">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3c22a-174">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3c22a-174">Parent elements</span></span>  
  
|<span data-ttu-id="3c22a-175">Element</span><span class="sxs-lookup"><span data-stu-id="3c22a-175">Element</span></span>|<span data-ttu-id="3c22a-176">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3c22a-176">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="3c22a-177">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="3c22a-177">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c22a-178">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3c22a-178">Remarks</span></span>

<span data-ttu-id="3c22a-179">Diese Bindung generiert standardmäßig eine Laufzeitkommunikation, die Transportsicherheit, TCP zur Nachrichtenübermittlung und eine binäre Nachrichtencodierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="3c22a-179">This binding generates a run-time communication stack by default, which uses transport security, TCP for message delivery, and a binary message encoding.</span></span> <span data-ttu-id="3c22a-180">Diese Bindung ist eine geeignete von einem System bereitgestellte Windows Communication Foundation (WCF) für die Kommunikation über ein Intranet.</span><span class="sxs-lookup"><span data-stu-id="3c22a-180">This binding is an appropriate Windows Communication Foundation (WCF) system-provided choice for communicating over an Intranet.</span></span>  
  
 <span data-ttu-id="3c22a-181">Die Standardkonfiguration für `netTcpBinding` ist schneller als die von bereitgestellte Konfiguration `wsHttpBinding` , Sie ist jedoch nur für die WCF-Kommunikation vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="3c22a-181">The default configuration for the `netTcpBinding` is faster than the configuration provided by the `wsHttpBinding`, but it is intended only for WCF communication.</span></span> <span data-ttu-id="3c22a-182">Das Sicherheitsverhalten ist mit dem optionalen `securityMode`-Attribut konfigurierbar.</span><span class="sxs-lookup"><span data-stu-id="3c22a-182">The security behavior is configurable using the optional `securityMode` attribute.</span></span> <span data-ttu-id="3c22a-183">Die Verwendung von WS-ReliableMessaging ist mit dem optionalen `reliableSessionEnabled`-Attribut konfigurierbar.</span><span class="sxs-lookup"><span data-stu-id="3c22a-183">The use of WS-ReliableMessaging is configurable using the optional `reliableSessionEnabled` attribute.</span></span> <span data-ttu-id="3c22a-184">Zuverlässiges Messaging ist jedoch standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="3c22a-184">But reliable messaging is off by default.</span></span> <span data-ttu-id="3c22a-185">Die vom System bereitgestellten HTTP-Bindungen, wie z.&#160;B. `wsHttpBinding` und `basicHttpBinding`, sind im Allgemeinen so konfiguriert, dass Funktionen standardmäßig aktiviert werden ,während die `netTcpBinding`-Bindung Funktionen standardmäßig deaktiviert, sodass Sie die Unterstützung für eine der WS-\*-Spezifikationen explizit übernehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="3c22a-185">More generally, the HTTP system-provided bindings such as `wsHttpBinding` and `basicHttpBinding` are configured to turn things on by default, whereas the `netTcpBinding` binding turns things off by default so that you have to opt-in to get support, for example, for one of the WS-\* specifications.</span></span> <span data-ttu-id="3c22a-186">Das bedeutet, dass die Standardkonfiguration für TCP Meldungen zwischen Endpunkten schneller austauscht als die standardmäßig für die HTTP-Bindungen festgelegten Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="3c22a-186">This means that the default configuration for TCP is faster at exchanging messages between endpoints than those configured for the HTTP bindings by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c22a-187">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3c22a-187">Example</span></span>

<span data-ttu-id="3c22a-188">Die Bindung wird in den Konfigurationsdateien für den Client und Dienst angegeben.</span><span class="sxs-lookup"><span data-stu-id="3c22a-188">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="3c22a-189">Der Bindungstyp wird im `binding`-Attribut des `<endpoint>`-Elements angegeben.</span><span class="sxs-lookup"><span data-stu-id="3c22a-189">The binding type is specified in the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="3c22a-190">Wenn Sie die netTcpBinding-Bindung konfigurieren und einige der Einstellungen ändern möchten, müssen Sie eine Bindungskonfiguration definieren.</span><span class="sxs-lookup"><span data-stu-id="3c22a-190">If you want to configure the netTcpBinding binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="3c22a-191">Der Endpunkt muss auf die Bindungskonfiguration mithilfe des `bindingConfiguration`-Attributs verweisen.</span><span class="sxs-lookup"><span data-stu-id="3c22a-191">The endpoint must reference the binding configuration with a `bindingConfiguration` attribute.</span></span> <span data-ttu-id="3c22a-192">Im folgenden Beispiel wird eine Bindungskonfiguration definiert.</span><span class="sxs-lookup"><span data-stu-id="3c22a-192">In the following example, a binding configuration is defined.</span></span>  
  
```xml  
<services>
  <service name="Microsoft.ServiceModel.Samples.CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    ...
    <endpoint address=""
              binding="netTcpBinding"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />
    ...
  </service>
</services>
<bindings>
  <netTcpBinding>
    <binding closeTimeout="00:01:00"
             openTimeout="00:01:00"
             receiveTimeout="00:10:00"
             sendTimeout="00:01:00"
             transactionFlow="false"
             transferMode="Buffered"
             transactionProtocol="OleTransactions"
             hostNameComparisonMode="StrongWildcard"
             listenBacklog="10"
             maxBufferPoolSize="524288"
             maxBufferSize="65536"
             maxConnections="10"
             maxReceivedMessageSize="65536">
      <readerQuotas maxDepth="32"
                    maxStringContentLength="8192"
                    maxArrayLength="16384"
                    maxBytesPerRead="4096"
                    maxNameTableCharCount="16384" />
      <reliableSession ordered="true"
                       inactivityTimeout="00:10:00"
                       enabled="false" />
      <security mode="Transport">
        <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign" />
      </security>
    </binding>
  </netTcpBinding>
</bindings>
```  
  
## <a name="see-also"></a><span data-ttu-id="3c22a-193">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3c22a-193">See also</span></span>

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement>
- [<span data-ttu-id="3c22a-194">Bindungen</span><span class="sxs-lookup"><span data-stu-id="3c22a-194">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3c22a-195">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="3c22a-195">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3c22a-196">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="3c22a-196">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
