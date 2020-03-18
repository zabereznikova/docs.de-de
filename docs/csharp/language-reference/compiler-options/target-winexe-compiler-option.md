---
title: -target:winexe (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /target:winexe
helpviewer_keywords:
- /target compiler options [C#], /target:winexe
- -target compiler options [C#], /target:winexe
- target compiler options [C#], /target:winexe
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
ms.openlocfilehash: 981f1b0b6ca9f708bb022a3662ab181a4f472040
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "69606376"
---
# <a name="-targetwinexe-c-compiler-options"></a><span data-ttu-id="a78cd-102">-target:winexe (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="a78cd-102">-target:winexe (C# Compiler Options)</span></span>
<span data-ttu-id="a78cd-103">Die Option **-target:winexe** bewirkt, dass der Compiler ein ausführbares Windows-Programm (EXE) erstellt.</span><span class="sxs-lookup"><span data-stu-id="a78cd-103">The **-target:winexe** option causes the compiler to create an executable (EXE), Windows program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a78cd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a78cd-104">Syntax</span></span>  
  
```console  
-target:winexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="a78cd-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a78cd-105">Remarks</span></span>  
 <span data-ttu-id="a78cd-106">Die ausführbare Datei wird mit der Dateiendung „.exe“ erstellt.</span><span class="sxs-lookup"><span data-stu-id="a78cd-106">The executable file will be created with the .exe extension.</span></span> <span data-ttu-id="a78cd-107">Ein Windows-Programm stellt eine Benutzeroberfläche entweder aus der .NET Framework-Bibliothek oder mit den Windows-APIs bereit.</span><span class="sxs-lookup"><span data-stu-id="a78cd-107">A Windows program is one that provides a user interface from either the .NET Framework library or with the Windows APIs.</span></span>  
  
 <span data-ttu-id="a78cd-108">Verwenden Sie [-target:exe](./target-exe-compiler-option.md), um eine Konsolenanwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a78cd-108">Use [-target:exe](./target-exe-compiler-option.md) to create a console application.</span></span>  
  
 <span data-ttu-id="a78cd-109">Sofern Sie nicht die Option [-out](./out-compiler-option.md) verwenden, erhält die Ausgabedatei den Namen der Eingabedatei, die die [Main](../../programming-guide/main-and-command-args/index.md)-Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="a78cd-109">Unless otherwise specified with the [-out](./out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="a78cd-110">Wenn es in der Befehlszeile angegeben wurde, werden alle Dateien bis zur nächsten Option **-out** oder [-target](./target-compiler-option.md) verwendet, um das Windows-Programm zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a78cd-110">When specified at the command line, all files until the next **-out** or [-target](./target-compiler-option.md) option are used to create the Windows program.</span></span>  
  
 <span data-ttu-id="a78cd-111">Nur eine **Main**-Methode wird in den Quellcodedateien benötigt, die in eine EXE-Datei kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="a78cd-111">One and only one **Main** method is required in the source code files that are compiled into an .exe file.</span></span> <span data-ttu-id="a78cd-112">Sollte Ihr Code mehr als eine Klasse mit einer [Main](./main-compiler-option.md)-Methode enthalten, können Sie mit der Option **-main** angeben, welche Klasse die **Main**-Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="a78cd-112">The [-main](./main-compiler-option.md) option lets you specify which class contains the **Main** method, in cases where your code has more than one class with a **Main** method.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="a78cd-113">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="a78cd-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="a78cd-114">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="a78cd-114">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="a78cd-115">Klicken Sie auf die Eigenschaftenseite **Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="a78cd-115">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="a78cd-116">Ändern Sie die Eigenschaft **Ausgabetyp**.</span><span class="sxs-lookup"><span data-stu-id="a78cd-116">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="a78cd-117">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="a78cd-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a78cd-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a78cd-118">Example</span></span>  
 <span data-ttu-id="a78cd-119">Kompilieren Sie `in.cs` in ein Windows-Programm:</span><span class="sxs-lookup"><span data-stu-id="a78cd-119">Compile `in.cs` into a Windows program:</span></span>  
  
```console  
csc -target:winexe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="a78cd-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a78cd-120">See also</span></span>

- [<span data-ttu-id="a78cd-121">-target (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="a78cd-121">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="a78cd-122">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="a78cd-122">C# Compiler Options</span></span>](./index.md)
