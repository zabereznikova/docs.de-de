---
title: -Linkresource (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: 97e0ccd46f413cc05b659731436bb141ee178419
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45596624"
---
# <a name="-linkresource-visual-basic"></a><span data-ttu-id="aa1e8-102">-Linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa1e8-102">-linkresource (Visual Basic)</span></span>
<span data-ttu-id="aa1e8-103">Erstellt einen Link zu einer verwalteten Ressource.</span><span class="sxs-lookup"><span data-stu-id="aa1e8-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa1e8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa1e8-104">Syntax</span></span>  
  
```  
-linkresource:filename[,identifier[,public|private]]  
' -or-  
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="aa1e8-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="aa1e8-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="aa1e8-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="aa1e8-106">Required.</span></span> <span data-ttu-id="aa1e8-107">Die Ressourcendatei der Assembly zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="aa1e8-107">The resource file to link to the assembly.</span></span> <span data-ttu-id="aa1e8-108">Wenn der Dateiname ein Leerzeichen enthält, setzen Sie den Namen in Anführungszeichen ("").</span><span class="sxs-lookup"><span data-stu-id="aa1e8-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="aa1e8-109">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="aa1e8-109">Optional.</span></span> <span data-ttu-id="aa1e8-110">Der logische Name für die Ressource.</span><span class="sxs-lookup"><span data-stu-id="aa1e8-110">The logical name for the resource.</span></span> <span data-ttu-id="aa1e8-111">Der Name, die zum Laden der Ressource verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="aa1e8-111">The name that is used to load the resource.</span></span> <span data-ttu-id="aa1e8-112">Der Standardwert ist der Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="aa1e8-112">The default is the name of the file.</span></span> <span data-ttu-id="aa1e8-113">Optional können Sie angeben, ob die Datei öffentlich oder privat ist, in das Assemblymanifest, z. B.: `-linkres:filename.res,myname.res,public`.</span><span class="sxs-lookup"><span data-stu-id="aa1e8-113">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `-linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="aa1e8-114">In der Standardeinstellung `filename` in der Assembly öffentlich ist.</span><span class="sxs-lookup"><span data-stu-id="aa1e8-114">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa1e8-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aa1e8-115">Remarks</span></span>  
 <span data-ttu-id="aa1e8-116">Die `-linkresource` Option bettet die Ressourcendatei in die Ausgabedatei nicht; verwenden Sie die `-resource` Option aus, um dies zu tun.</span><span class="sxs-lookup"><span data-stu-id="aa1e8-116">The `-linkresource` option does not embed the resource file in the output file; use the `-resource` option to do this.</span></span>  
  
 <span data-ttu-id="aa1e8-117">Die `-linkresource` -Option erfordert eine von der `-target` Optionen, die nicht `-target:module`.</span><span class="sxs-lookup"><span data-stu-id="aa1e8-117">The `-linkresource` option requires one of the `-target` options other than `-target:module`.</span></span>  
  
 <span data-ttu-id="aa1e8-118">Wenn `filename` ist eine [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Ressourcendatei erstellt haben, z. B. durch die [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) oder in der Entwicklungsumgebung, können sie Zugriff mit Membern in der <xref:System.Resources> Namespace.</span><span class="sxs-lookup"><span data-stu-id="aa1e8-118">If `filename` is a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="aa1e8-119">(Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager>.) Verwenden Sie den Zugriff auf alle anderen Ressourcen zur Laufzeit die Methoden, die mit beginnen `GetManifestResource` in die <xref:System.Reflection.Assembly> Klasse.</span><span class="sxs-lookup"><span data-stu-id="aa1e8-119">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="aa1e8-120">Der Dateiname kann jedes Dateiformat sein.</span><span class="sxs-lookup"><span data-stu-id="aa1e8-120">The file name can be any file format.</span></span> <span data-ttu-id="aa1e8-121">Sie können z.B. eine native DLL zu einem Teil der Assembly machen, sodass sie im globalen Assemblycache installiert und aus verwaltetem Code in der Assembly darauf zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="aa1e8-121">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="aa1e8-122">Die Kurzform von `-linkresource` ist `-linkres`.</span><span class="sxs-lookup"><span data-stu-id="aa1e8-122">The short form of `-linkresource` is `-linkres`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa1e8-123">Die `-linkresource` Option ist nicht verfügbar ist, aus der Visual Studio-Entwicklungsumgebung, sondern nur, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="aa1e8-123">The `-linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa1e8-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aa1e8-124">Example</span></span>  
 <span data-ttu-id="aa1e8-125">Der folgende code kompiliert `in.vb` und Links zu Ressourcen `rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="aa1e8-125">The following code compiles `in.vb` and links to resource file `rf.resource`.</span></span>  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="aa1e8-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa1e8-126">See also</span></span>

- [<span data-ttu-id="aa1e8-127">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="aa1e8-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
- [<span data-ttu-id="aa1e8-128">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa1e8-128">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
- [<span data-ttu-id="aa1e8-129">-Resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa1e8-129">-resource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/resource.md)  
- [<span data-ttu-id="aa1e8-130">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="aa1e8-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
