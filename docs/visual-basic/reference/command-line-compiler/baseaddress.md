---
title: / BaseAddress | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /baseaddress
- baseaddress
dev_langs:
- VB
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 5687f119a57e0e54eca4df8f91fdf5e8b2775f82
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="baseaddress"></a><span data-ttu-id="8362a-102">/baseaddress</span><span class="sxs-lookup"><span data-stu-id="8362a-102">/baseaddress</span></span>
<span data-ttu-id="8362a-103">Gibt eine Standard-Basisadresse an, beim Erstellen einer DLL.</span><span class="sxs-lookup"><span data-stu-id="8362a-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8362a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8362a-104">Syntax</span></span>  
  
```  
/baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="8362a-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="8362a-105">Arguments</span></span>  
  
|<span data-ttu-id="8362a-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="8362a-106">Term</span></span>|<span data-ttu-id="8362a-107">Definition</span><span class="sxs-lookup"><span data-stu-id="8362a-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="8362a-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8362a-108">Required.</span></span> <span data-ttu-id="8362a-109">Die Basisadresse für die DLL.</span><span class="sxs-lookup"><span data-stu-id="8362a-109">The base address for the DLL.</span></span> <span data-ttu-id="8362a-110">Diese Adresse muss als Hexadezimalwert angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8362a-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8362a-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8362a-111">Remarks</span></span>  
 <span data-ttu-id="8362a-112">Die Standard-Basisadresse für eine DLL-Datei festgelegt ist, durch die [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span><span class="sxs-lookup"><span data-stu-id="8362a-112">The default base address for a DLL is set by the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span>  
  
 <span data-ttu-id="8362a-113">Denken Sie daran, dass das niederwertige Wort in dieser Adresse gerundet wird.</span><span class="sxs-lookup"><span data-stu-id="8362a-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="8362a-114">Wenn Sie 0 x 11110001 angeben, wird sie z. B. auf 0 x 11110000 gerundet.</span><span class="sxs-lookup"><span data-stu-id="8362a-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="8362a-115">Um den Signaturprozess für eine DLL durchzuführen, verwenden die `–R` Möglichkeit, das Strong Name-Tool (Sn.exe).</span><span class="sxs-lookup"><span data-stu-id="8362a-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="8362a-116">Diese Option wird ignoriert, wenn das Ziel keine DLL ist.</span><span class="sxs-lookup"><span data-stu-id="8362a-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="8362a-117">/ Baseaddress in der Visual Studio-IDE festlegen</span><span class="sxs-lookup"><span data-stu-id="8362a-117">To set /baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="8362a-118">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="8362a-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="8362a-119">Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="8362a-119">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="8362a-120">Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="8362a-120">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="8362a-121">2.  Klicken Sie auf die **Kompilieren** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="8362a-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="8362a-122">3.  Klicken Sie auf **erweiterte**.</span><span class="sxs-lookup"><span data-stu-id="8362a-122">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="8362a-123">4.  Ändern Sie den Wert in der **DLL-Basisadresse:** Feld.</span><span class="sxs-lookup"><span data-stu-id="8362a-123">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="8362a-124">**Hinweis:** der **DLL-Basisadresse:** Feld ist schreibgeschützt, wenn das Ziel eine DLL ist.</span><span class="sxs-lookup"><span data-stu-id="8362a-124">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8362a-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8362a-125">See Also</span></span>  
 <span data-ttu-id="8362a-126">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="8362a-126">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="8362a-127"> [/ target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="8362a-127"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="8362a-128"> [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="8362a-128"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="8362a-129"> [Sn.exe (Strong Name-Tool)](https://msdn.microsoft.com/library/k5b5tt23)</span><span class="sxs-lookup"><span data-stu-id="8362a-129"> [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23)</span></span>
