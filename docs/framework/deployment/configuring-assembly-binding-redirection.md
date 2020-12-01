---
title: Konfigurieren der Umleitung der Assemblybindung
description: Erfahren Sie, wie Sie in .NET die Bindungsumleitung von Assemblys konfigurieren, indem Sie das applyTo-Attribut im assemblyBinding-Element einer Anwendungskonfigurationsdatei verwenden.
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: d266cbd8-bf91-41d1-baf0-afbc481a741f
ms.openlocfilehash: 2455cab19132a208fb99454d4131363a624315c5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236376"
---
# <a name="configuring-assembly-binding-redirection"></a><span data-ttu-id="b60c0-103">Konfigurieren der Umleitung der Assemblybindung</span><span class="sxs-lookup"><span data-stu-id="b60c0-103">Configuring Assembly Binding Redirection</span></span>

<span data-ttu-id="b60c0-104">Standardmäßig verwenden Anwendungen eine Reihe von .NET Framework-Assemblys, die mit der Laufzeitversion bereitgestellt werden, die zum Kompilieren der Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b60c0-104">By default, applications use the set of .NET Framework assemblies that shipped with the runtime version used to compile the application.</span></span> <span data-ttu-id="b60c0-105">Mithilfe des **appliesTo**-Attributs im [\<assemblyBinding>](../configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md)-Element in einer Anwendungskonfigurationsdatei können Sie Assemblybindungsverweise zu einer bestimmten Version der .NET Framework-Assemblys umleiten.</span><span class="sxs-lookup"><span data-stu-id="b60c0-105">You can use the **appliesTo** attribute on the [\<assemblyBinding>](../configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md) element in an application configuration file to redirect assembly binding references to a specific version of the .NET Framework assemblies.</span></span> <span data-ttu-id="b60c0-106">Dieses optionale Attribut verwendet eine .NET Framework-Versionsnummer, um anzugeben, welche Version verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b60c0-106">This optional attribute uses a .NET Framework version number to indicate which version it applies to.</span></span> <span data-ttu-id="b60c0-107">Ohne Angabe eines **appliesTo**-Attributs gilt das **\<assemblyBinding>** -Element für alle Versionen von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b60c0-107">If no **appliesTo** attribute is specified, the **\<assemblyBinding>** element applies to all versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="b60c0-108">Das **appliesTo**-Attribut wurde mit .NET Framework Version 1.1 eingeführt. Es wird von .NET Framework Version 1.0 ignoriert.</span><span class="sxs-lookup"><span data-stu-id="b60c0-108">The **appliesTo** attribute was introduced in the .NET Framework version 1.1; it is ignored by the .NET Framework version 1.0.</span></span> <span data-ttu-id="b60c0-109">Dies bedeutet, dass alle **\<assemblyBinding>** -Elemente bei Verwendung von .NET Framework Version 1.0 angewendet werden, auch wenn das **appliesTo**-Attribut angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="b60c0-109">This means that all **\<assemblyBinding>** elements are applied when using the .NET Framework version 1.0, even if an **appliesTo** attribute is specified.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b60c0-110">Verwenden Sie das **appliesTo**-Attribut, um die Umleitung der Assemblybindung auf eine spezielle Version der Runtime zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="b60c0-110">Use the **appliesTo** attribute to limit assembly binding redirection to a specific version of the runtime.</span></span>  
  
 <span data-ttu-id="b60c0-111">Um zum Beispiel die Assemblybindung einer .NET Framework 1.0-Assembly umzuleiten, müssten Sie den folgenden XML-Code in die Anwendungskonfigurationsdatei einfügen.</span><span class="sxs-lookup"><span data-stu-id="b60c0-111">For example, to redirect assembly binding for a .NET Framework version 1.0 assembly, you would include the following XML code in your application configuration file.</span></span>  
  
```xml  
<runtime>  
        <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
            <dependentAssembly>
               * assembly information goes here *  
            </dependentAssembly>  
       </assemblyBinding>  
</runtime>  
```  
  
 <span data-ttu-id="b60c0-112">Bei **\<assemblyBinding>** -Elemente wird die Reihenfolge beachtet.</span><span class="sxs-lookup"><span data-stu-id="b60c0-112">The **\<assemblyBinding>** elements are order-sensitive.</span></span> <span data-ttu-id="b60c0-113">Sie sollten zuerst Umleitungsinformationen für die Assemlybindungen aller .NET Framework 1.0-Assemblys eingeben, gefolgt von den Umleitungsinformationen für die Assemblybindungen beliebiger .NET Framework 1.1-Assemblys.</span><span class="sxs-lookup"><span data-stu-id="b60c0-113">You should enter assembly binding redirection information for any .NET Framework version 1.0 assemblies first, followed by assembly binding redirection information for any .NET Framework version 1.1 assemblies.</span></span> <span data-ttu-id="b60c0-114">Geben Sie zuletzt die Informationen zum Umleiten der Assemblybindung für alle .NET Framework-Assemblyumleitungen ein, bei denen nicht das **appliesTo** -Attribut verwendet wird und die daher für alle Versionen .NET Framework-Versionen gelten.</span><span class="sxs-lookup"><span data-stu-id="b60c0-114">Finally, enter assembly binding redirection information for any .NET Framework assembly redirection that does not use the **appliesTo** attribute and therefore applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="b60c0-115">Falls bei der Umleitung Konflikte auftreten, wird die erste passende Umleitungsanweisung in der Konfigurationsdatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="b60c0-115">In case of a conflict in redirection, the first matching redirection statement in the configuration file is used.</span></span>  
  
 <span data-ttu-id="b60c0-116">Beispiel: Zum Umleiten eines Verweises auf eine .NET Framework 1.0-Assembly und eines anderen Verweises auf eine .NET Framework 1.1-Assembly müssten Sie nach dem Muster im folgenden Pseudocode vorgehen.</span><span class="sxs-lookup"><span data-stu-id="b60c0-116">For example, to redirect one reference to a .NET Framework version 1.0 assembly and another reference to a .NET Framework version 1.1 assembly, you would use the pattern shown in the following pseudocode.</span></span>  
  
```xml  
<assemblyBinding xmlns="..." appliesTo="v1.0.3705">
  <!-- .NET Framework version 1.0 redirects here. -->
</assemblyBinding>
  
<assemblyBinding xmlns="..." appliesTo="v1.1.4322">
  <!-- .NET Framework version 1.1 redirects here. -->
</assemblyBinding>
  
<assemblyBinding xmlns="...">
  <!-- Redirects meant for all versions of the .NET Framework. -->
</assemblyBinding>  
```  
  
## <a name="debugging-configuration-file-errors"></a><span data-ttu-id="b60c0-117">Fehler beim Debuggen der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="b60c0-117">Debugging Configuration File Errors</span></span>  

 <span data-ttu-id="b60c0-118">Die Laufzeit analysiert Konfigurationsdateien einmal, wenn eine Anwendungsdomäne erstellt wird, und lädt dann Code in diese Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="b60c0-118">The runtime parses configuration files once when an application domain is created, and loads code into that application domain.</span></span> <span data-ttu-id="b60c0-119">Die Common Language Runtime behandelt Fehler in einer Konfigurationsdatei, indem der jeweilige Eintrag ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="b60c0-119">The common language runtime handles errors in a configuration file by ignoring the entry.</span></span> <span data-ttu-id="b60c0-120">Zur Laufzeit wird die gesamte Konfigurationsdatei ignoriert, wenn sie fehlerhaft formatierte XLM enthält.</span><span class="sxs-lookup"><span data-stu-id="b60c0-120">The runtime ignores the entire configuration file if it contains malformed XML.</span></span> <span data-ttu-id="b60c0-121">Bei ungültiger XML werden nur die ungültigen Abschnitte ignoriert.</span><span class="sxs-lookup"><span data-stu-id="b60c0-121">For invalid XML, only the invalid sections are ignored.</span></span>  
  
 <span data-ttu-id="b60c0-122">Sie können feststellen, ob eine Konfigurationsdatei genutzt wird, indem Sie ermitteln, ob Umleitungen der Assemblybindung auftreten.</span><span class="sxs-lookup"><span data-stu-id="b60c0-122">You can determine whether a configuration file is being used by determining whether assembly binding redirects are occurring.</span></span> <span data-ttu-id="b60c0-123">Verwenden Sie die [Assemblybindungs-Protokollanzeige (Fuslogvw.exe)](../tools/fuslogvw-exe-assembly-binding-log-viewer.md), um zu sehen, welche Assemblys geladen werden.</span><span class="sxs-lookup"><span data-stu-id="b60c0-123">Use the [Assembly Binding Log Viewer (Fuslogvw.exe)](../tools/fuslogvw-exe-assembly-binding-log-viewer.md) to see which assemblies are being loaded.</span></span> <span data-ttu-id="b60c0-124">Um alle Assemblybindungen anzuzeigen, müssen Sie in der Registrierung einen Eintrag für **ForceLog** anlegen.</span><span class="sxs-lookup"><span data-stu-id="b60c0-124">To see all assembly binds, you must set an entry for **ForceLog** in the registry.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b60c0-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b60c0-125">See also</span></span>

- [<span data-ttu-id="b60c0-126">How to: Aktivieren und Deaktivieren der Bindungsumleitung</span><span class="sxs-lookup"><span data-stu-id="b60c0-126">How to: Enable and Disable Automatic Binding Redirection</span></span>](../configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)
