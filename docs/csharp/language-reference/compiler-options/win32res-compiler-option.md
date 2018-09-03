---
title: -win32res (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /win32res
helpviewer_keywords:
- win32res compiler option
- /win32res compiler option [C#]
- -win32res compiler option [C#]
- win32res compiler option [C#]
ms.assetid: 3c33f750-6948-4c7e-a27e-bef98f77255b
ms.openlocfilehash: 96b0b089843495d35a54db43018688dbb4ffba2b
ms.sourcegitcommit: a368166a51e5204c0224fbf5e46476e3ed122817
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2018
ms.locfileid: "43330892"
---
# <a name="-win32res-c-compiler-options"></a><span data-ttu-id="e123f-102">-win32res (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="e123f-102">-win32res (C# Compiler Options)</span></span>
<span data-ttu-id="e123f-103">Die Option **-win32res** fügt eine Win32-Ressource in die Ausgabedatei ein.</span><span class="sxs-lookup"><span data-stu-id="e123f-103">The **-win32res** option inserts a Win32 resource in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e123f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e123f-104">Syntax</span></span>  
  
```console  
-win32res:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="e123f-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="e123f-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="e123f-106">Die Ressourcendatei, die Sie Ihrer Ausgabedatei hinzufügen möchten</span><span class="sxs-lookup"><span data-stu-id="e123f-106">The resource file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e123f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e123f-107">Remarks</span></span>  
 <span data-ttu-id="e123f-108">Eine Win32-Ressourcendatei kann mit dem [Ressourcencompiler](../../language-reference/compiler-options/resource-compiler-option.md) erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e123f-108">A Win32 resource file can be created with the [Resource Compiler](../../language-reference/compiler-options/resource-compiler-option.md).</span></span> <span data-ttu-id="e123f-109">Der Ressourcencompiler wird gestartet, wenn Sie ein Visual C++-Programm kompilieren. Aus der RC-Datei wird eine RES-Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="e123f-109">The Resource Compiler is invoked when you compile a Visual C++ program; a .res file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="e123f-110">Eine Win32-Ressource kann Versions- oder Bitmapinformationen (Symbolinformationen) enthalten, anhand derer die Anwendung im Datei-Explorer identifiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="e123f-110">A Win32 resource can contain version or bitmap (icon) information that would help identify your application in the File Explorer.</span></span> <span data-ttu-id="e123f-111">Wenn sie **-win32res** nicht angeben, generiert der Compiler Versionsinformationen auf Grundlage der Assemblyversion.</span><span class="sxs-lookup"><span data-stu-id="e123f-111">If you do not specify **-win32res**, the compiler will generate version information based on the assembly version.</span></span>  
  
 <span data-ttu-id="e123f-112">Weitere Informationen zum Verweisen auf eine .NET Framework-Ressourcendatei finden Sie unter [-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md), weitere Informationen zum Anfügen einer .NET Framework-Ressourcendatei unter [-resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="e123f-112">See [-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (to reference) or [-resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="e123f-113">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="e123f-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="e123f-114">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="e123f-114">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="e123f-115">Klicken Sie auf die Eigenschaftenseite **Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="e123f-115">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="e123f-116">Klicken Sie auf die Schaltfläche **Ressourcendatei**, und wählen Sie die Datei über das Kombinationsfeld aus.</span><span class="sxs-lookup"><span data-stu-id="e123f-116">Click on the **Resource File** button and choose a file by using the combo box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e123f-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e123f-117">Example</span></span>  
 <span data-ttu-id="e123f-118">Kompilieren Sie `in.cs`, und fügen Sie die Win32-Ressourcendatei `rf.res` an, um `in.exe` zu erzeugen:</span><span class="sxs-lookup"><span data-stu-id="e123f-118">Compile `in.cs` and attach a Win32 resource file `rf.res` to produce `in.exe`:</span></span>  
  
```console  
csc -win32res:rf.res in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="e123f-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e123f-119">See Also</span></span>  

- [<span data-ttu-id="e123f-120">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="e123f-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="e123f-121">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="e123f-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
