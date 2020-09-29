---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: c6d5e054063592db5777a76fe19da79337ed5034
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91084956"
---
# <a name="-win32icon"></a><span data-ttu-id="c9e04-102">-win32icon</span><span class="sxs-lookup"><span data-stu-id="c9e04-102">-win32icon</span></span>

<span data-ttu-id="c9e04-103">Diese Option fügt eine ICO-Datei in die Ausgabedatei ein.</span><span class="sxs-lookup"><span data-stu-id="c9e04-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="c9e04-104">Diese ICO-Datei stellt die Ausgabedatei im **Datei-Explorer** dar.</span><span class="sxs-lookup"><span data-stu-id="c9e04-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9e04-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c9e04-105">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="c9e04-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="c9e04-106">Arguments</span></span>  
  
|<span data-ttu-id="c9e04-107">Begriff</span><span class="sxs-lookup"><span data-stu-id="c9e04-107">Term</span></span>|<span data-ttu-id="c9e04-108">Definition</span><span class="sxs-lookup"><span data-stu-id="c9e04-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="c9e04-109">Hierbei handelt es sich um die ICO-Datei, die Sie Ihrer Ausgabedatei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c9e04-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="c9e04-110">Wenn der Dateiname ein Leerzeichen enthält, müssen Sie diesen in Anführungszeichen (" ") einschließen.</span><span class="sxs-lookup"><span data-stu-id="c9e04-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9e04-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c9e04-111">Remarks</span></span>  

 <span data-ttu-id="c9e04-112">Sie können eine ICO-Datei mit dem Microsoft Windows-Ressourcencompiler (RC) erstellen.</span><span class="sxs-lookup"><span data-stu-id="c9e04-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="c9e04-113">Der Ressourcencompiler wird gestartet, wenn Sie ein Visual C++-Programm kompilieren. Aus der RC-Datei wird eine ICO-Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="c9e04-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="c9e04-114">Die Optionen `-win32icon` und `-win32resource` schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="c9e04-114">The `-win32icon` and `-win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="c9e04-115">Weitere Informationen zum Verweis auf eine .NET Framework-Ressourcendatei finden Sie unter [-linkresource (Visual Basic)](linkresource.md). Informationen zum Hinzufügen einer .NET Framework-Ressourcendatei finden Sie unter [-resource (Visual Basic)](resource.md).</span><span class="sxs-lookup"><span data-stu-id="c9e04-115">See [-linkresource (Visual Basic)](linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](resource.md) to attach a .NET Framework resource file.</span></span> <span data-ttu-id="c9e04-116">Weitere Informationen zum Importieren einer RES-Datei finden Sie unter [-win32resource](win32resource.md).</span><span class="sxs-lookup"><span data-stu-id="c9e04-116">See [-win32resource](win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="c9e04-117">Festlegen der -win32icon-Option in der Visual Studio-IDE</span><span class="sxs-lookup"><span data-stu-id="c9e04-117">To set -win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="c9e04-118">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="c9e04-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c9e04-119">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="c9e04-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="c9e04-120">2.  Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="c9e04-120">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="c9e04-121">3.  Ändern Sie den Wert im Feld **Symbol**.</span><span class="sxs-lookup"><span data-stu-id="c9e04-121">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c9e04-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c9e04-122">Example</span></span>  

 <span data-ttu-id="c9e04-123">Mit dem folgenden Code werden `In.vb` kompiliert und eine ICO-Datei (`Rf.ico`) angefügt.</span><span class="sxs-lookup"><span data-stu-id="c9e04-123">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9e04-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9e04-124">See also</span></span>

- [<span data-ttu-id="c9e04-125">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="c9e04-125">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="c9e04-126">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="c9e04-126">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
