---
title: "Problemumgehung: X509CertificiateClaimSet.FindClaims-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ee356e3b-f932-48f5-875a-5e42340bee63
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 3
---
# Problemumgehung: X509CertificiateClaimSet.FindClaims-Methode
Beginnend mit Apps, die auf [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgerichtet sind, versucht die <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName>\-Methode das `claimType`\-Argument mit allen DNS\-Einträgen in seinem SAN\-Feld zu vergleichen.  
  
## Auswirkungen  
 Diese Änderung wirkt sich nur auf Apps aus, die auf [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgerichtet sind.  
  
 Bei Apps, die auf frühere Versionen von .NET Framework ausgerichtet sind, versucht die <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName>\-Methode, das `claimType`\-Argument nur mit den letzten DNS\-Eintrag abzustimmen.  
  
## Problemumgehung  
 Ist diese Änderung nicht erwünscht, kann sie für Apps, die für [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] vorgesehen sind, abgelehnt werden. Dazu muss dem [\<runtime\>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)\-Abschnitt der Konfigurationsdatei der App die folgende Konfigurationseinstellung hinzugefügt werden:  
  
```xml  
  
<runtime> <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" /> </runtime>  
  
```  
  
 Für Apps, die für frühere Versionen von .NET Framework vorgesehen sind, aber unter [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgeführt werden, kann dieses Verhalten übernommen werden, indem dem [\<runtime\>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)\-Abschnitt der Konfigurationsdatei der Anwendung die folgende Konfigurationseinstellung hinzugefügt wird:  
  
```xml  
  
<runtime> <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" /> </runtime>  
  
```  
  
## Siehe auch  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)