---
title: '&lt;add&gt; von &lt;filters&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ff083cfbcdfa772bb5904f4311d95e399c22c97e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltfiltersgt"></a>&lt;add&gt; von &lt;filters&gt;
Ein XPath-Filter, der den zu protokollierenden Nachrichtentyp angibt.  
  
 \<System. ServiceModel >  
\<Diagnose >  
\<MessageLogging >  
\<Filter >  
\<add>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<filters>  
   <add filter="String"/>  
</filters>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Filter|Eine Zeichenfolge, die die Abfrage eines XML-Dokuments angibt, die von einem XPath 1.0-Ausdruck definiert wird. Weitere Informationen finden Sie unter <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Filter >](../../../../../docs/framework/configure-apps/file-schema/wcf/filters.md)|Enthält eine Auflistung von XPath-Filtern, mit denen gesteuert wird, welcher Nachrichtentyp protokolliert wird.|  
  
## <a name="remarks"></a>Hinweise  
 Filter werden nur auf Transportebene angewendet, wenn `logMessagesAtTransportLevel` auf `true` festgelegt ist. Die Protokollierung von fehlerhaften Nachrichten und die Protokollierung von Nachrichten auf Dienstebene wird nicht von Filtern beeinflusst.  
  
 Um der Auflistung einen Filter hinzuzufügen, verwenden Sie das `add`-Schlüsselwort. Wenn mindestens ein Filter definiert ist, werden nur Nachrichten protokolliert, die mindestens einem der Filter entsprechen. Wenn kein Filter definiert wird, werden alle Meldungen protokolliert.  
  
 Filter unterstützen die gesamte Xpath-Syntax und werden in der Reihenfolge angewendet, in der sie in der Konfigurationsdatei angezeigt werden. Ein syntaktisch falscher Filter führt zu einer Konfigurationsausnahme.  
  
 Im Folgenden finden Sie ein Beispiel für das Konfigurieren eines Filters, der nur Nachrichten aufzeichnet, die über einen SOAP-Headerabschnitt verfügen.  
  
## <a name="example"></a>Beispiel  
 Im Folgenden finden Sie ein Beispiel für das Konfigurieren eines Filters, der nur Nachrichten aufzeichnet, die über einen SOAP-Headerabschnitt verfügen.  
  
```xml  
<messageLogging logEntireMessage="true"  
     logMalformedMessages="true" logMessagesAtServiceLevel="true"  
     logMessagesAtTransportLevel="true" maxMessagesToLog="420">  
     <filters>  
        <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">  
                        /soap:Envelope/soap:Headers  
        </add>  
     </filters>  
</messageLogging>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>  
 <xref:System.ServiceModel.Configuration.MessageLoggingElement>  
 <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>  
 <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>  
 <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>  
 [Konfigurieren der Nachrichtenprotokollierung](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)  
 [Konfigurieren der Nachrichtenprotokollierung](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)  
 [\<MessageLogging >](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)
