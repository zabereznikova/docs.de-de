---
title: <add> von <filters>
ms.date: 03/30/2017
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
ms.openlocfilehash: e7975bea1435abdb77528628e7b96c65a72cbbc2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926687"
---
# <a name="add-of-filters"></a><span data-ttu-id="c9735-102">\<Fügen Sie > \<von Filtern hinzu ></span><span class="sxs-lookup"><span data-stu-id="c9735-102">\<add> of \<filters></span></span>
<span data-ttu-id="c9735-103">Ein XPath-Filter, der den zu protokolliernden Nachrichtentyp angibt.</span><span class="sxs-lookup"><span data-stu-id="c9735-103">A XPath filter that specifies the kind of message to be logged.</span></span>  
  
 <span data-ttu-id="c9735-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c9735-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c9735-105">\<Diagnose ></span><span class="sxs-lookup"><span data-stu-id="c9735-105">\<diagnostic></span></span>  
<span data-ttu-id="c9735-106">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="c9735-106">\<messageLogging></span></span>  
<span data-ttu-id="c9735-107">\<Filter ></span><span class="sxs-lookup"><span data-stu-id="c9735-107">\<filters></span></span>  
<span data-ttu-id="c9735-108">\<add></span><span class="sxs-lookup"><span data-stu-id="c9735-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9735-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="c9735-109">Syntax</span></span>  
  
```xml  
<filters>
  <add filter="String" />
</filters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9735-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c9735-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c9735-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c9735-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9735-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="c9735-112">Attributes</span></span>  
  
|<span data-ttu-id="c9735-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="c9735-113">Attribute</span></span>|<span data-ttu-id="c9735-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c9735-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c9735-115">Filter</span><span class="sxs-lookup"><span data-stu-id="c9735-115">filter</span></span>|<span data-ttu-id="c9735-116">Eine Zeichenfolge, die die Abfrage eines XML-Dokuments angibt, die von einem XPath 1.0-Ausdruck definiert wird.</span><span class="sxs-lookup"><span data-stu-id="c9735-116">A string that specifies a query on an XML document defined by an XPath 1.0 expression.</span></span> <span data-ttu-id="c9735-117">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span><span class="sxs-lookup"><span data-stu-id="c9735-117">For more information, see <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c9735-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c9735-118">Child Elements</span></span>  
 <span data-ttu-id="c9735-119">Keine</span><span class="sxs-lookup"><span data-stu-id="c9735-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c9735-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c9735-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c9735-121">Element</span><span class="sxs-lookup"><span data-stu-id="c9735-121">Element</span></span>|<span data-ttu-id="c9735-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c9735-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9735-123">\<filters></span><span class="sxs-lookup"><span data-stu-id="c9735-123">\<filters></span></span>](filters.md)|<span data-ttu-id="c9735-124">Enthält eine Auflistung von XPath-Filtern, mit denen gesteuert wird, welcher Nachrichtentyp protokolliert wird.</span><span class="sxs-lookup"><span data-stu-id="c9735-124">Contains a collection of XPath filters used to control what kind of message is logged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9735-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c9735-125">Remarks</span></span>  
 <span data-ttu-id="c9735-126">Filter werden nur auf Transportebene angewendet, wenn `logMessagesAtTransportLevel` auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c9735-126">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="c9735-127">Die Protokollierung von fehlerhaften Nachrichten und die Protokollierung von Nachrichten auf Dienstebene wird nicht von Filtern beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="c9735-127">Service level and malformed message logging are not affected by filters.</span></span>  
  
 <span data-ttu-id="c9735-128">Um der Auflistung einen Filter hinzuzufügen, verwenden Sie das `add`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="c9735-128">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="c9735-129">Wenn mindestens ein Filter definiert ist, werden nur Nachrichten protokolliert, die mindestens einem der Filter entsprechen.</span><span class="sxs-lookup"><span data-stu-id="c9735-129">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="c9735-130">Wenn kein Filter definiert wird, werden alle Meldungen protokolliert.</span><span class="sxs-lookup"><span data-stu-id="c9735-130">If no filter is defined, all messages pass through.</span></span>  
  
 <span data-ttu-id="c9735-131">Filter unterstützen die gesamte XPath-Syntax und werden in der Reihenfolge angewendet, in der sie in der Konfigurationsdatei angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c9735-131">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="c9735-132">Ein syntaktisch falscher Filter führt zu einer Konfigurationsausnahme.</span><span class="sxs-lookup"><span data-stu-id="c9735-132">A syntactically incorrect filter results in a configuration exception.</span></span>  
  
 <span data-ttu-id="c9735-133">Im Folgenden finden Sie ein Beispiel für das Konfigurieren eines Filters, der nur Nachrichten aufzeichnet, die über einen SOAP-Headerabschnitt verfügen.</span><span class="sxs-lookup"><span data-stu-id="c9735-133">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9735-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c9735-134">Example</span></span>  
 <span data-ttu-id="c9735-135">Im Folgenden finden Sie ein Beispiel für das Konfigurieren eines Filters, der nur Nachrichten aufzeichnet, die über einen SOAP-Headerabschnitt verfügen.</span><span class="sxs-lookup"><span data-stu-id="c9735-135">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c9735-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9735-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>
- <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>
- [<span data-ttu-id="c9735-137">Konfigurieren der Nachrichtenprotokollierung</span><span class="sxs-lookup"><span data-stu-id="c9735-137">Configuring Message Logging</span></span>](../../../wcf/diagnostics/configuring-message-logging.md)
- [<span data-ttu-id="c9735-138">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="c9735-138">\<messageLogging></span></span>](messagelogging.md)
