---
title: / Resource (Visual Basic) | Microsoft-Dokumentation
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
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2278902f96f7b6349e91a9803f58c3caa89f4f33
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="resource-visual-basic"></a><span data-ttu-id="d6ae5-102">/resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6ae5-102">/resource (Visual Basic)</span></span>
<span data-ttu-id="d6ae5-103">Bettet eine verwaltete Ressource in eine Assembly ein.</span><span class="sxs-lookup"><span data-stu-id="d6ae5-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6ae5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d6ae5-104">Syntax</span></span>  
  
```  
/resource:filename[,identifier[,public|private]]  
' -or-  
/res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d6ae5-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="d6ae5-105">Arguments</span></span>  
  
|<span data-ttu-id="d6ae5-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="d6ae5-106">Term</span></span>|<span data-ttu-id="d6ae5-107">Definition</span><span class="sxs-lookup"><span data-stu-id="d6ae5-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="d6ae5-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d6ae5-108">Required.</span></span> <span data-ttu-id="d6ae5-109">Der Name der Ressourcendatei in die Ausgabedatei eingebettet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d6ae5-109">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="d6ae5-110">In der Standardeinstellung `filename` ist in der Assembly öffentlich.</span><span class="sxs-lookup"><span data-stu-id="d6ae5-110">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="d6ae5-111">Schließen Sie den Dateinamen in Anführungszeichen (""), wenn sie ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="d6ae5-111">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="d6ae5-112">Optional.</span><span class="sxs-lookup"><span data-stu-id="d6ae5-112">Optional.</span></span> <span data-ttu-id="d6ae5-113">Der logische Name der Ressource; der Name verwendet, um es zu laden.</span><span class="sxs-lookup"><span data-stu-id="d6ae5-113">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="d6ae5-114">Der Standardwert ist der Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="d6ae5-114">The default is the name of the file.</span></span> <span data-ttu-id="d6ae5-115">Optional können Sie angeben, ob die Ressource im Assemblymanifest öffentlich oder privat wie mit den folgenden ist: `/res:``filename.res`,`myname.res`,`public`</span><span class="sxs-lookup"><span data-stu-id="d6ae5-115">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `/res:``filename.res`,`myname.res`,`public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6ae5-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d6ae5-116">Remarks</span></span>  
 <span data-ttu-id="d6ae5-117">Verwendung `/linkresource` auf eine Ressource mit einer Assembly zu verknüpfen, ohne dass die Ressourcendatei in der Ausgabedatei.</span><span class="sxs-lookup"><span data-stu-id="d6ae5-117">Use `/linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="d6ae5-118">Wenn `filename` ist ein [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Ressourcendatei erstellt, z. B. durch die [Resgen.exe (Resource File Generator)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) oder in der Entwicklungsumgebung darauf zugreifen können mit Mitgliedern der <xref:System.Resources>Namespace (finden Sie unter <xref:System.Resources.ResourceManager>Weitere Informationen).</xref:System.Resources.ResourceManager> </xref:System.Resources></span><span class="sxs-lookup"><span data-stu-id="d6ae5-118">If `filename` is a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="d6ae5-119">Zugriff auf alle anderen Ressourcen zur Laufzeit verwenden Sie eine der folgenden Methoden: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, oder <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</xref:System.Reflection.Assembly.GetManifestResourceStream%2A> </xref:System.Reflection.Assembly.GetManifestResourceNames%2A> </xref:System.Reflection.Assembly.GetManifestResourceInfo%2A></span><span class="sxs-lookup"><span data-stu-id="d6ae5-119">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="d6ae5-120">Die Kurzform der `/resource` ist `/res`.</span><span class="sxs-lookup"><span data-stu-id="d6ae5-120">The short form of `/resource` is `/res`.</span></span>  
  
 <span data-ttu-id="d6ae5-121">Für Informationen zum Festlegen von `/resource` in der Visual Studio-IDE finden Sie unter [Verwalten von Ressourcen (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="d6ae5-121">For information about how to set `/resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6ae5-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d6ae5-122">Example</span></span>  
 <span data-ttu-id="d6ae5-123">Der folgende code kompiliert `In.vb` und fügt Ressourcendatei `Rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="d6ae5-123">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```  
vbc /res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6ae5-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6ae5-124">See Also</span></span>  
 <span data-ttu-id="d6ae5-125">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="d6ae5-125">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="d6ae5-126"> [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) </span><span class="sxs-lookup"><span data-stu-id="d6ae5-126"> [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) </span></span>  
<span data-ttu-id="d6ae5-127"> [/ linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) </span><span class="sxs-lookup"><span data-stu-id="d6ae5-127"> [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) </span></span>  
<span data-ttu-id="d6ae5-128"> [/ target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="d6ae5-128"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="d6ae5-129"> [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="d6ae5-129"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
