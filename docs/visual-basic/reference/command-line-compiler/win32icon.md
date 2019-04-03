---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: e36e9187ab8c9c2b4950a66ff8ff3fc93adbd9c4
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821477"
---
# <a name="-win32icon"></a><span data-ttu-id="bd996-102">-win32icon</span><span class="sxs-lookup"><span data-stu-id="bd996-102">-win32icon</span></span>
<span data-ttu-id="bd996-103">Fügt eine ICO-Datei in die Ausgabedatei ein.</span><span class="sxs-lookup"><span data-stu-id="bd996-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="bd996-104">Diese ICO-Datei stellt die Ausgabedatei im **Datei-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="bd996-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd996-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bd996-105">Syntax</span></span>  
  
```  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="bd996-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="bd996-106">Arguments</span></span>  
  
|<span data-ttu-id="bd996-107">Begriff</span><span class="sxs-lookup"><span data-stu-id="bd996-107">Term</span></span>|<span data-ttu-id="bd996-108">Definition</span><span class="sxs-lookup"><span data-stu-id="bd996-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="bd996-109">Die ICO-Datei Ihrer Ausgabedatei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="bd996-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="bd996-110">Schließen Sie den Dateinamen in Anführungszeichen (""), wenn sie ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="bd996-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd996-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bd996-111">Remarks</span></span>  
 <span data-ttu-id="bd996-112">Sie können eine ICO-Datei mit dem Microsoft Windows Resource-Compiler (RC) erstellen.</span><span class="sxs-lookup"><span data-stu-id="bd996-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="bd996-113">Der Ressourcencompiler wird aufgerufen, wenn Sie ein Visual C++-Programm kompilieren. eine ICO-Datei wird aus der RC-Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="bd996-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="bd996-114">Die `-win32icon` und `-win32resource` Optionen schließen sich gegenseitig.</span><span class="sxs-lookup"><span data-stu-id="bd996-114">The `-win32icon` and `-win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="bd996-115">Finden Sie unter [- Linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) zu verweisen eine [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Ressourcendatei oder [-Ressource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) zum Anfügen einer [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Ressourcendatei.</span><span class="sxs-lookup"><span data-stu-id="bd996-115">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file.</span></span> <span data-ttu-id="bd996-116">Finden Sie unter [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) um eine RES-Datei zu importieren.</span><span class="sxs-lookup"><span data-stu-id="bd996-116">See [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="bd996-117">Festzulegende - win32icon in der Visual Studio-IDE</span><span class="sxs-lookup"><span data-stu-id="bd996-117">To set -win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="bd996-118">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="bd996-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="bd996-119">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="bd996-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="bd996-120">2.  Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="bd996-120">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="bd996-121">3.  Ändern Sie den Wert in der **Symbol** Feld.</span><span class="sxs-lookup"><span data-stu-id="bd996-121">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bd996-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bd996-122">Example</span></span>  
 <span data-ttu-id="bd996-123">Der folgende code kompiliert `In.vb` und fügt eine ICO-Datei, `Rf.ico`.</span><span class="sxs-lookup"><span data-stu-id="bd996-123">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="bd996-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd996-124">See also</span></span>

- [<span data-ttu-id="bd996-125">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="bd996-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="bd996-126">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="bd996-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
