---
title: Konfigurieren der Umleitung der Assemblybindung
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: d266cbd8-bf91-41d1-baf0-afbc481a741f
ms.openlocfilehash: c7b9dcb99e08a1ef2844c5811897aa87ff86f866
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716555"
---
# <a name="configuring-assembly-binding-redirection"></a><span data-ttu-id="cf7da-102">Konfigurieren der Umleitung der Assemblybindung</span><span class="sxs-lookup"><span data-stu-id="cf7da-102">Configuring Assembly Binding Redirection</span></span>
<span data-ttu-id="cf7da-103">Standardmäßig verwenden Anwendungen eine Reihe von .NET Framework-Assemblys, die mit der Laufzeitversion bereitgestellt werden, die zum Kompilieren der Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cf7da-103">By default, applications use the set of .NET Framework assemblies that shipped with the runtime version used to compile the application.</span></span> <span data-ttu-id="cf7da-104">Mithilfe des **appliesTo**-Attributs im [\<assemblyBinding>](../configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md)-Element in einer Anwendungskonfigurationsdatei können Sie Assemblybindungsverweise zu einer bestimmten Version der .NET Framework-Assemblys umleiten.</span><span class="sxs-lookup"><span data-stu-id="cf7da-104">You can use the **appliesTo** attribute on the [\<assemblyBinding>](../configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md) element in an application configuration file to redirect assembly binding references to a specific version of the .NET Framework assemblies.</span></span> <span data-ttu-id="cf7da-105">Dieses optionale Attribut verwendet eine .NET Framework-Versionsnummer, um anzugeben, welche Version verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cf7da-105">This optional attribute uses a .NET Framework version number to indicate which version it applies to.</span></span> <span data-ttu-id="cf7da-106">Ohne Angabe eines **appliesTo**-Attributs gilt das **\<assemblyBinding>** -Element für alle Versionen von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cf7da-106">If no **appliesTo** attribute is specified, the **\<assemblyBinding>** element applies to all versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="cf7da-107">Das **appliesTo**-Attribut wurde mit .NET Framework Version 1.1 eingeführt. Es wird von .NET Framework Version 1.0 ignoriert.</span><span class="sxs-lookup"><span data-stu-id="cf7da-107">The **appliesTo** attribute was introduced in the .NET Framework version 1.1; it is ignored by the .NET Framework version 1.0.</span></span> <span data-ttu-id="cf7da-108">Dies bedeutet, dass alle **\<assemblyBinding>** -Elemente bei Verwendung von .NET Framework Version 1.0 angewendet werden, auch wenn das **appliesTo**-Attribut angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="cf7da-108">This means that all **\<assemblyBinding>** elements are applied when using the .NET Framework version 1.0, even if an **appliesTo** attribute is specified.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cf7da-109">Verwenden Sie das **appliesTo**-Attribut, um die Umleitung der Assemblybindung auf eine spezielle Version der Runtime zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="cf7da-109">Use the **appliesTo** attribute to limit assembly binding redirection to a specific version of the runtime.</span></span>  
  
 <span data-ttu-id="cf7da-110">Um zum Beispiel die Assemblybindung einer .NET Framework 1.0-Assembly umzuleiten, müssten Sie den folgenden XML-Code in die Anwendungskonfigurationsdatei einfügen.</span><span class="sxs-lookup"><span data-stu-id="cf7da-110">For example, to redirect assembly binding for a .NET Framework version 1.0 assembly, you would include the following XML code in your application configuration file.</span></span>  
  
```xml  
<runtime>  
        <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
            <dependentAssembly>   
               * assembly information goes here *  
            </dependentAssembly>  
       </assemblyBinding>  
</runtime>  
```  
  
 <span data-ttu-id="cf7da-111">Bei **\<assemblyBinding>** -Elemente wird die Reihenfolge beachtet.</span><span class="sxs-lookup"><span data-stu-id="cf7da-111">The **\<assemblyBinding>** elements are order-sensitive.</span></span> <span data-ttu-id="cf7da-112">Sie sollten zuerst Umleitungsinformationen für die Assemlybindungen aller .NET Framework 1.0-Assemblys eingeben, gefolgt von den Umleitungsinformationen für die Assemblybindungen beliebiger .NET Framework 1.1-Assemblys.</span><span class="sxs-lookup"><span data-stu-id="cf7da-112">You should enter assembly binding redirection information for any .NET Framework version 1.0 assemblies first, followed by assembly binding redirection information for any .NET Framework version 1.1 assemblies.</span></span> <span data-ttu-id="cf7da-113">Geben Sie zuletzt die Informationen zum Umleiten der Assemblybindung für alle .NET Framework-Assemblyumleitungen ein, bei denen nicht das **appliesTo** -Attribut verwendet wird und die daher für alle Versionen .NET Framework-Versionen gelten.</span><span class="sxs-lookup"><span data-stu-id="cf7da-113">Finally, enter assembly binding redirection information for any .NET Framework assembly redirection that does not use the **appliesTo** attribute and therefore applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="cf7da-114">Falls bei der Umleitung Konflikte auftreten, wird die erste passende Umleitungsanweisung in der Konfigurationsdatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="cf7da-114">In case of a conflict in redirection, the first matching redirection statement in the configuration file is used.</span></span>  
  
 <span data-ttu-id="cf7da-115">Beispiel: Zum Umleiten eines Verweises auf eine .NET Framework 1.0-Assembly und eines anderen Verweises auf eine .NET Framework 1.1-Assembly müssten Sie nach dem Muster im folgenden Pseudocode vorgehen.</span><span class="sxs-lookup"><span data-stu-id="cf7da-115">For example, to redirect one reference to a .NET Framework version 1.0 assembly and another reference to a .NET Framework version 1.1 assembly, you would use the pattern shown in the following pseudocode.</span></span>  
  
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
  
## <a name="debugging-configuration-file-errors"></a><span data-ttu-id="cf7da-116">Fehler beim Debuggen der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="cf7da-116">Debugging Configuration File Errors</span></span>  
 <span data-ttu-id="cf7da-117">Die Laufzeit analysiert Konfigurationsdateien einmal, wenn eine Anwendungsdomäne erstellt wird, und lädt dann Code in diese Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="cf7da-117">The runtime parses configuration files once when an application domain is created, and loads code into that application domain.</span></span> <span data-ttu-id="cf7da-118">Die Common Language Runtime behandelt Fehler in einer Konfigurationsdatei, indem der jeweilige Eintrag ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="cf7da-118">The common language runtime handles errors in a configuration file by ignoring the entry.</span></span> <span data-ttu-id="cf7da-119">Zur Laufzeit wird die gesamte Konfigurationsdatei ignoriert, wenn sie fehlerhaft formatierte XLM enthält.</span><span class="sxs-lookup"><span data-stu-id="cf7da-119">The runtime ignores the entire configuration file if it contains malformed XML.</span></span> <span data-ttu-id="cf7da-120">Bei ungültiger XML werden nur die ungültigen Abschnitte ignoriert.</span><span class="sxs-lookup"><span data-stu-id="cf7da-120">For invalid XML, only the invalid sections are ignored.</span></span>  
  
 <span data-ttu-id="cf7da-121">Sie können feststellen, ob eine Konfigurationsdatei genutzt wird, indem Sie ermitteln, ob Umleitungen der Assemblybindung auftreten.</span><span class="sxs-lookup"><span data-stu-id="cf7da-121">You can determine whether a configuration file is being used by determining whether assembly binding redirects are occurring.</span></span> <span data-ttu-id="cf7da-122">Verwenden Sie die [Assemblybindungs-Protokollanzeige (Fuslogvw.exe)](../tools/fuslogvw-exe-assembly-binding-log-viewer.md), um zu sehen, welche Assemblys geladen werden.</span><span class="sxs-lookup"><span data-stu-id="cf7da-122">Use the [Assembly Binding Log Viewer (Fuslogvw.exe)](../tools/fuslogvw-exe-assembly-binding-log-viewer.md) to see which assemblies are being loaded.</span></span> <span data-ttu-id="cf7da-123">Um alle Assemblybindungen anzuzeigen, müssen Sie in der Registrierung einen Eintrag für **ForceLog** anlegen.</span><span class="sxs-lookup"><span data-stu-id="cf7da-123">To see all assembly binds, you must set an entry for **ForceLog** in the registry.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf7da-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf7da-124">See also</span></span>

- [<span data-ttu-id="cf7da-125">Vorgehensweise: Aktivieren und Deaktivieren der Bindungsumleitung</span><span class="sxs-lookup"><span data-stu-id="cf7da-125">How to: Enable and Disable Automatic Binding Redirection</span></span>](../configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)
