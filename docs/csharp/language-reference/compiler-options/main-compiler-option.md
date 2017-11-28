---
title: -main (C#-Compileroptionen)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4a6dca6e62dbf69783babf2e16dc4e7c36c6705c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="main-c-compiler-options"></a><span data-ttu-id="daa72-102">/main (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="daa72-102">/main (C# Compiler Options)</span></span>
<span data-ttu-id="daa72-103">Diese Option gibt die Klasse an, die den Einstiegspunkt des Programms enthält, wenn mehr als eine Klasse eine **Main**-Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="daa72-103">This option specifies the class that contains the entry point to the program, if more than one class contains a **Main** method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daa72-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="daa72-104">Syntax</span></span>  
  
```console  
/main:class  
```  
  
## <a name="arguments"></a><span data-ttu-id="daa72-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="daa72-105">Arguments</span></span>  
 `class`  
 <span data-ttu-id="daa72-106">Der Typ, der die **Main**-Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="daa72-106">The type that contains the **Main** method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="daa72-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="daa72-107">Remarks</span></span>  
 <span data-ttu-id="daa72-108">Wenn Ihre Kompilierung mehr als einen Typ mit einer [Main](../../../csharp/programming-guide/main-and-command-args/index.md)-Methode enthält, können Sie angeben, welcher Typ die **Main**-Methode enthält, die Sie als Einstiegspunkt des Programms verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="daa72-108">If your compilation includes more than one type with a [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method, you can specify which type contains the **Main** method that you want to use as the entry point into the program.</span></span>  
  
 <span data-ttu-id="daa72-109">Diese Option wird verwendet, wenn eine EXE-Datei kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="daa72-109">This option is for use when compiling an .exe file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="daa72-110">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="daa72-110">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="daa72-111">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="daa72-111">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="daa72-112">Klicken Sie auf die Eigenschaftenseite **Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="daa72-112">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="daa72-113">Ändern Sie die Eigenschaft **Startobjekt**.</span><span class="sxs-lookup"><span data-stu-id="daa72-113">Modify the **Startup object** property.</span></span>  
  
     <span data-ttu-id="daa72-114">Wie Sie diese Compileroption programmgesteuert festlegen, erfahren Sie unter <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="daa72-114">To set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="daa72-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="daa72-115">Example</span></span>  
 <span data-ttu-id="daa72-116">Kompilieren Sie `t2.cs` und `t3.cs`, und geben Sie so an, dass die Methode **Main** in `Test2` gefunden wird:</span><span class="sxs-lookup"><span data-stu-id="daa72-116">Compile `t2.cs` and `t3.cs`, specifying that the **Main** method will be found in `Test2`:</span></span>  
  
```console  
csc t2.cs t3.cs /main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="daa72-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="daa72-117">See Also</span></span>  
 [<span data-ttu-id="daa72-118">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="daa72-118">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="daa72-119">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="daa72-119">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
