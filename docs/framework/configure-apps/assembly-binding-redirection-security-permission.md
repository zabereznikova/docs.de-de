---
title: Sicherheitsberechtigung für die Umleitung der Assemblybindung
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ef9295028aeb7bfcc6df88e9c8bb7f80e2a31368
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743263"
---
# <a name="assembly-binding-redirection-security-permission"></a><span data-ttu-id="5007d-102">Sicherheitsberechtigung für die Umleitung der Assemblybindung</span><span class="sxs-lookup"><span data-stu-id="5007d-102">Assembly Binding Redirection Security Permission</span></span>
<span data-ttu-id="5007d-103">Für die explizite Umleitung einer Assemblybindung in einer Anwendungskonfigurationsdatei ist eine Sicherheitsberechtigung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5007d-103">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="5007d-104">Dies betrifft die Umleitung von .NET Framework-Assemblys und Assemblys von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="5007d-104">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="5007d-105">Die Berechtigung wird erteilt, indem die <xref:System.Security.Permissions.SecurityPermissionFlag> flag für die <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="5007d-105">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="5007d-106">Verwaltete Assemblys verfügen standardmäßig über keine Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="5007d-106">Managed assemblies have no permissions by default.</span></span>  
  
 <span data-ttu-id="5007d-107">Die Sicherheitsberechtigung erhält Anwendungen, die in der Zone "Vertrauenswürdige" (lokaler Computer) und der Intranetzone ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5007d-107">The security permission is granted to applications running in the Trusted Zone (local machine) and Intranet Zone.</span></span> <span data-ttu-id="5007d-108">Anwendungen, die in der Internetzone ausgeführt strikt untersagt, Umleitung der Assemblybindung ausführen.</span><span class="sxs-lookup"><span data-stu-id="5007d-108">Applications running in the Internet Zone are strictly prohibited from performing assembly binding redirection.</span></span>  
  
 <span data-ttu-id="5007d-109">Die Berechtigung ist nicht erforderlich, wenn Assemblyumleitungen durchgeführt wird, in eine Herausgeberrichtliniendatei, die vom Komponentenherausgeber gesteuert wird, oder in die Konfigurationsdatei des Computers, die vom Administrator gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="5007d-109">The permission is not required if assembly redirection is performed in a publisher policy file that is controlled by the component publisher, or in the machine configuration file that is controlled by the administrator.</span></span> <span data-ttu-id="5007d-110">Die Berechtigung ist jedoch erforderlich, damit eine Anwendung explizit ignorieren Herausgeberrichtlinie mithilfe der [ \<PublisherPolicy gelten = "no" / >](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) Element in der Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="5007d-110">However, the permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span>  
  
 <span data-ttu-id="5007d-111">Die folgende Tabelle zeigt die Sicherheitseinstellungen für die **BindingRedirects** Flag.</span><span class="sxs-lookup"><span data-stu-id="5007d-111">The following table shows the default security settings for the **BindingRedirects** flag.</span></span>  
  
|<span data-ttu-id="5007d-112">Zone</span><span class="sxs-lookup"><span data-stu-id="5007d-112">Zone</span></span>|<span data-ttu-id="5007d-113">BindingRedirects-Flags</span><span class="sxs-lookup"><span data-stu-id="5007d-113">BindingRedirects flag setting</span></span>|  
|----------|-----------------------------------|  
|<span data-ttu-id="5007d-114">Vertrauenswürdige Zone (lokaler Computer)</span><span class="sxs-lookup"><span data-stu-id="5007d-114">Trusted Zone (local machine)</span></span>|<span data-ttu-id="5007d-115">**ON**</span><span class="sxs-lookup"><span data-stu-id="5007d-115">**ON**</span></span>|  
|<span data-ttu-id="5007d-116">Intranet-Zone</span><span class="sxs-lookup"><span data-stu-id="5007d-116">Intranet Zone</span></span>|<span data-ttu-id="5007d-117">**ON**</span><span class="sxs-lookup"><span data-stu-id="5007d-117">**ON**</span></span>|  
|<span data-ttu-id="5007d-118">Internetzone</span><span class="sxs-lookup"><span data-stu-id="5007d-118">Internet Zone</span></span>|<span data-ttu-id="5007d-119">**OFF**</span><span class="sxs-lookup"><span data-stu-id="5007d-119">**OFF**</span></span>|  
|<span data-ttu-id="5007d-120">Nicht vertrauenswürdige Zonen</span><span class="sxs-lookup"><span data-stu-id="5007d-120">Untrusted zones</span></span>|<span data-ttu-id="5007d-121">**OFF**</span><span class="sxs-lookup"><span data-stu-id="5007d-121">**OFF**</span></span>|  
  
 <span data-ttu-id="5007d-122">Ein Administrator kann diese Sicherheitseinstellungen zum unterstützen oder Einschränken von spezifischen Szenarien auf einem bestimmten Computer ändern.</span><span class="sxs-lookup"><span data-stu-id="5007d-122">An administrator can change these security settings to support or restrict specific scenarios on a given computer.</span></span> <span data-ttu-id="5007d-123">Es sind keine Tools zum Ändern der **BindingRedirects** Flag festlegen, die von der Standardeinstellung; ein Administrator muss die Security.config-Datei auf dem Computer eines Benutzers manuell bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="5007d-123">There are no tools for changing the **BindingRedirects** flag setting from the default; an administrator must manually edit the Security.config file on a user's computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5007d-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5007d-124">See Also</span></span>  
 [<span data-ttu-id="5007d-125">Herausgeberrichtliniendateien und Seite-an-Seite-Ausführung</span><span class="sxs-lookup"><span data-stu-id="5007d-125">Publisher Policy Files and Side-by-Side Execution</span></span>](http://msdn.microsoft.com/library/97a042be-4d72-40c3-91c0-76fd36bdf133)  
 [<span data-ttu-id="5007d-126">Gewusst wie: Aktivieren und Deaktivieren der Bindungsumleitung</span><span class="sxs-lookup"><span data-stu-id="5007d-126">How to: Enable and Disable Automatic Binding Redirection</span></span>](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)  
 [<span data-ttu-id="5007d-127">Parallele Ausführung</span><span class="sxs-lookup"><span data-stu-id="5007d-127">Side-by-Side Execution</span></span>](../../../docs/framework/deployment/side-by-side-execution.md)
