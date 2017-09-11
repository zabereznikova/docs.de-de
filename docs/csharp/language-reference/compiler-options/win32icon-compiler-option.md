---
title: -win32icon (C#-Compileroptionen)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /win32icon
dev_langs:
- CSharp
helpviewer_keywords:
- win32icon compiler option [C#]
- /win32icon compiler option [C#]
- -win32icon compiler option [C#]
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: af5b9c3a44163167d932d378cbac4976e07eacbf
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="win32icon-c-compiler-options"></a><span data-ttu-id="cf2d4-102">/win32icon (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="cf2d4-102">/win32icon (C# Compiler Options)</span></span>
<span data-ttu-id="cf2d4-103">Die Option **/win32icon** fügt der Ausgabedatei eine ICO-Datei hinzu, die der Ausgabedatei im Datei-Explorer das gewünschte Aussehen verleiht.</span><span class="sxs-lookup"><span data-stu-id="cf2d4-103">The **/win32icon** option inserts an .ico file in the output file, which gives the output file the desired appearance in the File Explorer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf2d4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf2d4-104">Syntax</span></span>  
  
```console  
/win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="cf2d4-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="cf2d4-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="cf2d4-106">Die ICO-Datei, die Sie Ihrer Ausgabedatei hinzufügen möchten</span><span class="sxs-lookup"><span data-stu-id="cf2d4-106">The .ico file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf2d4-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cf2d4-107">Remarks</span></span>  
 <span data-ttu-id="cf2d4-108">Eine ICO-Datei kann mit dem [Ressourcencompiler](http://go.microsoft.com/fwlink/?LinkId=148370) erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="cf2d4-108">An .ico file can be created with the [Resource Compiler](http://go.microsoft.com/fwlink/?LinkId=148370).</span></span> <span data-ttu-id="cf2d4-109">Der Ressourcencompiler wird gestartet, wenn Sie ein Visual C++-Programm kompilieren. Aus der RC-Datei wird eine ICO-Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="cf2d4-109">The Resource Compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="cf2d4-110">Schauen Sie sich [/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) zum Verweisen oder [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) zum Anfügen einer .NET Framework-Ressourcendatei an</span><span class="sxs-lookup"><span data-stu-id="cf2d4-110">See [/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (to reference) or [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span> <span data-ttu-id="cf2d4-111">Schauen Sie sich [/win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) an, um eine RES-Datei zu importieren.</span><span class="sxs-lookup"><span data-stu-id="cf2d4-111">See [/win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) to import a .res file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="cf2d4-112">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="cf2d4-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="cf2d4-113">Öffnen Sie die **Eigenschaftenseite**des Projekts.</span><span class="sxs-lookup"><span data-stu-id="cf2d4-113">Open the project's **Properties** pages.</span></span>  
  
2.  <span data-ttu-id="cf2d4-114">Klicken Sie auf die Eigenschaftenseite **Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="cf2d4-114">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="cf2d4-115">Ändern Sie die Eigenschaft **Anwendungssymbol**.</span><span class="sxs-lookup"><span data-stu-id="cf2d4-115">Modify the **Application icon** property.</span></span>  
  
 <span data-ttu-id="cf2d4-116">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span><span class="sxs-lookup"><span data-stu-id="cf2d4-116">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf2d4-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cf2d4-117">Example</span></span>  
 <span data-ttu-id="cf2d4-118">Kompilieren Sie `in.cs`, und fügen Sie eine ICO-Datei `rf.ico` hinzu, um `in.exe` zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="cf2d4-118">Compile `in.cs` and attach an .ico file `rf.ico` to produce `in.exe`:</span></span>  
  
```console  
csc /win32icon:rf.ico in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf2d4-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf2d4-119">See Also</span></span>  
 <span data-ttu-id="cf2d4-120">[C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="cf2d4-120">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="cf2d4-121">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="cf2d4-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

