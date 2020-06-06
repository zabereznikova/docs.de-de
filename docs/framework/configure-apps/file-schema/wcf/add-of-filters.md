---
title: <add> von <filters>
ms.date: 03/30/2017
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
ms.openlocfilehash: 280c516b17a133930bc4b6621a8c9bc7f4781085
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850562"
---
# <a name="add-of-filters"></a><span data-ttu-id="8fca7-102">\<add> von \<filters></span><span class="sxs-lookup"><span data-stu-id="8fca7-102">\<add> of \<filters></span></span>
<span data-ttu-id="8fca7-103">Ein XPath-Filter, der den zu protokolliernden Nachrichtentyp angibt.</span><span class="sxs-lookup"><span data-stu-id="8fca7-103">A XPath filter that specifies the kind of message to be logged.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<messageLogging>**](messagelogging.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="8fca7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8fca7-104">Syntax</span></span>  
  
```xml  
<filters>
  <add filter="String" />
</filters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8fca7-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8fca7-105">Attributes and Elements</span></span>  
 <span data-ttu-id="8fca7-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8fca7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8fca7-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="8fca7-107">Attributes</span></span>  
  
|<span data-ttu-id="8fca7-108">attribute</span><span class="sxs-lookup"><span data-stu-id="8fca7-108">Attribute</span></span>|<span data-ttu-id="8fca7-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8fca7-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8fca7-110">filter</span><span class="sxs-lookup"><span data-stu-id="8fca7-110">filter</span></span>|<span data-ttu-id="8fca7-111">Eine Zeichenfolge, die die Abfrage eines XML-Dokuments angibt, die von einem XPath 1.0-Ausdruck definiert wird.</span><span class="sxs-lookup"><span data-stu-id="8fca7-111">A string that specifies a query on an XML document defined by an XPath 1.0 expression.</span></span> <span data-ttu-id="8fca7-112">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span><span class="sxs-lookup"><span data-stu-id="8fca7-112">For more information, see <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8fca7-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8fca7-113">Child Elements</span></span>  
 <span data-ttu-id="8fca7-114">Keine</span><span class="sxs-lookup"><span data-stu-id="8fca7-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8fca7-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8fca7-115">Parent Elements</span></span>  
  
|<span data-ttu-id="8fca7-116">Element</span><span class="sxs-lookup"><span data-stu-id="8fca7-116">Element</span></span>|<span data-ttu-id="8fca7-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fca7-117">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters.md)|<span data-ttu-id="8fca7-118">Enthält eine Auflistung von XPath-Filtern, mit denen gesteuert wird, welcher Nachrichtentyp protokolliert wird.</span><span class="sxs-lookup"><span data-stu-id="8fca7-118">Contains a collection of XPath filters used to control what kind of message is logged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fca7-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8fca7-119">Remarks</span></span>  
 <span data-ttu-id="8fca7-120">Filter werden nur auf Transportebene angewendet, wenn `logMessagesAtTransportLevel` auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="8fca7-120">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="8fca7-121">Die Protokollierung von fehlerhaften Nachrichten und die Protokollierung von Nachrichten auf Dienstebene wird nicht von Filtern beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="8fca7-121">Service level and malformed message logging are not affected by filters.</span></span>  
  
 <span data-ttu-id="8fca7-122">Um der Auflistung einen Filter hinzuzufügen, verwenden Sie das `add`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="8fca7-122">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="8fca7-123">Wenn mindestens ein Filter definiert ist, werden nur Nachrichten protokolliert, die mindestens einem der Filter entsprechen.</span><span class="sxs-lookup"><span data-stu-id="8fca7-123">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="8fca7-124">Wenn kein Filter definiert wird, werden alle Meldungen protokolliert.</span><span class="sxs-lookup"><span data-stu-id="8fca7-124">If no filter is defined, all messages pass through.</span></span>  
  
 <span data-ttu-id="8fca7-125">Filter unterstützen die gesamte XPath-Syntax und werden in der Reihenfolge angewendet, in der sie in der Konfigurationsdatei angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8fca7-125">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="8fca7-126">Ein syntaktisch falscher Filter führt zu einer Konfigurationsausnahme.</span><span class="sxs-lookup"><span data-stu-id="8fca7-126">A syntactically incorrect filter results in a configuration exception.</span></span>  
  
 <span data-ttu-id="8fca7-127">Im Folgenden finden Sie ein Beispiel für das Konfigurieren eines Filters, der nur Nachrichten aufzeichnet, die über einen SOAP-Headerabschnitt verfügen.</span><span class="sxs-lookup"><span data-stu-id="8fca7-127">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fca7-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8fca7-128">Example</span></span>  
 <span data-ttu-id="8fca7-129">Im Folgenden finden Sie ein Beispiel für das Konfigurieren eines Filters, der nur Nachrichten aufzeichnet, die über einen SOAP-Headerabschnitt verfügen.</span><span class="sxs-lookup"><span data-stu-id="8fca7-129">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8fca7-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8fca7-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>
- <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>
- [<span data-ttu-id="8fca7-131">Konfigurieren der Nachrichtenprotokollierung</span><span class="sxs-lookup"><span data-stu-id="8fca7-131">Configuring Message Logging</span></span>](../../../wcf/diagnostics/configuring-message-logging.md)
- [\<messageLogging>](messagelogging.md)
