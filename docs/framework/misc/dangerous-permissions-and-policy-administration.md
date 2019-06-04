---
title: Problematische Berechtigungen und Richtlinienverwaltung
ms.date: 03/30/2017
helpviewer_keywords:
- permissions [.NET Framework], policy administration
- security [.NET Framework], dangerous permissions
- code security, dangerous permissions
- secure coding, dangerous permissions
- permissions [.NET Framework], dangerous
ms.assetid: 1929e854-23a0-4bb1-94be-e8aa3b609e32
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 17a596d9fc223dc53268ae9c91f7d02357b0a9b8
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489976"
---
# <a name="dangerous-permissions-and-policy-administration"></a><span data-ttu-id="3634c-102">Problematische Berechtigungen und Richtlinienverwaltung</span><span class="sxs-lookup"><span data-stu-id="3634c-102">Dangerous Permissions and Policy Administration</span></span>
<span data-ttu-id="3634c-103">Verschiedene der geschützten Operationen, für die von .NET Framework Berechtigungen bereitgestellt werden, ermöglichen unter Umständen die Umgehung des Sicherheitssystems.</span><span class="sxs-lookup"><span data-stu-id="3634c-103">Several of the protected operations for which the .NET Framework provides permissions can potentially allow the security system to be circumvented.</span></span> <span data-ttu-id="3634c-104">Diese problematischen Berechtigungen sollten nur bei Bedarf für vertrauenswürdigen Code erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="3634c-104">These dangerous permissions should be given only to trustworthy code, and then only as necessary.</span></span> <span data-ttu-id="3634c-105">Es gibt in der Regel keinen Schutz vor bösartigem Code, wenn dem Code diese Berechtigungen gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="3634c-105">There is usually no defense against malicious code if it is granted these permissions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3634c-106">In .NET Framework 4 wurden wichtige Änderungen an die .NET Framework-Sicherheitsmodell und die Terminologie.</span><span class="sxs-lookup"><span data-stu-id="3634c-106">In the .NET Framework 4, there have been important changes to the .NET Framework security model and terminology.</span></span> <span data-ttu-id="3634c-107">Weitere Informationen zu diesen Änderungen finden Sie unter [Sicherheitsänderungen](../../../docs/framework/security/security-changes.md).</span><span class="sxs-lookup"><span data-stu-id="3634c-107">For more information about these changes, see [Security Changes](../../../docs/framework/security/security-changes.md).</span></span>  
  
 <span data-ttu-id="3634c-108">Die problematischen Berechtigungen werden in der folgenden Tabelle erläutert.</span><span class="sxs-lookup"><span data-stu-id="3634c-108">The dangerous permissions are explained in the following table.</span></span>  
  
|<span data-ttu-id="3634c-109">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="3634c-109">Permission</span></span>|<span data-ttu-id="3634c-110">Mögliches Risiko</span><span class="sxs-lookup"><span data-stu-id="3634c-110">Potential risk</span></span>|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|<span data-ttu-id="3634c-111">Ermöglicht es verwaltetem Code, Aufrufe in nicht verwaltetem Code auszuführen. Dies stellt häufig ein Risiko dar.</span><span class="sxs-lookup"><span data-stu-id="3634c-111">Allows managed code to call into unmanaged code, which is often dangerous.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|<span data-ttu-id="3634c-112">Ohne eine Überprüfung kann der Code beliebige Aktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="3634c-112">Without verification, the code can do anything.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|<span data-ttu-id="3634c-113">Als ungültig erklärte Beweise können die Sicherheitsrichtlinien umgehen.</span><span class="sxs-lookup"><span data-stu-id="3634c-113">Invalidated evidence can fool security policy.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|<span data-ttu-id="3634c-114">Durch die Möglichkeit der Änderung von Sicherheitsrichtlinien kann die Sicherheit deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="3634c-114">The ability to modify security policy can disable security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|<span data-ttu-id="3634c-115">Durch die Serialisierung können Zugriffsmechanismen umgangen werden.</span><span class="sxs-lookup"><span data-stu-id="3634c-115">The use of serialization can circumvent accessibility mechanisms.</span></span> <span data-ttu-id="3634c-116">Weitere Informationen finden Sie unter [Sicherheit und Serialisierung](../../../docs/framework/misc/security-and-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="3634c-116">For details, see [Security and Serialization](../../../docs/framework/misc/security-and-serialization.md).</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|<span data-ttu-id="3634c-117">Durch die Fähigkeit zum Festlegen des aktuellen Prinzipals kann die rollenbasierte Sicherheit umgangen werden.</span><span class="sxs-lookup"><span data-stu-id="3634c-117">The ability to set the current principal can trick role-based security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|<span data-ttu-id="3634c-118">Die Änderung von Threads ist aufgrund des mit Threads verbundenen Sicherheitszustands riskant.</span><span class="sxs-lookup"><span data-stu-id="3634c-118">Manipulation of threads is dangerous because of the security state associated with threads.</span></span>|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|<span data-ttu-id="3634c-119">Kann private Member zur Überwindung von Zugriffsmechanismen verwenden.</span><span class="sxs-lookup"><span data-stu-id="3634c-119">Can use private members to defeat accessibility mechanisms.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3634c-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3634c-120">See also</span></span>

- [<span data-ttu-id="3634c-121">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="3634c-121">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
