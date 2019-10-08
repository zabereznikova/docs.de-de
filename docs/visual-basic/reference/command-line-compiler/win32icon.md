---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: 6b4b69d227c857442de6857fac023090b3698e81
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004642"
---
# <a name="-win32icon"></a><span data-ttu-id="a656d-102">-win32icon</span><span class="sxs-lookup"><span data-stu-id="a656d-102">-win32icon</span></span>
<span data-ttu-id="a656d-103">Fügt eine ICO-Datei in die Ausgabedatei ein.</span><span class="sxs-lookup"><span data-stu-id="a656d-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="a656d-104">Diese ICO-Datei stellt die Ausgabedatei im **Datei-Explorer**dar.</span><span class="sxs-lookup"><span data-stu-id="a656d-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a656d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a656d-105">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="a656d-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="a656d-106">Arguments</span></span>  
  
|<span data-ttu-id="a656d-107">Begriff</span><span class="sxs-lookup"><span data-stu-id="a656d-107">Term</span></span>|<span data-ttu-id="a656d-108">Definition</span><span class="sxs-lookup"><span data-stu-id="a656d-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="a656d-109">Die ICO-Datei, die der Ausgabedatei hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a656d-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="a656d-110">Schließen Sie den Dateinamen in Anführungszeichen ("") ein, wenn dieser ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="a656d-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a656d-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a656d-111">Remarks</span></span>  
 <span data-ttu-id="a656d-112">Mit dem Microsoft Windows-Ressourcen Compiler (RC) können Sie eine ICO-Datei erstellen.</span><span class="sxs-lookup"><span data-stu-id="a656d-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="a656d-113">Der Ressourcen Compiler wird aufgerufen, wenn Sie ein visuelles C++ Programm kompilieren. eine ICO-Datei wird aus der RC-Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="a656d-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="a656d-114">Die Optionen "`-win32icon`" und "`-win32resource`" schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="a656d-114">The `-win32icon` and `-win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="a656d-115">Weitere Informationen zum Hinzufügen einer .NET Framework Ressourcen Datei finden [Visual Basic](../../../visual-basic/reference/command-line-compiler/resource.md) .NET Framework Sie unter [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) .</span><span class="sxs-lookup"><span data-stu-id="a656d-115">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a .NET Framework resource file.</span></span> <span data-ttu-id="a656d-116">Weitere Informationen finden Sie unter win32resource, um eine res [-](../../../visual-basic/reference/command-line-compiler/win32resource.md) Datei zu importieren.</span><span class="sxs-lookup"><span data-stu-id="a656d-116">See [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="a656d-117">To Set-win32icon in der Visual Studio-IDE</span><span class="sxs-lookup"><span data-stu-id="a656d-117">To set -win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="a656d-118">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="a656d-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="a656d-119">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="a656d-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="a656d-120">2.  Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="a656d-120">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="a656d-121">3.  Ändern Sie den Wert im Feld **Symbol** .</span><span class="sxs-lookup"><span data-stu-id="a656d-121">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a656d-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a656d-122">Example</span></span>  
 <span data-ttu-id="a656d-123">Der folgende Code kompiliert `In.vb` und fügt eine ICO-Datei an, `Rf.ico`.</span><span class="sxs-lookup"><span data-stu-id="a656d-123">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="a656d-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a656d-124">See also</span></span>

- [<span data-ttu-id="a656d-125">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="a656d-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="a656d-126">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="a656d-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
