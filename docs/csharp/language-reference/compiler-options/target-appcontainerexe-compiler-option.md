---
description: -target:appcontainerexe (C#-Compileroptionen)
title: -target:appcontainerexe (C#-Compileroptionen)
ms.date: 07/20/2015
ms.assetid: e7e62229-23ea-4e53-bef5-380d951bf95f
ms.openlocfilehash: 8c3b85c2f5a20788bd311e9bf3b300c32967da77
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128581"
---
# <a name="-targetappcontainerexe-c-compiler-options"></a><span data-ttu-id="0ea96-103">-target:appcontainerexe (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="0ea96-103">-target:appcontainerexe (C# Compiler Options)</span></span>
<span data-ttu-id="0ea96-104">Wenn Sie die Compileroption **-target:appcontainerexe** verwenden, erstellt der Compiler eine ausführbare Windows-Datei (.exe), die in einem App-Container ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="0ea96-104">If you use the **-target:appcontainerexe** compiler option, the compiler creates a Windows executable (.exe) file that must be run in an app container.</span></span> <span data-ttu-id="0ea96-105">Diese Option entspricht [-target:winexe](./target-winexe-compiler-option.md), ist jedoch für Windows 8.x Store-Apps vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="0ea96-105">This option is equivalent to [-target:winexe](./target-winexe-compiler-option.md) but is designed for Windows 8.x Store apps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ea96-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ea96-106">Syntax</span></span>  
  
```console  
-target:appcontainerexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="0ea96-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0ea96-107">Remarks</span></span>  
 <span data-ttu-id="0ea96-108">Diese Option legt ein Bit in der [portierbaren ausführbaren](/windows/desktop/Debug/pe-format) Datei (Portable Executable, PE) fest, damit die App in einem App-Container ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="0ea96-108">To require the app to run in an app container, this option sets a bit in the [Portable Executable](/windows/desktop/Debug/pe-format) (PE) file.</span></span> <span data-ttu-id="0ea96-109">Wenn dieses Bit festgelegt ist, tritt ein Fehler auf, wenn die CreateProcess-Methode versucht, die ausführbare Datei außerhalb eines App-Containers zu starten.</span><span class="sxs-lookup"><span data-stu-id="0ea96-109">When that bit is set, an error occurs if the CreateProcess method tries to launch the executable file outside an app container.</span></span>  
  
 <span data-ttu-id="0ea96-110">Sofern Sie nicht die Option [-out](./out-compiler-option.md) verwenden, erhält der Name der Ausgabedatei den Namen der Eingabedatei, die die [Main](../../programming-guide/main-and-command-args/index.md)-Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="0ea96-110">Unless you use the [-out](./out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="0ea96-111">Wenn Sie diese Option in einer Eingabeaufforderung festlegen, werden alle Dateien bis zur nächsten Option namens **-out** oder **-target** verwendet, um die ausführbare Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0ea96-111">When you specify this option at a command prompt, all files until the next **-out** or **-target** option are used to create the executable file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-ide"></a><span data-ttu-id="0ea96-112">So legen Sie diese Compileroption in der IDE fest</span><span class="sxs-lookup"><span data-stu-id="0ea96-112">To set this compiler option in the IDE</span></span>  
  
1. <span data-ttu-id="0ea96-113">Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="0ea96-113">In **Solution Explorer**, open the shortcut menu for your project, and then choose **Properties**.</span></span>  
  
2. <span data-ttu-id="0ea96-114">Wählen Sie auf der Registerkarte **Anwendung** in der Liste **Ausgabetyp** die Option **Windows Store-App** aus.</span><span class="sxs-lookup"><span data-stu-id="0ea96-114">On the **Application** tab, in the **Output type** list, choose **Windows Store App**.</span></span>  
  
     <span data-ttu-id="0ea96-115">Diese Option ist nur für Windows 8.x Store-App-Vorlagen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0ea96-115">This option is available only for Windows 8.x Store app templates.</span></span>  
  
 <span data-ttu-id="0ea96-116">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="0ea96-116">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ea96-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0ea96-117">Example</span></span>  
 <span data-ttu-id="0ea96-118">Der folgende Befehl kompiliert `filename.cs` in eine ausführbare Windows-Datei, die nur in einem App-Container ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0ea96-118">The following command compiles `filename.cs` into a Windows executable file that can be run only in an app container.</span></span>  
  
```console  
csc -target:appcontainerexe filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ea96-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0ea96-119">See also</span></span>

- [<span data-ttu-id="0ea96-120">-target (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="0ea96-120">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="0ea96-121">-target:winexe (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="0ea96-121">-target:winexe (C# Compiler Options)</span></span>](./target-winexe-compiler-option.md)
- [<span data-ttu-id="0ea96-122">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="0ea96-122">C# Compiler Options</span></span>](./index.md)
