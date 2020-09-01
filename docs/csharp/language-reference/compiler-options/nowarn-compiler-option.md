---
description: -nowarn (C#-Compileroptionen)
title: -nowarn (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /nowarn
helpviewer_keywords:
- nowarn compiler option [C#]
- /nowarn compiler option [C#]
- -nowarn compiler option [C#]
ms.assetid: 6dcbc5e8-ae67-4566-9df3-f63cfdd9c4e4
ms.openlocfilehash: ab906912bc4bfab40e459c92a823b915240b8d55
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125084"
---
# <a name="-nowarn-c-compiler-options"></a><span data-ttu-id="e9011-103">-nowarn (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="e9011-103">-nowarn (C# Compiler Options)</span></span>
<span data-ttu-id="e9011-104">Mit der Option **-nowarn** können Sie unterdrücken, dass der Compiler eine oder mehrere Warnungen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="e9011-104">The **-nowarn** option lets you suppress the compiler from displaying one or more warnings.</span></span> <span data-ttu-id="e9011-105">Trennen Sie mehrere Warnnummern durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="e9011-105">Separate multiple warning numbers with a comma.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9011-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9011-106">Syntax</span></span>  
  
```console  
-nowarn:number1[,number2,...]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e9011-107">Argumente</span><span class="sxs-lookup"><span data-stu-id="e9011-107">Arguments</span></span>  
 <span data-ttu-id="e9011-108">`number1`, `number2`</span><span class="sxs-lookup"><span data-stu-id="e9011-108">`number1`, `number2`</span></span>  
 <span data-ttu-id="e9011-109">Warnnummer(n), die der Compiler unterdrücken soll.</span><span class="sxs-lookup"><span data-stu-id="e9011-109">Warning number(s) that you want the compiler to suppress.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9011-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e9011-110">Remarks</span></span>  
 <span data-ttu-id="e9011-111">Sie sollten lediglich den numerischen Teil des Warnungsbezeichners angeben.</span><span class="sxs-lookup"><span data-stu-id="e9011-111">You should only specify the numeric part of the warning identifier.</span></span> <span data-ttu-id="e9011-112">Wenn Sie z.B. CS0028 unterdrücken wollen, könnten Sie `-nowarn:28` angeben.</span><span class="sxs-lookup"><span data-stu-id="e9011-112">For example, if you want to suppress CS0028, you could specify `-nowarn:28`.</span></span>  
  
 <span data-ttu-id="e9011-113">Der Compiler wird automatisch die Warnnummern ignorieren, die an `-nowarn` übergeben wurden und in einer früheren Version gültig waren, jedoch aus dem Compiler entfernt worden sind.</span><span class="sxs-lookup"><span data-stu-id="e9011-113">The compiler will silently ignore warning numbers passed to `-nowarn` that were valid in previous releases, but that have been removed from the compiler.</span></span> <span data-ttu-id="e9011-114">CS0679 war z.B. im Compiler in Visual Studio .NET 2002 gültig, wurde aber später entfernt.</span><span class="sxs-lookup"><span data-stu-id="e9011-114">For example, CS0679 was valid in the compiler in Visual Studio .NET 2002 but was subsequently removed.</span></span>  
  
 <span data-ttu-id="e9011-115">Die folgenden Warnungen können nicht durch die Option `-nowarn` unterdrückt werden.</span><span class="sxs-lookup"><span data-stu-id="e9011-115">The following warnings cannot be suppressed by the `-nowarn` option:</span></span>  
  
- <span data-ttu-id="e9011-116">Compilerwarnung (Stufe 1) CS2002</span><span class="sxs-lookup"><span data-stu-id="e9011-116">Compiler Warning (level 1) CS2002</span></span>  
  
- <span data-ttu-id="e9011-117">Compilerwarnung (Stufe 1) CS2023</span><span class="sxs-lookup"><span data-stu-id="e9011-117">Compiler Warning (level 1) CS2023</span></span>  
  
- <span data-ttu-id="e9011-118">Compilerwarnung (Stufe 1) CS2029</span><span class="sxs-lookup"><span data-stu-id="e9011-118">Compiler Warning (level 1) CS2029</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="e9011-119">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="e9011-119">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="e9011-120">Öffnen Sie die Seite **Eigenschaften** für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="e9011-120">Open the **Properties** page for the project.</span></span> <span data-ttu-id="e9011-121">Informationen finden Sie auf der [Seite „Erstellen“, Projekt-Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="e9011-121">For details, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2. <span data-ttu-id="e9011-122">Klicken Sie auf die Eigenschaftenseite **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="e9011-122">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="e9011-123">Ändern Sie die Eigenschaft **Warnungen unterdrücken**.</span><span class="sxs-lookup"><span data-stu-id="e9011-123">Modify the **Suppress Warnings** property.</span></span>  
  
 <span data-ttu-id="e9011-124">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span><span class="sxs-lookup"><span data-stu-id="e9011-124">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9011-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e9011-125">See also</span></span>

- [<span data-ttu-id="e9011-126">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="e9011-126">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="e9011-127">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="e9011-127">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="e9011-128">C#-Compilerfehler</span><span class="sxs-lookup"><span data-stu-id="e9011-128">C# Compiler Errors</span></span>](../compiler-messages/index.md)
