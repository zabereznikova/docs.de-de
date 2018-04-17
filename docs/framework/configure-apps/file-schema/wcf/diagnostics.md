---
title: '&lt;Diagnose&gt;'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bb5506fd72745f32194b2e3cc409ff848fd1c270
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="ltdiagnosticsgt"></a>&lt;Diagnose&gt;
Das `diagnostics`-Element definiert Einstellungen, die von einem Administrator zur Laufzeitüberprüfung und -steuerung verwendet werden können.  
  
 \<system.ServiceModel>  
\<Diagnose >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.serviceModel>  
  <diagnostics 
      etwProviderId="String"       
      performanceCounters="Off/ServiceOnly/All/Default"              
      wmiProviderEnabled="Boolean" >       
    <endToEndTracing 
        activityTracing="Boolean"  
        messageFlowTracing="Boolean"  
        propagateActivity="Boolean" />  
    <messageLogging 
        logEntireMessage="Boolean"  
        logMalformedMessages="Boolean"  
        logMessagesAtServiceLevel="Boolean"  
        logMessagesAtTransportLevel="Boolean"  
        maxMessagesToLog="Integer"  
        maxSizeOfMessageToLog="Integer" >  
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
|performanceCounters|Gibt an, ob die Leistungsindikatoren für die Assembly aktiviert sind. Folgende Werte sind gültig:<br /><br /> -Off: Leistungsindikatoren sind deaktiviert.<br />-ServiceOnly: Nur Leistungsindikatoren für diesen Dienst aktiviert ist.<br />-Alle: Leistung Leistungsindikatoren zur Laufzeit angezeigt werden können.<br />-Standard: Eine einzelne Leistungsindikatorinstanz _WCF_Admin wird erstellt. Diese Instanz wird verwendet, um die Auflistung der SQM-Daten für die Verwendung durch die Infrastruktur zu aktivieren. Die Indikatorwerte für diese Instanz werden nicht aktualisiert und bleiben deshalb auf null. Dies ist der Standardwert, wenn keine Konfiguration für WCF vorhanden ist.|  
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
<diagnostics
    wmiProviderEnabled="false"  
    performanceCounters="all">  
  <messageLogging 
      logEntireMessage="true"  
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
