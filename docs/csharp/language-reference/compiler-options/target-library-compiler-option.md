---
title: -target:library (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /dll
helpviewer_keywords:
- -target compiler options [C#], /target:library
- target compiler options [C#], /target:library
- /target compiler options [C#], /target:library
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
ms.openlocfilehash: 39f6ad5839f7ca12b023502a3fc1ccde52e70899
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33215348"
---
# <a name="-targetlibrary-c-compiler-options"></a><span data-ttu-id="ac75e-102">-target:library (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="ac75e-102">-target:library (C# Compiler Options)</span></span>
<span data-ttu-id="ac75e-103">Die Option **-target:library** veranlasst den Compiler dazu, eine Dynamic Link Library (DLL) statt einer ausführbaren Datei (EXE) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ac75e-103">The **-target:library** option causes the compiler to create a dynamic-link library (DLL) rather than an executable file (EXE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac75e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac75e-104">Syntax</span></span>  
  
```console  
-target:library  
```  
  
## <a name="remarks"></a><span data-ttu-id="ac75e-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ac75e-105">Remarks</span></span>  
 <span data-ttu-id="ac75e-106">Die DLL wird mit der DLL-Dateiendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="ac75e-106">The DLL will be created with the .dll extension.</span></span>  
  
 <span data-ttu-id="ac75e-107">Sofern es nicht anders mit der Option [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) angegeben wurde, erhält die Ausgabedatei den Namen der ersten Eingabedatei.</span><span class="sxs-lookup"><span data-stu-id="ac75e-107">Unless otherwise specified with the [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span>  
  
 <span data-ttu-id="ac75e-108">Wenn es in der Befehlszeile angegeben wurde, werden alle Dateien bis zur nächsten Option **-out** oder **-target:module** verwendet, um die DLL-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ac75e-108">When specified at the command line, all files up to the next **-out** or **-target:module** option are used to create the .dll file.</span></span>  
  
 <span data-ttu-id="ac75e-109">Beim Erstellen einer DLL-Datei ist eine [Main](../../../csharp/programming-guide/main-and-command-args/index.md)-Methode nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ac75e-109">When building a .dll file, a [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method is not required.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="ac75e-110">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="ac75e-110">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="ac75e-111">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="ac75e-111">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="ac75e-112">Klicken Sie auf die Eigenschaftenseite **Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="ac75e-112">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="ac75e-113">Ändern Sie die Eigenschaft **Ausgabetyp**.</span><span class="sxs-lookup"><span data-stu-id="ac75e-113">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="ac75e-114">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="ac75e-114">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac75e-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ac75e-115">Example</span></span>  
 <span data-ttu-id="ac75e-116">Kompilieren Sie `in.cs`, und `in.dll` wird erstellt:</span><span class="sxs-lookup"><span data-stu-id="ac75e-116">Compile `in.cs`, creating `in.dll`:</span></span>  
  
```console  
csc -target:library in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac75e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac75e-117">See Also</span></span>  
 [<span data-ttu-id="ac75e-118">-target (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="ac75e-118">-target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [<span data-ttu-id="ac75e-119">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="ac75e-119">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
