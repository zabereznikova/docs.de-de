---
description: -filealign (C#-Compileroptionen)
title: -filealign (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /filealign
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
ms.openlocfilehash: 4b61217a3d6812ea3ab036f82d49bba05c20629e
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "91173242"
---
# <a name="-filealign-c-compiler-options"></a><span data-ttu-id="aba48-103">-filealign (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="aba48-103">-filealign (C# Compiler Options)</span></span>

<span data-ttu-id="aba48-104">Mit der Option **-filealign** können Sie die Größe der Abschnitte in Ihrer Ausgabedatei angeben.</span><span class="sxs-lookup"><span data-stu-id="aba48-104">The **-filealign** option lets you specify the size of sections in your output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aba48-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="aba48-105">Syntax</span></span>  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="aba48-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="aba48-106">Arguments</span></span>  

 `number`  
 <span data-ttu-id="aba48-107">Ein Wert, der die Größe der Abschnitte in der Ausgabedatei angibt.</span><span class="sxs-lookup"><span data-stu-id="aba48-107">A value that specifies the size of sections in the output file.</span></span> <span data-ttu-id="aba48-108">Gültige Werte sind 512, 1024, 2048, 4096 und 8192.</span><span class="sxs-lookup"><span data-stu-id="aba48-108">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="aba48-109">Diese Werte sind in Bytes angegeben.</span><span class="sxs-lookup"><span data-stu-id="aba48-109">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aba48-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aba48-110">Remarks</span></span>  

 <span data-ttu-id="aba48-111">Jeder Abschnitt wird auf einer Grenze angeordnet, die ein Vielfaches des Werts **-filealign** darstellt.</span><span class="sxs-lookup"><span data-stu-id="aba48-111">Each section will be aligned on a boundary that is a multiple of the **-filealign** value.</span></span> <span data-ttu-id="aba48-112">Es gibt keinen festen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="aba48-112">There is no fixed default.</span></span> <span data-ttu-id="aba48-113">Wenn **-filealign** nicht angegeben ist, wählt die Common Language Runtime zur Kompilierzeit einen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="aba48-113">If **-filealign** is not specified, the common language runtime picks a default at compile time.</span></span>  
  
 <span data-ttu-id="aba48-114">Das Angeben der Abschnittsgröße wirkt sich auf die Größe der Ausgabedatei aus.</span><span class="sxs-lookup"><span data-stu-id="aba48-114">By specifying the section size, you affect the size of the output file.</span></span> <span data-ttu-id="aba48-115">Das Ändern der Größe kann möglicherweise für Programme hilfreich sein, die auf kleineren Geräten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="aba48-115">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
 <span data-ttu-id="aba48-116">Verwenden Sie [DUMPBIN](/cpp/build/reference/dumpbin-options), um Informationen über Abschnitte in Ihrer Ausgabedatei anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="aba48-116">Use [DUMPBIN](/cpp/build/reference/dumpbin-options) to see information about sections in your output file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="aba48-117">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="aba48-117">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="aba48-118">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="aba48-118">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="aba48-119">Klicken Sie auf die Eigenschaftenseite **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="aba48-119">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="aba48-120">Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="aba48-120">Click the **Advanced** button.</span></span>  
  
4. <span data-ttu-id="aba48-121">Ändern der Eigenschaft **Dateianordnung**.</span><span class="sxs-lookup"><span data-stu-id="aba48-121">Modify the **File Alignment** property.</span></span>  
  
 <span data-ttu-id="aba48-122">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.</span><span class="sxs-lookup"><span data-stu-id="aba48-122">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aba48-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aba48-123">See also</span></span>

- [<span data-ttu-id="aba48-124">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="aba48-124">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="aba48-125">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="aba48-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
