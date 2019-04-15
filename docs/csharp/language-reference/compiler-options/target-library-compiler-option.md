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
ms.openlocfilehash: 2e0935965e9225ab524290429803fe4c9ccc80c6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59313644"
---
# <a name="-targetlibrary-c-compiler-options"></a><span data-ttu-id="57731-102">-target:library (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="57731-102">-target:library (C# Compiler Options)</span></span>
<span data-ttu-id="57731-103">Die Option **-target:library** veranlasst den Compiler dazu, eine Dynamic Link Library (DLL) statt einer ausführbaren Datei (EXE) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="57731-103">The **-target:library** option causes the compiler to create a dynamic-link library (DLL) rather than an executable file (EXE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57731-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="57731-104">Syntax</span></span>  
  
```console  
-target:library  
```  
  
## <a name="remarks"></a><span data-ttu-id="57731-105">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="57731-105">Remarks</span></span>  
 <span data-ttu-id="57731-106">Die DLL wird mit der DLL-Dateiendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="57731-106">The DLL will be created with the .dll extension.</span></span>  
  
 <span data-ttu-id="57731-107">Sofern es nicht anders mit der Option [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) angegeben wurde, erhält die Ausgabedatei den Namen der ersten Eingabedatei.</span><span class="sxs-lookup"><span data-stu-id="57731-107">Unless otherwise specified with the [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span>  
  
 <span data-ttu-id="57731-108">Wenn es in der Befehlszeile angegeben wurde, werden alle Dateien bis zur nächsten Option **-out** oder **-target:module** verwendet, um die DLL-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="57731-108">When specified at the command line, all files up to the next **-out** or **-target:module** option are used to create the .dll file.</span></span>  
  
 <span data-ttu-id="57731-109">Beim Erstellen einer DLL-Datei ist eine [Main](../../../csharp/programming-guide/main-and-command-args/index.md)-Methode nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="57731-109">When building a .dll file, a [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method is not required.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="57731-110">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="57731-110">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="57731-111">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="57731-111">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="57731-112">Klicken Sie auf die Eigenschaftenseite **Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="57731-112">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="57731-113">Ändern Sie die Eigenschaft **Ausgabetyp**.</span><span class="sxs-lookup"><span data-stu-id="57731-113">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="57731-114">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="57731-114">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57731-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="57731-115">Example</span></span>  
 <span data-ttu-id="57731-116">Kompilieren Sie `in.cs`, und `in.dll` wird erstellt:</span><span class="sxs-lookup"><span data-stu-id="57731-116">Compile `in.cs`, creating `in.dll`:</span></span>  
  
```console  
csc -target:library in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="57731-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57731-117">See also</span></span>

- [<span data-ttu-id="57731-118">-target (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="57731-118">-target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)
- [<span data-ttu-id="57731-119">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="57731-119">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
