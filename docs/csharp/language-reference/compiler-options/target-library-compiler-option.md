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
ms.openlocfilehash: c947b2015c19d0809cab4535e989ee83ebf17fd9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "69606397"
---
# <a name="-targetlibrary-c-compiler-options"></a><span data-ttu-id="21680-102">-target:library (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="21680-102">-target:library (C# Compiler Options)</span></span>
<span data-ttu-id="21680-103">Die Option **-target:library** veranlasst den Compiler dazu, eine Dynamic Link Library (DLL) statt einer ausführbaren Datei (EXE) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="21680-103">The **-target:library** option causes the compiler to create a dynamic-link library (DLL) rather than an executable file (EXE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21680-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="21680-104">Syntax</span></span>  
  
```console  
-target:library  
```  
  
## <a name="remarks"></a><span data-ttu-id="21680-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="21680-105">Remarks</span></span>  
 <span data-ttu-id="21680-106">Die DLL wird mit der DLL-Dateiendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="21680-106">The DLL will be created with the .dll extension.</span></span>  
  
 <span data-ttu-id="21680-107">Sofern es nicht anders mit der Option [-out](./out-compiler-option.md) angegeben wurde, erhält die Ausgabedatei den Namen der ersten Eingabedatei.</span><span class="sxs-lookup"><span data-stu-id="21680-107">Unless otherwise specified with the [-out](./out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span>  
  
 <span data-ttu-id="21680-108">Wenn es in der Befehlszeile angegeben wurde, werden alle Dateien bis zur nächsten Option **-out** oder **-target:module** verwendet, um die DLL-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="21680-108">When specified at the command line, all files up to the next **-out** or **-target:module** option are used to create the .dll file.</span></span>  
  
 <span data-ttu-id="21680-109">Beim Erstellen einer DLL-Datei ist eine [Main](../../programming-guide/main-and-command-args/index.md)-Methode nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="21680-109">When building a .dll file, a [Main](../../programming-guide/main-and-command-args/index.md) method is not required.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="21680-110">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="21680-110">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="21680-111">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="21680-111">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="21680-112">Klicken Sie auf die Eigenschaftenseite **Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="21680-112">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="21680-113">Ändern Sie die Eigenschaft **Ausgabetyp**.</span><span class="sxs-lookup"><span data-stu-id="21680-113">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="21680-114">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="21680-114">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21680-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21680-115">Example</span></span>  
 <span data-ttu-id="21680-116">Kompilieren Sie `in.cs`, und `in.dll` wird erstellt:</span><span class="sxs-lookup"><span data-stu-id="21680-116">Compile `in.cs`, creating `in.dll`:</span></span>  
  
```console  
csc -target:library in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="21680-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="21680-117">See also</span></span>

- [<span data-ttu-id="21680-118">-target (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="21680-118">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="21680-119">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="21680-119">C# Compiler Options</span></span>](./index.md)
