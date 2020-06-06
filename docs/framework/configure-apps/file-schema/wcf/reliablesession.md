---
title: <reliableSession>
ms.date: 03/30/2017
ms.assetid: 129b4a59-37f0-4030-b664-03795d257d29
ms.openlocfilehash: 95f6646041dc2dd7bae7691a0a9f748c844f50b6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738749"
---
# \<reliableSession>
<span data-ttu-id="3242b-101">Definiert die Einstellung für WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="3242b-101">Defines setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="3242b-102">Wenn dieses Element einer benutzerdefinierten Bindung hinzugefügt wird, kann der resultierende Kanal ExactlyOnce-Zustellungszusicherungen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="3242b-102">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<reliableSession>**  
  
## <a name="syntax"></a><span data-ttu-id="3242b-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="3242b-103">Syntax</span></span>  
  
```xml  
<reliableSession acknowledgementInterval="TimeSpan"
                 flowControlEnabled="Boolean"
                 inactivityTimeout="TimeSpan"
                 maxPendingChannels="Integer"
                 maxRetryCount="Integer"
                 maxTransferWindowSize="Integer"
                 reliableMessagingVersion="Default/WSReliableMessagingFebruary2005/WSReliableMessaging11"
                 ordered="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3242b-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3242b-104">Attributes and Elements</span></span>  
 <span data-ttu-id="3242b-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3242b-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3242b-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="3242b-106">Attributes</span></span>  
  
|<span data-ttu-id="3242b-107">attribute</span><span class="sxs-lookup"><span data-stu-id="3242b-107">Attribute</span></span>|<span data-ttu-id="3242b-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3242b-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3242b-109">acknowledgementInterval</span><span class="sxs-lookup"><span data-stu-id="3242b-109">acknowledgementInterval</span></span>|<span data-ttu-id="3242b-110">Eine <xref:System.TimeSpan>, die angibt, wie lange der Kanal maximal wartet, bis eine Bestätigung für die bis zu diesem Zeitpunkt erhaltenen Nachrichten gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="3242b-110">A <xref:System.TimeSpan> that contains the maximum time interval the channel is going to wait to send an acknowledgment for messages received up to that point.</span></span> <span data-ttu-id="3242b-111">Der Standardwert ist 00:00:0.2.</span><span class="sxs-lookup"><span data-stu-id="3242b-111">The default is 00:00:0.2.</span></span>|  
|<span data-ttu-id="3242b-112">flowControlEnabled</span><span class="sxs-lookup"><span data-stu-id="3242b-112">flowControlEnabled</span></span>|<span data-ttu-id="3242b-113">Eine boolescher Wert, der angibt, ob die erweiterte Flusssteuerung, eine Microsoft-spezifische Implementierung der Flusssteuerung für WS-Reliable Messaging, aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="3242b-113">A Boolean value that indicates whether advanced flow control, a Microsoft-specific implementation of flow control for WS-Reliable messaging, is activated.</span></span> <span data-ttu-id="3242b-114">Der Standardwert lautet `true`.</span><span class="sxs-lookup"><span data-stu-id="3242b-114">The default is `true`.</span></span>|  
|<span data-ttu-id="3242b-115">inactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="3242b-115">inactivityTimeout</span></span>|<span data-ttu-id="3242b-116">Eine <xref:System.TimeSpan>, die die maximale Dauer angibt, die der Kanal dem anderen Kommunikationsteilnehmer für das ausbleibende Senden von Nachrichten einräumt, bevor im Kanal ein Fehler ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="3242b-116">A <xref:System.TimeSpan> that specifies the maximum duration that the channel is going to allow the other communication party not to send any messages, before faulting the channel.</span></span> <span data-ttu-id="3242b-117">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="3242b-117">The default is 00:10:00.</span></span><br /><br /> <span data-ttu-id="3242b-118">Aktivität auf einem Kanal wird als Empfang einer Anwendungs- oder Infrastrukturnachricht definiert.</span><span class="sxs-lookup"><span data-stu-id="3242b-118">Activity on a channel is defined as receiving an application or infrastructure messages.</span></span> <span data-ttu-id="3242b-119">Diese Eigenschaft steuert die maximale Menge an Zeit, um eine inaktive Sitzung am Leben zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3242b-119">This property controls the maximum amount of time to keep an inactive session alive.</span></span> <span data-ttu-id="3242b-120">Bei längeren Zeiten ohne Aktivität wird die Sitzung durch die Infrastruktur beendet, und im Kanal wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="3242b-120">If longer time passes with no activity, the session is aborted by the infrastructure and the channel faults.</span></span> <span data-ttu-id="3242b-121">**Hinweis:**  Es ist nicht erforderlich, dass die Anwendung regelmäßig Nachrichten sendet, um die Verbindung aufrechtzuerhalten.</span><span class="sxs-lookup"><span data-stu-id="3242b-121">**Note:**  It is not necessary for the application to periodically send messages to keep the connection alive.</span></span>|  
|<span data-ttu-id="3242b-122">maxPendingChannels</span><span class="sxs-lookup"><span data-stu-id="3242b-122">maxPendingChannels</span></span>|<span data-ttu-id="3242b-123">Eine ganze Zahl, die die maximale Anzahl an Kanälen angibt, die im Listener warten können, um akzeptiert zu werden.</span><span class="sxs-lookup"><span data-stu-id="3242b-123">An integer that specifies the maximum number of channels that can wait on the listener to be accepted.</span></span> <span data-ttu-id="3242b-124">Dieser Wert sollte zwischen 1 und einschließlich 16384 liegen.</span><span class="sxs-lookup"><span data-stu-id="3242b-124">This value should be between 1 to 16384 inclusive.</span></span> <span data-ttu-id="3242b-125">Der Standardwert ist 4.</span><span class="sxs-lookup"><span data-stu-id="3242b-125">The default is 4.</span></span><br /><br /> <span data-ttu-id="3242b-126">Kanäle sind ausstehend, wenn sie darauf warten, akzeptiert zu werden.</span><span class="sxs-lookup"><span data-stu-id="3242b-126">Channels are pending when they are waiting to be accepted.</span></span> <span data-ttu-id="3242b-127">Wenn dieser Grenzwert einmal erreicht ist, werden keine Kanäle erstellt.</span><span class="sxs-lookup"><span data-stu-id="3242b-127">Once that limit is reached, no channels are created.</span></span> <span data-ttu-id="3242b-128">Sie werden dagegen in den ausstehenden Modus versetzt, bis diese Zahl sinkt (durch das Akzeptieren ausstehender Kanäle).</span><span class="sxs-lookup"><span data-stu-id="3242b-128">Rather, they are put in pending mode until this number goes down (by accepting pending channels).</span></span> <span data-ttu-id="3242b-129">Dieser Grenzwert wird pro Factory festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3242b-129">This is a per-factory limit.</span></span><br /><br /> <span data-ttu-id="3242b-130">Wenn der Schwellenwert erreicht wird und eine Remoteanwendung versucht, eine neue zuverlässige Sitzung herzustellen, wird die Anforderung abgelehnt und der Öffnungsvorgang, der dies angefordert hat, schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="3242b-130">When the threshold is reached and a remote application tries to establish a new reliable session, the request is denied and the open operation that prompted this faults.</span></span> <span data-ttu-id="3242b-131">Dieser Grenzwert gilt nicht für die Anzahl an ausstehenden ausgehenden Kanälen.</span><span class="sxs-lookup"><span data-stu-id="3242b-131">This limit does not apply to the number of pending outgoing channels.</span></span>|  
|<span data-ttu-id="3242b-132">maxRetryCount</span><span class="sxs-lookup"><span data-stu-id="3242b-132">maxRetryCount</span></span>|<span data-ttu-id="3242b-133">Eine ganze Zahl, die angibt, wie oft ein zuverlässiger Kanal maximal versucht, eine Nachricht, für die keine Bestätigung empfangen wurde, erneut zu übertragen (durch Aufrufen von Send im zugrunde liegenden Kanal).</span><span class="sxs-lookup"><span data-stu-id="3242b-133">An integer that specifies the maximum number of times a reliable channel attempts to retransmit a message it has not received an acknowledgment for, by calling Send on its underlying channel.</span></span><br /><br /> <span data-ttu-id="3242b-134">Dieser Wert muss größer als null sein.</span><span class="sxs-lookup"><span data-stu-id="3242b-134">This value should be greater than zero.</span></span> <span data-ttu-id="3242b-135">Der Standard ist 8.</span><span class="sxs-lookup"><span data-stu-id="3242b-135">The default is 8.</span></span><br /><br /> <span data-ttu-id="3242b-136">Dieser Wert sollte eine ganze Zahl größer null sein.</span><span class="sxs-lookup"><span data-stu-id="3242b-136">This value should be an integer greater than zero.</span></span> <span data-ttu-id="3242b-137">Wenn nach der letzten Übertragung keine Bestätigung empfangen wurde, tritt ein Fehler im Kanal auf.</span><span class="sxs-lookup"><span data-stu-id="3242b-137">If an acknowledgment is not received after the last retransmission, the channel faults.</span></span><br /><br /> <span data-ttu-id="3242b-138">Eine Nachricht wird als übertragen betrachtet, wenn die Zustellung vom Empfänger bestätigt wurde.</span><span class="sxs-lookup"><span data-stu-id="3242b-138">A message is considered to be transferred if its delivery at the recipient has been acknowledged by the recipient.</span></span><br /><br /> <span data-ttu-id="3242b-139">Wenn die Bestätigung nicht innerhalb einer bestimmten Zeit eingegangen ist, überträgt die Infrastruktur die Nachricht automatisch neu.</span><span class="sxs-lookup"><span data-stu-id="3242b-139">If an acknowledgment has not been received within a certain amount of time for a message that has been transmitted, the infrastructure automatically retransmits the message.</span></span> <span data-ttu-id="3242b-140">Die Infrastruktur versucht die Nachricht maximal so oft erneut zu senden, wie durch diese Eigenschaft festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3242b-140">The infrastructure tries to resend the message for at most the number of times specified by this property.</span></span> <span data-ttu-id="3242b-141">Wenn nach der letzten Übertragung keine Bestätigung empfangen wurde, tritt ein Fehler im Kanal auf.</span><span class="sxs-lookup"><span data-stu-id="3242b-141">If an acknowledgment is not received after the last retransmission, the channel faults.</span></span><br /><br /> <span data-ttu-id="3242b-142">Die Infrastruktur verwendet einen exponentiellen Backoff-Algorithmus um den Zeitpunkt für die Neuübertragung zu ermitteln. Dabei wird eine berechnete durchschnittliche Round Trip Time zugrunde gelegt.</span><span class="sxs-lookup"><span data-stu-id="3242b-142">The infrastructure uses an exponential back-off algorithm to determine when to retransmit, based on a computed average round-trip time.</span></span> <span data-ttu-id="3242b-143">Der Zeitpunkt liegt zunächst 1 Sekunde vor der Neuübertragung. Bei jedem erneuten Versuch wird die Verzögerung verdoppelt. Zwischen dem ersten Übertragungsversuch und dem letzten Übertragungsversuch liegen somit ca. 8,5 Minuten.</span><span class="sxs-lookup"><span data-stu-id="3242b-143">The time initially starts at 1 second before retransmission and doubling the delay with every attempt, which results in approximately 8.5 minutes passing between the first transmission attempt and the last retransmission attempt.</span></span> <span data-ttu-id="3242b-144">Der Zeitpunkt für den ersten Neuübertragungsversuch wird gemäß der berechneten Round Trip Time angepasst, und die daraus resultierende Zeitspanne für die Übertragungsversuche variiert entsprechend.</span><span class="sxs-lookup"><span data-stu-id="3242b-144">The time for the first retransmission attempt is adjusted according to the calculated round-trip time and the resulting stretch of time that those attempts take varies accordingly.</span></span> <span data-ttu-id="3242b-145">Dadurch können die Zeitpunkte für die Neuübertragung dynamisch an die unterschiedlichen Netzwerkbedingungen angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="3242b-145">This allows the retransmission time to dynamically adapt to varying network conditions.</span></span>|  
|<span data-ttu-id="3242b-146">maxTransferWindowSize</span><span class="sxs-lookup"><span data-stu-id="3242b-146">maxTransferWindowSize</span></span>|<span data-ttu-id="3242b-147">Eine ganze Zahl, die die maximale Größe des Puffers angibt.</span><span class="sxs-lookup"><span data-stu-id="3242b-147">An integer that specifies the maximum size of the buffer.</span></span> <span data-ttu-id="3242b-148">Gültige Werte reichen von 1 bis 4096 einschließlich.</span><span class="sxs-lookup"><span data-stu-id="3242b-148">Valid values are from 1 to 4096 inclusive.</span></span><br /><br /> <span data-ttu-id="3242b-149">Auf dem Client definiert dieses Attribut die maximale Größe des Puffers, in dem ein zuverlässiger Kanal die noch nicht vom Empfänger bestätigten Nachrichten speichert.</span><span class="sxs-lookup"><span data-stu-id="3242b-149">On the client, this attribute defines the maximum size of the buffer used by a reliable channel to hold messages not yet acknowledged by the receiver.</span></span> <span data-ttu-id="3242b-150">Die Einheit dieses Kontingents ist eine Nachricht.</span><span class="sxs-lookup"><span data-stu-id="3242b-150">The unit of the quota is a message.</span></span> <span data-ttu-id="3242b-151">Ist der Puffer voll, werden weitere SEND-Vorgänge blockiert.</span><span class="sxs-lookup"><span data-stu-id="3242b-151">If the buffer is full, further SEND operations are blocked.</span></span><br /><br /> <span data-ttu-id="3242b-152">Beim Empfänger definiert dieses Attribut die maximale Größe des Puffers, in dem ein Kanal eingehende Nachrichten speichert, die noch nicht an die Anwendung zugestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="3242b-152">On the receiver, this attribute defines the maximum size of the buffer used by the channel to store incoming messages not yet dispatched to the application.</span></span> <span data-ttu-id="3242b-153">Ist der Puffer voll, werden weitere Nachrichten vom Empfänger automatisch verworfen und müssen vom Client erneut übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="3242b-153">If the buffer is full, further messages are silently dropped by the receiver and require retransmission by the client.</span></span>|  
|<span data-ttu-id="3242b-154">geordnete</span><span class="sxs-lookup"><span data-stu-id="3242b-154">ordered</span></span>|<span data-ttu-id="3242b-155">Ein boolescher Wert, der angibt, ob Nachrichten auf jeden Fall in der Reihenfolge ihres Versands eintreffen.</span><span class="sxs-lookup"><span data-stu-id="3242b-155">A Boolean that specifies whether messages are guaranteed to arrive in the order they were sent.</span></span> <span data-ttu-id="3242b-156">Lautet diese Einstellung `false`, können Nachrichten außerhalb der Reihenfolge eintreffen.</span><span class="sxs-lookup"><span data-stu-id="3242b-156">If this setting is `false`, messages can arrive out of order.</span></span> <span data-ttu-id="3242b-157">Der Standardwert lautet `true`.</span><span class="sxs-lookup"><span data-stu-id="3242b-157">The default is `true`.</span></span>|  
|<span data-ttu-id="3242b-158">reliableMessagingVersion</span><span class="sxs-lookup"><span data-stu-id="3242b-158">reliableMessagingVersion</span></span>|<span data-ttu-id="3242b-159">Ein gültiger Wert von <xref:System.ServiceModel.ReliableMessagingVersion>, der die zu verwendende WS-ReliableMessaging-Version angibt.</span><span class="sxs-lookup"><span data-stu-id="3242b-159">A valid value from <xref:System.ServiceModel.ReliableMessagingVersion> that specifies the WS-ReliableMessaging version to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3242b-160">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3242b-160">Child Elements</span></span>  
 <span data-ttu-id="3242b-161">Keine</span><span class="sxs-lookup"><span data-stu-id="3242b-161">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3242b-162">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3242b-162">Parent Elements</span></span>  
  
|<span data-ttu-id="3242b-163">Element</span><span class="sxs-lookup"><span data-stu-id="3242b-163">Element</span></span>|<span data-ttu-id="3242b-164">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3242b-164">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="3242b-165">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="3242b-165">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3242b-166">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3242b-166">Remarks</span></span>  
 <span data-ttu-id="3242b-167">Zuverlässige Sitzungen bieten Funktionen für zuverlässiges Messaging.</span><span class="sxs-lookup"><span data-stu-id="3242b-167">Reliable sessions provide features for reliable messaging and sessions.</span></span> <span data-ttu-id="3242b-168">Beim zuverlässigen Messaging wird die Kommunikation bei Fehlern erneut gestartet, und es werden Zustellungszusicherungen, wie Prüfung der Nachrichtenreihenfolge beim Eingang, vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="3242b-168">Reliable messaging retries communication on failure and allows delivery assurances such as in-order arrival of messages to be specified.</span></span> <span data-ttu-id="3242b-169">Die Sitzungen erhalten den Status von Clients im Verlauf der verschiedenen Aufrufe aufrecht.</span><span class="sxs-lookup"><span data-stu-id="3242b-169">Sessions maintain state for clients between calls.</span></span> <span data-ttu-id="3242b-170">Dieses Element stellt auch optional sortierte Nachrichtenübermittlung bereit.</span><span class="sxs-lookup"><span data-stu-id="3242b-170">This element also optionally provides ordered message delivery.</span></span> <span data-ttu-id="3242b-171">Diese implementierte Sitzung kann SOAP und Transportvermittler überqueren.</span><span class="sxs-lookup"><span data-stu-id="3242b-171">This implemented session can cross SOAP and transport intermediaries.</span></span>  
  
 <span data-ttu-id="3242b-172">Jedes Bindungselement stellt einen Verarbeitungsschritt beim Senden und Empfangen von Nachrichten dar.</span><span class="sxs-lookup"><span data-stu-id="3242b-172">Each binding element represents a processing step when sending or receiving messages.</span></span> <span data-ttu-id="3242b-173">Zur Laufzeit erstellen Bindungselemente die Kanalfactorys und die Listener, die notwendig sind, um ausgehende und eingehende Kanalstapel zum Senden und Empfangen von Nachrichten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3242b-173">At runtime, binding elements create the channel factories and listeners that are necessary to build outgoing and incoming channel stacks required to send and receive messages.</span></span> <span data-ttu-id="3242b-174">Das `reliableSession` bietet eine optionale Ebene im Stapel, die eine zuverlässige Sitzung zwischen Endpunkten herstellen und das Sitzungsverhalten konfigurieren kann.</span><span class="sxs-lookup"><span data-stu-id="3242b-174">The `reliableSession` provides an optional layer in the stack that can establish a reliable session between endpoints and configure the behavior of this session.</span></span>  
  
 <span data-ttu-id="3242b-175">Weitere Informationen finden Sie unter [zuverlässige Sitzungen](../../../wcf/feature-details/reliable-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="3242b-175">For more information, see [Reliable Sessions](../../../wcf/feature-details/reliable-sessions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3242b-176">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3242b-176">Example</span></span>  
 <span data-ttu-id="3242b-177">Im folgenden Beispiel wird gezeigt, wie eine benutzerdefinierte Bindung mit verschiedenen Transport- und Codierungselementen konfiguriert wird, insbesondere durch zuverlässige Sitzungen, die den Clientstatus aufrechterhalten und Zustellungszusicherungen anhand der Nachrichtenreihenfolge vorgeben.</span><span class="sxs-lookup"><span data-stu-id="3242b-177">The following example demonstrates how to configure a custom binding with various transport and message encoding elements, especially enabling reliable sessions, which maintains client state and specifies in-order delivery assurances.</span></span> <span data-ttu-id="3242b-178">Diese Funktion wird in den Anwendungskonfigurationsdateien für den Client und den Dienst konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="3242b-178">This feature is configured in the application configuration files for the client and service.</span></span> <span data-ttu-id="3242b-179">Im Beispiel wird die Dienstkonfiguration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3242b-179">The example show the service configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <!-- This endpoint is exposed at the base address provided by host: http://localhost/servicemodelsamples/service.svc -->
        <!-- specify customBinding binding and a binding configuration to use -->
        <endpoint address=""
                  binding="customBinding"
                  bindingConfiguration="Binding1"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <!-- custom binding configuration - configures HTTP transport, reliable sessions -->
    <bindings>
      <customBinding>
        <binding name="Binding1">
          <reliableSession />
          <security authenticationMode="SecureConversation"
                    requireSecurityContextCancellation="true">
          </security>
          <compositeDuplex />
          <oneWay />
          <textMessageEncoding messageVersion="Soap12WSAddressing10"
                               writeEncoding="utf-8" />
          <httpTransport authenticationScheme="Anonymous"
                         bypassProxyOnLocal="false"
                         hostNameComparisonMode="StrongWildcard"
                         proxyAuthenticationScheme="Anonymous"
                         realm=""
                         useDefaultWebProxy="true" />
        </binding>
      </customBinding>
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
  
## <a name="see-also"></a><span data-ttu-id="3242b-180">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3242b-180">See also</span></span>

- <xref:System.ServiceModel.Configuration.ReliableSessionElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>
- [<span data-ttu-id="3242b-181">Zuverlässige Sitzungen</span><span class="sxs-lookup"><span data-stu-id="3242b-181">Reliable Sessions</span></span>](../../../wcf/feature-details/reliable-sessions.md)
- [<span data-ttu-id="3242b-182">Bindungen</span><span class="sxs-lookup"><span data-stu-id="3242b-182">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3242b-183">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="3242b-183">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="3242b-184">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="3242b-184">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
