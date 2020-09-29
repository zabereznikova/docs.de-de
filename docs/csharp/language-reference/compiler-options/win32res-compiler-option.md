---
description: -win32res (C#-Compileroptionen)
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
ms.openlocfilehash: 442c788595a01db9c0a1196d9e13b2a98963a38c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204345"
---
# <a name="-win32res-c-compiler-options"></a><span data-ttu-id="f56f2-103">-win32res (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="f56f2-103">-win32res (C# Compiler Options)</span></span>

<span data-ttu-id="f56f2-104">Die Option **-win32res** fügt eine Win32-Ressource in die Ausgabedatei ein.</span><span class="sxs-lookup"><span data-stu-id="f56f2-104">The **-win32res** option inserts a Win32 resource in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f56f2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f56f2-105">Syntax</span></span>  
  
```console  
-win32res:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="f56f2-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="f56f2-106">Arguments</span></span>  

 `filename`  
 <span data-ttu-id="f56f2-107">Die Ressourcendatei, die Sie Ihrer Ausgabedatei hinzufügen möchten</span><span class="sxs-lookup"><span data-stu-id="f56f2-107">The resource file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f56f2-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f56f2-108">Remarks</span></span>  

 <span data-ttu-id="f56f2-109">Eine Win32-Ressourcendatei kann mit dem [Ressourcencompiler](resource-compiler-option.md) erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f56f2-109">A Win32 resource file can be created with the [Resource Compiler](resource-compiler-option.md).</span></span> <span data-ttu-id="f56f2-110">Der Ressourcencompiler wird gestartet, wenn Sie ein Visual C++-Programm kompilieren. Aus der RC-Datei wird eine RES-Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="f56f2-110">The Resource Compiler is invoked when you compile a Visual C++ program; a .res file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="f56f2-111">Eine Win32-Ressource kann Versions- oder Bitmapinformationen (Symbolinformationen) enthalten, anhand derer die Anwendung im Datei-Explorer identifiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f56f2-111">A Win32 resource can contain version or bitmap (icon) information that would help identify your application in the File Explorer.</span></span> <span data-ttu-id="f56f2-112">Wenn sie **-win32res** nicht angeben, generiert der Compiler Versionsinformationen auf Grundlage der Assemblyversion.</span><span class="sxs-lookup"><span data-stu-id="f56f2-112">If you do not specify **-win32res**, the compiler will generate version information based on the assembly version.</span></span>  
  
 <span data-ttu-id="f56f2-113">Weitere Informationen zum Verweisen auf eine .NET Framework-Ressourcendatei finden Sie unter [-linkresource](./linkresource-compiler-option.md), weitere Informationen zum Anfügen einer .NET Framework-Ressourcendatei unter [-resource](./resource-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="f56f2-113">See [-linkresource](./linkresource-compiler-option.md) (to reference) or [-resource](./resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="f56f2-114">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="f56f2-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="f56f2-115">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="f56f2-115">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="f56f2-116">Klicken Sie auf die Eigenschaftenseite **Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="f56f2-116">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="f56f2-117">Klicken Sie auf die Schaltfläche **Ressourcendatei**, und wählen Sie die Datei über das Kombinationsfeld aus.</span><span class="sxs-lookup"><span data-stu-id="f56f2-117">Click on the **Resource File** button and choose a file by using the combo box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f56f2-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f56f2-118">Example</span></span>  

 <span data-ttu-id="f56f2-119">Kompilieren Sie `in.cs`, und fügen Sie die Win32-Ressourcendatei `rf.res` an, um `in.exe` zu erzeugen:</span><span class="sxs-lookup"><span data-stu-id="f56f2-119">Compile `in.cs` and attach a Win32 resource file `rf.res` to produce `in.exe`:</span></span>  
  
```console  
csc -win32res:rf.res in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="f56f2-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f56f2-120">See also</span></span>

- [<span data-ttu-id="f56f2-121">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="f56f2-121">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="f56f2-122">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="f56f2-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
