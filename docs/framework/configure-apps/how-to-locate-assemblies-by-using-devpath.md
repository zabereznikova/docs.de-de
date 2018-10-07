---
title: 'Gewusst wie: Suchen von Assemblys mit DEVPATH'
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 3a9ae9c60ad7de80d04f16984b3b2fb048421cc2
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2018
ms.locfileid: "48847568"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a><span data-ttu-id="b56f3-102">Gewusst wie: Suchen von Assemblys mit DEVPATH</span><span class="sxs-lookup"><span data-stu-id="b56f3-102">How to: Locate Assemblies by Using DEVPATH</span></span>
<span data-ttu-id="b56f3-103">Entwickler sollten sicherstellen, dass eine freigegebene Assembly, die sie erstellen mit mehreren Anwendungen funktioniert.</span><span class="sxs-lookup"><span data-stu-id="b56f3-103">Developers might want to make sure that a shared assembly they are building works correctly with multiple applications.</span></span> <span data-ttu-id="b56f3-104">Anstatt kontinuierlich platzieren die Assembly im globalen Assemblycache während des Entwicklungszyklus, kann Entwickler eine DEVPATH-Umgebungsvariable erstellen, die in das Ausgabeverzeichnis des Builds für die Assembly verweist.</span><span class="sxs-lookup"><span data-stu-id="b56f3-104">Instead of continually putting the assembly in the global assembly cache during the development cycle, the developer can create a DEVPATH environment variable that points to the build output directory for the assembly.</span></span>  
  
 <span data-ttu-id="b56f3-105">Nehmen wir beispielsweise an, dass Sie eine freigegebene Assembly, die mit dem Namen MySharedAssembly erstellen und das Ausgabeverzeichnis C:\MySharedAssembly\Debug ist.</span><span class="sxs-lookup"><span data-stu-id="b56f3-105">For example, assume that you are building a shared assembly called MySharedAssembly and the output directory is C:\MySharedAssembly\Debug.</span></span> <span data-ttu-id="b56f3-106">Sie können in der Variablen DEVPATH C:\MySharedAssembly\Debug einbinden.</span><span class="sxs-lookup"><span data-stu-id="b56f3-106">You can put C:\MySharedAssembly\Debug in the DEVPATH variable.</span></span> <span data-ttu-id="b56f3-107">Sie müssen angeben, die [ \<DevelopmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) Element in der Computerkonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b56f3-107">You must then specify the [\<developmentMode>](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) element in the machine configuration file.</span></span> <span data-ttu-id="b56f3-108">Dieses Element weist die common Language Runtime DEVPATH verwenden, um Assemblys zu suchen.</span><span class="sxs-lookup"><span data-stu-id="b56f3-108">This element tells the common language runtime to use DEVPATH to locate assemblies.</span></span>  
  
 <span data-ttu-id="b56f3-109">Die freigegebene Assembly muss von der Laufzeit erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="b56f3-109">The shared assembly must be discoverable by the runtime.</span></span>  <span data-ttu-id="b56f3-110">Zum Angeben eines privaten Verzeichnisses für das Auflösen von Assembly-Verweise verwendet die [ \<codeBase > Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) oder [ \<probing > Element](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) in einer Konfigurationsdatei, wie in beschrieben [Angeben des Speicherortes einer Assembly](../../../docs/framework/configure-apps/specify-assembly-location.md).</span><span class="sxs-lookup"><span data-stu-id="b56f3-110">To specify a private directory for resolving assembly references use the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) or [\<probing> Element](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) in a configuration file, as described in [Specifying an Assembly's Location](../../../docs/framework/configure-apps/specify-assembly-location.md).</span></span>  <span data-ttu-id="b56f3-111">Sie können auch die Assembly in einem Unterverzeichnis des Anwendungsverzeichnisses einfügen.</span><span class="sxs-lookup"><span data-stu-id="b56f3-111">You can also put the assembly in a subdirectory of the application directory.</span></span> <span data-ttu-id="b56f3-112">Weitere Informationen finden Sie unter [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)(Seite möglicherweise auf Englisch).</span><span class="sxs-lookup"><span data-stu-id="b56f3-112">For more information, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b56f3-113">Dies ist eine erweiterte Funktion, die nur für die Entwicklung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="b56f3-113">This is an advanced feature, intended only for development.</span></span>  
  
 <span data-ttu-id="b56f3-114">Das folgende Beispiel zeigt, wie Sie dazu führen, dass die Runtime sucht nach Assemblys in Verzeichnissen, die durch die DEVPATH-Umgebungsvariable angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b56f3-114">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b56f3-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b56f3-115">Example</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="b56f3-116">Diese Einstellung wird standardmäßig auf "false".</span><span class="sxs-lookup"><span data-stu-id="b56f3-116">This setting defaults to false.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b56f3-117">Verwenden Sie diese Einstellung nur zum Zeitpunkt der Entwicklung.</span><span class="sxs-lookup"><span data-stu-id="b56f3-117">Use this setting only at development time.</span></span> <span data-ttu-id="b56f3-118">Die Runtime überprüft nicht die Versionen auf Assemblys mit starkem Namen finden Sie in die DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="b56f3-118">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="b56f3-119">Sie verwendet einfach die erste Assembly gefundenen.</span><span class="sxs-lookup"><span data-stu-id="b56f3-119">It simply uses the first assembly it finds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b56f3-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b56f3-120">See Also</span></span>  
 [<span data-ttu-id="b56f3-121">Konfigurieren von .NET Framework-Apps</span><span class="sxs-lookup"><span data-stu-id="b56f3-121">Configuring .NET Framework Apps</span></span>](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
