---
title: <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 00a8580b-face-47a4-838d-b9fed48e72df
ms.openlocfilehash: f1ec6091d72c1d1c6d75c44dd1f98d6d4e10ea12
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204566"
---
# \<netNamedPipeBinding>

<span data-ttu-id="2cdcd-101">Definiert eine Bindung, die sicher und zuverlässig ist und für eine prozessübergreifende Kommunikation auf einem Computer optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-101">Defines a binding that is secure, reliable, optimized for on-machine cross process communication.</span></span> <span data-ttu-id="2cdcd-102">Sie generiert standardmäßig einen Laufzeitkommunikationsstapel mit WS-ReliableMessaging für Verlässlichkeit, Transport- und Übertragungssicherheit, benannte Pipes für den Nachrichtentransport sowie binäre Nachrichtencodierung.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-102">By default, it generates a runtime communication stack with WS-ReliableMessaging for reliability, transport security for transfer security, named pipes for message delivery, and binary message encoding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netNamedPipeBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="2cdcd-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="2cdcd-103">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="Integer"
           maxBufferSize="Integer"
           maxConnections="Integer"
           maxReceivedMessageSize="Integer"
           name="String"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           transactionFlow="Boolean"
           transactionProtocol="OleTransactions/WS-AtomicTransactionOctober2004"
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2cdcd-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2cdcd-104">Attributes and Elements</span></span>  

 <span data-ttu-id="2cdcd-105">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2cdcd-106">Attributes</span><span class="sxs-lookup"><span data-stu-id="2cdcd-106">Attributes</span></span>  
  
|<span data-ttu-id="2cdcd-107">attribute</span><span class="sxs-lookup"><span data-stu-id="2cdcd-107">Attribute</span></span>|<span data-ttu-id="2cdcd-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2cdcd-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2cdcd-109">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="2cdcd-109">closeTimeout</span></span>|<span data-ttu-id="2cdcd-110">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-110">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="2cdcd-111">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-111">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="2cdcd-112">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-112">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="2cdcd-113">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="2cdcd-113">hostNameComparisonMode</span></span>|<span data-ttu-id="2cdcd-114">Gibt den HTTP-Hostnamen-Vergleichsmodus an, der verwendet wird, um URIs zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-114">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="2cdcd-115">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HostNameComparisonMode> und gibt an, ob beim Abgleich des URI der Hostname zum Erreichen des Dienstes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-115">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="2cdcd-116">Der Standardwert lautet <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, wodurch der Hostname beim Abgleich ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-116">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="2cdcd-117">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="2cdcd-117">maxBufferPoolSize</span></span>|<span data-ttu-id="2cdcd-118">Eine ganze Zahl, die die maximale Pufferpoolgröße für diese Bindung angibt.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-118">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="2cdcd-119">Der Standardwert ist 524.288 Byte (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="2cdcd-119">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="2cdcd-120">Viele Teile von Windows Communication Foundation (WCF) verwenden Puffer.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-120">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="2cdcd-121">Das Erstellen und Zerstören von Puffern bei jeder Verwendung ist kostspielig. Dasselbe gilt für die Garbage Collection für Puffer.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-121">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="2cdcd-122">Bei Pufferpools können Sie einen zu verwendenden Puffer aus dem Pool nehmen und ihn nach der Verwendung wieder dem Pool zuführen.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-122">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="2cdcd-123">So wird der Aufwand beim Erstellen und Zerstören von Puffern vermieden.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-123">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="2cdcd-124">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="2cdcd-124">maxBufferSize</span></span>|<span data-ttu-id="2cdcd-125">Eine positive ganze Zahl, die die maximale Größe des Puffers in Bytes angibt, der zum Speichern von Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-125">A positive integer that specifies the maximum size, in bytes, of the buffer used to store messages in memory.</span></span> <span data-ttu-id="2cdcd-126">Falls der Puffer voll ist, verbleiben die überzähligen Daten so lange im zugrunde liegenden Socket, bis der Puffer wieder Platz bietet.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-126">If the buffer is full, excess data remains in the underlying socket until the buffer has room again.</span></span> <span data-ttu-id="2cdcd-127">Dieser Wert darf nicht kleiner sein als das `maxReceivedMessageSize`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-127">This value cannot be less than `maxReceivedMessageSize` attribute.</span></span> <span data-ttu-id="2cdcd-128">Der Standard ist 65536.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-128">The default is 65536.</span></span> <span data-ttu-id="2cdcd-129">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-129">For more information, see <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span></span>|  
|<span data-ttu-id="2cdcd-130">maxConnections</span><span class="sxs-lookup"><span data-stu-id="2cdcd-130">maxConnections</span></span>|<span data-ttu-id="2cdcd-131">Eine ganze Zahl, die die maximale Anzahl ausgehender und eingehender Verbindungen angibt, die der Dienst erstellt bzw. akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-131">An integer that specifies the maximum number of outbound and inbound connections the service will create/accept.</span></span> <span data-ttu-id="2cdcd-132">Eingehende und ausgehende Verbindungen werden mit einem separaten, von diesem Attribut angegebenen Grenzwert verglichen.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-132">Incoming and outgoing connections are counted against a separate limit specified by this attribute.</span></span><br /><br /> <span data-ttu-id="2cdcd-133">Eingehende Verbindungen, die diesen Grenzwert überschreiten, werden in die Warteschlange gestellt, bis wieder Speicherplatz verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-133">Inbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="2cdcd-134">Ausgehende Verbindungen, die diesen Grenzwert überschreiten, werden in die Warteschlange gestellt, bis wieder Speicherplatz verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-134">Outbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="2cdcd-135">Der Standardwert ist 10.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-135">The default is 10.</span></span>|  
|<span data-ttu-id="2cdcd-136">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="2cdcd-136">maxReceivedMessageSize</span></span>|<span data-ttu-id="2cdcd-137">Eine positive ganze Zahl, die die maximale Nachrichtengröße in Bytes einschließlich Header angibt, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-137">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="2cdcd-138">Der Absender einer Nachricht, die diese Grenze überschreitet, erhält einen SOAP-Fehler.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-138">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="2cdcd-139">Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-139">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="2cdcd-140">Der Standard ist 65536.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-140">The default is 65536.</span></span>|  
|<span data-ttu-id="2cdcd-141">name</span><span class="sxs-lookup"><span data-stu-id="2cdcd-141">name</span></span>|<span data-ttu-id="2cdcd-142">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-142">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="2cdcd-143">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-143">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="2cdcd-144">Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-144">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="2cdcd-145">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="2cdcd-145">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="2cdcd-146">openTimeout</span><span class="sxs-lookup"><span data-stu-id="2cdcd-146">openTimeout</span></span>|<span data-ttu-id="2cdcd-147">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-147">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="2cdcd-148">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-148">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="2cdcd-149">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-149">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="2cdcd-150">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="2cdcd-150">receiveTimeout</span></span>|<span data-ttu-id="2cdcd-151">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-151">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="2cdcd-152">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-152">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="2cdcd-153">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-153">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="2cdcd-154">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="2cdcd-154">sendTimeout</span></span>|<span data-ttu-id="2cdcd-155">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-155">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="2cdcd-156">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-156">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="2cdcd-157">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-157">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="2cdcd-158">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="2cdcd-158">transactionFlow</span></span>|<span data-ttu-id="2cdcd-159">Ein boolescher Wert, der angibt, ob die Bindung geleitete WS-Transaktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-159">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="2cdcd-160">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-160">The default is `false`.</span></span>|  
|<span data-ttu-id="2cdcd-161">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="2cdcd-161">transactionProtocol</span></span>|<span data-ttu-id="2cdcd-162">Gibt das Transaktionsprotokoll an, das mit dieser Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-162">Specifies the transaction protocol to be used with this binding.</span></span> <span data-ttu-id="2cdcd-163">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="2cdcd-163">Valid values are</span></span><br /><br /> <span data-ttu-id="2cdcd-164">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="2cdcd-164">-   OleTransactions</span></span><br /><span data-ttu-id="2cdcd-165">-WS-AtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="2cdcd-165">-   WS-AtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="2cdcd-166">Der Standardwert ist OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-166">The default is OleTransactions.</span></span> <span data-ttu-id="2cdcd-167">Dieses Attribut ist vom Typ <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-167">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
|<span data-ttu-id="2cdcd-168">transferMode</span><span class="sxs-lookup"><span data-stu-id="2cdcd-168">transferMode</span></span>|<span data-ttu-id="2cdcd-169">Ein <xref:System.ServiceModel.TransferMode>-Wert, der angibt, ob Nachrichten bei einer Anforderung oder Antwort gepuffert oder per Stream übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-169">A <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed or a request or response.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2cdcd-170">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2cdcd-170">Child Elements</span></span>  
  
|<span data-ttu-id="2cdcd-171">Element</span><span class="sxs-lookup"><span data-stu-id="2cdcd-171">Element</span></span>|<span data-ttu-id="2cdcd-172">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2cdcd-172">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netnamedpipebinding.md)|<span data-ttu-id="2cdcd-173">Definiert die Sicherheitseinstellungen für die Bindung.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-173">Defines the security settings for the binding.</span></span> <span data-ttu-id="2cdcd-174">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-174">This element is of type <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>.</span></span>|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="2cdcd-175">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-175">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="2cdcd-176">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-176">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2cdcd-177">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2cdcd-177">Parent Elements</span></span>  
  
|<span data-ttu-id="2cdcd-178">Element</span><span class="sxs-lookup"><span data-stu-id="2cdcd-178">Element</span></span>|<span data-ttu-id="2cdcd-179">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2cdcd-179">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="2cdcd-180">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-180">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2cdcd-181">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2cdcd-181">Remarks</span></span>  

 <span data-ttu-id="2cdcd-182">`NetNamedPipeBinding` generiert standardmäßig eine Laufzeitkommunikation, die Transportsicherheit, Named Pipes zur Nachrichtenübermittlung und eine binäre Nachrichtencodierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-182">The `NetNamedPipeBinding` generates a run-time communication stack by default, which uses transport security, named pipes for message delivery, and a binary message encoding.</span></span> <span data-ttu-id="2cdcd-183">Diese Bindung ist eine entsprechende vom System bereitgestellte Windows Communication Foundation (WCF)-Wahl für die computerinterne Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-183">This binding is an appropriate Windows Communication Foundation (WCF) system-provided choice for on-machine communication.</span></span> <span data-ttu-id="2cdcd-184">Sie unterstützt auch Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-184">It also supports transactions.</span></span>  
  
 <span data-ttu-id="2cdcd-185">Die Standardkonfiguration für `NetNamedPipeBinding` ähnelt der Konfiguration, die von `NetTcpBinding` bereitgestellt wird, sie ist jedoch einfacher, da die WCF-Implementierung nur für die computerinterne Verwendung konzipiert ist und daher weniger Funktionen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-185">The default configuration for the `NetNamedPipeBinding` is similar to the configuration provided by the `NetTcpBinding`, but it is simpler because the WCF implementation is only meant for on-machine use and consequently there are fewer exposed features.</span></span> <span data-ttu-id="2cdcd-186">Der wichtigste Unterschied besteht darin, dass die `securityMode`-Einstellung nur die Optionen `None` und `Transport` anbietet.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-186">The most notable difference is that the `securityMode` setting only offers the `None` and `Transport` options.</span></span> <span data-ttu-id="2cdcd-187">SOAP-Sicherheitsunterstützung ist keine eingeschlossene Option.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-187">SOAP security support is not an included option.</span></span> <span data-ttu-id="2cdcd-188">Das Sicherheitsverhalten ist mit dem optionalen `securityMode`-Attribut konfigurierbar.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-188">The security behavior is configurable using the optional `securityMode` attribute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cdcd-189">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2cdcd-189">Example</span></span>  

 <span data-ttu-id="2cdcd-190">Im folgenden Beispiel wird die netNamedPipeBinding-Bindung, die prozessübergreifende Kommunikation auf dem gleichen Computer bereitstellt, veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-190">The following example demonstrates the netNamedPipeBinding binding, which provides cross-process communication on the same machine.</span></span> <span data-ttu-id="2cdcd-191">Benannte Pipes funktionieren nicht computerübergreifend.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-191">Named pipes do not work across machines.</span></span>  
  
 <span data-ttu-id="2cdcd-192">Die Bindung wird in den Konfigurationsdateien für den Client und Dienst angegeben.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-192">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="2cdcd-193">Der Bindungstyp wird im `binding`-Attribut des `<endpoint>`-Elements angegeben.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-193">The binding type is specified in the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="2cdcd-194">Wenn Sie die netNamedPipeBinding-Bindung konfigurieren und einige der Einstellungen ändern möchten, müssen Sie eine Bindungskonfiguration definieren.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-194">If you want to configure the netNamedPipeBinding binding and change some of its settings, you must define a binding configuration.</span></span> <span data-ttu-id="2cdcd-195">Der Endpunkt muss auf die Bindungskonfiguration mithilfe des `bindingConfiguration`-Attributs mit einem Namen verweisen.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-195">The endpoint must reference the binding configuration by name with a `bindingConfiguration` attribute.</span></span> <span data-ttu-id="2cdcd-196">In diesem Beispiel wird die Bindungskonfiguration „Binding1“ genannt.</span><span class="sxs-lookup"><span data-stu-id="2cdcd-196">In this example, the binding configuration is named Binding1.</span></span>  
  
```xml  
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <host>
          <baseAddresses>
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
          </baseAddresses>
        </host>
        <!-- this endpoint is exposed at the base address provided by host: net.pipe://localhost/ServiceModelSamples/service  -->
        <endpoint address="net.pipe://localhost/ServiceModelSamples/service"
                  binding="netNamedPipeBinding"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <bindings>
      <netNamedPipeBinding>
        <binding closeTimeout="00:01:00"
                 openTimeout="00:01:00"
                 receiveTimeout="00:10:00"
                 sendTimeout="00:01:00"
                 transactionFlow="false"
                 transferMode="Buffered"
                 transactionProtocol="OleTransactions"
                 hostNameComparisonMode="StrongWildcard"
                 maxBufferPoolSize="524288"
                 maxBufferSize="65536"
                 maxConnections="10"
                 maxReceivedMessageSize="65536">
          <security mode="Transport">
            <transport protectionLevel="EncryptAndSign" />
          </security>
        </binding>
      </netNamedPipeBinding>
    </bindings>
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceMetadata httpGetEnabled="True" />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="2cdcd-197">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2cdcd-197">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>
- <xref:System.ServiceModel.NetNamedPipeBinding>
- [\<binding>](bindings.md)
- [<span data-ttu-id="2cdcd-198">Bindungen</span><span class="sxs-lookup"><span data-stu-id="2cdcd-198">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2cdcd-199">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="2cdcd-199">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="2cdcd-200">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="2cdcd-200">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
