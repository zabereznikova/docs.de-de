---
title: -linkresource
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: 8c4f753f94aedaf0a4f997a3f9b99fb3f417abf8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91065683"
---
# <a name="-linkresource-visual-basic"></a><span data-ttu-id="67b01-102">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67b01-102">-linkresource (Visual Basic)</span></span>

<span data-ttu-id="67b01-103">Erstellt einen Link zu einer verwalteten Ressource.</span><span class="sxs-lookup"><span data-stu-id="67b01-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67b01-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="67b01-104">Syntax</span></span>  
  
```console  
-linkresource:filename[,identifier[,public|private]]  
```

<span data-ttu-id="67b01-105">oder</span><span class="sxs-lookup"><span data-stu-id="67b01-105">or</span></span>  

```console
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="67b01-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="67b01-106">Arguments</span></span>  

 `filename`  
 <span data-ttu-id="67b01-107">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="67b01-107">Required.</span></span> <span data-ttu-id="67b01-108">Die Ressourcendatei, die mit der Assembly verknüpft werden soll.</span><span class="sxs-lookup"><span data-stu-id="67b01-108">The resource file to link to the assembly.</span></span> <span data-ttu-id="67b01-109">Wenn der Dateiname ein Leerzeichen enthält, müssen Sie diesen in Anführungszeichen (" ") einschließen.</span><span class="sxs-lookup"><span data-stu-id="67b01-109">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="67b01-110">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="67b01-110">Optional.</span></span> <span data-ttu-id="67b01-111">Der logische Name der Ressource.</span><span class="sxs-lookup"><span data-stu-id="67b01-111">The logical name for the resource.</span></span> <span data-ttu-id="67b01-112">Der Name, der zum Laden der Ressource verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="67b01-112">The name that is used to load the resource.</span></span> <span data-ttu-id="67b01-113">Der Standardwert ist der Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="67b01-113">The default is the name of the file.</span></span> <span data-ttu-id="67b01-114">Optional können Sie folgendermaßen angeben, ob die Datei im Assemblymanifest öffentlich oder privat ist: `-linkres:filename.res,myname.res,public`.</span><span class="sxs-lookup"><span data-stu-id="67b01-114">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `-linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="67b01-115">Standardmäßig ist `filename` in der Assembly öffentlich.</span><span class="sxs-lookup"><span data-stu-id="67b01-115">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67b01-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="67b01-116">Remarks</span></span>  

 <span data-ttu-id="67b01-117">Mit der Option `-linkresource` wird die Ressourcendatei nicht in die Ausgabedatei eingebettet. Verwenden Sie hierfür die Option `-resource`.</span><span class="sxs-lookup"><span data-stu-id="67b01-117">The `-linkresource` option does not embed the resource file in the output file; use the `-resource` option to do this.</span></span>  
  
 <span data-ttu-id="67b01-118">Die Option `-linkresource` erfordert eine der `-target`-Optionen (außer `-target:module`).</span><span class="sxs-lookup"><span data-stu-id="67b01-118">The `-linkresource` option requires one of the `-target` options other than `-target:module`.</span></span>  
  
 <span data-ttu-id="67b01-119">Wenn es sich bei `filename` um eine .NET Framework-Ressourcendatei handelt, die beispielsweise durch den Resource File Generator ([Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md)) oder in der Entwicklungsumgebung erstellt wurde, ist der Zugriff mit Membern im <xref:System.Resources>-Namespace möglich.</span><span class="sxs-lookup"><span data-stu-id="67b01-119">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="67b01-120">Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager>. Wenn Sie zur Laufzeit auf alle anderen Ressourcen zugreifen möchten, verwenden Sie die Methoden der Klasse <xref:System.Reflection.Assembly>, die mit `GetManifestResource` beginnen.</span><span class="sxs-lookup"><span data-stu-id="67b01-120">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="67b01-121">Der Dateiname kann ein beliebiges Dateiformat aufweisen.</span><span class="sxs-lookup"><span data-stu-id="67b01-121">The file name can be any file format.</span></span> <span data-ttu-id="67b01-122">Sie können z.B. eine native DLL zu einem Teil der Assembly machen, sodass sie im globalen Assemblycache installiert und aus verwaltetem Code in der Assembly darauf zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="67b01-122">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="67b01-123">Die Kurzform von `-linkresource` ist `-linkres`.</span><span class="sxs-lookup"><span data-stu-id="67b01-123">The short form of `-linkresource` is `-linkres`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="67b01-124">Die Option `-linkresource` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="67b01-124">The `-linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67b01-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="67b01-125">Example</span></span>  

 <span data-ttu-id="67b01-126">Mit dem folgenden Code werden `in.vb` kompiliert und eine Verknüpfung mit der Ressourcendatei `rf.resource` generiert.</span><span class="sxs-lookup"><span data-stu-id="67b01-126">The following code compiles `in.vb` and links to resource file `rf.resource`.</span></span>  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="67b01-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67b01-127">See also</span></span>

- [<span data-ttu-id="67b01-128">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="67b01-128">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="67b01-129">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67b01-129">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="67b01-130">-resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67b01-130">-resource (Visual Basic)</span></span>](resource.md)
- [<span data-ttu-id="67b01-131">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="67b01-131">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
