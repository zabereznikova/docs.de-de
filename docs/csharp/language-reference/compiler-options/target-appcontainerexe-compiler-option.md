---
title: -target:appcontainerexe (C#-Compileroptionen)
ms.date: 07/20/2015
ms.assetid: e7e62229-23ea-4e53-bef5-380d951bf95f
ms.openlocfilehash: 64661e72f9efe190606cadd93558678cb849e8cc
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204526"
---
# <a name="-targetappcontainerexe-c-compiler-options"></a><span data-ttu-id="91c51-102">-target:appcontainerexe (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="91c51-102">-target:appcontainerexe (C# Compiler Options)</span></span>
<span data-ttu-id="91c51-103">Wenn Sie die Compileroption **-target:appcontainerexe** verwenden, erstellt der Compiler eine ausführbare Windows-Datei (.exe), die in einem App-Container ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="91c51-103">If you use the **-target:appcontainerexe** compiler option, the compiler creates a Windows executable (.exe) file that must be run in an app container.</span></span> <span data-ttu-id="91c51-104">Diese Option entspricht [-target:winexe](./target-winexe-compiler-option.md), ist jedoch für Windows 8.x Store-Apps vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="91c51-104">This option is equivalent to [-target:winexe](./target-winexe-compiler-option.md) but is designed for Windows 8.x Store apps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91c51-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="91c51-105">Syntax</span></span>  
  
```console  
-target:appcontainerexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="91c51-106">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="91c51-106">Remarks</span></span>  
 <span data-ttu-id="91c51-107">Diese Option legt ein Bit in der [portierbaren ausführbaren](/windows/desktop/Debug/pe-format) Datei (Portable Executable, PE) fest, damit die App in einem App-Container ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="91c51-107">To require the app to run in an app container, this option sets a bit in the [Portable Executable](/windows/desktop/Debug/pe-format) (PE) file.</span></span> <span data-ttu-id="91c51-108">Wenn dieses Bit festgelegt ist, tritt ein Fehler auf, wenn die CreateProcess-Methode versucht, die ausführbare Datei außerhalb eines App-Containers zu starten.</span><span class="sxs-lookup"><span data-stu-id="91c51-108">When that bit is set, an error occurs if the CreateProcess method tries to launch the executable file outside an app container.</span></span>  
  
 <span data-ttu-id="91c51-109">Sofern Sie nicht die Option [-out](./out-compiler-option.md) verwenden, erhält der Name der Ausgabedatei den Namen der Eingabedatei, die die [Main](../../programming-guide/main-and-command-args/index.md)-Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="91c51-109">Unless you use the [-out](./out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="91c51-110">Wenn Sie diese Option in einer Eingabeaufforderung festlegen, werden alle Dateien bis zur nächsten Option namens **-out** oder **-target** verwendet, um die ausführbare Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="91c51-110">When you specify this option at a command prompt, all files until the next **-out** or **-target** option are used to create the executable file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-ide"></a><span data-ttu-id="91c51-111">So legen Sie diese Compileroption in der IDE fest</span><span class="sxs-lookup"><span data-stu-id="91c51-111">To set this compiler option in the IDE</span></span>  
  
1. <span data-ttu-id="91c51-112">Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="91c51-112">In **Solution Explorer**, open the shortcut menu for your project, and then choose **Properties**.</span></span>  
  
2. <span data-ttu-id="91c51-113">Wählen Sie auf der Registerkarte **Anwendung** in der Liste **Ausgabetyp** die Option **Windows Store-App** aus.</span><span class="sxs-lookup"><span data-stu-id="91c51-113">On the **Application** tab, in the **Output type** list, choose **Windows Store App**.</span></span>  
  
     <span data-ttu-id="91c51-114">Diese Option ist nur für Windows 8.x Store-App-Vorlagen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="91c51-114">This option is available only for Windows 8.x Store app templates.</span></span>  
  
 <span data-ttu-id="91c51-115">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="91c51-115">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91c51-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91c51-116">Example</span></span>  
 <span data-ttu-id="91c51-117">Der folgende Befehl kompiliert `filename.cs` in eine ausführbare Windows-Datei, die nur in einem App-Container ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="91c51-117">The following command compiles `filename.cs` into a Windows executable file that can be run only in an app container.</span></span>  
  
```console  
csc -target:appcontainerexe filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="91c51-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91c51-118">See also</span></span>

- [<span data-ttu-id="91c51-119">-target (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="91c51-119">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="91c51-120">-target:winexe (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="91c51-120">-target:winexe (C# Compiler Options)</span></span>](./target-winexe-compiler-option.md)
- [<span data-ttu-id="91c51-121">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="91c51-121">C# Compiler Options</span></span>](./index.md)
