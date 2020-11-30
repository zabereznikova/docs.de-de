---
description: -target:library (C#-Compileroptionen)
title: -target:library (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /dll
helpviewer_keywords:
- -target compiler options [C#], /target:library
- target compiler options [C#], /target:library
- /target compiler options [C#], /target:library
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
ms.openlocfilehash: 0f5b1e1bec8fd601bf111e1c2c64adf22d0a064e
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "91193724"
---
# <a name="-targetlibrary-c-compiler-options"></a><span data-ttu-id="4807f-103">-target:library (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="4807f-103">-target:library (C# Compiler Options)</span></span>

<span data-ttu-id="4807f-104">Die Option **-target:library** veranlasst den Compiler dazu, eine Dynamic Link Library (DLL) statt einer ausführbaren Datei (EXE) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4807f-104">The **-target:library** option causes the compiler to create a dynamic-link library (DLL) rather than an executable file (EXE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4807f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4807f-105">Syntax</span></span>  
  
```console  
-target:library  
```  
  
## <a name="remarks"></a><span data-ttu-id="4807f-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4807f-106">Remarks</span></span>  

 <span data-ttu-id="4807f-107">Die DLL wird mit der DLL-Dateiendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="4807f-107">The DLL will be created with the .dll extension.</span></span>  
  
 <span data-ttu-id="4807f-108">Sofern es nicht anders mit der Option [-out](./out-compiler-option.md) angegeben wurde, erhält die Ausgabedatei den Namen der ersten Eingabedatei.</span><span class="sxs-lookup"><span data-stu-id="4807f-108">Unless otherwise specified with the [-out](./out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span>  
  
 <span data-ttu-id="4807f-109">Wenn es in der Befehlszeile angegeben wurde, werden alle Dateien bis zur nächsten Option **-out** oder **-target:module** verwendet, um die DLL-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4807f-109">When specified at the command line, all files up to the next **-out** or **-target:module** option are used to create the .dll file.</span></span>  
  
 <span data-ttu-id="4807f-110">Beim Erstellen einer DLL-Datei ist eine [Main](../../programming-guide/main-and-command-args/index.md)-Methode nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4807f-110">When building a .dll file, a [Main](../../programming-guide/main-and-command-args/index.md) method is not required.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="4807f-111">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="4807f-111">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="4807f-112">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="4807f-112">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="4807f-113">Klicken Sie auf die Eigenschaftenseite **Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="4807f-113">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="4807f-114">Ändern Sie die Eigenschaft **Ausgabetyp**.</span><span class="sxs-lookup"><span data-stu-id="4807f-114">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="4807f-115">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="4807f-115">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4807f-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4807f-116">Example</span></span>  

 <span data-ttu-id="4807f-117">Kompilieren Sie `in.cs`, und `in.dll` wird erstellt:</span><span class="sxs-lookup"><span data-stu-id="4807f-117">Compile `in.cs`, creating `in.dll`:</span></span>  
  
```console  
csc -target:library in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="4807f-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4807f-118">See also</span></span>

- [<span data-ttu-id="4807f-119">-target (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="4807f-119">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="4807f-120">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="4807f-120">C# Compiler Options</span></span>](./index.md)
