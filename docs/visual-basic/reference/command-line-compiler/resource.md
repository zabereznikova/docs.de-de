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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ab5593455546e65bdd760d9e60532031dc1f12a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-resource-visual-basic"></a><span data-ttu-id="184db-102">-Ressource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="184db-102">-resource (Visual Basic)</span></span>
<span data-ttu-id="184db-103">Bettet eine verwaltete Ressource in eine Assembly ein.</span><span class="sxs-lookup"><span data-stu-id="184db-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="184db-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="184db-104">Syntax</span></span>  
  
```  
-resource:filename[,identifier[,public|private]]  
' -or-  
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="184db-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="184db-105">Arguments</span></span>  
  
|<span data-ttu-id="184db-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="184db-106">Term</span></span>|<span data-ttu-id="184db-107">Definition</span><span class="sxs-lookup"><span data-stu-id="184db-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="184db-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="184db-108">Required.</span></span> <span data-ttu-id="184db-109">Der Name der Ressourcendatei in die Ausgabedatei eingebettet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="184db-109">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="184db-110">Standardmäßig `filename` in der Assembly öffentlich ist.</span><span class="sxs-lookup"><span data-stu-id="184db-110">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="184db-111">Setzen Sie den Dateinamen in Anführungszeichen (""), wenn es sich um ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="184db-111">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="184db-112">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="184db-112">Optional.</span></span> <span data-ttu-id="184db-113">Der logische Name für die Ressource; der Name verwendet, um es zu laden.</span><span class="sxs-lookup"><span data-stu-id="184db-113">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="184db-114">Der Standardwert ist der Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="184db-114">The default is the name of the file.</span></span> <span data-ttu-id="184db-115">Optional können Sie angeben, ob die Ressource öffentlich oder privat in das Assemblymanifest, wie mit den folgenden ist: `-res:filename.res, myname.res, public`</span><span class="sxs-lookup"><span data-stu-id="184db-115">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="184db-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="184db-116">Remarks</span></span>  
 <span data-ttu-id="184db-117">Verwendung `-linkresource` auf eine Ressource mit einer Assembly verknüpft werden, ohne die Ressourcendatei in die Ausgabedatei platziert.</span><span class="sxs-lookup"><span data-stu-id="184db-117">Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="184db-118">Wenn `filename` ist ein [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Ressourcendatei erstellt haben, z. B. durch die [Resgen.exe (Resource File Generator)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) oder in der Entwicklungsumgebung können sie Zugriff mit Membern in der <xref:System.Resources> Namespace (siehe <xref:System.Resources.ResourceManager> für Weitere Informationen).</span><span class="sxs-lookup"><span data-stu-id="184db-118">If `filename` is a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="184db-119">Verwenden Sie den Zugriff auf alle anderen Ressourcen zur Laufzeit eine der folgenden Methoden: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, oder <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="184db-119">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="184db-120">Die Kurzform von `-resource` ist `-res`.</span><span class="sxs-lookup"><span data-stu-id="184db-120">The short form of `-resource` is `-res`.</span></span>  
  
 <span data-ttu-id="184db-121">Informationen zum Festlegen von `-resource` in der Visual Studio-IDE finden Sie unter [verwalten Anwendung Ressourcen (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="184db-121">For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="184db-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="184db-122">Example</span></span>  
 <span data-ttu-id="184db-123">Der folgende code kompiliert `In.vb` und fügt Ressourcendatei `Rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="184db-123">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="184db-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="184db-124">See Also</span></span>  
 [<span data-ttu-id="184db-125">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="184db-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="184db-126">-win32resource</span><span class="sxs-lookup"><span data-stu-id="184db-126">-win32resource</span></span>](../../../visual-basic/reference/command-line-compiler/win32resource.md)  
 [<span data-ttu-id="184db-127">-Linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="184db-127">-linkresource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/linkresource.md)  
 [<span data-ttu-id="184db-128">-Ziel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="184db-128">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="184db-129">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="184db-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
