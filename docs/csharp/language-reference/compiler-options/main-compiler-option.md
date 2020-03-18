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
ms.openlocfilehash: 6c842abc1423e7ee0d98b71392e02410c6cf9172
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "69602723"
---
# <a name="-main-c-compiler-options"></a><span data-ttu-id="6e106-102">-main (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="6e106-102">-main (C# Compiler Options)</span></span>
<span data-ttu-id="6e106-103">Diese Option gibt die Klasse an, die den Einstiegspunkt des Programms enthält, wenn mehr als eine Klasse eine **Main**-Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="6e106-103">This option specifies the class that contains the entry point to the program, if more than one class contains a **Main** method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e106-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e106-104">Syntax</span></span>  
  
```console  
-main:class  
```  
  
## <a name="arguments"></a><span data-ttu-id="6e106-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="6e106-105">Arguments</span></span>  
 `class`  
 <span data-ttu-id="6e106-106">Der Typ, der die **Main**-Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="6e106-106">The type that contains the **Main** method.</span></span>  
 <span data-ttu-id="6e106-107">Der angegebene Klassenname muss vollqualifiziert sein. Er muss den vollständigen Namespace mit der Klasse, gefolgt von dem Klassennamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="6e106-107">The provided class name must be fully qualified; it must include the full namespace containing the class, followed by the class name.</span></span> <span data-ttu-id="6e106-108">Wenn sich die `Main`-Methode beispielsweise in der `Program`-Klasse im Namespace `MyApplication.Core` befindet, muss die Compileroption `-main:MyApplication.Core.Program` lauten.</span><span class="sxs-lookup"><span data-stu-id="6e106-108">For example, when the `Main` method is located inside the `Program` class in the `MyApplication.Core` namespace, the compiler option has to be `-main:MyApplication.Core.Program`.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="6e106-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6e106-109">Remarks</span></span>  
 <span data-ttu-id="6e106-110">Wenn Ihre Kompilierung mehr als einen Typ mit einer [Main](../../programming-guide/main-and-command-args/index.md)-Methode enthält, können Sie angeben, welcher Typ die **Main**-Methode enthält, die Sie als Einstiegspunkt des Programms verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="6e106-110">If your compilation includes more than one type with a [Main](../../programming-guide/main-and-command-args/index.md) method, you can specify which type contains the **Main** method that you want to use as the entry point into the program.</span></span>  
  
 <span data-ttu-id="6e106-111">Diese Option wird verwendet, wenn eine EXE-Datei kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="6e106-111">This option is for use when compiling an .exe file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="6e106-112">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="6e106-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="6e106-113">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="6e106-113">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="6e106-114">Klicken Sie auf die Eigenschaftenseite **Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="6e106-114">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="6e106-115">Ändern Sie die Eigenschaft **Startobjekt**.</span><span class="sxs-lookup"><span data-stu-id="6e106-115">Modify the **Startup object** property.</span></span>  
  
     <span data-ttu-id="6e106-116">Um diese Compileroption programmgesteuert festzulegen, sehen Sie sich <xref:VSLangProj80.ProjectProperties3.StartupObject%2A> an.</span><span class="sxs-lookup"><span data-stu-id="6e106-116">To set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e106-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6e106-117">Example</span></span>  
 <span data-ttu-id="6e106-118">Kompilieren Sie `t2.cs` und `t3.cs`, und geben Sie so an, dass die Methode **Main** in `Test2` gefunden wird:</span><span class="sxs-lookup"><span data-stu-id="6e106-118">Compile `t2.cs` and `t3.cs`, specifying that the **Main** method will be found in `Test2`:</span></span>  
  
```console  
csc t2.cs t3.cs -main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="6e106-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6e106-119">See also</span></span>

- [<span data-ttu-id="6e106-120">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="6e106-120">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="6e106-121">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="6e106-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
