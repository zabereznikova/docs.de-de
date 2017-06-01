---
title: "&lt;net.pipe&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6a0f0318-f8f6-466c-9fae-199d7274a82e
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# &lt;net.pipe&gt;
Gibt Konfigurationseinstellungen für den Aktivierungsdienst der benannten Pipes an, der die Lebensdauer der Verbindung der benannten Pipes verwaltet und Aktivierungsanforderungen verarbeitet, die über benannte Pipes eintreffen.  
  
## Syntax  
  
```  
  
<configuration>  
   <system.serviceModel.activation>  
       <net.pipe maxPendingAccepts="Integer"  
                    maxPendingConnections="Integer"  
          receiveTimeout="TimeSpan">  
          <allowAccounts>  
             // LocalSystem account  
             <add securityIdentifier="S-1-5-18"/>  
             // LocalService account  
             <add securityIdentifier="S-1-5-19"/>  
             // Administrators account  
             <add securityIdentifier="S-1-5-20"/>  
             // Network Service account  
             <add securityIdentifier="S-1-5-32-544" />  
             // IIS_IUSRS account (Vista only)  
             <add securityIdentifier="S-1-5-32-568"/>  
           </allowAccounts>  
       </net.pipe>  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## Typ  
 `Type`  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|`maxPendingAccepts`|Eine ganze Zahl, die den Höchstwert für ausstehende gleichzeitig annehmende Threads am überwachenden Endpunkt für den Freigabedienst festlegt.  Der Standard ist 2.|  
|`maxPendingConnections`|Eine ganze Zahl, die die maximale Anzahl von Verbindungen angibt, die auf eine Verteilung warten können.  Der Standard ist 100.|  
|`receiveTimeout`|Eine <xref:System.Timespan>, die das Timeout für das Lesen der Rahmendaten und das Ausführen der Verbindungsverteilung der zugrunde liegenden Verbindungen angibt.  Der Standardwert ist "00:00:10".|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<allowAccounts\>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|Eine Auflistung von Konfigurationselementen, die ein `securityIdentifier`\-Attribut zum Angeben von Benutzerkonten für Prozesse enthalten, die [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Dienste hosten und Verbindungszugriff auf den Freigabedienst haben.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<system.serviceModel.activation\>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|Enthält Konfigurationseinstellungen für den Listenerprozess SMSvcHost.exe.|  
  
## Siehe auch  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection>