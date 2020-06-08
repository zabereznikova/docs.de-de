---
title: -resource
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: cf9fe8dae0d35df694891633a6e3cf950bfb7376
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363616"
---
# <a name="-resource-visual-basic"></a><span data-ttu-id="51b66-102">-resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51b66-102">-resource (Visual Basic)</span></span>
<span data-ttu-id="51b66-103">Bettet eine verwaltete Ressource in eine Assembly ein.</span><span class="sxs-lookup"><span data-stu-id="51b66-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51b66-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="51b66-104">Syntax</span></span>  
  
```console  
-resource:filename[,identifier[,public|private]]  
```

<span data-ttu-id="51b66-105">oder</span><span class="sxs-lookup"><span data-stu-id="51b66-105">or</span></span>  

```console
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="51b66-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="51b66-106">Arguments</span></span>  
  
|<span data-ttu-id="51b66-107">Begriff</span><span class="sxs-lookup"><span data-stu-id="51b66-107">Term</span></span>|<span data-ttu-id="51b66-108">Definition</span><span class="sxs-lookup"><span data-stu-id="51b66-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="51b66-109">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="51b66-109">Required.</span></span> <span data-ttu-id="51b66-110">Der Name der Ressourcendatei, die in die Ausgabedatei eingebettet werden soll.</span><span class="sxs-lookup"><span data-stu-id="51b66-110">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="51b66-111">Standardmäßig ist `filename` in der Assembly öffentlich.</span><span class="sxs-lookup"><span data-stu-id="51b66-111">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="51b66-112">Wenn der Dateiname ein Leerzeichen enthält, müssen Sie diesen in Anführungszeichen (" ") einschließen.</span><span class="sxs-lookup"><span data-stu-id="51b66-112">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="51b66-113">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="51b66-113">Optional.</span></span> <span data-ttu-id="51b66-114">Der logische Name der Ressource, der zum Laden derselben verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="51b66-114">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="51b66-115">Der Standardwert ist der Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="51b66-115">The default is the name of the file.</span></span> <span data-ttu-id="51b66-116">Optional können Sie folgendermaßen angeben, ob die Ressource im Assemblymanifest öffentlich oder privat ist: `-res:filename.res, myname.res, public`</span><span class="sxs-lookup"><span data-stu-id="51b66-116">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51b66-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="51b66-117">Remarks</span></span>  
 <span data-ttu-id="51b66-118">Verwenden Sie `-linkresource`, um eine Ressource mit einer Assembly zu verknüpfen, ohne die Ressourcendatei zur Ausgabedatei hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="51b66-118">Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="51b66-119">Wenn es sich bei `filename` um eine .NET Framework-Ressourcendatei handelt, die beispielsweise durch den Resource File Generator ([Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md)) oder in der Entwicklungsumgebung erstellt wurde, ist der Zugriff über Member im <xref:System.Resources>-Namespace möglich. Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager>.</span><span class="sxs-lookup"><span data-stu-id="51b66-119">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="51b66-120">Wenn Sie zur Laufzeit auf alle anderen Ressourcen zugreifen möchten, verwenden Sie die Methoden <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>oder <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="51b66-120">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="51b66-121">Die Kurzform von `-resource` ist `-res`.</span><span class="sxs-lookup"><span data-stu-id="51b66-121">The short form of `-resource` is `-res`.</span></span>  
  
 <span data-ttu-id="51b66-122">Weitere Informationen zum Festlegen von `-resource` in der Visual Studio-IDE finden Sie unter [Verwalten von Anwendungsressourcen (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="51b66-122">For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="51b66-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="51b66-123">Example</span></span>  
 <span data-ttu-id="51b66-124">Mit dem folgenden Code werden `In.vb` kompiliert und die Ressourcendatei `Rf.resource` angefügt.</span><span class="sxs-lookup"><span data-stu-id="51b66-124">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="51b66-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51b66-125">See also</span></span>

- [<span data-ttu-id="51b66-126">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="51b66-126">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="51b66-127">-win32resource</span><span class="sxs-lookup"><span data-stu-id="51b66-127">-win32resource</span></span>](win32resource.md)
- [<span data-ttu-id="51b66-128">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51b66-128">-linkresource (Visual Basic)</span></span>](linkresource.md)
- [<span data-ttu-id="51b66-129">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51b66-129">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="51b66-130">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="51b66-130">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
