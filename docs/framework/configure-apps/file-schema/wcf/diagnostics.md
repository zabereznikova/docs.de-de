---
title: '&lt;Diagnose&gt;'
ms.date: 03/30/2017
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
ms.openlocfilehash: 3ee611d3903ba36748837d2743cd03d54670befd
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149344"
---
# <a name="ltdiagnosticsgt"></a>&lt;Diagnose&gt;
Das `diagnostics`-Element definiert Einstellungen, die von einem Administrator zur Laufzeitüberprüfung und -steuerung verwendet werden können.  
  
 \<system.ServiceModel>  
\<Diagnose >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.serviceModel>
  <diagnostics etwProviderId="String"
               performanceCounters="Off/ServiceOnly/All/Default"
               wmiProviderEnabled="Boolean">
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
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
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|etwProviderId|Eine Zeichenfolge, die den Bezeichner für den Anbieter der Ereignisablaufverfolgung angibt, der Ereignisse in ETW-Sitzungen schreibt.|  
|performanceCounters|Gibt an, ob die Leistungsindikatoren für die Assembly aktiviert sind. Folgende Werte sind gültig:<br /><br /> -Deaktiviert: Leistungsindikatoren sind deaktiviert.<br />-ServiceOnly: Nur Leistungsindikatoren für diesen Dienst sind aktiviert.<br />– Alle: Leistungsindikatoren können zur Laufzeit angezeigt werden.<br />– Default: Die einzelne Leistungsindikatorinstanz _WCF_Admin wird erstellt. Diese Instanz wird verwendet, um die Auflistung der SQM-Daten für die Verwendung durch die Infrastruktur zu aktivieren. Die Indikatorwerte für diese Instanz werden nicht aktualisiert und bleiben deshalb auf null. Dies ist der Standardwert, wenn keine Konfiguration für WCF vorhanden ist.|  
|wmiProviderEnabled|Ein boolescher Wert, der angibt, ob der WMI-Anbieter für die Assembly aktiviert ist. Der WMI-Anbieter ist für Benutzer erforderlich, um Laufzeitzugriff auf die Überprüfungs- und Steuerungsfunktionen von Windows Communication Foundation (WCF) zu erhalten. Die Standardeinstellung ist `false`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<EndToEndTracing >](../../../../../docs/framework/configure-apps/file-schema/wcf/endtoendtracing.md)|Ein Konfigurationselement, das Ihnen ermöglicht, unterschiedliche Aspekte der End-to-End-Ablaufverfolgung während der Ausführung einer Dienstanwendung zu aktivieren bzw. zu deaktivieren.|  
|[\<MessageLogging >](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)|Beschreibt die Einstellungen für die WCF-Nachrichtenprotokollierung.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|serviceModel|Das Stammelement aller WCF-Konfigurationselemente.|  
  
## <a name="remarks"></a>Hinweise  
 Der `diagnostics`-Abschnitt definiert die Diagnoseeinstellungen für alle Dienste in einer Assembly. Es ist nicht möglich, separate Diagnoseeinstellungen auf Dienstebene zu definieren, es sei denn, es befindet sich nur ein Dienst in der Assembly. Attribute werden gemäß den Anforderungen des Abschnitts festgelegt.  
  
## <a name="example"></a>Beispiel  
  
```xml  
<diagnostics wmiProviderEnabled="false"
             performanceCounters="all">
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
</diagnostics>
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>
