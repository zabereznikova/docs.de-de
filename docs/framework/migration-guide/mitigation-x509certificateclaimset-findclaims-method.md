---
title: 'Entschärfung: X509CertificateClaimSet.FindClaims-Methode'
ms.date: 03/30/2017
ms.assetid: ee356e3b-f932-48f5-875a-5e42340bee63
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e3b3645d9fc00087e163b9200edb5fbcf0dbbd9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59217210"
---
# <a name="mitigation-x509certificateclaimsetfindclaims-method"></a><span data-ttu-id="47127-102">Entschärfung: X509CertificateClaimSet.FindClaims-Methode</span><span class="sxs-lookup"><span data-stu-id="47127-102">Mitigation: X509CertificateClaimSet.FindClaims Method</span></span>
<span data-ttu-id="47127-103">Beginnend mit Apps, die auf [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgerichtet sind, versucht die <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType>-Methode das `claimType`-Argument mit allen DNS-Einträgen in seinem SAN-Feld zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="47127-103">Starting with apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)],  the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> method will attempt to match the `claimType` argument with all the DNS entries in its SAN field.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="47127-104">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="47127-104">Impact</span></span>  
 <span data-ttu-id="47127-105">Diese Änderung betrifft nur Apps, die auf Versionen von .NET Framework ausgerichtet sind, die mit [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] beginnen.</span><span class="sxs-lookup"><span data-stu-id="47127-105">This change only affects apps that target versions of the .NET Framework starting with the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].</span></span>  
  
 <span data-ttu-id="47127-106">Bei Apps, die auf frühere Versionen von .NET Framework ausgerichtet sind, versucht die <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType>-Methode, das `claimType`-Argument nur mit dem letzten DNS-Eintrag abzustimmen.</span><span class="sxs-lookup"><span data-stu-id="47127-106">For apps that target previous versions of the .NET Framework, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> method attempts to match the `claimType` argument only with the last  DNS entry.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="47127-107">Minderung</span><span class="sxs-lookup"><span data-stu-id="47127-107">Mitigation</span></span>  
 <span data-ttu-id="47127-108">Ist diese Änderung nicht erwünscht, kann sie für Apps, die auf Versionen von .NET Framework ausgerichtet sind, die mit [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] beginnen, abgelehnt werden. Dazu muss dem [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)-Abschnitt der Konfigurationsdatei der App die folgende Konfigurationseinstellung hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="47127-108">If this change is undesirable, apps that target versions of the .NET Framework starting with the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] can opt out of it by adding the following configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" />   
</runtime>  
```  
  
 <span data-ttu-id="47127-109">Für Apps, die für frühere Versionen von .NET Framework vorgesehen sind, aber unter [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] und höheren Versionen ausgeführt werden, kann dieses Verhalten übernommen werden, indem dem [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)-Abschnitt der Konfigurationsdatei der Anwendung die folgende Konfigurationseinstellung hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="47127-109">In addition, apps that target previous versions of the .NET Framework but are running under the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and later versions can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" />   
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="47127-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47127-110">See also</span></span>

- [<span data-ttu-id="47127-111">Neuausrichtungsänderungen</span><span class="sxs-lookup"><span data-stu-id="47127-111">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)
