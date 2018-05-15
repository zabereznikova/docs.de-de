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
manager: markl
ms.openlocfilehash: 918acf069c63d3aa8187f0f04e1f6c55ec961458
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a><span data-ttu-id="6fc46-102">Gewusst wie: Suchen von Assemblys mit DEVPATH</span><span class="sxs-lookup"><span data-stu-id="6fc46-102">How to: Locate Assemblies by Using DEVPATH</span></span>
<span data-ttu-id="6fc46-103">Entwickler sollten sicherstellen, dass eine freigegebene Assembly, die sie erstellen mit mehreren Anwendungen ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="6fc46-103">Developers might want to make sure that a shared assembly they are building works correctly with multiple applications.</span></span> <span data-ttu-id="6fc46-104">Anstatt kontinuierlich platzieren die Assembly im globalen Assemblycache während des Entwicklungszyklus, kann der Entwickler eine DEVPATH-Umgebungsvariable erstellen, die auf das Buildausgabeverzeichnis für die Assembly verweist.</span><span class="sxs-lookup"><span data-stu-id="6fc46-104">Instead of continually putting the assembly in the global assembly cache during the development cycle, the developer can create a DEVPATH environment variable that points to the build output directory for the assembly.</span></span>  
  
 <span data-ttu-id="6fc46-105">Nehmen wir beispielsweise an, dass Sie beim Erstellen einer freigegebenen Assemblys mit dem Namen MySharedAssembly und das Ausgabeverzeichnis C:\MySharedAssembly\Debug.</span><span class="sxs-lookup"><span data-stu-id="6fc46-105">For example, assume that you are building a shared assembly called MySharedAssembly and the output directory is C:\MySharedAssembly\Debug.</span></span> <span data-ttu-id="6fc46-106">Sie können in der Variablen DEVPATH C:\MySharedAssembly\Debug einfügen.</span><span class="sxs-lookup"><span data-stu-id="6fc46-106">You can put C:\MySharedAssembly\Debug in the DEVPATH variable.</span></span> <span data-ttu-id="6fc46-107">Sie müssen dann geben Sie die [ \<DevelopmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) Element in der Computerkonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="6fc46-107">You must then specify the [\<developmentMode>](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) element in the machine configuration file.</span></span> <span data-ttu-id="6fc46-108">Dieses Element weist die common Language Runtime DEVPATH verwenden, um Assemblys zu suchen.</span><span class="sxs-lookup"><span data-stu-id="6fc46-108">This element tells the common language runtime to use DEVPATH to locate assemblies.</span></span>  
  
 <span data-ttu-id="6fc46-109">Die diese freigegebene Assembly muss von der Laufzeit erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="6fc46-109">The shared assembly must be discoverable by the runtime.</span></span>  <span data-ttu-id="6fc46-110">Zum Angeben eines privaten Verzeichnisses zum Auflösen von Assembly Verweise verwenden die [ \<codeBase >-Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) oder [ \<probing > Element](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) in einer Konfigurationsdatei, wie in beschrieben [Angeben des Speicherortes einer Assembly](../../../docs/framework/configure-apps/specify-assembly-location.md).</span><span class="sxs-lookup"><span data-stu-id="6fc46-110">To specify a private directory for resolving assembly references use the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) or [\<probing> Element](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) in a configuration file, as described in [Specifying an Assembly's Location](../../../docs/framework/configure-apps/specify-assembly-location.md).</span></span>  <span data-ttu-id="6fc46-111">Sie können auch die Assembly in einem Unterverzeichnis des Anwendungsverzeichnisses platziert.</span><span class="sxs-lookup"><span data-stu-id="6fc46-111">You can also put the assembly in a subdirectory of the application directory.</span></span> <span data-ttu-id="6fc46-112">Weitere Informationen finden Sie unter [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)(Seite möglicherweise auf Englisch).</span><span class="sxs-lookup"><span data-stu-id="6fc46-112">For more information, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fc46-113">Dies ist eine erweiterte Funktion, die nur für die Entwicklung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="6fc46-113">This is an advanced feature, intended only for development.</span></span>  
  
 <span data-ttu-id="6fc46-114">Das folgende Beispiel veranschaulicht die dazu führen, dass die Common Language Runtime nach Assemblys die DEVPATH-Umgebungsvariable angegebenen Verzeichnisse suchen.</span><span class="sxs-lookup"><span data-stu-id="6fc46-114">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fc46-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6fc46-115">Example</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="6fc46-116">Diese Einstellung wird standardmäßig auf "false".</span><span class="sxs-lookup"><span data-stu-id="6fc46-116">This setting defaults to false.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fc46-117">Verwenden Sie diese Einstellung nur zum Zeitpunkt der Entwicklung.</span><span class="sxs-lookup"><span data-stu-id="6fc46-117">Use this setting only at development time.</span></span> <span data-ttu-id="6fc46-118">Die Common Language Runtime überprüft nicht die Versionen auf Assemblys mit starkem Namen in die DEVPATH gefunden.</span><span class="sxs-lookup"><span data-stu-id="6fc46-118">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="6fc46-119">Sie verwendet einfach die erste Assembly gefundenen.</span><span class="sxs-lookup"><span data-stu-id="6fc46-119">It simply uses the first assembly it finds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fc46-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6fc46-120">See Also</span></span>  
 [<span data-ttu-id="6fc46-121">Konfigurieren von .NET Framework-Apps</span><span class="sxs-lookup"><span data-stu-id="6fc46-121">Configuring .NET Framework Apps</span></span>](http://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
