---
title: -nowarn (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /nowarn
helpviewer_keywords:
- nowarn compiler option [C#]
- /nowarn compiler option [C#]
- -nowarn compiler option [C#]
ms.assetid: 6dcbc5e8-ae67-4566-9df3-f63cfdd9c4e4
ms.openlocfilehash: 76bb008c40d84ed6048b8f960f050048319273b9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43518204"
---
# <a name="-nowarn-c-compiler-options"></a><span data-ttu-id="81f8d-102">-nowarn (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="81f8d-102">-nowarn (C# Compiler Options)</span></span>
<span data-ttu-id="81f8d-103">Mit der Option **-nowarn** können Sie unterdrücken, dass der Compiler eine oder mehrere Warnungen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="81f8d-103">The **-nowarn** option lets you suppress the compiler from displaying one or more warnings.</span></span> <span data-ttu-id="81f8d-104">Trennen Sie mehrere Warnnummern durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="81f8d-104">Separate multiple warning numbers with a comma.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81f8d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="81f8d-105">Syntax</span></span>  
  
```console  
-nowarn:number1[,number2,...]  
```  
  
## <a name="arguments"></a><span data-ttu-id="81f8d-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="81f8d-106">Arguments</span></span>  
 <span data-ttu-id="81f8d-107">`number1`, `number2`</span><span class="sxs-lookup"><span data-stu-id="81f8d-107">`number1`, `number2`</span></span>  
 <span data-ttu-id="81f8d-108">Warnnummer(n), die der Compiler unterdrücken soll.</span><span class="sxs-lookup"><span data-stu-id="81f8d-108">Warning number(s) that you want the compiler to suppress.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81f8d-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="81f8d-109">Remarks</span></span>  
 <span data-ttu-id="81f8d-110">Sie sollten lediglich den numerischen Teil des Warnungsbezeichners angeben.</span><span class="sxs-lookup"><span data-stu-id="81f8d-110">You should only specify the numeric part of the warning identifier.</span></span> <span data-ttu-id="81f8d-111">Wenn Sie z.B. CS0028 unterdrücken wollen, könnten Sie `-nowarn:28` angeben.</span><span class="sxs-lookup"><span data-stu-id="81f8d-111">For example, if you want to suppress CS0028, you could specify `-nowarn:28`.</span></span>  
  
 <span data-ttu-id="81f8d-112">Der Compiler wird automatisch die Warnnummern ignorieren, die an `-nowarn` übergeben wurden und in einer früheren Version gültig waren, jedoch aus dem Compiler entfernt worden sind.</span><span class="sxs-lookup"><span data-stu-id="81f8d-112">The compiler will silently ignore warning numbers passed to `-nowarn` that were valid in previous releases, but that have been removed from the compiler.</span></span> <span data-ttu-id="81f8d-113">CS0679 war z.B. im Compiler in Visual Studio .NET 2002 gültig, wurde aber später entfernt.</span><span class="sxs-lookup"><span data-stu-id="81f8d-113">For example, CS0679 was valid in the compiler in Visual Studio .NET 2002 but was subsequently removed.</span></span>  
  
 <span data-ttu-id="81f8d-114">Die folgenden Warnungen können nicht durch die Option `-nowarn` unterdrückt werden.</span><span class="sxs-lookup"><span data-stu-id="81f8d-114">The following warnings cannot be suppressed by the `-nowarn` option:</span></span>  
  
-   <span data-ttu-id="81f8d-115">Compilerwarnung (Stufe 1) CS2002</span><span class="sxs-lookup"><span data-stu-id="81f8d-115">Compiler Warning (level 1) CS2002</span></span>  
  
-   <span data-ttu-id="81f8d-116">Compilerwarnung (Stufe 1) CS2023</span><span class="sxs-lookup"><span data-stu-id="81f8d-116">Compiler Warning (level 1) CS2023</span></span>  
  
-   <span data-ttu-id="81f8d-117">Compilerwarnung (Stufe 1) CS2029</span><span class="sxs-lookup"><span data-stu-id="81f8d-117">Compiler Warning (level 1) CS2029</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="81f8d-118">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="81f8d-118">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="81f8d-119">Öffnen Sie die Seite **Eigenschaften** für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="81f8d-119">Open the **Properties** page for the project.</span></span> <span data-ttu-id="81f8d-120">Informationen finden Sie auf der [Seite „Erstellen“, Projekt-Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="81f8d-120">For details, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2.  <span data-ttu-id="81f8d-121">Klicken Sie auf die Eigenschaftenseite **Build** .</span><span class="sxs-lookup"><span data-stu-id="81f8d-121">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="81f8d-122">Ändern Sie die Eigenschaft **Warnungen unterdrücken**.</span><span class="sxs-lookup"><span data-stu-id="81f8d-122">Modify the **Suppress Warnings** property.</span></span>  
  
 <span data-ttu-id="81f8d-123">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span><span class="sxs-lookup"><span data-stu-id="81f8d-123">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81f8d-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81f8d-124">See Also</span></span>  

- [<span data-ttu-id="81f8d-125">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="81f8d-125">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="81f8d-126">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="81f8d-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
- [<span data-ttu-id="81f8d-127">C#-Compilerfehler</span><span class="sxs-lookup"><span data-stu-id="81f8d-127">C# Compiler Errors</span></span>](../../../csharp/language-reference/compiler-messages/index.md)
