---
title: -unsafe (C#-Compileroptionen)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.assetid: fdb77ed9-da03-45bd-bb7f-250704da1bcc
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 146977522b400418a26f6a83e1a0ccdca8675bf9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="unsafe-c-compiler-options"></a><span data-ttu-id="505ac-102">/unsafe (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="505ac-102">/unsafe (C# Compiler Options)</span></span>
<span data-ttu-id="505ac-103">Die **/unsafe**-Compileroption ermöglicht das Kompilieren von Code, der das [unsafe](../../../csharp/language-reference/keywords/unsafe.md)-Schlüsselwort verwendet.</span><span class="sxs-lookup"><span data-stu-id="505ac-103">The **/unsafe** compiler option allows code that uses the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="505ac-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="505ac-104">Syntax</span></span>  
  
```console  
/unsafe  
```  
  
## <a name="remarks"></a><span data-ttu-id="505ac-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="505ac-105">Remarks</span></span>  
 <span data-ttu-id="505ac-106">Weitere Informationen zu unsicherem Code finden Sie unter [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="505ac-106">For more information about unsafe code, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="505ac-107">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="505ac-107">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="505ac-108">Öffnen Sie die **Eigenschaften**-Seite des Projekts.</span><span class="sxs-lookup"><span data-stu-id="505ac-108">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="505ac-109">Klicken Sie auf die Eigenschaftenseite **Build** .</span><span class="sxs-lookup"><span data-stu-id="505ac-109">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="505ac-110">Wählen Sie die **Unsicheren Code zulassen**-Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="505ac-110">Select the **Allow Unsafe Code** check box.</span></span>  
  
 <span data-ttu-id="505ac-111">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span><span class="sxs-lookup"><span data-stu-id="505ac-111">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="505ac-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="505ac-112">Example</span></span>  
 <span data-ttu-id="505ac-113">Kompilieren Sie `in.cs` für den unsicheren Modus:</span><span class="sxs-lookup"><span data-stu-id="505ac-113">Compile `in.cs` for unsafe mode:</span></span>  
  
```console  
csc /unsafe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="505ac-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="505ac-114">See Also</span></span>  
 [<span data-ttu-id="505ac-115">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="505ac-115">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="505ac-116">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="505ac-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
