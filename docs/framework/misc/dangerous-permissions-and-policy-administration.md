---
title: Problematische Berechtigungen und Richtlinienverwaltung
description: Weitere Informationen finden Sie unter Links zu den verschiedenen gefährlichen Berechtigungen in .net. Diese Berechtigungen sollten nur bei Bedarf für vertrauenswürdigen Code erteilt werden.
ms.date: 03/30/2017
helpviewer_keywords:
- permissions [.NET Framework], policy administration
- security [.NET Framework], dangerous permissions
- code security, dangerous permissions
- secure coding, dangerous permissions
- permissions [.NET Framework], dangerous
ms.assetid: 1929e854-23a0-4bb1-94be-e8aa3b609e32
ms.openlocfilehash: a2f4469590fea38924430b07eaf20d49f4dc46e9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556940"
---
# <a name="dangerous-permissions-and-policy-administration"></a><span data-ttu-id="a3c65-104">Problematische Berechtigungen und Richtlinienverwaltung</span><span class="sxs-lookup"><span data-stu-id="a3c65-104">Dangerous Permissions and Policy Administration</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="a3c65-105">Verschiedene der geschützten Operationen, für die von .NET Framework Berechtigungen bereitgestellt werden, ermöglichen unter Umständen die Umgehung des Sicherheitssystems.</span><span class="sxs-lookup"><span data-stu-id="a3c65-105">Several of the protected operations for which the .NET Framework provides permissions can potentially allow the security system to be circumvented.</span></span> <span data-ttu-id="a3c65-106">Diese problematischen Berechtigungen sollten nur bei Bedarf für vertrauenswürdigen Code erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="a3c65-106">These dangerous permissions should be given only to trustworthy code, and then only as necessary.</span></span> <span data-ttu-id="a3c65-107">Es gibt in der Regel keinen Schutz vor bösartigem Code, wenn dem Code diese Berechtigungen gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="a3c65-107">There is usually no defense against malicious code if it is granted these permissions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a3c65-108">In .NET Framework 4 gab es wichtige Änderungen am .NET Framework Sicherheitsmodell und der Terminologie.</span><span class="sxs-lookup"><span data-stu-id="a3c65-108">In the .NET Framework 4, there have been important changes to the .NET Framework security model and terminology.</span></span> <span data-ttu-id="a3c65-109">Weitere Informationen zu diesen Änderungen finden Sie unter [Sicherheitsänderungen](/previous-versions/dotnet/framework/security/security-changes).</span><span class="sxs-lookup"><span data-stu-id="a3c65-109">For more information about these changes, see [Security Changes](/previous-versions/dotnet/framework/security/security-changes).</span></span>  
  
 <span data-ttu-id="a3c65-110">Die problematischen Berechtigungen werden in der folgenden Tabelle erläutert.</span><span class="sxs-lookup"><span data-stu-id="a3c65-110">The dangerous permissions are explained in the following table.</span></span>  
  
|<span data-ttu-id="a3c65-111">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="a3c65-111">Permission</span></span>|<span data-ttu-id="a3c65-112">Mögliches Risiko</span><span class="sxs-lookup"><span data-stu-id="a3c65-112">Potential risk</span></span>|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|<span data-ttu-id="a3c65-113">Ermöglicht es verwaltetem Code, Aufrufe in nicht verwaltetem Code auszuführen. Dies stellt häufig ein Risiko dar.</span><span class="sxs-lookup"><span data-stu-id="a3c65-113">Allows managed code to call into unmanaged code, which is often dangerous.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|<span data-ttu-id="a3c65-114">Ohne eine Überprüfung kann der Code beliebige Aktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="a3c65-114">Without verification, the code can do anything.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|<span data-ttu-id="a3c65-115">Als ungültig erklärte Beweise können die Sicherheitsrichtlinien umgehen.</span><span class="sxs-lookup"><span data-stu-id="a3c65-115">Invalidated evidence can fool security policy.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|<span data-ttu-id="a3c65-116">Durch die Möglichkeit der Änderung von Sicherheitsrichtlinien kann die Sicherheit deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="a3c65-116">The ability to modify security policy can disable security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|<span data-ttu-id="a3c65-117">Durch die Serialisierung können Zugriffsmechanismen umgangen werden.</span><span class="sxs-lookup"><span data-stu-id="a3c65-117">The use of serialization can circumvent accessibility mechanisms.</span></span> <span data-ttu-id="a3c65-118">Weitere Informationen finden Sie unter [Sicherheit und Serialisierung](security-and-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="a3c65-118">For details, see [Security and Serialization](security-and-serialization.md).</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|<span data-ttu-id="a3c65-119">Durch die Fähigkeit zum Festlegen des aktuellen Prinzipals kann die rollenbasierte Sicherheit umgangen werden.</span><span class="sxs-lookup"><span data-stu-id="a3c65-119">The ability to set the current principal can trick role-based security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|<span data-ttu-id="a3c65-120">Die Änderung von Threads ist aufgrund des mit Threads verbundenen Sicherheitszustands riskant.</span><span class="sxs-lookup"><span data-stu-id="a3c65-120">Manipulation of threads is dangerous because of the security state associated with threads.</span></span>|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|<span data-ttu-id="a3c65-121">Kann private Member zur Überwindung von Zugriffsmechanismen verwenden.</span><span class="sxs-lookup"><span data-stu-id="a3c65-121">Can use private members to defeat accessibility mechanisms.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a3c65-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3c65-122">See also</span></span>

- [<span data-ttu-id="a3c65-123">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="a3c65-123">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
