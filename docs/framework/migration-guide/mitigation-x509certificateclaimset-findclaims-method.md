---
title: 'Entschärfung: X509CertificateClaimSet.FindClaims-Methode'
ms.date: 03/30/2017
ms.assetid: ee356e3b-f932-48f5-875a-5e42340bee63
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7fb1eb0c502584caac11ca3dde6e7e646b29cfe
ms.sourcegitcommit: 26f4a7697c32978f6a328c89dc4ea87034065989
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2019
ms.locfileid: "66251096"
---
# <a name="mitigation-x509certificateclaimsetfindclaims-method"></a>Entschärfung: X509CertificateClaimSet.FindClaims-Methode
Ab Apps, die auf .NET Framework 4.6.1 ausgerichtet sind, wird von der Methode <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> versucht, das Argument `claimType` mit allen DNS-Einträgen im zugehörigen SAN-Feld zu vergleichen.  
  
## <a name="impact"></a>Auswirkungen  
 Diese Änderung betrifft nur Apps, die auf Versionen von .NET Framework ab .NET Framework 4.6.1 ausgerichtet sind.  
  
 Bei Apps, die auf frühere Versionen von .NET Framework ausgerichtet sind, versucht die <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType>-Methode, das `claimType`-Argument nur mit dem letzten DNS-Eintrag abzustimmen.  
  
## <a name="mitigation"></a>Minderung  
 Ist diese Änderung nicht erwünscht, kann sie für Apps, die für .NET Framework-Versionen ab .NET Framework 4.6.1 vorgesehen sind, deaktiviert werden. Dazu muss dem Abschnitt [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) der App-Konfigurationsdatei die folgende Konfigurationseinstellung hinzugefügt werden:  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" />   
</runtime>  
```  
  
 Für Apps, die für frühere Versionen von .NET Framework vorgesehen sind, aber unter .NET Framework 4.6.1 oder unter höheren Versionen ausgeführt werden, kann dieses Verhalten aktiviert werden, indem dem Abschnitt [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) der App-Konfigurationsdatei die folgende Konfigurationseinstellung hinzugefügt wird:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" />   
</runtime>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)
