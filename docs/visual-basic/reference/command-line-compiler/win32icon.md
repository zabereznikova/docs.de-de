---
title: /win32icon
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 65149c617220966bc3bb6897d757a71cd60167d6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="win32icon"></a><span data-ttu-id="bf11b-102">/win32icon</span><span class="sxs-lookup"><span data-stu-id="bf11b-102">/win32icon</span></span>
<span data-ttu-id="bf11b-103">Fügt eine ICO-Datei in die Ausgabedatei ein.</span><span class="sxs-lookup"><span data-stu-id="bf11b-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="bf11b-104">Diese ICO-Datei stellt die Ausgabedatei in **Datei-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="bf11b-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf11b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf11b-105">Syntax</span></span>  
  
```  
/win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="bf11b-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="bf11b-106">Arguments</span></span>  
  
|<span data-ttu-id="bf11b-107">Begriff</span><span class="sxs-lookup"><span data-stu-id="bf11b-107">Term</span></span>|<span data-ttu-id="bf11b-108">Definition</span><span class="sxs-lookup"><span data-stu-id="bf11b-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="bf11b-109">Die ICO-Datei für die Ausgabedatei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="bf11b-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="bf11b-110">Setzen Sie den Dateinamen in Anführungszeichen (""), wenn es sich um ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="bf11b-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf11b-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bf11b-111">Remarks</span></span>  
 <span data-ttu-id="bf11b-112">Sie können eine ICO-Datei mit der Microsoft Windows Resource-Compiler (RC) erstellen.</span><span class="sxs-lookup"><span data-stu-id="bf11b-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="bf11b-113">Der Ressourcencompiler wird aufgerufen, wenn Sie ein Visual C++-Programm kompilieren. eine ICO-Datei wird aus der RC-Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="bf11b-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="bf11b-114">Die `/win32icon` und `/win32resource` Optionen schließen sich gegenseitig.</span><span class="sxs-lookup"><span data-stu-id="bf11b-114">The `/win32icon` and `/win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="bf11b-115">Finden Sie unter [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) zu verweisen eine [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Ressourcendatei oder [/Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) Anfügen einer [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Ressourcendatei.</span><span class="sxs-lookup"><span data-stu-id="bf11b-115">See [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file, or [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file.</span></span> <span data-ttu-id="bf11b-116">Finden Sie unter [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) eine RES-Datei zu importieren.</span><span class="sxs-lookup"><span data-stu-id="bf11b-116">See [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="bf11b-117">So legen Sie /win32icon in der Visual Studio-IDE fest</span><span class="sxs-lookup"><span data-stu-id="bf11b-117">To set /win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="bf11b-118">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="bf11b-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="bf11b-119">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="bf11b-119">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="bf11b-120">Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="bf11b-120">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="bf11b-121">2.  Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="bf11b-121">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="bf11b-122">3.  Ändern Sie den Wert in der **Symbol** Feld.</span><span class="sxs-lookup"><span data-stu-id="bf11b-122">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bf11b-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bf11b-123">Example</span></span>  
 <span data-ttu-id="bf11b-124">Der folgende code kompiliert `In.vb` und fügt eine ICO-Datei `Rf.ico`.</span><span class="sxs-lookup"><span data-stu-id="bf11b-124">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```  
vbc /win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="bf11b-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf11b-125">See Also</span></span>  
 [<span data-ttu-id="bf11b-126">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="bf11b-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="bf11b-127">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="bf11b-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
