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
ms.openlocfilehash: fa3079bf1431ba1a16b5a2eef0dd5500fe95909c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "69606612"
---
# <a name="-nowarn-c-compiler-options"></a><span data-ttu-id="97b41-102">-nowarn (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="97b41-102">-nowarn (C# Compiler Options)</span></span>
<span data-ttu-id="97b41-103">Mit der Option **-nowarn** können Sie unterdrücken, dass der Compiler eine oder mehrere Warnungen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="97b41-103">The **-nowarn** option lets you suppress the compiler from displaying one or more warnings.</span></span> <span data-ttu-id="97b41-104">Trennen Sie mehrere Warnnummern durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="97b41-104">Separate multiple warning numbers with a comma.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97b41-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="97b41-105">Syntax</span></span>  
  
```console  
-nowarn:number1[,number2,...]  
```  
  
## <a name="arguments"></a><span data-ttu-id="97b41-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="97b41-106">Arguments</span></span>  
 <span data-ttu-id="97b41-107">`number1`, `number2`</span><span class="sxs-lookup"><span data-stu-id="97b41-107">`number1`, `number2`</span></span>  
 <span data-ttu-id="97b41-108">Warnnummer(n), die der Compiler unterdrücken soll.</span><span class="sxs-lookup"><span data-stu-id="97b41-108">Warning number(s) that you want the compiler to suppress.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97b41-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="97b41-109">Remarks</span></span>  
 <span data-ttu-id="97b41-110">Sie sollten lediglich den numerischen Teil des Warnungsbezeichners angeben.</span><span class="sxs-lookup"><span data-stu-id="97b41-110">You should only specify the numeric part of the warning identifier.</span></span> <span data-ttu-id="97b41-111">Wenn Sie z.B. CS0028 unterdrücken wollen, könnten Sie `-nowarn:28` angeben.</span><span class="sxs-lookup"><span data-stu-id="97b41-111">For example, if you want to suppress CS0028, you could specify `-nowarn:28`.</span></span>  
  
 <span data-ttu-id="97b41-112">Der Compiler wird automatisch die Warnnummern ignorieren, die an `-nowarn` übergeben wurden und in einer früheren Version gültig waren, jedoch aus dem Compiler entfernt worden sind.</span><span class="sxs-lookup"><span data-stu-id="97b41-112">The compiler will silently ignore warning numbers passed to `-nowarn` that were valid in previous releases, but that have been removed from the compiler.</span></span> <span data-ttu-id="97b41-113">CS0679 war z.B. im Compiler in Visual Studio .NET 2002 gültig, wurde aber später entfernt.</span><span class="sxs-lookup"><span data-stu-id="97b41-113">For example, CS0679 was valid in the compiler in Visual Studio .NET 2002 but was subsequently removed.</span></span>  
  
 <span data-ttu-id="97b41-114">Die folgenden Warnungen können nicht durch die Option `-nowarn` unterdrückt werden.</span><span class="sxs-lookup"><span data-stu-id="97b41-114">The following warnings cannot be suppressed by the `-nowarn` option:</span></span>  
  
- <span data-ttu-id="97b41-115">Compilerwarnung (Stufe 1) CS2002</span><span class="sxs-lookup"><span data-stu-id="97b41-115">Compiler Warning (level 1) CS2002</span></span>  
  
- <span data-ttu-id="97b41-116">Compilerwarnung (Stufe 1) CS2023</span><span class="sxs-lookup"><span data-stu-id="97b41-116">Compiler Warning (level 1) CS2023</span></span>  
  
- <span data-ttu-id="97b41-117">Compilerwarnung (Stufe 1) CS2029</span><span class="sxs-lookup"><span data-stu-id="97b41-117">Compiler Warning (level 1) CS2029</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="97b41-118">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="97b41-118">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="97b41-119">Öffnen Sie die Seite **Eigenschaften** für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="97b41-119">Open the **Properties** page for the project.</span></span> <span data-ttu-id="97b41-120">Informationen finden Sie auf der [Seite „Erstellen“, Projekt-Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="97b41-120">For details, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2. <span data-ttu-id="97b41-121">Klicken Sie auf die Eigenschaftenseite **Build** .</span><span class="sxs-lookup"><span data-stu-id="97b41-121">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="97b41-122">Ändern Sie die Eigenschaft **Warnungen unterdrücken**.</span><span class="sxs-lookup"><span data-stu-id="97b41-122">Modify the **Suppress Warnings** property.</span></span>  
  
 <span data-ttu-id="97b41-123">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span><span class="sxs-lookup"><span data-stu-id="97b41-123">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97b41-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="97b41-124">See also</span></span>

- [<span data-ttu-id="97b41-125">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="97b41-125">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="97b41-126">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="97b41-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="97b41-127">C#-Compilerfehler</span><span class="sxs-lookup"><span data-stu-id="97b41-127">C# Compiler Errors</span></span>](../compiler-messages/index.md)
