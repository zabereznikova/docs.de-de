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
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45510302"
---
# <a name="-resource-visual-basic"></a><span data-ttu-id="78c6c-102">-Resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78c6c-102">-resource (Visual Basic)</span></span>
<span data-ttu-id="78c6c-103">Bettet eine verwaltete Ressource in eine Assembly ein.</span><span class="sxs-lookup"><span data-stu-id="78c6c-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78c6c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="78c6c-104">Syntax</span></span>  
  
```  
-resource:filename[,identifier[,public|private]]  
' -or-  
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="78c6c-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="78c6c-105">Arguments</span></span>  
  
|<span data-ttu-id="78c6c-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="78c6c-106">Term</span></span>|<span data-ttu-id="78c6c-107">Definition</span><span class="sxs-lookup"><span data-stu-id="78c6c-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="78c6c-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="78c6c-108">Required.</span></span> <span data-ttu-id="78c6c-109">Der Name der Ressourcendatei in die Ausgabedatei eingebettet werden soll.</span><span class="sxs-lookup"><span data-stu-id="78c6c-109">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="78c6c-110">In der Standardeinstellung `filename` in der Assembly öffentlich ist.</span><span class="sxs-lookup"><span data-stu-id="78c6c-110">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="78c6c-111">Schließen Sie den Dateinamen in Anführungszeichen (""), wenn sie ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="78c6c-111">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="78c6c-112">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="78c6c-112">Optional.</span></span> <span data-ttu-id="78c6c-113">Der logische Name für die Ressource; der Name, der zum Laden der Daten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="78c6c-113">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="78c6c-114">Der Standardwert ist der Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="78c6c-114">The default is the name of the file.</span></span> <span data-ttu-id="78c6c-115">Optional können Sie angeben, ob die Ressource öffentlich oder privat ist, in das Assemblymanifest, wie Sie sich mit den folgenden ist: `-res:filename.res, myname.res, public`</span><span class="sxs-lookup"><span data-stu-id="78c6c-115">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78c6c-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="78c6c-116">Remarks</span></span>  
 <span data-ttu-id="78c6c-117">Verwendung `-linkresource` verknüpfen eine Ressource auf eine Assembly, die Ressourcendatei in der Ausgabedatei platziert.</span><span class="sxs-lookup"><span data-stu-id="78c6c-117">Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="78c6c-118">Wenn `filename` ist eine [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Ressourcendatei erstellt haben, z. B. durch die [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) oder in der Entwicklungsumgebung, können sie Zugriff mit Membern in der <xref:System.Resources> Namespace (siehe <xref:System.Resources.ResourceManager> Informationen).</span><span class="sxs-lookup"><span data-stu-id="78c6c-118">If `filename` is a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="78c6c-119">Um auf alle anderen Ressourcen zur Laufzeit zuzugreifen, verwenden Sie eine der folgenden Methoden: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, oder <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="78c6c-119">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="78c6c-120">Die Kurzform von `-resource` ist `-res`.</span><span class="sxs-lookup"><span data-stu-id="78c6c-120">The short form of `-resource` is `-res`.</span></span>  
  
 <span data-ttu-id="78c6c-121">Informationen zum Festlegen `-resource` finden Sie in der Visual Studio-IDE unter [Verwalten von Ressourcen (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="78c6c-121">For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="78c6c-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="78c6c-122">Example</span></span>  
 <span data-ttu-id="78c6c-123">Der folgende code kompiliert `In.vb` und fügt Ressourcendatei `Rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="78c6c-123">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="78c6c-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78c6c-124">See also</span></span>

- [<span data-ttu-id="78c6c-125">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="78c6c-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
- [<span data-ttu-id="78c6c-126">-win32resource</span><span class="sxs-lookup"><span data-stu-id="78c6c-126">-win32resource</span></span>](../../../visual-basic/reference/command-line-compiler/win32resource.md)  
- [<span data-ttu-id="78c6c-127">-Linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78c6c-127">-linkresource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/linkresource.md)  
- [<span data-ttu-id="78c6c-128">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78c6c-128">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
- [<span data-ttu-id="78c6c-129">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="78c6c-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
