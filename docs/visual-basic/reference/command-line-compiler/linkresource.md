---
title: / linkresource (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8d4d2d2fdacef0c830414790efa544a96c35fd3c
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="linkresource-visual-basic"></a><span data-ttu-id="e2a3c-102">/linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2a3c-102">/linkresource (Visual Basic)</span></span>
<span data-ttu-id="e2a3c-103">Erstellt einen Link zu einer verwalteten Ressource.</span><span class="sxs-lookup"><span data-stu-id="e2a3c-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2a3c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2a3c-104">Syntax</span></span>  
  
```  
/linkresource:filename[,identifier[,public|private]]  
' -or-  
/linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e2a3c-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="e2a3c-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="e2a3c-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e2a3c-106">Required.</span></span> <span data-ttu-id="e2a3c-107">Die Ressourcendatei, die mit der Assembly zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="e2a3c-107">The resource file to link to the assembly.</span></span> <span data-ttu-id="e2a3c-108">Wenn der Dateiname ein Leerzeichen enthält, schließen Sie den Namen in Anführungszeichen ("").</span><span class="sxs-lookup"><span data-stu-id="e2a3c-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="e2a3c-109">Optional.</span><span class="sxs-lookup"><span data-stu-id="e2a3c-109">Optional.</span></span> <span data-ttu-id="e2a3c-110">Der logische Name der Ressource.</span><span class="sxs-lookup"><span data-stu-id="e2a3c-110">The logical name for the resource.</span></span> <span data-ttu-id="e2a3c-111">Der Name, der zum Laden der Ressource verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e2a3c-111">The name that is used to load the resource.</span></span> <span data-ttu-id="e2a3c-112">Der Standardwert ist der Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="e2a3c-112">The default is the name of the file.</span></span> <span data-ttu-id="e2a3c-113">Optional können Sie angeben, ob die Datei im Assemblymanifest öffentlich oder privat beispielsweise ist: `/linkres:filename.res,myname.res,public`.</span><span class="sxs-lookup"><span data-stu-id="e2a3c-113">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `/linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="e2a3c-114">In der Standardeinstellung `filename` ist in der Assembly öffentlich.</span><span class="sxs-lookup"><span data-stu-id="e2a3c-114">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2a3c-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e2a3c-115">Remarks</span></span>  
 <span data-ttu-id="e2a3c-116">Die `/linkresource` Option bettet die Ressourcendatei in der Ausgabedatei nicht; verwenden Sie die `/resource` Option hierfür.</span><span class="sxs-lookup"><span data-stu-id="e2a3c-116">The `/linkresource` option does not embed the resource file in the output file; use the `/resource` option to do this.</span></span>  
  
 <span data-ttu-id="e2a3c-117">Die `/linkresource` -Option erfordert eine der der `/target` -Optionen `/target:module`.</span><span class="sxs-lookup"><span data-stu-id="e2a3c-117">The `/linkresource` option requires one of the `/target` options other than `/target:module`.</span></span>  
  
 <span data-ttu-id="e2a3c-118">Wenn `filename` ist ein [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Ressourcendatei erstellt, z. B. durch die [Resgen.exe (Resource File Generator)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) oder in der Entwicklungsumgebung darauf zugreifen können mit Mitgliedern der <xref:System.Resources>Namespace.</xref:System.Resources></span><span class="sxs-lookup"><span data-stu-id="e2a3c-118">If `filename` is a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="e2a3c-119">(Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager>.)</xref:System.Resources.ResourceManager> Zugriff auf alle anderen Ressourcen zur Laufzeit verwenden Sie die Methoden, die mit `GetManifestResource` in der <xref:System.Reflection.Assembly>Klasse.</xref:System.Reflection.Assembly></span><span class="sxs-lookup"><span data-stu-id="e2a3c-119">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="e2a3c-120">Der Dateiname kann jedes Dateiformat sein.</span><span class="sxs-lookup"><span data-stu-id="e2a3c-120">The file name can be any file format.</span></span> <span data-ttu-id="e2a3c-121">Beispielsweise empfiehlt es sich um eine systemeigene DLL Teil der Assembly, sodass im globalen Assemblycache installiert und aus verwaltetem Code in der Assembly zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="e2a3c-121">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="e2a3c-122">Die Kurzform der `/linkresource` ist `/linkres`.</span><span class="sxs-lookup"><span data-stu-id="e2a3c-122">The short form of `/linkresource` is `/linkres`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2a3c-123">Die `/linkresource` Option ist nicht verfügbar in der Visual Studio-Entwicklungsumgebung; es kann nur, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="e2a3c-123">The `/linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2a3c-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e2a3c-124">Example</span></span>  
 <span data-ttu-id="e2a3c-125">Der folgende code kompiliert `In.vb` und Links zu Ressourcen-Datei `Rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="e2a3c-125">The following code compiles `In.vb` and links to resource file `Rf.resource`.</span></span>  
  
```  
vbc /linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e2a3c-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2a3c-126">See Also</span></span>  
 <span data-ttu-id="e2a3c-127">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="e2a3c-127">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="e2a3c-128"> [/ target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="e2a3c-128"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="e2a3c-129"> [/ Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) </span><span class="sxs-lookup"><span data-stu-id="e2a3c-129"> [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) </span></span>  
<span data-ttu-id="e2a3c-130"> [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="e2a3c-130"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
