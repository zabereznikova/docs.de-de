---
title: -BaseAddress-Element
ms.date: 08/09/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3abe566e7a32a0b350a4f483df5c77fa4d003367
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="-baseaddress"></a><span data-ttu-id="71736-102">-BaseAddress-Element</span><span class="sxs-lookup"><span data-stu-id="71736-102">-baseaddress</span></span>
<span data-ttu-id="71736-103">Gibt eine Standard-Basisadresse an, beim Erstellen einer DLL.</span><span class="sxs-lookup"><span data-stu-id="71736-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71736-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="71736-104">Syntax</span></span>  
  
```  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="71736-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="71736-105">Arguments</span></span>  
  
|<span data-ttu-id="71736-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="71736-106">Term</span></span>|<span data-ttu-id="71736-107">Definition</span><span class="sxs-lookup"><span data-stu-id="71736-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="71736-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="71736-108">Required.</span></span> <span data-ttu-id="71736-109">Die Basisadresse für die DLL.</span><span class="sxs-lookup"><span data-stu-id="71736-109">The base address for the DLL.</span></span> <span data-ttu-id="71736-110">Diese Adresse muss als eine hexadezimale Zahl angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="71736-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71736-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="71736-111">Remarks</span></span>  
 <span data-ttu-id="71736-112">Die Standard-Basisadresse für eine DLL wird durch Festlegen der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="71736-112">The default base address for a DLL is set by the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>  
  
 <span data-ttu-id="71736-113">Denken Sie daran, dass das niederwertige Wort in dieser Adresse gerundet wird.</span><span class="sxs-lookup"><span data-stu-id="71736-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="71736-114">Wenn Sie 0 x 11110001 angeben, wird es beispielsweise auf 0 x 11110000 gerundet.</span><span class="sxs-lookup"><span data-stu-id="71736-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="71736-115">Zum Ausführen des signierungsprozesses für eine DLL verwenden die `–R` Möglichkeit, das Strong Name-Tool (Sn.exe).</span><span class="sxs-lookup"><span data-stu-id="71736-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="71736-116">Diese Option wird ignoriert, wenn das Ziel keine DLL ist.</span><span class="sxs-lookup"><span data-stu-id="71736-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="71736-117">-BaseAddress-Element in der Visual Studio-IDE festlegen</span><span class="sxs-lookup"><span data-stu-id="71736-117">To set -baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="71736-118">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="71736-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="71736-119">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="71736-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="71736-120">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="71736-120">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="71736-121">3.  Klicken Sie auf **erweiterte**.</span><span class="sxs-lookup"><span data-stu-id="71736-121">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="71736-122">4.  Ändern Sie den Wert in der **Basisadresse der DLL:** Feld.</span><span class="sxs-lookup"><span data-stu-id="71736-122">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="71736-123">**Hinweis:** der **Basisadresse der DLL:** Feld ist schreibgeschützt, es sei denn, das Ziel eine DLL ist.</span><span class="sxs-lookup"><span data-stu-id="71736-123">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="71736-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71736-124">See Also</span></span>  
 [<span data-ttu-id="71736-125">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="71736-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="71736-126">-Ziel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71736-126">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="71736-127">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="71736-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 <span data-ttu-id="71736-128">[Sn.exe (Strong Name-Tool)] [Sn.exe (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="71736-128">[Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
