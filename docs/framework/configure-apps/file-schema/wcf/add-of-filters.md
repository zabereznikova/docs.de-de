---
title: <add> von <filters>
ms.date: 03/30/2017
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
ms.openlocfilehash: 399fc4e22a9253469a5494af61dac862e33814a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704543"
---
# <a name="add-of-filters"></a><span data-ttu-id="1d080-102">\<Hinzufügen > der \<Filter ></span><span class="sxs-lookup"><span data-stu-id="1d080-102">\<add> of \<filters></span></span>
<span data-ttu-id="1d080-103">Ein XPath-Filter, der den zu protokolliernden Nachrichtentyp angibt.</span><span class="sxs-lookup"><span data-stu-id="1d080-103">A XPath filter that specifies the kind of message to be logged.</span></span>  
  
 <span data-ttu-id="1d080-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1d080-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1d080-105">\<diagnostic></span><span class="sxs-lookup"><span data-stu-id="1d080-105">\<diagnostic></span></span>  
<span data-ttu-id="1d080-106">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="1d080-106">\<messageLogging></span></span>  
<span data-ttu-id="1d080-107">\<filters></span><span class="sxs-lookup"><span data-stu-id="1d080-107">\<filters></span></span>  
<span data-ttu-id="1d080-108">\<add></span><span class="sxs-lookup"><span data-stu-id="1d080-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d080-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d080-109">Syntax</span></span>  
  
```xml  
<filters>
  <add filter="String" />
</filters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d080-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1d080-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1d080-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1d080-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d080-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="1d080-112">Attributes</span></span>  
  
|<span data-ttu-id="1d080-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="1d080-113">Attribute</span></span>|<span data-ttu-id="1d080-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1d080-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1d080-115">Filter</span><span class="sxs-lookup"><span data-stu-id="1d080-115">filter</span></span>|<span data-ttu-id="1d080-116">Eine Zeichenfolge, die die Abfrage eines XML-Dokuments angibt, die von einem XPath 1.0-Ausdruck definiert wird.</span><span class="sxs-lookup"><span data-stu-id="1d080-116">A string that specifies a query on an XML document defined by an XPath 1.0 expression.</span></span> <span data-ttu-id="1d080-117">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span><span class="sxs-lookup"><span data-stu-id="1d080-117">For more information, see <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1d080-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1d080-118">Child Elements</span></span>  
 <span data-ttu-id="1d080-119">Keine</span><span class="sxs-lookup"><span data-stu-id="1d080-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1d080-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1d080-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1d080-121">Element</span><span class="sxs-lookup"><span data-stu-id="1d080-121">Element</span></span>|<span data-ttu-id="1d080-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1d080-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d080-123">\<filters></span><span class="sxs-lookup"><span data-stu-id="1d080-123">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters.md)|<span data-ttu-id="1d080-124">Enthält eine Auflistung von XPath-Filtern, mit denen gesteuert wird, welcher Nachrichtentyp protokolliert wird.</span><span class="sxs-lookup"><span data-stu-id="1d080-124">Contains a collection of XPath filters used to control what kind of message is logged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d080-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1d080-125">Remarks</span></span>  
 <span data-ttu-id="1d080-126">Filter werden nur auf Transportebene angewendet, wenn `logMessagesAtTransportLevel` auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="1d080-126">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="1d080-127">Die Protokollierung von fehlerhaften Nachrichten und die Protokollierung von Nachrichten auf Dienstebene wird nicht von Filtern beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="1d080-127">Service level and malformed message logging are not affected by filters.</span></span>  
  
 <span data-ttu-id="1d080-128">Um der Auflistung einen Filter hinzuzufügen, verwenden Sie das `add`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="1d080-128">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="1d080-129">Wenn mindestens ein Filter definiert ist, werden nur Nachrichten protokolliert, die mindestens einem der Filter entsprechen.</span><span class="sxs-lookup"><span data-stu-id="1d080-129">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="1d080-130">Wenn kein Filter definiert wird, werden alle Meldungen protokolliert.</span><span class="sxs-lookup"><span data-stu-id="1d080-130">If no filter is defined, all messages pass through.</span></span>  
  
 <span data-ttu-id="1d080-131">Filter unterstützen die gesamte XPath-Syntax und werden in der Reihenfolge angewendet, in der sie in der Konfigurationsdatei angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1d080-131">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="1d080-132">Ein syntaktisch falscher Filter führt zu einer Konfigurationsausnahme.</span><span class="sxs-lookup"><span data-stu-id="1d080-132">A syntactically incorrect filter results in a configuration exception.</span></span>  
  
 <span data-ttu-id="1d080-133">Im Folgenden finden Sie ein Beispiel für das Konfigurieren eines Filters, der nur Nachrichten aufzeichnet, die über einen SOAP-Headerabschnitt verfügen.</span><span class="sxs-lookup"><span data-stu-id="1d080-133">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d080-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1d080-134">Example</span></span>  
 <span data-ttu-id="1d080-135">Im Folgenden finden Sie ein Beispiel für das Konfigurieren eines Filters, der nur Nachrichten aufzeichnet, die über einen SOAP-Headerabschnitt verfügen.</span><span class="sxs-lookup"><span data-stu-id="1d080-135">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1d080-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d080-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>
- <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>
- [<span data-ttu-id="1d080-137">Konfigurieren der Nachrichtenprotokollierung</span><span class="sxs-lookup"><span data-stu-id="1d080-137">Configuring Message Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)
- [<span data-ttu-id="1d080-138">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="1d080-138">\<messageLogging></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)
