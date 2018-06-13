---
title: -win32icon (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /win32icon
helpviewer_keywords:
- win32icon compiler option [C#]
- /win32icon compiler option [C#]
- -win32icon compiler option [C#]
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
ms.openlocfilehash: ba5c7fcc8fe9e3eaab0a955f4cd1a1e07169049e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33216200"
---
# <a name="-win32icon-c-compiler-options"></a><span data-ttu-id="0c568-102">-win32icon (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="0c568-102">-win32icon (C# Compiler Options)</span></span>
<span data-ttu-id="0c568-103">Die Option **-win32icon** fügt der Ausgabedatei eine ICO-Datei hinzu, die der Ausgabedatei im Datei-Explorer das gewünschte Aussehen verleiht.</span><span class="sxs-lookup"><span data-stu-id="0c568-103">The **-win32icon** option inserts an .ico file in the output file, which gives the output file the desired appearance in the File Explorer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c568-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0c568-104">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="0c568-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="0c568-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="0c568-106">Die ICO-Datei, die Sie Ihrer Ausgabedatei hinzufügen möchten</span><span class="sxs-lookup"><span data-stu-id="0c568-106">The .ico file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c568-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0c568-107">Remarks</span></span>  
 <span data-ttu-id="0c568-108">Eine ICO-Datei kann mit dem [Ressourcencompiler](https://msdn.microsoft.com/library/aa381042.aspx) erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="0c568-108">An .ico file can be created with the [Resource Compiler](https://msdn.microsoft.com/library/aa381042.aspx).</span></span> <span data-ttu-id="0c568-109">Der Ressourcencompiler wird gestartet, wenn Sie ein Visual C++-Programm kompilieren. Aus der RC-Datei wird eine ICO-Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="0c568-109">The Resource Compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="0c568-110">Weitere Informationen zum Verweisen auf eine .NET Framework-Ressourcendatei finden Sie unter [-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md), weitere Informationen zum Anfügen einer .NET Framework-Ressourcendatei unter [-resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="0c568-110">See [-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (to reference) or [-resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span> <span data-ttu-id="0c568-111">Weitere Informationen zum Importieren einer RES-Datei finden Sie unter [-win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="0c568-111">See [-win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) to import a .res file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="0c568-112">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="0c568-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="0c568-113">Öffnen Sie die **Eigenschaftenseite**des Projekts.</span><span class="sxs-lookup"><span data-stu-id="0c568-113">Open the project's **Properties** pages.</span></span>  
  
2.  <span data-ttu-id="0c568-114">Klicken Sie auf die Eigenschaftenseite **Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="0c568-114">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="0c568-115">Ändern Sie die Eigenschaft **Anwendungssymbol**.</span><span class="sxs-lookup"><span data-stu-id="0c568-115">Modify the **Application icon** property.</span></span>  
  
 <span data-ttu-id="0c568-116">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span><span class="sxs-lookup"><span data-stu-id="0c568-116">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c568-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0c568-117">Example</span></span>  
 <span data-ttu-id="0c568-118">Kompilieren Sie `in.cs`, und fügen Sie eine ICO-Datei `rf.ico` hinzu, um `in.exe` zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="0c568-118">Compile `in.cs` and attach an .ico file `rf.ico` to produce `in.exe`:</span></span>  
  
```console  
csc -win32icon:rf.ico in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="0c568-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c568-119">See Also</span></span>  
 [<span data-ttu-id="0c568-120">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="0c568-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="0c568-121">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="0c568-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
