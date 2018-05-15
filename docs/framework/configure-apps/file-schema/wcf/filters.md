---
title: '&lt;Filter&gt;'
ms.date: 03/30/2017
ms.assetid: 37a87222-ec78-4728-8105-9ca1bd961f0c
ms.openlocfilehash: af0821d6477ed7f3525cd0fe8d46f3699c48acb0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltfiltersgt"></a><span data-ttu-id="9d078-102">&lt;Filter&gt;</span><span class="sxs-lookup"><span data-stu-id="9d078-102">&lt;filters&gt;</span></span>

<span data-ttu-id="9d078-103">Das `filters`-Element enthält eine Auflistung von XPath-Filtern, mit denen gesteuert wird, welcher Nachrichtentyp protokolliert wird.</span><span class="sxs-lookup"><span data-stu-id="9d078-103">The `filters` element holds a collection of XPath filters used to control what kind of message is logged.</span></span>

<span data-ttu-id="9d078-104">Filter werden nur auf Transportebene angewendet, wenn `logMessagesAtTransportLevel` auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9d078-104">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="9d078-105">Die Protokollierung von fehlerhaften Nachrichten und die Protokollierung von Nachrichten auf Dienstebene wird nicht von Filtern beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="9d078-105">Service level and malformed message logging are not affected by filters.</span></span>

<span data-ttu-id="9d078-106">Um der Auflistung einen Filter hinzuzufügen, verwenden Sie das `add`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="9d078-106">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="9d078-107">Wenn mindestens ein Filter definiert ist, werden nur Nachrichten protokolliert, die mindestens einem der Filter entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9d078-107">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="9d078-108">Wenn kein Filter definiert wird, werden alle Meldungen protokolliert.</span><span class="sxs-lookup"><span data-stu-id="9d078-108">If no filter is defined, all messages pass through.</span></span>

<span data-ttu-id="9d078-109">Filter unterstützen die gesamte Xpath-Syntax und werden in der Reihenfolge angewendet, in der sie in der Konfigurationsdatei angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9d078-109">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="9d078-110">Ein syntaktisch falscher Filter führt zu einer Konfigurationsausnahme.</span><span class="sxs-lookup"><span data-stu-id="9d078-110">A syntactically incorrect filter results in a configuration exception.</span></span>

<span data-ttu-id="9d078-111">Im Folgenden finden Sie ein Beispiel für das Konfigurieren eines Filters, der nur Nachrichten aufzeichnet, die über einen SOAP-Headerabschnitt verfügen.</span><span class="sxs-lookup"><span data-stu-id="9d078-111">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>

```xml
<messageLogging logEntireMessage="true"
                logMalformedMessages="true"
                logMessagesAtServiceLevel="true"
                logMessagesAtTransportLevel="true"
                maxMessagesToLog="420">  
  <filters>  
    <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">  
      /soap:Envelope/soap:Headers  
    </add>  
  </filters>  
</messageLogging>
```

## <a name="see-also"></a><span data-ttu-id="9d078-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d078-112">See also</span></span>

 <span data-ttu-id="9d078-113"><xref:System.ServiceModel.Configuration.DiagnosticSection> <xref:System.ServiceModel.Diagnostics> <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> <xref:System.ServiceModel.Configuration.MessageLoggingElement> <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A> <xref:System.ServiceModel.Configuration.XPathMessageFilterElementCollection> <xref:System.ServiceModel.Configuration.XPathMessageFilterElement> <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> [Konfigurieren der Nachrichtenprotokollierung](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) [ \<MessageLogging >](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)</span><span class="sxs-lookup"><span data-stu-id="9d078-113"><xref:System.ServiceModel.Configuration.DiagnosticSection> <xref:System.ServiceModel.Diagnostics> <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> <xref:System.ServiceModel.Configuration.MessageLoggingElement> <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A> <xref:System.ServiceModel.Configuration.XPathMessageFilterElementCollection> <xref:System.ServiceModel.Configuration.XPathMessageFilterElement> <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> [Configuring Message Logging](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) [\<messageLogging>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)</span></span>
