---
description: -win32icon (C#-Compileroptionen)
title: -win32icon (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /win32icon
helpviewer_keywords:
- win32icon compiler option [C#]
- /win32icon compiler option [C#]
- -win32icon compiler option [C#]
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
ms.openlocfilehash: 76a54f9011371492bdc15f15c3e40d51082deed3
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138409"
---
# <a name="-win32icon-c-compiler-options"></a><span data-ttu-id="25f13-103">-win32icon (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="25f13-103">-win32icon (C# Compiler Options)</span></span>
<span data-ttu-id="25f13-104">Die Option **-win32icon** fügt der Ausgabedatei eine ICO-Datei hinzu, die der Ausgabedatei im Datei-Explorer das gewünschte Aussehen verleiht.</span><span class="sxs-lookup"><span data-stu-id="25f13-104">The **-win32icon** option inserts an .ico file in the output file, which gives the output file the desired appearance in the File Explorer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25f13-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="25f13-105">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="25f13-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="25f13-106">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="25f13-107">Die ICO-Datei, die Sie Ihrer Ausgabedatei hinzufügen möchten</span><span class="sxs-lookup"><span data-stu-id="25f13-107">The .ico file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25f13-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="25f13-108">Remarks</span></span>  
 <span data-ttu-id="25f13-109">Eine ICO-Datei kann mit dem [Ressourcencompiler](/windows/desktop/menurc/resource-compiler) erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="25f13-109">An .ico file can be created with the [Resource Compiler](/windows/desktop/menurc/resource-compiler).</span></span> <span data-ttu-id="25f13-110">Der Ressourcencompiler wird gestartet, wenn Sie ein Visual C++-Programm kompilieren. Aus der RC-Datei wird eine ICO-Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="25f13-110">The Resource Compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="25f13-111">Weitere Informationen zum Verweisen auf eine .NET Framework-Ressourcendatei finden Sie unter [-linkresource](./linkresource-compiler-option.md), weitere Informationen zum Anfügen einer .NET Framework-Ressourcendatei unter [-resource](./resource-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="25f13-111">See [-linkresource](./linkresource-compiler-option.md) (to reference) or [-resource](./resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span> <span data-ttu-id="25f13-112">Weitere Informationen zum Importieren einer RES-Datei finden Sie unter [-win32res](./win32res-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="25f13-112">See [-win32res](./win32res-compiler-option.md) to import a .res file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="25f13-113">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="25f13-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="25f13-114">Öffnen Sie die **Eigenschaftenseite**des Projekts.</span><span class="sxs-lookup"><span data-stu-id="25f13-114">Open the project's **Properties** pages.</span></span>  
  
2. <span data-ttu-id="25f13-115">Klicken Sie auf die Eigenschaftenseite **Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="25f13-115">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="25f13-116">Ändern Sie die Eigenschaft **Anwendungssymbol**.</span><span class="sxs-lookup"><span data-stu-id="25f13-116">Modify the **Application icon** property.</span></span>  
  
 <span data-ttu-id="25f13-117">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span><span class="sxs-lookup"><span data-stu-id="25f13-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25f13-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="25f13-118">Example</span></span>  
 <span data-ttu-id="25f13-119">Kompilieren Sie `in.cs`, und fügen Sie eine ICO-Datei `rf.ico` hinzu, um `in.exe` zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="25f13-119">Compile `in.cs` and attach an .ico file `rf.ico` to produce `in.exe`:</span></span>  
  
```console  
csc -win32icon:rf.ico in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="25f13-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="25f13-120">See also</span></span>

- [<span data-ttu-id="25f13-121">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="25f13-121">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="25f13-122">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="25f13-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
