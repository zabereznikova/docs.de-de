---
title: -Resource (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a69d0e15f9094860c4c66f3fe0a195a0a609db9
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44184018"
---
# <a name="-resource-visual-basic"></a><span data-ttu-id="4406e-102">-Resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4406e-102">-resource (Visual Basic)</span></span>
<span data-ttu-id="4406e-103">Bettet eine verwaltete Ressource in eine Assembly ein.</span><span class="sxs-lookup"><span data-stu-id="4406e-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4406e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4406e-104">Syntax</span></span>  
  
```  
-resource:filename[,identifier[,public|private]]  
' -or-  
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="4406e-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="4406e-105">Arguments</span></span>  
  
|<span data-ttu-id="4406e-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="4406e-106">Term</span></span>|<span data-ttu-id="4406e-107">Definition</span><span class="sxs-lookup"><span data-stu-id="4406e-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="4406e-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4406e-108">Required.</span></span> <span data-ttu-id="4406e-109">Der Name der Ressourcendatei in die Ausgabedatei eingebettet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4406e-109">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="4406e-110">In der Standardeinstellung `filename` in der Assembly öffentlich ist.</span><span class="sxs-lookup"><span data-stu-id="4406e-110">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="4406e-111">Schließen Sie den Dateinamen in Anführungszeichen (""), wenn sie ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="4406e-111">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="4406e-112">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4406e-112">Optional.</span></span> <span data-ttu-id="4406e-113">Der logische Name für die Ressource; der Name, der zum Laden der Daten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4406e-113">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="4406e-114">Der Standardwert ist der Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="4406e-114">The default is the name of the file.</span></span> <span data-ttu-id="4406e-115">Optional können Sie angeben, ob die Ressource öffentlich oder privat ist, in das Assemblymanifest, wie Sie sich mit den folgenden ist: `-res:filename.res, myname.res, public`</span><span class="sxs-lookup"><span data-stu-id="4406e-115">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4406e-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4406e-116">Remarks</span></span>  
 <span data-ttu-id="4406e-117">Verwendung `-linkresource` verknüpfen eine Ressource auf eine Assembly, die Ressourcendatei in der Ausgabedatei platziert.</span><span class="sxs-lookup"><span data-stu-id="4406e-117">Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="4406e-118">Wenn `filename` ist eine [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Ressourcendatei erstellt haben, z. B. durch die [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) oder in der Entwicklungsumgebung, können sie Zugriff mit Membern in der <xref:System.Resources> Namespace (siehe <xref:System.Resources.ResourceManager> Informationen).</span><span class="sxs-lookup"><span data-stu-id="4406e-118">If `filename` is a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="4406e-119">Um auf alle anderen Ressourcen zur Laufzeit zuzugreifen, verwenden Sie eine der folgenden Methoden: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, oder <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="4406e-119">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="4406e-120">Die Kurzform von `-resource` ist `-res`.</span><span class="sxs-lookup"><span data-stu-id="4406e-120">The short form of `-resource` is `-res`.</span></span>  
  
 <span data-ttu-id="4406e-121">Informationen zum Festlegen `-resource` finden Sie in der Visual Studio-IDE unter [Verwalten von Ressourcen (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="4406e-121">For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4406e-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4406e-122">Example</span></span>  
 <span data-ttu-id="4406e-123">Der folgende code kompiliert `In.vb` und fügt Ressourcendatei `Rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="4406e-123">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="4406e-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4406e-124">See also</span></span>

- [<span data-ttu-id="4406e-125">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="4406e-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
- [<span data-ttu-id="4406e-126">-win32resource</span><span class="sxs-lookup"><span data-stu-id="4406e-126">-win32resource</span></span>](../../../visual-basic/reference/command-line-compiler/win32resource.md)  
- [<span data-ttu-id="4406e-127">-Linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4406e-127">-linkresource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/linkresource.md)  
- [<span data-ttu-id="4406e-128">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4406e-128">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
- [<span data-ttu-id="4406e-129">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="4406e-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
