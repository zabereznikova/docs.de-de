---
title: -main (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
ms.openlocfilehash: 2f3c9daf98bfe77ea9462c8126f7a8368016875c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516665"
---
# <a name="-main-c-compiler-options"></a><span data-ttu-id="af300-102">-main (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="af300-102">-main (C# Compiler Options)</span></span>
<span data-ttu-id="af300-103">Diese Option gibt die Klasse an, die den Einstiegspunkt des Programms enthält, wenn mehr als eine Klasse eine **Main**-Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="af300-103">This option specifies the class that contains the entry point to the program, if more than one class contains a **Main** method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af300-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="af300-104">Syntax</span></span>  
  
```console  
-main:class  
```  
  
## <a name="arguments"></a><span data-ttu-id="af300-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="af300-105">Arguments</span></span>  
 `class`  
 <span data-ttu-id="af300-106">Der Typ, der die **Main**-Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="af300-106">The type that contains the **Main** method.</span></span>  
 <span data-ttu-id="af300-107">Der angegebene Klassenname muss vollqualifiziert sein. Er muss den vollständigen Namespace mit der Klasse, gefolgt von dem Klassennamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="af300-107">The provided class name must be fully qualified; it must include the full namespace containing the class, followed by the class name.</span></span> <span data-ttu-id="af300-108">Wenn sich die `Main`-Methode beispielsweise in der `Program`-Klasse im Namespace `MyApplication.Core` befindet, muss die Compileroption `-main:MyApplication.Core.Program` lauten.</span><span class="sxs-lookup"><span data-stu-id="af300-108">For example, when the `Main` method is located inside the `Program` class in the `MyApplication.Core` namespace, the compiler option has to be `-main:MyApplication.Core.Program`.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="af300-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="af300-109">Remarks</span></span>  
 <span data-ttu-id="af300-110">Wenn Ihre Kompilierung mehr als einen Typ mit einer [Main](../../../csharp/programming-guide/main-and-command-args/index.md)-Methode enthält, können Sie angeben, welcher Typ die **Main**-Methode enthält, die Sie als Einstiegspunkt des Programms verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="af300-110">If your compilation includes more than one type with a [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method, you can specify which type contains the **Main** method that you want to use as the entry point into the program.</span></span>  
  
 <span data-ttu-id="af300-111">Diese Option wird verwendet, wenn eine EXE-Datei kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="af300-111">This option is for use when compiling an .exe file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="af300-112">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="af300-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="af300-113">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="af300-113">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="af300-114">Klicken Sie auf die Eigenschaftenseite **Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="af300-114">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="af300-115">Ändern Sie die Eigenschaft **Startobjekt**.</span><span class="sxs-lookup"><span data-stu-id="af300-115">Modify the **Startup object** property.</span></span>  
  
     <span data-ttu-id="af300-116">Wie Sie diese Compileroption programmgesteuert festlegen, erfahren Sie unter <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="af300-116">To set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af300-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="af300-117">Example</span></span>  
 <span data-ttu-id="af300-118">Kompilieren Sie `t2.cs` und `t3.cs`, und geben Sie so an, dass die Methode **Main** in `Test2` gefunden wird:</span><span class="sxs-lookup"><span data-stu-id="af300-118">Compile `t2.cs` and `t3.cs`, specifying that the **Main** method will be found in `Test2`:</span></span>  
  
```console  
csc t2.cs t3.cs -main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="af300-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af300-119">See Also</span></span>

- [<span data-ttu-id="af300-120">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="af300-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="af300-121">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="af300-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
