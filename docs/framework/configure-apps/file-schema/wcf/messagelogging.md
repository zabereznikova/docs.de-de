---
title: <messageLogging>
ms.date: 03/30/2017
ms.assetid: 1d06a7e6-9633-4a12-8c5d-123adbbc19c5
ms.openlocfilehash: f54028489ec5aa34ae38115d7a582b01b9da92f9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931416"
---
# <a name="messagelogging"></a><span data-ttu-id="911bc-101">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="911bc-101">\<messageLogging></span></span>
<span data-ttu-id="911bc-102">Dieses Element definiert die Einstellungen für die Nachrichtenprotokollierungsfunktionen von Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="911bc-102">This element defines the settings for the message-logging capabilities of Windows Communication Foundation (WCF).</span></span>  
  
 <span data-ttu-id="911bc-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="911bc-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="911bc-104">\<Diagnose ></span><span class="sxs-lookup"><span data-stu-id="911bc-104">\<diagnostic></span></span>  
<span data-ttu-id="911bc-105">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="911bc-105">\<messageLogging></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="911bc-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="911bc-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="911bc-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="911bc-107">Attributes and Elements</span></span>  
 <span data-ttu-id="911bc-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="911bc-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="911bc-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="911bc-109">Attributes</span></span>  
  
|<span data-ttu-id="911bc-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="911bc-110">Attribute</span></span>|<span data-ttu-id="911bc-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="911bc-111">Description</span></span>|  
|---------------|-----------------|  
|`logEntireMessage`|<span data-ttu-id="911bc-112">Ein boolescher Wert, der angibt, ob die ganze Nachricht (Nachrichtenheader und Text) protokolliert wird.</span><span class="sxs-lookup"><span data-stu-id="911bc-112">A Boolean value that specifies whether the entire message (message header and body) is logged.</span></span> <span data-ttu-id="911bc-113">Der Standard ist `false`, wobei nur der Nachrichtenheader protokolliert wird.</span><span class="sxs-lookup"><span data-stu-id="911bc-113">The default is `false`, which means that only the message header is logged.</span></span> <span data-ttu-id="911bc-114">Diese Einstellung beeinflusst alle Meldungsprotokollebenen (Dienst, Transport und fehlerhaft).</span><span class="sxs-lookup"><span data-stu-id="911bc-114">This setting affects all message logging levels (service, transport, and malformed).</span></span>|  
|`logMalformedMessages`|<span data-ttu-id="911bc-115">Ein boolescher Wert, der angibt, ob fehlerhafte Nachrichten protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="911bc-115">A Boolean value that specifies whether malformed messages are logged.</span></span> <span data-ttu-id="911bc-116">Fehlerhafte Nachrichten werden bei `maxMessagesToLog` nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="911bc-116">Malformed messages do not count toward the `maxMessagesToLog`.</span></span> <span data-ttu-id="911bc-117">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="911bc-117">The default is `false`.</span></span>|  
|`logMessagesAtServiceLevel`|<span data-ttu-id="911bc-118">Ein boolescher Wert, der angibt, ob Nachrichten auf Dienstebene (vor Verschlüsselung und transportbezogenen Transformationen) verfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="911bc-118">A Boolean value that specifies whether messages are traced at the service level (before encryption- and transport-related transforms).</span></span> <span data-ttu-id="911bc-119">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="911bc-119">The default is `false`.</span></span>|  
|`logMessagesAtTransportLevel`|<span data-ttu-id="911bc-120">Ein boolescher Wert, der angibt, ob Nachrichten auf der Transportebene verfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="911bc-120">A Boolean value that specifies whether messages are traced at the transport level.</span></span> <span data-ttu-id="911bc-121">Alle in der Konfigurationsdatei angegebenen Filter werden angewendet, und nur Nachrichten, die den Filtern entsprechen, werden verfolgt.</span><span class="sxs-lookup"><span data-stu-id="911bc-121">Any filters specified in the config file are applied, and only messages that match the filters are traced.</span></span> <span data-ttu-id="911bc-122">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="911bc-122">The default is `false`.</span></span>|  
|`maxMessagesToLog`|<span data-ttu-id="911bc-123">Eine positive ganze Zahl, die die maximale Anzahl an zu protokollierenden Nachrichten angibt.</span><span class="sxs-lookup"><span data-stu-id="911bc-123">A positive integer that specifies the maximum number of messages to log.</span></span> <span data-ttu-id="911bc-124">Der Standard ist 1000.</span><span class="sxs-lookup"><span data-stu-id="911bc-124">The default is 1000.</span></span>|  
|`maxSizeOfMessageToLog`|<span data-ttu-id="911bc-125">Eine positive ganze Zahl, die die maximale Größe einer zu protokollierenden Nachrichten in Bytes angibt.</span><span class="sxs-lookup"><span data-stu-id="911bc-125">A positive integer that specifies the maximum size, in bytes, of a message to log.</span></span> <span data-ttu-id="911bc-126">Nachrichten oberhalb dieses Grenzwerts werden nicht protokolliert.</span><span class="sxs-lookup"><span data-stu-id="911bc-126">Messages larger than the limit will not be logged.</span></span> <span data-ttu-id="911bc-127">Diese Einstellung wirkt sich auf alle Nachverfolgungsebenen aus.</span><span class="sxs-lookup"><span data-stu-id="911bc-127">This setting affects all trace levels.</span></span> <span data-ttu-id="911bc-128">Die Standardeinstellung ist 262144(0x4000).</span><span class="sxs-lookup"><span data-stu-id="911bc-128">The default is 262144(0x4000).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="911bc-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="911bc-129">Child Elements</span></span>  
  
|<span data-ttu-id="911bc-130">Element</span><span class="sxs-lookup"><span data-stu-id="911bc-130">Element</span></span>|<span data-ttu-id="911bc-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="911bc-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="911bc-132">Filter</span><span class="sxs-lookup"><span data-stu-id="911bc-132">filters</span></span>|<span data-ttu-id="911bc-133">Das `filters`-Element enthält eine Auflistung von XPath-Filtern.</span><span class="sxs-lookup"><span data-stu-id="911bc-133">The `filters` element holds a collection of XPath filters.</span></span> <span data-ttu-id="911bc-134">Wenn die Transportnachrichtenprotokollierung aktiviert ist (`logMessagesAtTransportLevel` ist `true`), werden nur Nachrichten protokolliert, die den Filtern entsprechen.</span><span class="sxs-lookup"><span data-stu-id="911bc-134">When transport message logging is enabled (`logMessagesAtTransportLevel` is `true`), only messages matching the filters will be logged.</span></span><br /><br /> <span data-ttu-id="911bc-135">Filter werden nur auf Transportebene angewendet.</span><span class="sxs-lookup"><span data-stu-id="911bc-135">Filters are applied only at the transport layer.</span></span> <span data-ttu-id="911bc-136">Die Protokollierung von fehlerhaften Nachrichten und die Protokollierung von Nachrichten auf Dienstebene wird nicht von Filtern beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="911bc-136">Service level and malformed message logging are not affected by filters.</span></span><br /><br /> <span data-ttu-id="911bc-137">Das einzige Attribut für dieses Element (`filter`) ist ein XPath-Filter.</span><span class="sxs-lookup"><span data-stu-id="911bc-137">The only attribute for this element, `filter`, is an XpathFilter.</span></span><br /><br /> `<filters>     <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">/soap:Envelope</add> </filters>`|  
  
### <a name="parent-elements"></a><span data-ttu-id="911bc-138">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="911bc-138">Parent Elements</span></span>  
  
|<span data-ttu-id="911bc-139">Element</span><span class="sxs-lookup"><span data-stu-id="911bc-139">Element</span></span>|<span data-ttu-id="911bc-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="911bc-140">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="911bc-141">Diagnose</span><span class="sxs-lookup"><span data-stu-id="911bc-141">diagnostics</span></span>|<span data-ttu-id="911bc-142">Definiert WCF-Einstellungen für die Laufzeitüberprüfung und Steuerungen für den Administrator.</span><span class="sxs-lookup"><span data-stu-id="911bc-142">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="911bc-143">Hinweise</span><span class="sxs-lookup"><span data-stu-id="911bc-143">Remarks</span></span>  
 <span data-ttu-id="911bc-144">Nachrichten werden auf drei verschiedenen Ebenen im Stapel protokolliert: Dienst, Transport und fehlerhaft.</span><span class="sxs-lookup"><span data-stu-id="911bc-144">Messages are logged at three different levels in the stack: service, transport, and malformed.</span></span> <span data-ttu-id="911bc-145">Jede Ebene kann separat aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="911bc-145">Each level can be activated separately.</span></span>  
  
 <span data-ttu-id="911bc-146">XPath-Filter können hinzugefügt werden, um bestimmte Nachrichten auf Transport- und Dienstebene zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="911bc-146">XPath filters can be added to log specific messages at the transport and service levels.</span></span> <span data-ttu-id="911bc-147">Wenn keine Filter definiert werden, werden alle Meldungen protokolliert.</span><span class="sxs-lookup"><span data-stu-id="911bc-147">If no filters are defined, all messages are logged.</span></span> <span data-ttu-id="911bc-148">Filter werden nur auf die Header der Nachricht angewendet.</span><span class="sxs-lookup"><span data-stu-id="911bc-148">Filters are applied only to the headers of the message.</span></span> <span data-ttu-id="911bc-149">Der Nachrichtentext wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="911bc-149">The body is ignored.</span></span> <span data-ttu-id="911bc-150">WCF ignoriert den Nachrichtentext, um die Leistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="911bc-150">WCF ignores the message body to improve performance.</span></span> <span data-ttu-id="911bc-151">Wenn Sie basierend auf dem Textinhalt filtern möchten, können Sie zu diesem Zweck einen benutzerdefinierten Listener mit einem Filter erstellen.</span><span class="sxs-lookup"><span data-stu-id="911bc-151">If you want to filter based on the content of the body, you can create a custom listener with a filter that does so.</span></span>  
  
 <span data-ttu-id="911bc-152">Sie müssen einen Ablaufverfolgungslistener erstellen, um die Nachrichtenablaufverfolgung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="911bc-152">You need to create a trace listener to activate message tracing.</span></span> <span data-ttu-id="911bc-153">Der Listener selbst kann jeder Listener sein, der mit der <xref:System.Diagnostics>-Ablaufverfolgungsarchitektur verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="911bc-153">The listener itself can be any listener that works with the <xref:System.Diagnostics> tracing architecture.</span></span> <span data-ttu-id="911bc-154">Im folgenden Beispiel wird das Erstellen eines solchen Listeners veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="911bc-154">The following example demonstrates how to create such a listener.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="911bc-155">Beispiel</span><span class="sxs-lookup"><span data-stu-id="911bc-155">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="911bc-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="911bc-156">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- [<span data-ttu-id="911bc-157">Konfigurieren der Nachrichtenprotokollierung</span><span class="sxs-lookup"><span data-stu-id="911bc-157">Configuring Message Logging</span></span>](../../../wcf/diagnostics/configuring-message-logging.md)
