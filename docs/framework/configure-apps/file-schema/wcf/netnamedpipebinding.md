---
title: <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 00a8580b-face-47a4-838d-b9fed48e72df
ms.openlocfilehash: f1aa68bcdda43fd77bee397c079695f7937faa52
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74139470"
---
# <a name="netnamedpipebinding"></a><span data-ttu-id="02d47-101">\<NetNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="02d47-101">\<netNamedPipeBinding></span></span>
<span data-ttu-id="02d47-102">Definiert eine Bindung, die sicher und zuverlässig ist und für eine prozessübergreifende Kommunikation auf einem Computer optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="02d47-102">Defines a binding that is secure, reliable, optimized for on-machine cross process communication.</span></span> <span data-ttu-id="02d47-103">Sie generiert standardmäßig einen Laufzeitkommunikationsstapel mit WS-ReliableMessaging für Verlässlichkeit, Transport- und Übertragungssicherheit, benannte Pipes für den Nachrichtentransport sowie binäre Nachrichtencodierung.</span><span class="sxs-lookup"><span data-stu-id="02d47-103">By default, it generates a runtime communication stack with WS-ReliableMessaging for reliability, transport security for transfer security, named pipes for message delivery, and binary message encoding.</span></span>  
  
<span data-ttu-id="02d47-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="02d47-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="02d47-105">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="02d47-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="02d47-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="02d47-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="02d47-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<NetNamedPipeBinding >**</span><span class="sxs-lookup"><span data-stu-id="02d47-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netNamedPipeBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02d47-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="02d47-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02d47-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="02d47-109">Attributes and Elements</span></span>  
 <span data-ttu-id="02d47-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="02d47-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02d47-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="02d47-111">Attributes</span></span>  
  
|<span data-ttu-id="02d47-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="02d47-112">Attribute</span></span>|<span data-ttu-id="02d47-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02d47-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="02d47-114">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="02d47-114">closeTimeout</span></span>|<span data-ttu-id="02d47-115">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="02d47-115">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="02d47-116">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="02d47-116">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="02d47-117">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="02d47-117">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="02d47-118">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="02d47-118">hostNameComparisonMode</span></span>|<span data-ttu-id="02d47-119">Gibt den HTTP-Hostnamen-Vergleichsmodus an, der verwendet wird, um URIs zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="02d47-119">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="02d47-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HostNameComparisonMode> und gibt an, ob beim Abgleich des URI der Hostname zum Erreichen des Dienstes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="02d47-120">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="02d47-121">Der Standardwert lautet <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, wodurch der Hostname beim Abgleich ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="02d47-121">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="02d47-122">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="02d47-122">maxBufferPoolSize</span></span>|<span data-ttu-id="02d47-123">Eine ganze Zahl, die die maximale Pufferpoolgröße für diese Bindung angibt.</span><span class="sxs-lookup"><span data-stu-id="02d47-123">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="02d47-124">Der Standardwert ist 524.288 Byte (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="02d47-124">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="02d47-125">Viele Teile von Windows Communication Foundation (WCF) verwenden Puffer.</span><span class="sxs-lookup"><span data-stu-id="02d47-125">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="02d47-126">Das Erstellen und Zerstören von Puffern bei jeder Verwendung ist kostspielig. Dasselbe gilt für die Garbage Collection für Puffer.</span><span class="sxs-lookup"><span data-stu-id="02d47-126">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="02d47-127">Bei Pufferpools können Sie einen zu verwendenden Puffer aus dem Pool nehmen und ihn nach der Verwendung wieder dem Pool zuführen.</span><span class="sxs-lookup"><span data-stu-id="02d47-127">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="02d47-128">So wird der Aufwand beim Erstellen und Zerstören von Puffern vermieden.</span><span class="sxs-lookup"><span data-stu-id="02d47-128">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="02d47-129">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="02d47-129">maxBufferSize</span></span>|<span data-ttu-id="02d47-130">Eine positive ganze Zahl, die die maximale Größe des Puffers in Bytes angibt, der zum Speichern von Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="02d47-130">A positive integer that specifies the maximum size, in bytes, of the buffer used to store messages in memory.</span></span> <span data-ttu-id="02d47-131">Falls der Puffer voll ist, verbleiben die überzähligen Daten so lange im zugrunde liegenden Socket, bis der Puffer wieder Platz bietet.</span><span class="sxs-lookup"><span data-stu-id="02d47-131">If the buffer is full, excess data remains in the underlying socket until the buffer has room again.</span></span> <span data-ttu-id="02d47-132">Dieser Wert darf nicht kleiner sein als das `maxReceivedMessageSize`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="02d47-132">This value cannot be less than `maxReceivedMessageSize` attribute.</span></span> <span data-ttu-id="02d47-133">Der Standard ist 65536.</span><span class="sxs-lookup"><span data-stu-id="02d47-133">The default is 65536.</span></span> <span data-ttu-id="02d47-134">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span><span class="sxs-lookup"><span data-stu-id="02d47-134">For more information, see <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span></span>|  
|<span data-ttu-id="02d47-135">maxConnections</span><span class="sxs-lookup"><span data-stu-id="02d47-135">maxConnections</span></span>|<span data-ttu-id="02d47-136">Eine ganze Zahl, die die maximale Anzahl ausgehender und eingehender Verbindungen angibt, die der Dienst erstellt bzw. akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="02d47-136">An integer that specifies the maximum number of outbound and inbound connections the service will create/accept.</span></span> <span data-ttu-id="02d47-137">Eingehende und ausgehende Verbindungen werden mit einem separaten, von diesem Attribut angegebenen Grenzwert verglichen.</span><span class="sxs-lookup"><span data-stu-id="02d47-137">Incoming and outgoing connections are counted against a separate limit specified by this attribute.</span></span><br /><br /> <span data-ttu-id="02d47-138">Eingehende Verbindungen, die diesen Grenzwert überschreiten, werden in die Warteschlange gestellt, bis wieder Speicherplatz verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="02d47-138">Inbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="02d47-139">Ausgehende Verbindungen, die diesen Grenzwert überschreiten, werden in die Warteschlange gestellt, bis wieder Speicherplatz verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="02d47-139">Outbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="02d47-140">Der Standard ist 10.</span><span class="sxs-lookup"><span data-stu-id="02d47-140">The default is 10.</span></span>|  
|<span data-ttu-id="02d47-141">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="02d47-141">maxReceivedMessageSize</span></span>|<span data-ttu-id="02d47-142">Eine positive ganze Zahl, die die maximale Nachrichtengröße in Bytes einschließlich Header angibt, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="02d47-142">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="02d47-143">Der Absender einer Nachricht, die diese Grenze überschreitet, erhält einen SOAP-Fehler.</span><span class="sxs-lookup"><span data-stu-id="02d47-143">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="02d47-144">Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="02d47-144">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="02d47-145">Der Standard ist 65536.</span><span class="sxs-lookup"><span data-stu-id="02d47-145">The default is 65536.</span></span>|  
|<span data-ttu-id="02d47-146">Name</span><span class="sxs-lookup"><span data-stu-id="02d47-146">name</span></span>|<span data-ttu-id="02d47-147">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="02d47-147">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="02d47-148">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="02d47-148">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="02d47-149">Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="02d47-149">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="02d47-150">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="02d47-150">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="02d47-151">openTimeout</span><span class="sxs-lookup"><span data-stu-id="02d47-151">openTimeout</span></span>|<span data-ttu-id="02d47-152">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="02d47-152">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="02d47-153">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="02d47-153">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="02d47-154">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="02d47-154">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="02d47-155">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="02d47-155">receiveTimeout</span></span>|<span data-ttu-id="02d47-156">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="02d47-156">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="02d47-157">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="02d47-157">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="02d47-158">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="02d47-158">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="02d47-159">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="02d47-159">sendTimeout</span></span>|<span data-ttu-id="02d47-160">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="02d47-160">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="02d47-161">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="02d47-161">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="02d47-162">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="02d47-162">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="02d47-163">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="02d47-163">transactionFlow</span></span>|<span data-ttu-id="02d47-164">Ein boolescher Wert, der angibt, ob die Bindung geleitete WS-Transaktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="02d47-164">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="02d47-165">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="02d47-165">The default is `false`.</span></span>|  
|<span data-ttu-id="02d47-166">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="02d47-166">transactionProtocol</span></span>|<span data-ttu-id="02d47-167">Gibt das Transaktionsprotokoll an, das mit dieser Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="02d47-167">Specifies the transaction protocol to be used with this binding.</span></span> <span data-ttu-id="02d47-168">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="02d47-168">Valid values are</span></span><br /><br /> <span data-ttu-id="02d47-169">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="02d47-169">-   OleTransactions</span></span><br /><span data-ttu-id="02d47-170">-WS-AtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="02d47-170">-   WS-AtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="02d47-171">Der Standardwert ist OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="02d47-171">The default is OleTransactions.</span></span> <span data-ttu-id="02d47-172">Dieses Attribut ist vom Typ <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="02d47-172">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
|<span data-ttu-id="02d47-173">transferMode</span><span class="sxs-lookup"><span data-stu-id="02d47-173">transferMode</span></span>|<span data-ttu-id="02d47-174">Ein <xref:System.ServiceModel.TransferMode>-Wert, der angibt, ob Nachrichten bei einer Anforderung oder Antwort gepuffert oder per Stream übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="02d47-174">A <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed or a request or response.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02d47-175">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="02d47-175">Child Elements</span></span>  
  
|<span data-ttu-id="02d47-176">Element</span><span class="sxs-lookup"><span data-stu-id="02d47-176">Element</span></span>|<span data-ttu-id="02d47-177">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02d47-177">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02d47-178">\<Sicherheits ></span><span class="sxs-lookup"><span data-stu-id="02d47-178">\<security></span></span>](security-of-netnamedpipebinding.md)|<span data-ttu-id="02d47-179">Definiert die Sicherheitseinstellungen für die Bindung.</span><span class="sxs-lookup"><span data-stu-id="02d47-179">Defines the security settings for the binding.</span></span> <span data-ttu-id="02d47-180">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="02d47-180">This element is of type <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>.</span></span>|  
|<span data-ttu-id="02d47-181">[\<von Readerkontingenten >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="02d47-181">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="02d47-182">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="02d47-182">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="02d47-183">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="02d47-183">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="02d47-184">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="02d47-184">Parent Elements</span></span>  
  
|<span data-ttu-id="02d47-185">Element</span><span class="sxs-lookup"><span data-stu-id="02d47-185">Element</span></span>|<span data-ttu-id="02d47-186">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02d47-186">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02d47-187">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="02d47-187">\<bindings></span></span>](bindings.md)|<span data-ttu-id="02d47-188">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="02d47-188">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02d47-189">Hinweise</span><span class="sxs-lookup"><span data-stu-id="02d47-189">Remarks</span></span>  
 <span data-ttu-id="02d47-190">`NetNamedPipeBinding` generiert standardmäßig eine Laufzeitkommunikation, die Transportsicherheit, Named Pipes zur Nachrichtenübermittlung und eine binäre Nachrichtencodierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="02d47-190">The `NetNamedPipeBinding` generates a run-time communication stack by default, which uses transport security, named pipes for message delivery, and a binary message encoding.</span></span> <span data-ttu-id="02d47-191">Diese Bindung ist eine entsprechende vom System bereitgestellte Windows Communication Foundation (WCF)-Wahl für die computerinterne Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="02d47-191">This binding is an appropriate Windows Communication Foundation (WCF) system-provided choice for on-machine communication.</span></span> <span data-ttu-id="02d47-192">Sie unterstützt auch Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="02d47-192">It also supports transactions.</span></span>  
  
 <span data-ttu-id="02d47-193">Die Standardkonfiguration für `NetNamedPipeBinding` ähnelt der Konfiguration, die von `NetTcpBinding` bereitgestellt wird, sie ist jedoch einfacher, da die WCF-Implementierung nur für die computerinterne Verwendung konzipiert ist und daher weniger Funktionen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="02d47-193">The default configuration for the `NetNamedPipeBinding` is similar to the configuration provided by the `NetTcpBinding`, but it is simpler because the WCF implementation is only meant for on-machine use and consequently there are fewer exposed features.</span></span> <span data-ttu-id="02d47-194">Der wichtigste Unterschied besteht darin, dass die `securityMode`-Einstellung nur die Optionen `None` und `Transport` anbietet.</span><span class="sxs-lookup"><span data-stu-id="02d47-194">The most notable difference is that the `securityMode` setting only offers the `None` and `Transport` options.</span></span> <span data-ttu-id="02d47-195">SOAP-Sicherheitsunterstützung ist keine eingeschlossene Option.</span><span class="sxs-lookup"><span data-stu-id="02d47-195">SOAP security support is not an included option.</span></span> <span data-ttu-id="02d47-196">Das Sicherheitsverhalten ist mit dem optionalen `securityMode`-Attribut konfigurierbar.</span><span class="sxs-lookup"><span data-stu-id="02d47-196">The security behavior is configurable using the optional `securityMode` attribute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02d47-197">Beispiel</span><span class="sxs-lookup"><span data-stu-id="02d47-197">Example</span></span>  
 <span data-ttu-id="02d47-198">Im folgenden Beispiel wird die netNamedPipeBinding-Bindung, die prozessübergreifende Kommunikation auf dem gleichen Computer bereitstellt, veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="02d47-198">The following example demonstrates the netNamedPipeBinding binding, which provides cross-process communication on the same machine.</span></span> <span data-ttu-id="02d47-199">Benannte Pipes funktionieren nicht computerübergreifend.</span><span class="sxs-lookup"><span data-stu-id="02d47-199">Named pipes do not work across machines.</span></span>  
  
 <span data-ttu-id="02d47-200">Die Bindung wird in den Konfigurationsdateien für den Client und Dienst angegeben.</span><span class="sxs-lookup"><span data-stu-id="02d47-200">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="02d47-201">Der Bindungstyp wird im `binding`-Attribut des `<endpoint>`-Elements angegeben.</span><span class="sxs-lookup"><span data-stu-id="02d47-201">The binding type is specified in the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="02d47-202">Wenn Sie die netNamedPipeBinding-Bindung konfigurieren und einige der Einstellungen ändern möchten, müssen Sie eine Bindungskonfiguration definieren.</span><span class="sxs-lookup"><span data-stu-id="02d47-202">If you want to configure the netNamedPipeBinding binding and change some of its settings, you must define a binding configuration.</span></span> <span data-ttu-id="02d47-203">Der Endpunkt muss auf die Bindungskonfiguration mithilfe des `bindingConfiguration`-Attributs mit einem Namen verweisen.</span><span class="sxs-lookup"><span data-stu-id="02d47-203">The endpoint must reference the binding configuration by name with a `bindingConfiguration` attribute.</span></span> <span data-ttu-id="02d47-204">In diesem Beispiel wird die Bindungskonfiguration „Binding1“ genannt.</span><span class="sxs-lookup"><span data-stu-id="02d47-204">In this example, the binding configuration is named Binding1.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="02d47-205">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02d47-205">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>
- <xref:System.ServiceModel.NetNamedPipeBinding>
- [<span data-ttu-id="02d47-206">\<Bindungs ></span><span class="sxs-lookup"><span data-stu-id="02d47-206">\<binding></span></span>](bindings.md)
- [<span data-ttu-id="02d47-207">Bindungen</span><span class="sxs-lookup"><span data-stu-id="02d47-207">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="02d47-208">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="02d47-208">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="02d47-209">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="02d47-209">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
