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
ms.openlocfilehash: b9b9ac5c4e8ce08b9f926b0cdf7149dbdd9ac2da
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43388965"
---
# <a name="assembly-binding-redirection-security-permission"></a><span data-ttu-id="2ec31-102">Sicherheitsberechtigung für die Umleitung der Assemblybindung</span><span class="sxs-lookup"><span data-stu-id="2ec31-102">Assembly Binding Redirection Security Permission</span></span>
<span data-ttu-id="2ec31-103">Für die explizite Umleitung einer Assemblybindung in einer Anwendungskonfigurationsdatei ist eine Sicherheitsberechtigung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2ec31-103">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="2ec31-104">Dies betrifft die Umleitung von .NET Framework-Assemblys und Assemblys von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="2ec31-104">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="2ec31-105">Die Berechtigung wird erteilt, indem die <xref:System.Security.Permissions.SecurityPermissionFlag> flag für die <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="2ec31-105">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="2ec31-106">Verwaltete Assemblys verfügen standardmäßig über keine Berechtigungen zu.</span><span class="sxs-lookup"><span data-stu-id="2ec31-106">Managed assemblies have no permissions by default.</span></span>  
  
 <span data-ttu-id="2ec31-107">Anwendungen, die in der Zone der vertrauenswürdigen (lokaler Computer) und der Intranetzone ausgeführt wird die Sicherheitsberechtigung gewährt.</span><span class="sxs-lookup"><span data-stu-id="2ec31-107">The security permission is granted to applications running in the Trusted Zone (local machine) and Intranet Zone.</span></span> <span data-ttu-id="2ec31-108">Anwendungen, die in der Internetzone ausgeführt werden streng untersagt, von der Durchführung der Umleitung der Assemblybindung.</span><span class="sxs-lookup"><span data-stu-id="2ec31-108">Applications running in the Internet Zone are strictly prohibited from performing assembly binding redirection.</span></span>  
  
 <span data-ttu-id="2ec31-109">Die Berechtigung ist nicht erforderlich, wenn Assemblyumleitungen durchgeführt wird, in eine Herausgeberrichtliniendatei, die von der Komponentenherausgeber gesteuert wird, oder in der Konfigurationsdatei des Computers ein, die vom Administrator gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="2ec31-109">The permission is not required if assembly redirection is performed in a publisher policy file that is controlled by the component publisher, or in the machine configuration file that is controlled by the administrator.</span></span> <span data-ttu-id="2ec31-110">Die Berechtigung ist jedoch erforderlich, damit eine Anwendung explizit ignoriert Herausgeberrichtlinie mithilfe der [ \<PublisherPolicy anwenden = "no" / >](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) Element in der Konfigurationsdatei der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2ec31-110">However, the permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span>  
  
 <span data-ttu-id="2ec31-111">Die folgende Tabelle zeigt die Sicherheitseinstellungen für die **BindingRedirects** Flag.</span><span class="sxs-lookup"><span data-stu-id="2ec31-111">The following table shows the default security settings for the **BindingRedirects** flag.</span></span>  
  
|<span data-ttu-id="2ec31-112">Zone</span><span class="sxs-lookup"><span data-stu-id="2ec31-112">Zone</span></span>|<span data-ttu-id="2ec31-113">BindingRedirects-Flags</span><span class="sxs-lookup"><span data-stu-id="2ec31-113">BindingRedirects flag setting</span></span>|  
|----------|-----------------------------------|  
|<span data-ttu-id="2ec31-114">Vertrauenswürdigen Zone (lokaler Computer)</span><span class="sxs-lookup"><span data-stu-id="2ec31-114">Trusted Zone (local machine)</span></span>|<span data-ttu-id="2ec31-115">**ON**</span><span class="sxs-lookup"><span data-stu-id="2ec31-115">**ON**</span></span>|  
|<span data-ttu-id="2ec31-116">Intranetzone</span><span class="sxs-lookup"><span data-stu-id="2ec31-116">Intranet Zone</span></span>|<span data-ttu-id="2ec31-117">**ON**</span><span class="sxs-lookup"><span data-stu-id="2ec31-117">**ON**</span></span>|  
|<span data-ttu-id="2ec31-118">Internetzone</span><span class="sxs-lookup"><span data-stu-id="2ec31-118">Internet Zone</span></span>|<span data-ttu-id="2ec31-119">**OFF**</span><span class="sxs-lookup"><span data-stu-id="2ec31-119">**OFF**</span></span>|  
|<span data-ttu-id="2ec31-120">Nicht vertrauenswürdige Zonen</span><span class="sxs-lookup"><span data-stu-id="2ec31-120">Untrusted zones</span></span>|<span data-ttu-id="2ec31-121">**OFF**</span><span class="sxs-lookup"><span data-stu-id="2ec31-121">**OFF**</span></span>|  
  
 <span data-ttu-id="2ec31-122">Diese Sicherheitseinstellungen für die Unterstützung oder bestimmte Szenarien auf einem Computer zu beschränken, kann ein Administrator ändern.</span><span class="sxs-lookup"><span data-stu-id="2ec31-122">An administrator can change these security settings to support or restrict specific scenarios on a given computer.</span></span> <span data-ttu-id="2ec31-123">Es sind keine Tools zum Ändern der **BindingRedirects** Flag, das auf den Standard die Security.config-Datei auf dem Computer eines Benutzers muss von ein Administrator manuell bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="2ec31-123">There are no tools for changing the **BindingRedirects** flag setting from the default; an administrator must manually edit the Security.config file on a user's computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ec31-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ec31-124">See Also</span></span>  
 [<span data-ttu-id="2ec31-125">Herausgeberrichtliniendateien und Seite-an-Seite-Ausführung</span><span class="sxs-lookup"><span data-stu-id="2ec31-125">Publisher Policy Files and Side-by-Side Execution</span></span>](https://msdn.microsoft.com/library/97a042be-4d72-40c3-91c0-76fd36bdf133)  
 [<span data-ttu-id="2ec31-126">Gewusst wie: Aktivieren und Deaktivieren der Bindungsumleitung</span><span class="sxs-lookup"><span data-stu-id="2ec31-126">How to: Enable and Disable Automatic Binding Redirection</span></span>](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)  
 [<span data-ttu-id="2ec31-127">Parallele Ausführung</span><span class="sxs-lookup"><span data-stu-id="2ec31-127">Side-by-Side Execution</span></span>](../../../docs/framework/deployment/side-by-side-execution.md)
