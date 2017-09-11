---
title: "Entschärfung: ClaimsIdentity-Konstruktor"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 946903f1-0fbf-4f67-805b-1eb48352024d
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a50cbd69aa1f2c72adc9fc4d10a070f5faa0cf54
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-claimsidentity-constructor"></a><span data-ttu-id="ca441-102">Entschärfung: ClaimsIdentity-Konstruktor</span><span class="sxs-lookup"><span data-stu-id="ca441-102">Mitigation: ClaimsIdentity Constructor</span></span>
<span data-ttu-id="ca441-103">Beginnend mit [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] gibt es eine Änderung in der Weise, wie der <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=fullName>-Konstruktor die <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName>-Eigenschaft festlegt.</span><span class="sxs-lookup"><span data-stu-id="ca441-103">Starting with the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], there is change in how the <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=fullName> constructor sets the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> property.</span></span> <span data-ttu-id="ca441-104">Wenn es sich bei dem <xref:System.Security.Principal.IIdentity>-Argument um ein <xref:System.Security.Claims.ClaimsIdentity>-Objekt handelt und die <xref:System.Security.Claims.ClaimsIdentity.Actor%2A>-Eigenschaft des <xref:System.Security.Claims.ClaimsIdentity>-Objekts nicht `null` ist, wird die <xref:System.Security.Claims.ClaimsIdentity.Actor%2A>-Eigenschaft mithilfe der <xref:System.Security.Claims.ClaimsIdentity.Clone%2A?displayProperty=fullName>-Methode angefügt.</span><span class="sxs-lookup"><span data-stu-id="ca441-104">If the <xref:System.Security.Principal.IIdentity> argument is a <xref:System.Security.Claims.ClaimsIdentity> object, and the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> property of that <xref:System.Security.Claims.ClaimsIdentity> object is not `null`, the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> property is attached by using the <xref:System.Security.Claims.ClaimsIdentity.Clone%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="ca441-105">In [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] wird die <xref:System.Security.Claims.ClaimsIdentity.Actor%2A>-Eigenschaft als vorhandener Verweis angefügt.</span><span class="sxs-lookup"><span data-stu-id="ca441-105">In the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> property is attached as a  existing reference.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="ca441-106">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="ca441-106">Impact</span></span>  
 <span data-ttu-id="ca441-107">Beginnend mit [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] ist die <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName>-Eigenschaft des neuen <xref:System.Security.Claims.ClaimsIdentity>-Objekts nicht gleich der <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName>-Eigenschaft des <xref:System.Security.Principal.IIdentity>-Arguments des Konstruktors.</span><span class="sxs-lookup"><span data-stu-id="ca441-107">Starting with the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> property of the new <xref:System.Security.Claims.ClaimsIdentity> object is not equal to the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> property of the constructor's <xref:System.Security.Principal.IIdentity> argument.</span></span> <span data-ttu-id="ca441-108">In [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] und früheren Versionen ist sie gleich.</span><span class="sxs-lookup"><span data-stu-id="ca441-108">In the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier versions, it is equal.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="ca441-109">Problemumgehung</span><span class="sxs-lookup"><span data-stu-id="ca441-109">Mitigation</span></span>  
 <span data-ttu-id="ca441-110">Wenn dieses Verhalten nicht erwünscht ist, können Sie das vorherige Verhalten wiederherstellen, indem Sie den `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity`-Schalter in Ihrer Anwendungskonfigurationsdatei auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="ca441-110">If this behavior is undesirable, you can restore the previous behavior by setting the `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` switch in your application configuration file to `true`.</span></span> <span data-ttu-id="ca441-111">Dazu müssen Sie dem Abschnitt [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer web.config-Datei Folgendes hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="ca441-111">This requires that you add the following to  the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your web.config file:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <AppContextSwitchOverrides value="Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity=true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ca441-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca441-112">See Also</span></span>  
 [<span data-ttu-id="ca441-113">Neuausrichtungsänderungen</span><span class="sxs-lookup"><span data-stu-id="ca441-113">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

