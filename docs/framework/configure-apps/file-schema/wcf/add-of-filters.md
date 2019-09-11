---
title: <add> von <filters>
ms.date: 03/30/2017
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
ms.openlocfilehash: 280c516b17a133930bc4b6621a8c9bc7f4781085
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850562"
---
# <a name="add-of-filters"></a><span data-ttu-id="e0ba4-102">\<Fügen Sie > \<von Filtern hinzu ></span><span class="sxs-lookup"><span data-stu-id="e0ba4-102">\<add> of \<filters></span></span>
<span data-ttu-id="e0ba4-103">Ein XPath-Filter, der den zu protokolliernden Nachrichtentyp angibt.</span><span class="sxs-lookup"><span data-stu-id="e0ba4-103">A XPath filter that specifies the kind of message to be logged.</span></span>  
  
<span data-ttu-id="e0ba4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e0ba4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e0ba4-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e0ba4-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e0ba4-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Diagnose >** ](diagnostics.md)</span><span class="sxs-lookup"><span data-stu-id="e0ba4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)</span></span>\
<span data-ttu-id="e0ba4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<MessageLogging->** ](messagelogging.md)</span><span class="sxs-lookup"><span data-stu-id="e0ba4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<messageLogging>**](messagelogging.md)</span></span>\
<span data-ttu-id="e0ba4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Filter >** ](filters.md)</span><span class="sxs-lookup"><span data-stu-id="e0ba4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters.md)</span></span>\
<span data-ttu-id="e0ba4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<add>**</span><span class="sxs-lookup"><span data-stu-id="e0ba4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0ba4-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0ba4-110">Syntax</span></span>  
  
```xml  
<filters>
  <add filter="String" />
</filters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0ba4-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e0ba4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e0ba4-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e0ba4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0ba4-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="e0ba4-113">Attributes</span></span>  
  
|<span data-ttu-id="e0ba4-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="e0ba4-114">Attribute</span></span>|<span data-ttu-id="e0ba4-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0ba4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e0ba4-116">Filter</span><span class="sxs-lookup"><span data-stu-id="e0ba4-116">filter</span></span>|<span data-ttu-id="e0ba4-117">Eine Zeichenfolge, die die Abfrage eines XML-Dokuments angibt, die von einem XPath 1.0-Ausdruck definiert wird.</span><span class="sxs-lookup"><span data-stu-id="e0ba4-117">A string that specifies a query on an XML document defined by an XPath 1.0 expression.</span></span> <span data-ttu-id="e0ba4-118">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span><span class="sxs-lookup"><span data-stu-id="e0ba4-118">For more information, see <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e0ba4-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e0ba4-119">Child Elements</span></span>  
 <span data-ttu-id="e0ba4-120">Keine</span><span class="sxs-lookup"><span data-stu-id="e0ba4-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e0ba4-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e0ba4-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e0ba4-122">Element</span><span class="sxs-lookup"><span data-stu-id="e0ba4-122">Element</span></span>|<span data-ttu-id="e0ba4-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0ba4-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e0ba4-124">\<filters></span><span class="sxs-lookup"><span data-stu-id="e0ba4-124">\<filters></span></span>](filters.md)|<span data-ttu-id="e0ba4-125">Enthält eine Auflistung von XPath-Filtern, mit denen gesteuert wird, welcher Nachrichtentyp protokolliert wird.</span><span class="sxs-lookup"><span data-stu-id="e0ba4-125">Contains a collection of XPath filters used to control what kind of message is logged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0ba4-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e0ba4-126">Remarks</span></span>  
 <span data-ttu-id="e0ba4-127">Filter werden nur auf Transportebene angewendet, wenn `logMessagesAtTransportLevel` auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e0ba4-127">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="e0ba4-128">Die Protokollierung von fehlerhaften Nachrichten und die Protokollierung von Nachrichten auf Dienstebene wird nicht von Filtern beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="e0ba4-128">Service level and malformed message logging are not affected by filters.</span></span>  
  
 <span data-ttu-id="e0ba4-129">Um der Auflistung einen Filter hinzuzufügen, verwenden Sie das `add`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="e0ba4-129">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="e0ba4-130">Wenn mindestens ein Filter definiert ist, werden nur Nachrichten protokolliert, die mindestens einem der Filter entsprechen.</span><span class="sxs-lookup"><span data-stu-id="e0ba4-130">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="e0ba4-131">Wenn kein Filter definiert wird, werden alle Meldungen protokolliert.</span><span class="sxs-lookup"><span data-stu-id="e0ba4-131">If no filter is defined, all messages pass through.</span></span>  
  
 <span data-ttu-id="e0ba4-132">Filter unterstützen die gesamte XPath-Syntax und werden in der Reihenfolge angewendet, in der sie in der Konfigurationsdatei angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e0ba4-132">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="e0ba4-133">Ein syntaktisch falscher Filter führt zu einer Konfigurationsausnahme.</span><span class="sxs-lookup"><span data-stu-id="e0ba4-133">A syntactically incorrect filter results in a configuration exception.</span></span>  
  
 <span data-ttu-id="e0ba4-134">Im Folgenden finden Sie ein Beispiel für das Konfigurieren eines Filters, der nur Nachrichten aufzeichnet, die über einen SOAP-Headerabschnitt verfügen.</span><span class="sxs-lookup"><span data-stu-id="e0ba4-134">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0ba4-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e0ba4-135">Example</span></span>  
 <span data-ttu-id="e0ba4-136">Im Folgenden finden Sie ein Beispiel für das Konfigurieren eines Filters, der nur Nachrichten aufzeichnet, die über einen SOAP-Headerabschnitt verfügen.</span><span class="sxs-lookup"><span data-stu-id="e0ba4-136">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e0ba4-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0ba4-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>
- <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>
- [<span data-ttu-id="e0ba4-138">Konfigurieren der Nachrichtenprotokollierung</span><span class="sxs-lookup"><span data-stu-id="e0ba4-138">Configuring Message Logging</span></span>](../../../wcf/diagnostics/configuring-message-logging.md)
- [<span data-ttu-id="e0ba4-139">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="e0ba4-139">\<messageLogging></span></span>](messagelogging.md)
