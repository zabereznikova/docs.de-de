---
title: -Ressource (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: 5bedc346381f6de293933dce14a8c5c3044b246f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005190"
---
# <a name="-resource-visual-basic"></a><span data-ttu-id="5c0cb-102">-Ressource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c0cb-102">-resource (Visual Basic)</span></span>
<span data-ttu-id="5c0cb-103">Bettet eine verwaltete Ressource in eine Assembly ein.</span><span class="sxs-lookup"><span data-stu-id="5c0cb-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c0cb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c0cb-104">Syntax</span></span>  
  
```console  
-resource:filename[,identifier[,public|private]]  
```

<span data-ttu-id="5c0cb-105">oder</span><span class="sxs-lookup"><span data-stu-id="5c0cb-105">or</span></span>  

```console
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="5c0cb-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="5c0cb-106">Arguments</span></span>  
  
|<span data-ttu-id="5c0cb-107">Begriff</span><span class="sxs-lookup"><span data-stu-id="5c0cb-107">Term</span></span>|<span data-ttu-id="5c0cb-108">Definition</span><span class="sxs-lookup"><span data-stu-id="5c0cb-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="5c0cb-109">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5c0cb-109">Required.</span></span> <span data-ttu-id="5c0cb-110">Der Name der Ressourcen Datei, die in die Ausgabedatei eingebettet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c0cb-110">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="5c0cb-111">Standardmäßig ist `filename` in der Assembly öffentlich.</span><span class="sxs-lookup"><span data-stu-id="5c0cb-111">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="5c0cb-112">Schließen Sie den Dateinamen in Anführungszeichen ("") ein, wenn dieser ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="5c0cb-112">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="5c0cb-113">Optional.</span><span class="sxs-lookup"><span data-stu-id="5c0cb-113">Optional.</span></span> <span data-ttu-id="5c0cb-114">Der logische Name der Ressource. der Name, der verwendet wird, um ihn zu laden.</span><span class="sxs-lookup"><span data-stu-id="5c0cb-114">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="5c0cb-115">Der Standardwert ist der Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="5c0cb-115">The default is the name of the file.</span></span> <span data-ttu-id="5c0cb-116">Optional können Sie angeben, ob die Ressource im Assemblymanifest öffentlich oder privat ist, wie im folgenden angegeben: `-res:filename.res, myname.res, public`</span><span class="sxs-lookup"><span data-stu-id="5c0cb-116">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c0cb-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5c0cb-117">Remarks</span></span>  
 <span data-ttu-id="5c0cb-118">Verwenden Sie `-linkresource`, um eine Ressource mit einer Assembly zu verknüpfen, ohne die Ressourcen Datei in der Ausgabedatei zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="5c0cb-118">Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="5c0cb-119">Wenn `filename` eine .NET Framework Ressourcen Datei ist, die beispielsweise von [Resgen. exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) oder in der Entwicklungsumgebung erstellt wurde, ist der Zugriff mit Membern im <xref:System.Resources>-Namespace möglich (Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager>).</span><span class="sxs-lookup"><span data-stu-id="5c0cb-119">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="5c0cb-120">Wenn Sie zur Laufzeit auf alle anderen Ressourcen zugreifen möchten, verwenden Sie eine der folgenden Methoden: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A> oder <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="5c0cb-120">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="5c0cb-121">Die Kurzform von `-resource` ist `-res`.</span><span class="sxs-lookup"><span data-stu-id="5c0cb-121">The short form of `-resource` is `-res`.</span></span>  
  
 <span data-ttu-id="5c0cb-122">Informationen dazu, wie Sie `-resource` in der Visual Studio-IDE festlegen, finden Sie unter [Verwalten von Anwendungs Ressourcen (.net)](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="5c0cb-122">For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c0cb-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c0cb-123">Example</span></span>  
 <span data-ttu-id="5c0cb-124">Mit dem folgenden Code wird `In.vb` kompiliert und die Ressourcen Datei `Rf.resource` angefügt.</span><span class="sxs-lookup"><span data-stu-id="5c0cb-124">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="5c0cb-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c0cb-125">See also</span></span>

- [<span data-ttu-id="5c0cb-126">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="5c0cb-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="5c0cb-127">-win32resource</span><span class="sxs-lookup"><span data-stu-id="5c0cb-127">-win32resource</span></span>](../../../visual-basic/reference/command-line-compiler/win32resource.md)
- [<span data-ttu-id="5c0cb-128">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c0cb-128">-linkresource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/linkresource.md)
- [<span data-ttu-id="5c0cb-129">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c0cb-129">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="5c0cb-130">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="5c0cb-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
