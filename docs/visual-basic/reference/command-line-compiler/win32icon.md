---
title: /win32icon | Microsoft-Dokumentation
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
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
caps.latest.revision: 13
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
ms.openlocfilehash: f7d451026438be722d6cb7eecfffe397ccff82ae
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="win32icon"></a><span data-ttu-id="baedd-102">/win32icon</span><span class="sxs-lookup"><span data-stu-id="baedd-102">/win32icon</span></span>
<span data-ttu-id="baedd-103">Fügt eine ICO-Datei in die Ausgabedatei ein.</span><span class="sxs-lookup"><span data-stu-id="baedd-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="baedd-104">Diese ICO-Datei stellt die Ausgabedatei in **Datei-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="baedd-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baedd-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="baedd-105">Syntax</span></span>  
  
```  
/win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="baedd-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="baedd-106">Arguments</span></span>  
  
|<span data-ttu-id="baedd-107">Begriff</span><span class="sxs-lookup"><span data-stu-id="baedd-107">Term</span></span>|<span data-ttu-id="baedd-108">Definition</span><span class="sxs-lookup"><span data-stu-id="baedd-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="baedd-109">Die ICO-Datei in die Ausgabedatei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="baedd-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="baedd-110">Schließen Sie den Dateinamen in Anführungszeichen (""), wenn sie ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="baedd-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="baedd-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="baedd-111">Remarks</span></span>  
 <span data-ttu-id="baedd-112">Sie können eine ICO-Datei mit dem Microsoft Windows Resource Compiler (RC) erstellen.</span><span class="sxs-lookup"><span data-stu-id="baedd-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="baedd-113">Der Ressourcencompiler wird aufgerufen, wenn Sie ein Visual C++-Programm kompilieren. eine ICO-Datei wird aus der RC-Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="baedd-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="baedd-114">Die `/win32icon` und `/win32resource` Optionen gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="baedd-114">The `/win32icon` and `/win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="baedd-115">Finden Sie unter [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) auf eine [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Ressourcendatei oder [/Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) Anfügen einer [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Ressourcendatei.</span><span class="sxs-lookup"><span data-stu-id="baedd-115">See [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] resource file, or [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] resource file.</span></span> <span data-ttu-id="baedd-116">Finden Sie unter [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) eine RES-Datei zu importieren.</span><span class="sxs-lookup"><span data-stu-id="baedd-116">See [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="baedd-117">/Win32icon in der Visual Studio-IDE festlegen</span><span class="sxs-lookup"><span data-stu-id="baedd-117">To set /win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="baedd-118">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="baedd-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="baedd-119">Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="baedd-119">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="baedd-120">Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="baedd-120">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="baedd-121">2.  Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="baedd-121">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="baedd-122">3.  Ändern Sie den Wert in der **Symbol** Feld.</span><span class="sxs-lookup"><span data-stu-id="baedd-122">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="baedd-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="baedd-123">Example</span></span>  
 <span data-ttu-id="baedd-124">Der folgende code kompiliert `In.vb` und fügt eine ICO-Datei `Rf.ico`.</span><span class="sxs-lookup"><span data-stu-id="baedd-124">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```  
vbc /win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="baedd-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="baedd-125">See Also</span></span>  
 <span data-ttu-id="baedd-126">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="baedd-126">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="baedd-127"> [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="baedd-127"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
