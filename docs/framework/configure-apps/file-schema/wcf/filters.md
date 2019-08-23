---
title: <filters>
ms.date: 03/30/2017
ms.assetid: 37a87222-ec78-4728-8105-9ca1bd961f0c
ms.openlocfilehash: e4ce0452cc46a8f29334fa67f51f14b83290b1c8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918874"
---
# <a name="filters"></a><span data-ttu-id="4acf9-101">\<Filter ></span><span class="sxs-lookup"><span data-stu-id="4acf9-101">\<filters></span></span>

<span data-ttu-id="4acf9-102">Das `filters`-Element enthält eine Auflistung von XPath-Filtern, mit denen gesteuert wird, welcher Nachrichtentyp protokolliert wird.</span><span class="sxs-lookup"><span data-stu-id="4acf9-102">The `filters` element holds a collection of XPath filters used to control what kind of message is logged.</span></span>

<span data-ttu-id="4acf9-103">Filter werden nur auf Transportebene angewendet, wenn `logMessagesAtTransportLevel` auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4acf9-103">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="4acf9-104">Die Protokollierung von fehlerhaften Nachrichten und die Protokollierung von Nachrichten auf Dienstebene wird nicht von Filtern beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="4acf9-104">Service level and malformed message logging are not affected by filters.</span></span>

<span data-ttu-id="4acf9-105">Um der Auflistung einen Filter hinzuzufügen, verwenden Sie das `add`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="4acf9-105">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="4acf9-106">Wenn mindestens ein Filter definiert ist, werden nur Nachrichten protokolliert, die mindestens einem der Filter entsprechen.</span><span class="sxs-lookup"><span data-stu-id="4acf9-106">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="4acf9-107">Wenn kein Filter definiert wird, werden alle Meldungen protokolliert.</span><span class="sxs-lookup"><span data-stu-id="4acf9-107">If no filter is defined, all messages pass through.</span></span>

<span data-ttu-id="4acf9-108">Filter unterstützen die gesamte XPath-Syntax und werden in der Reihenfolge angewendet, in der sie in der Konfigurationsdatei angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4acf9-108">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="4acf9-109">Ein syntaktisch falscher Filter führt zu einer Konfigurationsausnahme.</span><span class="sxs-lookup"><span data-stu-id="4acf9-109">A syntactically incorrect filter results in a configuration exception.</span></span>

<span data-ttu-id="4acf9-110">Im Folgenden finden Sie ein Beispiel für das Konfigurieren eines Filters, der nur Nachrichten aufzeichnet, die über einen SOAP-Headerabschnitt verfügen.</span><span class="sxs-lookup"><span data-stu-id="4acf9-110">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="4acf9-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4acf9-111">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElementCollection>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>
- <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>
- [<span data-ttu-id="4acf9-112">Konfigurieren der Nachrichtenprotokollierung</span><span class="sxs-lookup"><span data-stu-id="4acf9-112">Configuring Message Logging</span></span>](../../../wcf/diagnostics/configuring-message-logging.md)
- [<span data-ttu-id="4acf9-113">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="4acf9-113">\<messageLogging></span></span>](messagelogging.md)
