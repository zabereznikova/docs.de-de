---
title: -filealign (C#-Compileroptionen)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /filealign
helpviewer_keywords:
- /alignment compiler option [C#]
- filealign compiler option [C#]
- -filealign compiler option [C#]
- /sections compiler option [C#]
- alignment compiler option [C#]
- sections compiler option [C#]
- -sections compiler option [C#]
- /filealign compiler option [C#]
- file sharing [C#]
- -alignment compiler option [C#]
- section alignment [C#]
ms.assetid: 15cf1c98-3798-4ced-9f08-60619308a073
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f00db0cfd191de060b67aee4618d99740cb81248
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="-filealign-c-compiler-options"></a><span data-ttu-id="163ac-102">-filealign (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="163ac-102">-filealign (C# Compiler Options)</span></span>
<span data-ttu-id="163ac-103">Mit der Option **-filealign** können Sie die Größe der Abschnitte in Ihrer Ausgabedatei angeben.</span><span class="sxs-lookup"><span data-stu-id="163ac-103">The **-filealign** option lets you specify the size of sections in your output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="163ac-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="163ac-104">Syntax</span></span>  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="163ac-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="163ac-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="163ac-106">Ein Wert, der die Größe der Abschnitte in der Ausgabedatei angibt.</span><span class="sxs-lookup"><span data-stu-id="163ac-106">A value that specifies the size of sections in the output file.</span></span> <span data-ttu-id="163ac-107">Gültige Werte sind 512, 1024, 2048, 4096 und 8192.</span><span class="sxs-lookup"><span data-stu-id="163ac-107">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="163ac-108">Diese Werte sind in Bytes angegeben.</span><span class="sxs-lookup"><span data-stu-id="163ac-108">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="163ac-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="163ac-109">Remarks</span></span>  
 <span data-ttu-id="163ac-110">Jeder Abschnitt wird auf einer Grenze angeordnet, die ein Vielfaches des Werts **-filealign** darstellt.</span><span class="sxs-lookup"><span data-stu-id="163ac-110">Each section will be aligned on a boundary that is a multiple of the **-filealign** value.</span></span> <span data-ttu-id="163ac-111">Es gibt keinen festen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="163ac-111">There is no fixed default.</span></span> <span data-ttu-id="163ac-112">Wenn **-filealign** nicht angegeben ist, wählt die Common Language Runtime zur Kompilierzeit einen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="163ac-112">If **-filealign** is not specified, the common language runtime picks a default at compile time.</span></span>  
  
 <span data-ttu-id="163ac-113">Das Angeben der Abschnittsgröße wirkt sich auf die Größe der Ausgabedatei aus.</span><span class="sxs-lookup"><span data-stu-id="163ac-113">By specifying the section size, you affect the size of the output file.</span></span> <span data-ttu-id="163ac-114">Das Ändern der Größe kann möglicherweise für Programme hilfreich sein, die auf kleineren Geräten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="163ac-114">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
 <span data-ttu-id="163ac-115">Verwenden Sie [DUMPBIN](/cpp/build/reference/dumpbin-options), um Informationen über Abschnitte in Ihrer Ausgabedatei anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="163ac-115">Use [DUMPBIN](/cpp/build/reference/dumpbin-options) to see information about sections in your output file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="163ac-116">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="163ac-116">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="163ac-117">Öffnen Sie die **Eigenschaftenseite** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="163ac-117">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="163ac-118">Klicken Sie auf die Eigenschaftenseite **Build** .</span><span class="sxs-lookup"><span data-stu-id="163ac-118">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="163ac-119">Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="163ac-119">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="163ac-120">Ändern der Eigenschaft **Dateianordnung**.</span><span class="sxs-lookup"><span data-stu-id="163ac-120">Modify the **File Alignment** property.</span></span>  
  
 <span data-ttu-id="163ac-121">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.</span><span class="sxs-lookup"><span data-stu-id="163ac-121">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="163ac-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="163ac-122">See Also</span></span>  
 [<span data-ttu-id="163ac-123">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="163ac-123">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="163ac-124">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="163ac-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
