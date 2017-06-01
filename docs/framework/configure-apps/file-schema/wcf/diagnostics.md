---
title: "&lt;Diagnose&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
caps.latest.revision: 20
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 20
---
# &lt;Diagnose&gt;
Das `diagnostics`\-Element definiert Einstellungen, die von einem Administrator zur Laufzeitüberprüfung und \-steuerung verwendet werden können.  
  
## Syntax  
  
```  
  
<system.serviceModel>  
   <diagnostics etwProviderId=”String”  
       performanceCounters="Off/ServiceOnly/All/Default"         
       wmiProviderEnabled="Boolean" >  
       <endToEndTracing activityTracing="Boolean"  
          messageFlowTracing="Boolean"  
          propagateActivity="Boolean" />  
       <messageLogging logEntireMessage="Boolean"  
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
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|etwProviderId|Eine Zeichenfolge, die den Bezeichner für den Anbieter der Ereignisablaufverfolgung angibt, der Ereignisse in ETW\-Sitzungen schreibt.|  
|performanceCounters|Gibt an, ob die Leistungsindikatoren für die Assembly aktiviert sind.  Folgende Werte sind gültig:<br /><br /> -   Off: Leistungsindikatoren sind deaktiviert.<br />-   ServiceOnly: Nur Leistungsindikatoren für diesen Dienst sind aktiviert.<br />-   All: Leistungsindikatoren können zur Laufzeit angezeigt werden.<br />-   Default: Die einzelne Leistungsindikatorinstanz \_WCF\_Admin wird erstellt.  Diese Instanz wird verwendet, um die Auflistung der SQM\-Daten für die Verwendung durch die Infrastruktur zu aktivieren.  Die Indikatorwerte für diese Instanz werden nicht aktualisiert und bleiben deshalb auf null.  Dies ist der Standardwert, wenn keine Konfiguration für WCF vorhanden ist.|  
|wmiProviderEnabled|Ein boolescher Wert, der angibt, ob der WMI\-Anbieter für die Assembly aktiviert ist.  Der WMI\-Anbieter ist für Benutzer erforderlich, um Laufzeitzugriff auf die Überprüfungs\- und Steuerungsfunktionen von Windows Communication Foundation \(WCF\) zu erhalten.  Die Standardeinstellung ist `false`.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<endToEndTracing\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endtoendtracing.md)|Ein Konfigurationselement, das Ihnen ermöglicht, unterschiedliche Aspekte der End\-to\-End\-Ablaufverfolgung während der Ausführung einer Dienstanwendung zu aktivieren bzw. zu deaktivieren.|  
|[\<messageLogging\>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)|Beschreibt die Einstellungen für die WCF\-Nachrichtenprotokollierung.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|serviceModel|Das Stammelement aller WCF\-Konfigurationselemente.|  
  
## Hinweise  
 Der `diagnostics`\-Abschnitt definiert die Diagnoseeinstellungen für alle Dienste in einer Assembly.  Es ist nicht möglich, separate Diagnoseeinstellungen auf Dienstebene zu definieren, es sei denn, es befindet sich nur ein Dienst in der Assembly.  Attribute werden gemäß den Anforderungen des Abschnitts festgelegt.  
  
## Beispiel  
  
```  
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
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>   
 <xref:System.ServiceModel.Diagnostics>