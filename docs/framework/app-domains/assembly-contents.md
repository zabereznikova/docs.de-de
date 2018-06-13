---
title: Assemblyinhalte
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- assemblies [.NET Framework], single-file
- single-file assemblies
- multifile assemblies
ms.assetid: 28116714-da77-45f7-826d-fa035d121948
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38c0081e5677ca65e8c730c7199ebac5d4c86261
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32741827"
---
# <a name="assembly-contents"></a><span data-ttu-id="e3b52-102">Assemblyinhalte</span><span class="sxs-lookup"><span data-stu-id="e3b52-102">Assembly Contents</span></span>
<span data-ttu-id="e3b52-103">Im Allgemeinen kann eine statische Assembly vier Elemente enthalten:</span><span class="sxs-lookup"><span data-stu-id="e3b52-103">In general, a static assembly can consist of four elements:</span></span>  
  
-   <span data-ttu-id="e3b52-104">Das [Assemblymanifest](../../../docs/framework/app-domains/assembly-manifest.md), das die Assemblymetadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="e3b52-104">The [assembly manifest](../../../docs/framework/app-domains/assembly-manifest.md), which contains assembly metadata.</span></span>  
  
-   <span data-ttu-id="e3b52-105">Die Typmetadaten.</span><span class="sxs-lookup"><span data-stu-id="e3b52-105">Type metadata.</span></span>  
  
-   <span data-ttu-id="e3b52-106">MSIL-Code (Microsoft Intermediate Language), der die Typen implementiert.</span><span class="sxs-lookup"><span data-stu-id="e3b52-106">Microsoft intermediate language (MSIL) code that implements the types.</span></span>  
  
-   <span data-ttu-id="e3b52-107">Eine Gruppe von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="e3b52-107">A set of resources.</span></span>  
  
 <span data-ttu-id="e3b52-108">Von diesen ist nur das Assemblymanifest erforderlich. Um der Assembly jedoch eine sinnvolle Funktion zu geben, sind entweder Typen oder Ressourcen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e3b52-108">Only the assembly manifest is required, but either types or resources are needed to give the assembly any meaningful functionality.</span></span>  
  
 <span data-ttu-id="e3b52-109">Es gibt eine Reihe von Möglichkeiten, diese Elemente in einer Assembly zusammenzufassen.</span><span class="sxs-lookup"><span data-stu-id="e3b52-109">There are several ways to group these elements in an assembly.</span></span> <span data-ttu-id="e3b52-110">Sie können alle Elemente in einer einzelnen physischen Datei gruppieren, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e3b52-110">You can group all elements in a single physical file, which is shown in the following illustration.</span></span>  
  
 <span data-ttu-id="e3b52-111">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover1.gif "assemblyover1")</span><span class="sxs-lookup"><span data-stu-id="e3b52-111">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover1.gif "assemblyover1")</span></span>  
<span data-ttu-id="e3b52-112">Einzeldateiassembly</span><span class="sxs-lookup"><span data-stu-id="e3b52-112">Single-file assembly</span></span>  
  
 <span data-ttu-id="e3b52-113">Wahlweise können die Elemente einer Assembly auch in mehreren Dateien enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="e3b52-113">Alternatively, the elements of an assembly can be contained in several files.</span></span> <span data-ttu-id="e3b52-114">Diese Dateien können Module aus kompiliertem Code (NETMODULE-Dateien), Ressourcen (beispielsweise BMP- oder JPG-Dateien) oder andere von der Anwendung benötigte Dateien sein.</span><span class="sxs-lookup"><span data-stu-id="e3b52-114">These files can be modules of compiled code (.netmodule), resources (such as .bmp or .jpg files), or other files required by the application.</span></span> <span data-ttu-id="e3b52-115">Sie erstellen eine Mehrfachdateiassembly, wenn Sie Module kombinieren möchten, die in verschiedenen Sprachen geschrieben sind, oder um das Herunterladen einer Anwendung zu optimieren, indem Sie selten verwendete Typen in einem Modul ablegen, das nur bei Bedarf heruntergeladen wird.</span><span class="sxs-lookup"><span data-stu-id="e3b52-115">Create a multifile assembly when you want to combine modules written in different languages and to optimize downloading an application by putting seldom used types in a module that is downloaded only when needed.</span></span>  
  
 <span data-ttu-id="e3b52-116">In der folgenden Abbildung hat der Entwickler einer hypothetischen Anwendung Code eines Dienstprogramms in einem anderen Modul abgelegt. In der Originaldatei ist eine umfangreiche Ressourcendatei gespeichert (hier eine BMP-Grafik).</span><span class="sxs-lookup"><span data-stu-id="e3b52-116">In the following illustration, the developer of a hypothetical application has chosen to separate some utility code into a different module and to keep a large resource file (in this case a .bmp image) in its original file.</span></span> <span data-ttu-id="e3b52-117">Eine Datei wird nur dann von .NET Framework heruntergeladen, wenn auf diese verwiesen wird. Das Herunterladen von Code wird optimiert, wenn Code, auf den selten verwiesen wird, statt in der Anwendung in einer zusätzlichen Datei abgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e3b52-117">The .NET Framework downloads a file only when it is referenced; keeping infrequently referenced code in a separate file from the application optimizes code download.</span></span>  
  
 <span data-ttu-id="e3b52-118">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover2.gif "assemblyover2")</span><span class="sxs-lookup"><span data-stu-id="e3b52-118">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover2.gif "assemblyover2")</span></span>  
<span data-ttu-id="e3b52-119">Mehrfachdateiassembly</span><span class="sxs-lookup"><span data-stu-id="e3b52-119">Multifile assembly</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3b52-120">Die Dateien, die zu einer Mehrfachdateiassembly gehören, werden vom Dateisystem nicht physisch verknüpft.</span><span class="sxs-lookup"><span data-stu-id="e3b52-120">The files that make up a multifile assembly are not physically linked by the file system.</span></span> <span data-ttu-id="e3b52-121">Stattdessen sind sie über das Assemblymanifest verbunden, und die Common Language Runtime verwaltet sie als Einheit.</span><span class="sxs-lookup"><span data-stu-id="e3b52-121">Rather, they are linked through the assembly manifest and the common language runtime manages them as a unit.</span></span>  
  
 <span data-ttu-id="e3b52-122">In dieser Abbildung gehören alle drei Dateien zu einer Assembly, wie im Assemblymanifest in MyAssembly.dll beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e3b52-122">In this illustration, all three files belong to an assembly, as described in the assembly manifest contained in MyAssembly.dll.</span></span> <span data-ttu-id="e3b52-123">Das Dateisystem betrachtet diese als drei getrennte Dateien.</span><span class="sxs-lookup"><span data-stu-id="e3b52-123">To the file system, they are three separate files.</span></span> <span data-ttu-id="e3b52-124">Beachten Sie, dass die Datei "Util.netmodule" als Modul kompiliert wurde, da sie keine Assemblyinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="e3b52-124">Note that the file Util.netmodule was compiled as a module because it contains no assembly information.</span></span> <span data-ttu-id="e3b52-125">Beim Erstellen der Assembly wurde das Assemblymanifest "MyAssembly.dll" hinzugefügt, um die Beziehungen zwischen den Dateien "Util.netmodule" und "Graphic.bmp" anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e3b52-125">When the assembly was created, the assembly manifest was added to MyAssembly.dll, indicating its relationship with Util.netmodule and Graphic.bmp.</span></span>  
  
 <span data-ttu-id="e3b52-126">Wenn Sie gegenwärtig Quellcode schreiben, treffen Sie explizite Entscheidungen darüber, wie die Funktionen einer Anwendung in eine oder mehrere Dateien aufgeteilt werden.</span><span class="sxs-lookup"><span data-stu-id="e3b52-126">As you currently design your source code, you make explicit decisions about how to partition the functionality of your application into one or more files.</span></span> <span data-ttu-id="e3b52-127">Beim Entwerfen von .NET Framework-Code werden Sie in Zukunft ähnliche Entscheidungen darüber treffen, wie Sie Funktionen in eine oder mehrere Assemblys aufteilen.</span><span class="sxs-lookup"><span data-stu-id="e3b52-127">When designing .NET Framework code, you will make similar decisions about how to partition the functionality into one or more assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3b52-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3b52-128">See Also</span></span>  
 [<span data-ttu-id="e3b52-129">Assemblys in der Common Language Runtime (CLR)</span><span class="sxs-lookup"><span data-stu-id="e3b52-129">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [<span data-ttu-id="e3b52-130">Assemblymanifest</span><span class="sxs-lookup"><span data-stu-id="e3b52-130">Assembly Manifest</span></span>](../../../docs/framework/app-domains/assembly-manifest.md)  
 [<span data-ttu-id="e3b52-131">Überlegungen zur Assemblysicherheit</span><span class="sxs-lookup"><span data-stu-id="e3b52-131">Assembly Security Considerations</span></span>](../../../docs/framework/app-domains/assembly-security-considerations.md)
