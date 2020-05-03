---
title: 'Entschärfung: X509CertificateClaimSet.FindClaims-Methode'
ms.date: 03/30/2017
ms.assetid: ee356e3b-f932-48f5-875a-5e42340bee63
ms.openlocfilehash: 0b306960c4f11bb6f54aecaeb13297e7725e16a8
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102644"
---
# <a name="mitigation-x509certificateclaimsetfindclaims-method"></a><span data-ttu-id="34b04-102">Entschärfung: X509CertificateClaimSet.FindClaims-Methode</span><span class="sxs-lookup"><span data-stu-id="34b04-102">Mitigation: X509CertificateClaimSet.FindClaims Method</span></span>

<span data-ttu-id="34b04-103">Ab .NET Framework 4.6.1 wird von der Methode <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> der App versucht, das Argument `claimType` mit allen DNS-Einträgen im zugehörigen SAN-Feld zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="34b04-103">Starting with apps that target .NET Framework 4.6.1, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> method will attempt to match the `claimType` argument with all the DNS entries in its SAN field.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="34b04-104">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="34b04-104">Impact</span></span>  
 <span data-ttu-id="34b04-105">Diese Änderung betrifft nur Apps, die auf Versionen von .NET Framework ab .NET Framework 4.6.1 ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="34b04-105">This change only affects apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1.</span></span>  
  
 <span data-ttu-id="34b04-106">Bei Apps, die auf frühere Versionen von .NET Framework ausgerichtet sind, versucht die <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType>-Methode, das `claimType`-Argument nur mit dem letzten DNS-Eintrag abzustimmen.</span><span class="sxs-lookup"><span data-stu-id="34b04-106">For apps that target previous versions of the .NET Framework, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> method attempts to match the `claimType` argument only with the last  DNS entry.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="34b04-107">Minderung</span><span class="sxs-lookup"><span data-stu-id="34b04-107">Mitigation</span></span>  
 <span data-ttu-id="34b04-108">Ist diese Änderung nicht erwünscht, kann sie für Apps, die für .NET Framework-Versionen ab .NET Framework 4.6.1 vorgesehen sind, deaktiviert werden. Dazu muss dem Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) der App-Konfigurationsdatei die folgende Konfigurationseinstellung hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="34b04-108">If this change is undesirable, apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1 can opt out of it by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" />
</runtime>  
```  
  
 <span data-ttu-id="34b04-109">Für Apps, die für frühere Versionen von .NET Framework vorgesehen sind, aber unter .NET Framework 4.6.1 oder unter höheren Versionen ausgeführt werden, kann dieses Verhalten aktiviert werden, indem dem Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) der App-Konfigurationsdatei die folgende Konfigurationseinstellung hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="34b04-109">In addition, apps that target previous versions of the .NET Framework but are running under the .NET Framework 4.6.1 and later versions can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" />
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="34b04-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34b04-110">See also</span></span>

- [<span data-ttu-id="34b04-111">Anwendungskompatibilität</span><span class="sxs-lookup"><span data-stu-id="34b04-111">Application compatibility</span></span>](application-compatibility.md)
