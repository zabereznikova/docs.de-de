---
title: 'Vorgehensweise: Suchen von Assemblys mit DEVPATH'
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
ms.openlocfilehash: 6fa864f814d6a9ce04f2bce92c61cd0075ab5145
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "69913003"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a><span data-ttu-id="70024-102">Vorgehensweise: Suchen von Assemblys mit DEVPATH</span><span class="sxs-lookup"><span data-stu-id="70024-102">How to: Locate Assemblies by Using DEVPATH</span></span>
<span data-ttu-id="70024-103">Entwickler möchten möglicherweise sicherstellen, dass eine freigegebene Assembly, die Sie erstellen, mit mehreren Anwendungen ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="70024-103">Developers might want to make sure that a shared assembly they are building works correctly with multiple applications.</span></span> <span data-ttu-id="70024-104">Anstatt die Assembly während des Entwicklungsprozesses ständig in den globalen Assemblycache zu versetzen, kann der Entwickler eine DEVPATH-Umgebungsvariable erstellen, die auf das Buildausgabeverzeichnis für die Assembly zeigt.</span><span class="sxs-lookup"><span data-stu-id="70024-104">Instead of continually putting the assembly in the global assembly cache during the development cycle, the developer can create a DEVPATH environment variable that points to the build output directory for the assembly.</span></span>  
  
 <span data-ttu-id="70024-105">Nehmen Sie beispielsweise an, dass Sie eine freigegebene Assembly namens MySharedAssembly erstellen und das Ausgabeverzeichnis c:\MySharedAssembly\Debug.</span><span class="sxs-lookup"><span data-stu-id="70024-105">For example, assume that you are building a shared assembly called MySharedAssembly and the output directory is C:\MySharedAssembly\Debug.</span></span> <span data-ttu-id="70024-106">Sie können "c:\MySharedAssembly\Debug" in der DEVPATH-Variablen ablegen.</span><span class="sxs-lookup"><span data-stu-id="70024-106">You can put C:\MySharedAssembly\Debug in the DEVPATH variable.</span></span> <span data-ttu-id="70024-107">Sie müssen dann das- [\<developmentMode>](./file-schema/runtime/developmentmode-element.md) Element in der Computer Konfigurationsdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="70024-107">You must then specify the [\<developmentMode>](./file-schema/runtime/developmentmode-element.md) element in the machine configuration file.</span></span> <span data-ttu-id="70024-108">Dieses Element teilt dem Common Language Runtime mit, DEVPATH zum Suchen nach Assemblys zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="70024-108">This element tells the common language runtime to use DEVPATH to locate assemblies.</span></span>  
  
 <span data-ttu-id="70024-109">Die freigegebene Assembly muss von der Laufzeit erkannt werden können.</span><span class="sxs-lookup"><span data-stu-id="70024-109">The shared assembly must be discoverable by the runtime.</span></span>  <span data-ttu-id="70024-110">Um ein privates Verzeichnis zum Auflösen von Assemblyverweisen anzugeben, verwenden Sie das- [ \<codeBase> Element](./file-schema/runtime/codebase-element.md) oder- [ \<probing> Element](./file-schema/runtime/probing-element.md) in einer Konfigurationsdatei, wie unter [angeben des Speicher Orts einer Assembly](specify-assembly-location.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="70024-110">To specify a private directory for resolving assembly references use the [\<codeBase> Element](./file-schema/runtime/codebase-element.md) or [\<probing> Element](./file-schema/runtime/probing-element.md) in a configuration file, as described in [Specifying an Assembly's Location](specify-assembly-location.md).</span></span>  <span data-ttu-id="70024-111">Sie können die Assembly auch in einem Unterverzeichnis des Anwendungs Verzeichnisses platzieren.</span><span class="sxs-lookup"><span data-stu-id="70024-111">You can also put the assembly in a subdirectory of the application directory.</span></span> <span data-ttu-id="70024-112">Weitere Informationen finden Sie unter [so](../deployment/how-the-runtime-locates-assemblies.md)sucht Common Language Runtime nach Assemblys.</span><span class="sxs-lookup"><span data-stu-id="70024-112">For more information, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70024-113">Dies ist eine erweiterte Funktion, die nur für die Entwicklung vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="70024-113">This is an advanced feature, intended only for development.</span></span>  
  
 <span data-ttu-id="70024-114">Im folgenden Beispiel wird gezeigt, wie Sie bewirken, dass die Laufzeit Assemblys in Verzeichnissen sucht, die durch die DEVPATH-Umgebungsvariable angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="70024-114">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70024-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="70024-115">Example</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="70024-116">Diese Einstellung ist standardmäßig auf false festgelegt.</span><span class="sxs-lookup"><span data-stu-id="70024-116">This setting defaults to false.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70024-117">Verwenden Sie diese Einstellung nur zur Entwicklungszeit.</span><span class="sxs-lookup"><span data-stu-id="70024-117">Use this setting only at development time.</span></span> <span data-ttu-id="70024-118">Die Laufzeit überprüft nicht die Versionen von Assemblys mit starkem Namen, die im DEVPATH gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="70024-118">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="70024-119">Es wird einfach die erste gefundene Assembly verwendet.</span><span class="sxs-lookup"><span data-stu-id="70024-119">It simply uses the first assembly it finds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70024-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="70024-120">See also</span></span>

- [<span data-ttu-id="70024-121">Konfigurieren von Apps mithilfe von Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="70024-121">Configuring Apps by using Configuration Files</span></span>](index.md)
