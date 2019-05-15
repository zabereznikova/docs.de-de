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
ms.openlocfilehash: dd41051bd770d3579137aa158e70cef41aed49f8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64607828"
---
# <a name="assembly-contents"></a><span data-ttu-id="96033-102">Assemblyinhalte</span><span class="sxs-lookup"><span data-stu-id="96033-102">Assembly Contents</span></span>
<span data-ttu-id="96033-103">Im Allgemeinen kann eine statische Assembly vier Elemente enthalten:</span><span class="sxs-lookup"><span data-stu-id="96033-103">In general, a static assembly can consist of four elements:</span></span>  
  
- <span data-ttu-id="96033-104">Das [Assemblymanifest](../../../docs/framework/app-domains/assembly-manifest.md), das die Assemblymetadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="96033-104">The [assembly manifest](../../../docs/framework/app-domains/assembly-manifest.md), which contains assembly metadata.</span></span>  
  
- <span data-ttu-id="96033-105">Die Typmetadaten.</span><span class="sxs-lookup"><span data-stu-id="96033-105">Type metadata.</span></span>  
  
- <span data-ttu-id="96033-106">MSIL-Code (Microsoft Intermediate Language), der die Typen implementiert.</span><span class="sxs-lookup"><span data-stu-id="96033-106">Microsoft intermediate language (MSIL) code that implements the types.</span></span>  
  
- <span data-ttu-id="96033-107">Eine Gruppe von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="96033-107">A set of resources.</span></span>  
  
 <span data-ttu-id="96033-108">Von diesen ist nur das Assemblymanifest erforderlich. Um der Assembly jedoch eine sinnvolle Funktion zu geben, sind entweder Typen oder Ressourcen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="96033-108">Only the assembly manifest is required, but either types or resources are needed to give the assembly any meaningful functionality.</span></span>  
  
 <span data-ttu-id="96033-109">Es gibt eine Reihe von Möglichkeiten, diese Elemente in einer Assembly zusammenzufassen.</span><span class="sxs-lookup"><span data-stu-id="96033-109">There are several ways to group these elements in an assembly.</span></span> <span data-ttu-id="96033-110">Sie können alle Elemente in einer einzelnen physischen Datei gruppieren, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="96033-110">You can group all elements in a single physical file, which is shown in the following illustration.</span></span>  
  
 ![Diagramm einer Einzeldateiassembly namens „MyAssembly.dll“](./media/assembly-contents/single-file-assembly.gif)  
  
 <span data-ttu-id="96033-112">Wahlweise können die Elemente einer Assembly auch in mehreren Dateien enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="96033-112">Alternatively, the elements of an assembly can be contained in several files.</span></span> <span data-ttu-id="96033-113">Diese Dateien können Module aus kompiliertem Code (NETMODULE-Dateien), Ressourcen (beispielsweise BMP- oder JPG-Dateien) oder andere von der Anwendung benötigte Dateien sein.</span><span class="sxs-lookup"><span data-stu-id="96033-113">These files can be modules of compiled code (.netmodule), resources (such as .bmp or .jpg files), or other files required by the application.</span></span> <span data-ttu-id="96033-114">Sie erstellen eine Mehrfachdateiassembly, wenn Sie Module kombinieren möchten, die in verschiedenen Sprachen geschrieben sind, oder um das Herunterladen einer Anwendung zu optimieren, indem Sie selten verwendete Typen in einem Modul ablegen, das nur bei Bedarf heruntergeladen wird.</span><span class="sxs-lookup"><span data-stu-id="96033-114">Create a multifile assembly when you want to combine modules written in different languages and to optimize downloading an application by putting seldom used types in a module that is downloaded only when needed.</span></span>  
  
 <span data-ttu-id="96033-115">In der folgenden Abbildung hat der Entwickler einer hypothetischen Anwendung Code eines Dienstprogramms in einem anderen Modul abgelegt. In der Originaldatei ist eine umfangreiche Ressourcendatei gespeichert (hier eine BMP-Grafik).</span><span class="sxs-lookup"><span data-stu-id="96033-115">In the following illustration, the developer of a hypothetical application has chosen to separate some utility code into a different module and to keep a large resource file (in this case a .bmp image) in its original file.</span></span> <span data-ttu-id="96033-116">Eine Datei wird nur dann von .NET Framework heruntergeladen, wenn auf diese verwiesen wird. Das Herunterladen von Code wird optimiert, wenn Code, auf den selten verwiesen wird, statt in der Anwendung in einer zusätzlichen Datei abgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="96033-116">The .NET Framework downloads a file only when it is referenced; keeping infrequently referenced code in a separate file from the application optimizes code download.</span></span>  
  
 ![Diagramm einer Mehrfachdateiassembly](./media/assembly-contents/multifile-assembly-diagram.gif) 
  
> [!NOTE]
>  <span data-ttu-id="96033-118">Die Dateien, die zu einer Mehrfachdateiassembly gehören, werden vom Dateisystem nicht physisch verknüpft.</span><span class="sxs-lookup"><span data-stu-id="96033-118">The files that make up a multifile assembly are not physically linked by the file system.</span></span> <span data-ttu-id="96033-119">Stattdessen sind sie über das Assemblymanifest verbunden, und die Common Language Runtime verwaltet sie als Einheit.</span><span class="sxs-lookup"><span data-stu-id="96033-119">Rather, they are linked through the assembly manifest and the common language runtime manages them as a unit.</span></span>  
  
 <span data-ttu-id="96033-120">In dieser Abbildung gehören alle drei Dateien zu einer Assembly, wie im Assemblymanifest in MyAssembly.dll beschrieben.</span><span class="sxs-lookup"><span data-stu-id="96033-120">In this illustration, all three files belong to an assembly, as described in the assembly manifest contained in MyAssembly.dll.</span></span> <span data-ttu-id="96033-121">Das Dateisystem betrachtet diese als drei getrennte Dateien.</span><span class="sxs-lookup"><span data-stu-id="96033-121">To the file system, they are three separate files.</span></span> <span data-ttu-id="96033-122">Beachten Sie, dass die Datei "Util.netmodule" als Modul kompiliert wurde, da sie keine Assemblyinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="96033-122">Note that the file Util.netmodule was compiled as a module because it contains no assembly information.</span></span> <span data-ttu-id="96033-123">Beim Erstellen der Assembly wurde das Assemblymanifest "MyAssembly.dll" hinzugefügt, um die Beziehungen zwischen den Dateien "Util.netmodule" und "Graphic.bmp" anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="96033-123">When the assembly was created, the assembly manifest was added to MyAssembly.dll, indicating its relationship with Util.netmodule and Graphic.bmp.</span></span>  
  
 <span data-ttu-id="96033-124">Wenn Sie gegenwärtig Quellcode schreiben, treffen Sie explizite Entscheidungen darüber, wie die Funktionen einer Anwendung in eine oder mehrere Dateien aufgeteilt werden.</span><span class="sxs-lookup"><span data-stu-id="96033-124">As you currently design your source code, you make explicit decisions about how to partition the functionality of your application into one or more files.</span></span> <span data-ttu-id="96033-125">Beim Entwerfen von .NET Framework-Code werden Sie in Zukunft ähnliche Entscheidungen darüber treffen, wie Sie Funktionen in eine oder mehrere Assemblys aufteilen.</span><span class="sxs-lookup"><span data-stu-id="96033-125">When designing .NET Framework code, you will make similar decisions about how to partition the functionality into one or more assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96033-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96033-126">See also</span></span>

- [<span data-ttu-id="96033-127">Assemblys in der Common Language Runtime (CLR)</span><span class="sxs-lookup"><span data-stu-id="96033-127">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
- [<span data-ttu-id="96033-128">Assemblymanifest</span><span class="sxs-lookup"><span data-stu-id="96033-128">Assembly Manifest</span></span>](../../../docs/framework/app-domains/assembly-manifest.md)
- [<span data-ttu-id="96033-129">Überlegungen zur Assemblysicherheit</span><span class="sxs-lookup"><span data-stu-id="96033-129">Assembly Security Considerations</span></span>](../../../docs/framework/app-domains/assembly-security-considerations.md)
