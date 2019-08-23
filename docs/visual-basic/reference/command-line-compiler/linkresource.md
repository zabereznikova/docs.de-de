---
title: -linkresource (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: d92b0d08daf660880b648875c67c3b78069143d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69924860"
---
# <a name="-linkresource-visual-basic"></a><span data-ttu-id="0f081-102">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f081-102">-linkresource (Visual Basic)</span></span>
<span data-ttu-id="0f081-103">Erstellt einen Link zu einer verwalteten Ressource.</span><span class="sxs-lookup"><span data-stu-id="0f081-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f081-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f081-104">Syntax</span></span>  
  
```  
-linkresource:filename[,identifier[,public|private]]  
' -or-  
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0f081-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="0f081-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="0f081-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0f081-106">Required.</span></span> <span data-ttu-id="0f081-107">Die Ressourcen Datei, die mit der Assembly verknüpft werden soll.</span><span class="sxs-lookup"><span data-stu-id="0f081-107">The resource file to link to the assembly.</span></span> <span data-ttu-id="0f081-108">Wenn der Dateiname ein Leerzeichen enthält, müssen Sie den Namen in Anführungszeichen ("") einschließen.</span><span class="sxs-lookup"><span data-stu-id="0f081-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="0f081-109">Optional.</span><span class="sxs-lookup"><span data-stu-id="0f081-109">Optional.</span></span> <span data-ttu-id="0f081-110">Der logische Name der Ressource.</span><span class="sxs-lookup"><span data-stu-id="0f081-110">The logical name for the resource.</span></span> <span data-ttu-id="0f081-111">Der Name, der zum Laden der Ressource verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0f081-111">The name that is used to load the resource.</span></span> <span data-ttu-id="0f081-112">Der Standardwert ist der Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="0f081-112">The default is the name of the file.</span></span> <span data-ttu-id="0f081-113">Optional können Sie angeben, ob die Datei im Assemblymanifest öffentlich oder privat ist, z. `-linkres:filename.res,myname.res,public`b.:.</span><span class="sxs-lookup"><span data-stu-id="0f081-113">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `-linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="0f081-114">Standardmäßig `filename` ist in der Assembly öffentlich.</span><span class="sxs-lookup"><span data-stu-id="0f081-114">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f081-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0f081-115">Remarks</span></span>  
 <span data-ttu-id="0f081-116">Die `-linkresource` -Option bettet die Ressourcen Datei nicht in die Ausgabedatei ein. `-resource` verwenden Sie hierfür die-Option.</span><span class="sxs-lookup"><span data-stu-id="0f081-116">The `-linkresource` option does not embed the resource file in the output file; use the `-resource` option to do this.</span></span>  
  
 <span data-ttu-id="0f081-117">Die `-linkresource` Option erfordert eine `-target` der anderen Optionen als `-target:module`.</span><span class="sxs-lookup"><span data-stu-id="0f081-117">The `-linkresource` option requires one of the `-target` options other than `-target:module`.</span></span>  
  
 <span data-ttu-id="0f081-118">Wenn `filename` eine .NET Framework Ressourcen Datei ist, die beispielsweise von [Resgen. exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) oder in der Entwicklungsumgebung erstellt wurde, kann <xref:System.Resources> mit Membern im-Namespace darauf zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="0f081-118">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="0f081-119">(Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager>.) Wenn Sie zur Laufzeit auf alle anderen Ressourcen zugreifen möchten, verwenden Sie die Methoden `GetManifestResource` , die <xref:System.Reflection.Assembly> mit in der-Klasse beginnen.</span><span class="sxs-lookup"><span data-stu-id="0f081-119">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="0f081-120">Der Dateiname kann ein beliebiges Dateiformat aufweisen.</span><span class="sxs-lookup"><span data-stu-id="0f081-120">The file name can be any file format.</span></span> <span data-ttu-id="0f081-121">Sie können z.B. eine native DLL zu einem Teil der Assembly machen, sodass sie im globalen Assemblycache installiert und aus verwaltetem Code in der Assembly darauf zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="0f081-121">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="0f081-122">Die Kurzform von `-linkresource` ist `-linkres`.</span><span class="sxs-lookup"><span data-stu-id="0f081-122">The short form of `-linkresource` is `-linkres`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0f081-123">Die `-linkresource` Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="0f081-123">The `-linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f081-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0f081-124">Example</span></span>  
 <span data-ttu-id="0f081-125">Der folgende Code kompiliert `in.vb` und verknüpft die Ressourcen Datei. `rf.resource`</span><span class="sxs-lookup"><span data-stu-id="0f081-125">The following code compiles `in.vb` and links to resource file `rf.resource`.</span></span>  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f081-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f081-126">See also</span></span>

- [<span data-ttu-id="0f081-127">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="0f081-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="0f081-128">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f081-128">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="0f081-129">-Ressource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f081-129">-resource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/resource.md)
- [<span data-ttu-id="0f081-130">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="0f081-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
