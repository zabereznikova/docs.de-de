---
title: /resource (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 858a216873ad9999722388e45d5de28398b27fbe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="resource-visual-basic"></a><span data-ttu-id="f6f4e-102">/resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6f4e-102">/resource (Visual Basic)</span></span>
<span data-ttu-id="f6f4e-103">Bettet eine verwaltete Ressource in eine Assembly ein.</span><span class="sxs-lookup"><span data-stu-id="f6f4e-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6f4e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f6f4e-104">Syntax</span></span>  
  
```  
/resource:filename[,identifier[,public|private]]  
' -or-  
/res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="f6f4e-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="f6f4e-105">Arguments</span></span>  
  
|<span data-ttu-id="f6f4e-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="f6f4e-106">Term</span></span>|<span data-ttu-id="f6f4e-107">Definition</span><span class="sxs-lookup"><span data-stu-id="f6f4e-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="f6f4e-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f6f4e-108">Required.</span></span> <span data-ttu-id="f6f4e-109">Der Name der Ressourcendatei in die Ausgabedatei eingebettet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f6f4e-109">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="f6f4e-110">Standardmäßig `filename` in der Assembly öffentlich ist.</span><span class="sxs-lookup"><span data-stu-id="f6f4e-110">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="f6f4e-111">Setzen Sie den Dateinamen in Anführungszeichen (""), wenn es sich um ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="f6f4e-111">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="f6f4e-112">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="f6f4e-112">Optional.</span></span> <span data-ttu-id="f6f4e-113">Der logische Name für die Ressource; der Name verwendet, um es zu laden.</span><span class="sxs-lookup"><span data-stu-id="f6f4e-113">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="f6f4e-114">Der Standardwert ist der Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="f6f4e-114">The default is the name of the file.</span></span> <span data-ttu-id="f6f4e-115">Optional können Sie angeben, ob die Ressource öffentlich oder privat in das Assemblymanifest, wie mit den folgenden ist: `/res:``filename.res`,`myname.res`,`public`</span><span class="sxs-lookup"><span data-stu-id="f6f4e-115">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `/res:``filename.res`,`myname.res`,`public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6f4e-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f6f4e-116">Remarks</span></span>  
 <span data-ttu-id="f6f4e-117">Verwendung `/linkresource` auf eine Ressource mit einer Assembly verknüpft werden, ohne die Ressourcendatei in die Ausgabedatei platziert.</span><span class="sxs-lookup"><span data-stu-id="f6f4e-117">Use `/linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="f6f4e-118">Wenn `filename` ist ein [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Ressourcendatei erstellt haben, z. B. durch die [Resgen.exe (Resource File Generator)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) oder in der Entwicklungsumgebung können sie Zugriff mit Membern in der <xref:System.Resources> Namespace (siehe <xref:System.Resources.ResourceManager> für Weitere Informationen).</span><span class="sxs-lookup"><span data-stu-id="f6f4e-118">If `filename` is a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="f6f4e-119">Verwenden Sie den Zugriff auf alle anderen Ressourcen zur Laufzeit eine der folgenden Methoden: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, oder <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="f6f4e-119">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="f6f4e-120">Die Kurzform von `/resource` ist `/res`.</span><span class="sxs-lookup"><span data-stu-id="f6f4e-120">The short form of `/resource` is `/res`.</span></span>  
  
 <span data-ttu-id="f6f4e-121">Informationen zum Festlegen von `/resource` in der Visual Studio-IDE finden Sie unter [verwalten Anwendung Ressourcen (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="f6f4e-121">For information about how to set `/resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6f4e-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f6f4e-122">Example</span></span>  
 <span data-ttu-id="f6f4e-123">Der folgende code kompiliert `In.vb` und fügt Ressourcendatei `Rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="f6f4e-123">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```  
vbc /res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f6f4e-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6f4e-124">See Also</span></span>  
 [<span data-ttu-id="f6f4e-125">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="f6f4e-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="f6f4e-126">/win32resource</span><span class="sxs-lookup"><span data-stu-id="f6f4e-126">/win32resource</span></span>](../../../visual-basic/reference/command-line-compiler/win32resource.md)  
 [<span data-ttu-id="f6f4e-127">/ linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6f4e-127">/linkresource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/linkresource.md)  
 [<span data-ttu-id="f6f4e-128">/ target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6f4e-128">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="f6f4e-129">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="f6f4e-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
