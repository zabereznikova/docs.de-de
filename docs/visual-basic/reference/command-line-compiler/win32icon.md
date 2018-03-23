---
title: -win32icon
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95b2e2b4542f2e396a136f6a3d9baeb3e0c037a3
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="-win32icon"></a><span data-ttu-id="3e416-102">-win32icon</span><span class="sxs-lookup"><span data-stu-id="3e416-102">-win32icon</span></span>
<span data-ttu-id="3e416-103">Fügt eine ICO-Datei in die Ausgabedatei ein.</span><span class="sxs-lookup"><span data-stu-id="3e416-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="3e416-104">Diese ICO-Datei stellt die Ausgabedatei in **Datei-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="3e416-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e416-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3e416-105">Syntax</span></span>  
  
```  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="3e416-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="3e416-106">Arguments</span></span>  
  
|<span data-ttu-id="3e416-107">Begriff</span><span class="sxs-lookup"><span data-stu-id="3e416-107">Term</span></span>|<span data-ttu-id="3e416-108">Definition</span><span class="sxs-lookup"><span data-stu-id="3e416-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="3e416-109">Die ICO-Datei für die Ausgabedatei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3e416-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="3e416-110">Setzen Sie den Dateinamen in Anführungszeichen (""), wenn es sich um ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="3e416-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e416-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3e416-111">Remarks</span></span>  
 <span data-ttu-id="3e416-112">Sie können eine ICO-Datei mit der Microsoft Windows Resource-Compiler (RC) erstellen.</span><span class="sxs-lookup"><span data-stu-id="3e416-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="3e416-113">Der Ressourcencompiler wird aufgerufen, wenn Sie ein Visual C++-Programm kompilieren. eine ICO-Datei wird aus der RC-Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="3e416-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="3e416-114">Die `-win32icon` und `-win32resource` Optionen schließen sich gegenseitig.</span><span class="sxs-lookup"><span data-stu-id="3e416-114">The `-win32icon` and `-win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="3e416-115">Finden Sie unter [- Linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) zu verweisen eine [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Ressourcendatei oder [-Ressource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) Anfügen einer [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Ressourcendatei.</span><span class="sxs-lookup"><span data-stu-id="3e416-115">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file.</span></span> <span data-ttu-id="3e416-116">Finden Sie unter [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) eine RES-Datei zu importieren.</span><span class="sxs-lookup"><span data-stu-id="3e416-116">See [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="3e416-117">Festzulegende - win32icon in der Visual Studio-IDE</span><span class="sxs-lookup"><span data-stu-id="3e416-117">To set -win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="3e416-118">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="3e416-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="3e416-119">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="3e416-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="3e416-120">2.  Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="3e416-120">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="3e416-121">3.  Ändern Sie den Wert in der **Symbol** Feld.</span><span class="sxs-lookup"><span data-stu-id="3e416-121">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3e416-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3e416-122">Example</span></span>  
 <span data-ttu-id="3e416-123">Der folgende code kompiliert `In.vb` und fügt eine ICO-Datei `Rf.ico`.</span><span class="sxs-lookup"><span data-stu-id="3e416-123">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="3e416-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3e416-124">See Also</span></span>  
 [<span data-ttu-id="3e416-125">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="3e416-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="3e416-126">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="3e416-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
