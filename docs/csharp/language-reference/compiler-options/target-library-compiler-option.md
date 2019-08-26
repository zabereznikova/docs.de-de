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
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606397"
---
# <a name="-targetlibrary-c-compiler-options"></a><span data-ttu-id="7cb84-102">-target:library (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="7cb84-102">-target:library (C# Compiler Options)</span></span>
<span data-ttu-id="7cb84-103">Die Option **-target:library** veranlasst den Compiler dazu, eine Dynamic Link Library (DLL) statt einer ausführbaren Datei (EXE) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7cb84-103">The **-target:library** option causes the compiler to create a dynamic-link library (DLL) rather than an executable file (EXE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cb84-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7cb84-104">Syntax</span></span>  
  
```console  
-target:library  
```  
  
## <a name="remarks"></a><span data-ttu-id="7cb84-105">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="7cb84-105">Remarks</span></span>  
 <span data-ttu-id="7cb84-106">Die DLL wird mit der DLL-Dateiendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="7cb84-106">The DLL will be created with the .dll extension.</span></span>  
  
 <span data-ttu-id="7cb84-107">Sofern es nicht anders mit der Option [-out](./out-compiler-option.md) angegeben wurde, erhält die Ausgabedatei den Namen der ersten Eingabedatei.</span><span class="sxs-lookup"><span data-stu-id="7cb84-107">Unless otherwise specified with the [-out](./out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span>  
  
 <span data-ttu-id="7cb84-108">Wenn es in der Befehlszeile angegeben wurde, werden alle Dateien bis zur nächsten Option **-out** oder **-target:module** verwendet, um die DLL-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7cb84-108">When specified at the command line, all files up to the next **-out** or **-target:module** option are used to create the .dll file.</span></span>  
  
 <span data-ttu-id="7cb84-109">Beim Erstellen einer DLL-Datei ist eine [Main](../../programming-guide/main-and-command-args/index.md)-Methode nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7cb84-109">When building a .dll file, a [Main](../../programming-guide/main-and-command-args/index.md) method is not required.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="7cb84-110">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="7cb84-110">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="7cb84-111">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="7cb84-111">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="7cb84-112">Klicken Sie auf die Eigenschaftenseite **Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="7cb84-112">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="7cb84-113">Ändern Sie die Eigenschaft **Ausgabetyp**.</span><span class="sxs-lookup"><span data-stu-id="7cb84-113">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="7cb84-114">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="7cb84-114">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7cb84-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7cb84-115">Example</span></span>  
 <span data-ttu-id="7cb84-116">Kompilieren Sie `in.cs`, und `in.dll` wird erstellt:</span><span class="sxs-lookup"><span data-stu-id="7cb84-116">Compile `in.cs`, creating `in.dll`:</span></span>  
  
```console  
csc -target:library in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="7cb84-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7cb84-117">See also</span></span>

- [<span data-ttu-id="7cb84-118">-target (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="7cb84-118">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="7cb84-119">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="7cb84-119">C# Compiler Options</span></span>](./index.md)
