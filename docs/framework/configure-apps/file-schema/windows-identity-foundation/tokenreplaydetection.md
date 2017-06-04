---
title: "&lt;tokenReplayDetection&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;tokenReplayDetection&gt;
Aktiviert Tokens wiedergaben Auflistungserkennung und gibt die Ablaufzeit für das Token an.  
  
## Syntax  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Typ  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|enabled|Ein Wert, der angibt, ob Token Erkennung wiedergeben, ist aktiviert. „True“ Tokens wiedergaben Auflistungserkennung aktivieren.|  
|expirationPeriod|<xref:System.TimeSpan>, der die maximale Dauer angibt, nach der ein Element als aus dem Cache abgelaufen und entfernt wird.  Weitere Informationen zum Erstellen <xref:System.TimeSpan>\-Werte finden Sie unter angibt [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_TimespanValues).|  
  
### Untergeordnete Elemente  
 None  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Gibt die Identität von Einstellungen auf Dienstebene auf.|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Stellt Konfiguration für eine Auflistung von Sicherheitstoken Ereignishandler bereit.|  
  
## Hinweise  
 Ein Element kann `<tokenReplayDetection>` auf dem Servicelevel unter dem `<identityConfiguration>`\-Element oder in der Auflistung der Klassenhandler Sicherheitstoken angegeben werden, die unter dem Element `<securityTokenHandlerConfiguration>`.  Einstellungen für eine Auflistung von Token für die überschreiben, die auf dem Dienst angegeben werden.  
  
 Der Typ des Tokens besitzt wiedergaben das [\<tokenReplayCache\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)\-Element angegeben.