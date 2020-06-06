---
title: <messageLogging>
ms.date: 03/30/2017
ms.assetid: 1d06a7e6-9633-4a12-8c5d-123adbbc19c5
ms.openlocfilehash: 9291c38af28c18d20e23e34e8316b4a9fe523123
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855122"
---
# \<messageLogging>
<span data-ttu-id="b6bb8-101">Dieses Element definiert die Einstellungen für die Nachrichtenprotokollierungsfunktionen von Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="b6bb8-101">This element defines the settings for the message-logging capabilities of Windows Communication Foundation (WCF).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageLogging>**  
  
## <a name="syntax"></a><span data-ttu-id="b6bb8-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6bb8-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <messageLogging logEntireMessage="Boolean"
                    logMalformedMessages="Boolean"
                    logMessagesAtServiceLevel="Boolean"
                    logMessagesAtTransportLevel="Boolean"
                    maxMessagesToLog="Integer"
                    maxSizeOfMessageToLog="Integer">
      <filters>
        <clear />
      </filters>
    </messageLogging>
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6bb8-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b6bb8-103">Attributes and Elements</span></span>  
 <span data-ttu-id="b6bb8-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6bb8-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="b6bb8-105">Attributes</span></span>  
  
|<span data-ttu-id="b6bb8-106">attribute</span><span class="sxs-lookup"><span data-stu-id="b6bb8-106">Attribute</span></span>|<span data-ttu-id="b6bb8-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b6bb8-107">Description</span></span>|  
|---------------|-----------------|  
|`logEntireMessage`|<span data-ttu-id="b6bb8-108">Ein boolescher Wert, der angibt, ob die ganze Nachricht (Nachrichtenheader und Text) protokolliert wird.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-108">A Boolean value that specifies whether the entire message (message header and body) is logged.</span></span> <span data-ttu-id="b6bb8-109">Der Standard ist `false`, wobei nur der Nachrichtenheader protokolliert wird.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-109">The default is `false`, which means that only the message header is logged.</span></span> <span data-ttu-id="b6bb8-110">Diese Einstellung beeinflusst alle Meldungsprotokollebenen (Dienst, Transport und fehlerhaft).</span><span class="sxs-lookup"><span data-stu-id="b6bb8-110">This setting affects all message logging levels (service, transport, and malformed).</span></span>|  
|`logMalformedMessages`|<span data-ttu-id="b6bb8-111">Ein boolescher Wert, der angibt, ob fehlerhafte Nachrichten protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-111">A Boolean value that specifies whether malformed messages are logged.</span></span> <span data-ttu-id="b6bb8-112">Fehlerhafte Nachrichten werden bei `maxMessagesToLog` nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-112">Malformed messages do not count toward the `maxMessagesToLog`.</span></span> <span data-ttu-id="b6bb8-113">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-113">The default is `false`.</span></span>|  
|`logMessagesAtServiceLevel`|<span data-ttu-id="b6bb8-114">Ein boolescher Wert, der angibt, ob Nachrichten auf Dienstebene (vor Verschlüsselung und transportbezogenen Transformationen) verfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-114">A Boolean value that specifies whether messages are traced at the service level (before encryption- and transport-related transforms).</span></span> <span data-ttu-id="b6bb8-115">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-115">The default is `false`.</span></span>|  
|`logMessagesAtTransportLevel`|<span data-ttu-id="b6bb8-116">Ein boolescher Wert, der angibt, ob Nachrichten auf der Transportebene verfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-116">A Boolean value that specifies whether messages are traced at the transport level.</span></span> <span data-ttu-id="b6bb8-117">Alle in der Konfigurationsdatei angegebenen Filter werden angewendet, und nur Nachrichten, die den Filtern entsprechen, werden verfolgt.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-117">Any filters specified in the config file are applied, and only messages that match the filters are traced.</span></span> <span data-ttu-id="b6bb8-118">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-118">The default is `false`.</span></span>|  
|`maxMessagesToLog`|<span data-ttu-id="b6bb8-119">Eine positive ganze Zahl, die die maximale Anzahl an zu protokollierenden Nachrichten angibt.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-119">A positive integer that specifies the maximum number of messages to log.</span></span> <span data-ttu-id="b6bb8-120">Der Standardwert lautet 1000.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-120">The default is 1000.</span></span>|  
|`maxSizeOfMessageToLog`|<span data-ttu-id="b6bb8-121">Eine positive ganze Zahl, die die maximale Größe einer zu protokollierenden Nachrichten in Bytes angibt.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-121">A positive integer that specifies the maximum size, in bytes, of a message to log.</span></span> <span data-ttu-id="b6bb8-122">Nachrichten oberhalb dieses Grenzwerts werden nicht protokolliert.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-122">Messages larger than the limit will not be logged.</span></span> <span data-ttu-id="b6bb8-123">Diese Einstellung wirkt sich auf alle Nachverfolgungsebenen aus.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-123">This setting affects all trace levels.</span></span> <span data-ttu-id="b6bb8-124">Die Standardeinstellung ist 262144(0x4000).</span><span class="sxs-lookup"><span data-stu-id="b6bb8-124">The default is 262144(0x4000).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6bb8-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b6bb8-125">Child Elements</span></span>  
  
|<span data-ttu-id="b6bb8-126">Element</span><span class="sxs-lookup"><span data-stu-id="b6bb8-126">Element</span></span>|<span data-ttu-id="b6bb8-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6bb8-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b6bb8-128">Filter</span><span class="sxs-lookup"><span data-stu-id="b6bb8-128">filters</span></span>|<span data-ttu-id="b6bb8-129">Das `filters`-Element enthält eine Auflistung von XPath-Filtern.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-129">The `filters` element holds a collection of XPath filters.</span></span> <span data-ttu-id="b6bb8-130">Wenn die Transportnachrichtenprotokollierung aktiviert ist (`logMessagesAtTransportLevel` ist `true`), werden nur Nachrichten protokolliert, die den Filtern entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-130">When transport message logging is enabled (`logMessagesAtTransportLevel` is `true`), only messages matching the filters will be logged.</span></span><br /><br /> <span data-ttu-id="b6bb8-131">Filter werden nur auf Transportebene angewendet.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-131">Filters are applied only at the transport layer.</span></span> <span data-ttu-id="b6bb8-132">Die Protokollierung von fehlerhaften Nachrichten und die Protokollierung von Nachrichten auf Dienstebene wird nicht von Filtern beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-132">Service level and malformed message logging are not affected by filters.</span></span><br /><br /> <span data-ttu-id="b6bb8-133">Das einzige Attribut für dieses Element (`filter`) ist ein XPath-Filter.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-133">The only attribute for this element, `filter`, is an XpathFilter.</span></span><br /><br /> `<filters>     <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">/soap:Envelope</add> </filters>`|  
  
### <a name="parent-elements"></a><span data-ttu-id="b6bb8-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b6bb8-134">Parent Elements</span></span>  
  
|<span data-ttu-id="b6bb8-135">Element</span><span class="sxs-lookup"><span data-stu-id="b6bb8-135">Element</span></span>|<span data-ttu-id="b6bb8-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6bb8-136">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b6bb8-137">Diagnose</span><span class="sxs-lookup"><span data-stu-id="b6bb8-137">diagnostics</span></span>|<span data-ttu-id="b6bb8-138">Definiert WCF-Einstellungen für die Laufzeitüberprüfung und Steuerungen für den Administrator.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-138">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6bb8-139">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b6bb8-139">Remarks</span></span>  
 <span data-ttu-id="b6bb8-140">Nachrichten werden auf drei verschiedenen Ebenen im Stapel protokolliert: Dienst, Transport und fehlerhaft.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-140">Messages are logged at three different levels in the stack: service, transport, and malformed.</span></span> <span data-ttu-id="b6bb8-141">Jede Ebene kann separat aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-141">Each level can be activated separately.</span></span>  
  
 <span data-ttu-id="b6bb8-142">XPath-Filter können hinzugefügt werden, um bestimmte Nachrichten auf Transport- und Dienstebene zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-142">XPath filters can be added to log specific messages at the transport and service levels.</span></span> <span data-ttu-id="b6bb8-143">Wenn keine Filter definiert werden, werden alle Meldungen protokolliert.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-143">If no filters are defined, all messages are logged.</span></span> <span data-ttu-id="b6bb8-144">Filter werden nur auf die Header der Nachricht angewendet.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-144">Filters are applied only to the headers of the message.</span></span> <span data-ttu-id="b6bb8-145">Der Nachrichtentext wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-145">The body is ignored.</span></span> <span data-ttu-id="b6bb8-146">WCF ignoriert den Nachrichtentext, um die Leistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-146">WCF ignores the message body to improve performance.</span></span> <span data-ttu-id="b6bb8-147">Wenn Sie basierend auf dem Textinhalt filtern möchten, können Sie zu diesem Zweck einen benutzerdefinierten Listener mit einem Filter erstellen.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-147">If you want to filter based on the content of the body, you can create a custom listener with a filter that does so.</span></span>  
  
 <span data-ttu-id="b6bb8-148">Sie müssen einen Ablaufverfolgungslistener erstellen, um die Nachrichtenablaufverfolgung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-148">You need to create a trace listener to activate message tracing.</span></span> <span data-ttu-id="b6bb8-149">Der Listener selbst kann jeder Listener sein, der mit der <xref:System.Diagnostics>-Ablaufverfolgungsarchitektur verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-149">The listener itself can be any listener that works with the <xref:System.Diagnostics> tracing architecture.</span></span> <span data-ttu-id="b6bb8-150">Im folgenden Beispiel wird das Erstellen eines solchen Listeners veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b6bb8-150">The following example demonstrates how to create such a listener.</span></span>  
  
```xml  
<system.diagnostics>
  <sources>
    <source name="System.ServiceModel"
            switchValue="Verbose">
      <listeners>
        <clear />
        <add type="System.Diagnostics.DefaultTraceListener"
             name="Default"
             traceOutputOptions="None" />
        <add name="ServiceModel Listener"
             traceOutputOptions="None" />
      </listeners>
    </source>
    <source name="System.ServiceModel.MessageLogging">
      <listeners>
        <clear />
        <add type="System.Diagnostics.DefaultTraceListener"
             name="Default"
             traceOutputOptions="None" />
        <add name="MessageLogging Listener"
             traceOutputOptions="None" />
      </listeners>
    </source>
  </sources>
  <sharedListeners>
    <add initializeData="C:\ItProTools\TraceLog.xml"
         type="System.Diagnostics.XmlWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
         name="ServiceModel Listener"
         traceOutputOptions="LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack" />
    <add initializeData="C:\ItProTools\MessageLog.log"
         type="System.Diagnostics.XmlWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
         name="MessageLogging Listener"
         traceOutputOptions="LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack" />
  </sharedListeners>
</system.diagnostics>
```  
  
## <a name="example"></a><span data-ttu-id="b6bb8-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b6bb8-151">Example</span></span>  
  
```xml  
<messageLogging logEntireMessage="true"
                logMalformedMessages="true"
                logMessagesAtServiceLevel="true"
                logMessagesAtTransportLevel="true"
                maxMessagesToLog="42"
                maxSizeOfMessageToLog="42">
  <filters>
    <clear />
  </filters>
</messageLogging>
```  
  
## <a name="see-also"></a><span data-ttu-id="b6bb8-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b6bb8-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- [<span data-ttu-id="b6bb8-153">Konfigurieren der Nachrichtenprotokollierung</span><span class="sxs-lookup"><span data-stu-id="b6bb8-153">Configuring Message Logging</span></span>](../../../wcf/diagnostics/configuring-message-logging.md)
