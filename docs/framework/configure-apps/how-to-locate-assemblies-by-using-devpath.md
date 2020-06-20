---
title: 'Vorgehensweise: Suchen von Assemblys mit DEVPATH'
description: Testen Sie, ob eine freigegebene Assembly mit vielen Anwendungen in .net ordnungsgemäß funktioniert, indem Sie eine XML-Computer Konfigurationsdatei und die DEVPATH-Umgebungsvariable verwenden.
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
ms.openlocfilehash: 50b61eedddabd660b1834565a61738f460ae9ff9
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105383"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a><span data-ttu-id="271d8-103">Vorgehensweise: Suchen von Assemblys mit DEVPATH</span><span class="sxs-lookup"><span data-stu-id="271d8-103">How to: Locate Assemblies by Using DEVPATH</span></span>
<span data-ttu-id="271d8-104">Entwickler möchten möglicherweise sicherstellen, dass eine freigegebene Assembly, die Sie erstellen, mit mehreren Anwendungen ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="271d8-104">Developers might want to make sure that a shared assembly they are building works correctly with multiple applications.</span></span> <span data-ttu-id="271d8-105">Anstatt die Assembly während des Entwicklungsprozesses ständig in den globalen Assemblycache zu versetzen, kann der Entwickler eine DEVPATH-Umgebungsvariable erstellen, die auf das Buildausgabeverzeichnis für die Assembly zeigt.</span><span class="sxs-lookup"><span data-stu-id="271d8-105">Instead of continually putting the assembly in the global assembly cache during the development cycle, the developer can create a DEVPATH environment variable that points to the build output directory for the assembly.</span></span>  
  
 <span data-ttu-id="271d8-106">Nehmen Sie beispielsweise an, dass Sie eine freigegebene Assembly namens MySharedAssembly erstellen und das Ausgabeverzeichnis c:\MySharedAssembly\Debug.</span><span class="sxs-lookup"><span data-stu-id="271d8-106">For example, assume that you are building a shared assembly called MySharedAssembly and the output directory is C:\MySharedAssembly\Debug.</span></span> <span data-ttu-id="271d8-107">Sie können "c:\MySharedAssembly\Debug" in der DEVPATH-Variablen ablegen.</span><span class="sxs-lookup"><span data-stu-id="271d8-107">You can put C:\MySharedAssembly\Debug in the DEVPATH variable.</span></span> <span data-ttu-id="271d8-108">Sie müssen dann das- [\<developmentMode>](./file-schema/runtime/developmentmode-element.md) Element in der Computer Konfigurationsdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="271d8-108">You must then specify the [\<developmentMode>](./file-schema/runtime/developmentmode-element.md) element in the machine configuration file.</span></span> <span data-ttu-id="271d8-109">Dieses Element teilt dem Common Language Runtime mit, DEVPATH zum Suchen nach Assemblys zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="271d8-109">This element tells the common language runtime to use DEVPATH to locate assemblies.</span></span>  
  
 <span data-ttu-id="271d8-110">Die freigegebene Assembly muss von der Laufzeit erkannt werden können.</span><span class="sxs-lookup"><span data-stu-id="271d8-110">The shared assembly must be discoverable by the runtime.</span></span>  <span data-ttu-id="271d8-111">Um ein privates Verzeichnis zum Auflösen von Assemblyverweisen anzugeben, verwenden Sie das- [ \<codeBase> Element](./file-schema/runtime/codebase-element.md) oder- [ \<probing> Element](./file-schema/runtime/probing-element.md) in einer Konfigurationsdatei, wie unter [angeben des Speicher Orts einer Assembly](specify-assembly-location.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="271d8-111">To specify a private directory for resolving assembly references use the [\<codeBase> Element](./file-schema/runtime/codebase-element.md) or [\<probing> Element](./file-schema/runtime/probing-element.md) in a configuration file, as described in [Specifying an Assembly's Location](specify-assembly-location.md).</span></span>  <span data-ttu-id="271d8-112">Sie können die Assembly auch in einem Unterverzeichnis des Anwendungs Verzeichnisses platzieren.</span><span class="sxs-lookup"><span data-stu-id="271d8-112">You can also put the assembly in a subdirectory of the application directory.</span></span> <span data-ttu-id="271d8-113">Weitere Informationen finden Sie unter [so](../deployment/how-the-runtime-locates-assemblies.md)sucht Common Language Runtime nach Assemblys.</span><span class="sxs-lookup"><span data-stu-id="271d8-113">For more information, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="271d8-114">Dies ist eine erweiterte Funktion, die nur für die Entwicklung vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="271d8-114">This is an advanced feature, intended only for development.</span></span>  
  
 <span data-ttu-id="271d8-115">Im folgenden Beispiel wird gezeigt, wie Sie bewirken, dass die Laufzeit Assemblys in Verzeichnissen sucht, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="271d8-115">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="271d8-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="271d8-116">Example</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="271d8-117">Diese Einstellung ist standardmäßig auf false festgelegt.</span><span class="sxs-lookup"><span data-stu-id="271d8-117">This setting defaults to false.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="271d8-118">Verwenden Sie diese Einstellung nur zur Entwicklungszeit.</span><span class="sxs-lookup"><span data-stu-id="271d8-118">Use this setting only at development time.</span></span> <span data-ttu-id="271d8-119">Die Laufzeit überprüft nicht die Versionen von Assemblys mit starkem Namen, die im DEVPATH gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="271d8-119">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="271d8-120">Es wird einfach die erste gefundene Assembly verwendet.</span><span class="sxs-lookup"><span data-stu-id="271d8-120">It simply uses the first assembly it finds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="271d8-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="271d8-121">See also</span></span>

- [<span data-ttu-id="271d8-122">Konfigurieren von Apps mithilfe von Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="271d8-122">Configuring Apps by using Configuration Files</span></span>](index.md)
