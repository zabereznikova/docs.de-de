---
description: -target:winmdobj (C#-Compileroptionen)
title: -target:winmdobj (C#-Compileroptionen)
ms.date: 07/20/2015
ms.assetid: 1819a045-659d-498a-9457-c466e902986f
ms.openlocfilehash: a13e2da02698209a514e716d65c1df3508cf1508
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "91171402"
---
# <a name="-targetwinmdobj-c-compiler-options"></a><span data-ttu-id="c67d6-103">-target:winmdobj (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="c67d6-103">-target:winmdobj (C# Compiler Options)</span></span>

<span data-ttu-id="c67d6-104">Wenn Sie die Compileroption **-target:winmdobj** verwenden, erstellt der Compiler eine WINMDOBJ-Zwischendatei, die Sie in eine binäre Windows Runtime-Datei (.winmd) konvertieren können.</span><span class="sxs-lookup"><span data-stu-id="c67d6-104">If you use the **-target:winmdobj** compiler option, the compiler creates an intermediate .winmdobj file that you can convert to a Windows Runtime binary (.winmd) file.</span></span> <span data-ttu-id="c67d6-105">Die WINMD-Datei kann dann von verwalteten Sprachprogrammen und auch von JavaScript- und C++-Programmen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c67d6-105">The .winmd file can then be consumed by JavaScript and C++ programs, in addition to managed language programs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c67d6-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c67d6-106">Syntax</span></span>  
  
```console  
-target:winmdobj  
```  
  
## <a name="remarks"></a><span data-ttu-id="c67d6-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c67d6-107">Remarks</span></span>  

 <span data-ttu-id="c67d6-108">Die Einstellung **winmdobj** signalisiert dem Compiler, dass ein Zwischenmodul erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c67d6-108">The **winmdobj** setting signals to the compiler that an intermediate module is required.</span></span> <span data-ttu-id="c67d6-109">Als Antwort darauf kompiliert Visual Studio die C#-Klassenbibliothek als WINMDOBJ-Datei.</span><span class="sxs-lookup"><span data-stu-id="c67d6-109">In response, Visual Studio compiles the C# class library as a .winmdobj file.</span></span> <span data-ttu-id="c67d6-110">Die WINMDOBJ-Datei kann dann durch das <xref:Microsoft.Build.Tasks.WinMDExp>-Exporttool eingegeben werden, um eine Windows-Metadatendatei (.winmd) zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="c67d6-110">The .winmdobj file can then be fed through the <xref:Microsoft.Build.Tasks.WinMDExp> export tool to produce a Windows metadata (.winmd) file.</span></span> <span data-ttu-id="c67d6-111">Die WINMD-Datei enthält sowohl den Code von der ursprünglichen Bibliothek als auch die WinMD-Metadaten, die von JavaScript oder C++ und von der Windows-Runtime verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c67d6-111">The .winmd file contains both the code from the original library and the WinMD metadata that is used by JavaScript or C++ and by the Windows Runtime.</span></span>  
  
 <span data-ttu-id="c67d6-112">Die Ausgabe einer Datei, die mithilfe der Compileroption **-target:winmdobj** kompiliert wird, ist für die reine Verwendung als Eingabe für das WimMDExp-Exporttool vorgesehen. Auf die WINMDOBJ-Datei selbst wird nicht direkt verwiesen.</span><span class="sxs-lookup"><span data-stu-id="c67d6-112">The output of a file that’s compiled by using the **-target:winmdobj** compiler option is designed to be used only as input for the WimMDExp export tool; the .winmdobj file itself isn’t referenced directly.</span></span>  
  
 <span data-ttu-id="c67d6-113">Sofern Sie nicht die Option [-out](./out-compiler-option.md) verwenden, erhält die Ausgabedatei den Namen der ersten Eingabedatei.</span><span class="sxs-lookup"><span data-stu-id="c67d6-113">Unless you use the [-out](./out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span> <span data-ttu-id="c67d6-114">Eine [Main](../../programming-guide/main-and-command-args/index.md)-Methode ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c67d6-114">A [Main](../../programming-guide/main-and-command-args/index.md) method isn’t required.</span></span>  
  
 <span data-ttu-id="c67d6-115">Wenn Sie die Option -target:winmdobj an einer Eingabeaufforderung festlegen, werden alle Dateien bis zur nächsten Option **-out** oder [-target:module](./target-module-compiler-option.md) verwendet, um das Windows-Programm zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c67d6-115">If you specify the -target:winmdobj option at a command prompt, all files until the next **-out** or [-target:module](./target-module-compiler-option.md) option are used to create the Windows program.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-ide-for-a-windows-store-app"></a><span data-ttu-id="c67d6-116">So legen Sie diese Compileroption in der Visual Studio-IDE für eine Windows Store-App fest</span><span class="sxs-lookup"><span data-stu-id="c67d6-116">To set this compiler option in the Visual Studio IDE for a Windows Store app</span></span>  
  
1. <span data-ttu-id="c67d6-117">Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="c67d6-117">In **Solution Explorer**, open the shortcut menu for your project, and then choose **Properties**.</span></span>  
  
2. <span data-ttu-id="c67d6-118">Wählen Sie die Registerkarte **Anwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="c67d6-118">Choose the **Application** tab.</span></span>  
  
3. <span data-ttu-id="c67d6-119">Wählen Sie in der Liste **Ausgabetyp** die Option **WinMD-Datei** aus.</span><span class="sxs-lookup"><span data-stu-id="c67d6-119">In the **Output type** list, choose **WinMD File**.</span></span>  
  
     <span data-ttu-id="c67d6-120">Die Option **WinMD File** ist nur für Windows 8.x Store-App-Vorlagen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c67d6-120">The **WinMD File** option is available only for Windows 8.x Store app templates.</span></span>  
  
 <span data-ttu-id="c67d6-121">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="c67d6-121">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c67d6-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c67d6-122">Example</span></span>  

 <span data-ttu-id="c67d6-123">Der folgende Befehl kompiliert `filename.cs` in eine WINMDOBJ-Zwischendatei.</span><span class="sxs-lookup"><span data-stu-id="c67d6-123">The following command compiles `filename.cs` into an intermediate .winmdobj file.</span></span>  
  
```console  
csc -target:winmdobj filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="c67d6-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c67d6-124">See also</span></span>

- [<span data-ttu-id="c67d6-125">-target (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="c67d6-125">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="c67d6-126">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="c67d6-126">C# Compiler Options</span></span>](./index.md)
