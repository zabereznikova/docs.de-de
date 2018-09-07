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
ms.openlocfilehash: 4f4b3db768b5466f8912b66a0a4709d0f773c1f3
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44047190"
---
# <a name="-linkresource-visual-basic"></a><span data-ttu-id="e6d2c-102">-Linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6d2c-102">-linkresource (Visual Basic)</span></span>
<span data-ttu-id="e6d2c-103">Erstellt einen Link zu einer verwalteten Ressource.</span><span class="sxs-lookup"><span data-stu-id="e6d2c-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6d2c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6d2c-104">Syntax</span></span>  
  
```  
-linkresource:filename[,identifier[,public|private]]  
' -or-  
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e6d2c-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="e6d2c-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="e6d2c-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e6d2c-106">Required.</span></span> <span data-ttu-id="e6d2c-107">Die Ressourcendatei der Assembly zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="e6d2c-107">The resource file to link to the assembly.</span></span> <span data-ttu-id="e6d2c-108">Wenn der Dateiname ein Leerzeichen enthält, setzen Sie den Namen in Anführungszeichen ("").</span><span class="sxs-lookup"><span data-stu-id="e6d2c-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="e6d2c-109">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e6d2c-109">Optional.</span></span> <span data-ttu-id="e6d2c-110">Der logische Name für die Ressource.</span><span class="sxs-lookup"><span data-stu-id="e6d2c-110">The logical name for the resource.</span></span> <span data-ttu-id="e6d2c-111">Der Name, die zum Laden der Ressource verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e6d2c-111">The name that is used to load the resource.</span></span> <span data-ttu-id="e6d2c-112">Der Standardwert ist der Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="e6d2c-112">The default is the name of the file.</span></span> <span data-ttu-id="e6d2c-113">Optional können Sie angeben, ob die Datei öffentlich oder privat ist, in das Assemblymanifest, z. B.: `-linkres:filename.res,myname.res,public`.</span><span class="sxs-lookup"><span data-stu-id="e6d2c-113">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `-linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="e6d2c-114">In der Standardeinstellung `filename` in der Assembly öffentlich ist.</span><span class="sxs-lookup"><span data-stu-id="e6d2c-114">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6d2c-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e6d2c-115">Remarks</span></span>  
 <span data-ttu-id="e6d2c-116">Die `-linkresource` Option bettet die Ressourcendatei in die Ausgabedatei nicht; verwenden Sie die `-resource` Option aus, um dies zu tun.</span><span class="sxs-lookup"><span data-stu-id="e6d2c-116">The `-linkresource` option does not embed the resource file in the output file; use the `-resource` option to do this.</span></span>  
  
 <span data-ttu-id="e6d2c-117">Die `-linkresource` -Option erfordert eine von der `-target` Optionen, die nicht `-target:module`.</span><span class="sxs-lookup"><span data-stu-id="e6d2c-117">The `-linkresource` option requires one of the `-target` options other than `-target:module`.</span></span>  
  
 <span data-ttu-id="e6d2c-118">Wenn `filename` ist eine [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Ressourcendatei erstellt haben, z. B. durch die [Resgen.exe (Resource File Generator)](https://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) oder in der Entwicklungsumgebung, können sie Zugriff mit Membern in der <xref:System.Resources> Namespace.</span><span class="sxs-lookup"><span data-stu-id="e6d2c-118">If `filename` is a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](https://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="e6d2c-119">(Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager>.) Verwenden Sie den Zugriff auf alle anderen Ressourcen zur Laufzeit die Methoden, die mit beginnen `GetManifestResource` in die <xref:System.Reflection.Assembly> Klasse.</span><span class="sxs-lookup"><span data-stu-id="e6d2c-119">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="e6d2c-120">Der Dateiname kann jedes Dateiformat sein.</span><span class="sxs-lookup"><span data-stu-id="e6d2c-120">The file name can be any file format.</span></span> <span data-ttu-id="e6d2c-121">Sie können z.B. eine native DLL zu einem Teil der Assembly machen, sodass sie im globalen Assemblycache installiert und aus verwaltetem Code in der Assembly darauf zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="e6d2c-121">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="e6d2c-122">Die Kurzform von `-linkresource` ist `-linkres`.</span><span class="sxs-lookup"><span data-stu-id="e6d2c-122">The short form of `-linkresource` is `-linkres`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6d2c-123">Die `-linkresource` Option ist nicht verfügbar ist, aus der Visual Studio-Entwicklungsumgebung, sondern nur, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="e6d2c-123">The `-linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6d2c-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e6d2c-124">Example</span></span>  
 <span data-ttu-id="e6d2c-125">Der folgende code kompiliert `in.vb` und Links zu Ressourcen `rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="e6d2c-125">The following code compiles `in.vb` and links to resource file `rf.resource`.</span></span>  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6d2c-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6d2c-126">See Also</span></span>  
 [<span data-ttu-id="e6d2c-127">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="e6d2c-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="e6d2c-128">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6d2c-128">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="e6d2c-129">-Resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6d2c-129">-resource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/resource.md)  
 [<span data-ttu-id="e6d2c-130">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="e6d2c-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
