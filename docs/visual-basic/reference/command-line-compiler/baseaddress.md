---
title: -baseaddress
ms.date: 08/09/2018
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
ms.openlocfilehash: 0550e4ad700494c8773a5d9b5b282dfa116adfed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61839552"
---
# <a name="-baseaddress"></a><span data-ttu-id="7fca6-102">-baseaddress</span><span class="sxs-lookup"><span data-stu-id="7fca6-102">-baseaddress</span></span>
<span data-ttu-id="7fca6-103">Gibt einen Standard-Basisadresse an, beim Erstellen einer DLL.</span><span class="sxs-lookup"><span data-stu-id="7fca6-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fca6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7fca6-104">Syntax</span></span>  
  
```  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="7fca6-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="7fca6-105">Arguments</span></span>  
  
|<span data-ttu-id="7fca6-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="7fca6-106">Term</span></span>|<span data-ttu-id="7fca6-107">Definition</span><span class="sxs-lookup"><span data-stu-id="7fca6-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="7fca6-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7fca6-108">Required.</span></span> <span data-ttu-id="7fca6-109">Die Basisadresse für die DLL.</span><span class="sxs-lookup"><span data-stu-id="7fca6-109">The base address for the DLL.</span></span> <span data-ttu-id="7fca6-110">Diese Adresse muss als hexadezimale Zahl angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7fca6-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fca6-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7fca6-111">Remarks</span></span>  
 <span data-ttu-id="7fca6-112">Die Standard-Basisadresse für eine DLL-Datei wird festgelegt, durch die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7fca6-112">The default base address for a DLL is set by the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>  
  
 <span data-ttu-id="7fca6-113">Denken Sie daran, dass das niederwertige Wort in dieser Adresse gerundet wird.</span><span class="sxs-lookup"><span data-stu-id="7fca6-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="7fca6-114">Wenn Sie 0 x 11110001 angeben, wird es beispielsweise auf 0 x 11110000 gerundet.</span><span class="sxs-lookup"><span data-stu-id="7fca6-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="7fca6-115">Um die Signatur für eine DLL abzuschließen, verwenden Sie die `–R` Möglichkeit, das Strong Name-Tool (Sn.exe).</span><span class="sxs-lookup"><span data-stu-id="7fca6-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="7fca6-116">Diese Option wird ignoriert, wenn das Ziel nicht um eine DLL-Datei ist.</span><span class="sxs-lookup"><span data-stu-id="7fca6-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="7fca6-117">-Baseaddress in Visual Studio-IDE festlegen</span><span class="sxs-lookup"><span data-stu-id="7fca6-117">To set -baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="7fca6-118">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="7fca6-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="7fca6-119">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="7fca6-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="7fca6-120">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="7fca6-120">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="7fca6-121">3.  Klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="7fca6-121">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="7fca6-122">4.  Ändern Sie den Wert in der **DLL-Basisadresse:** Feld.</span><span class="sxs-lookup"><span data-stu-id="7fca6-122">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="7fca6-123">**Hinweis**:      Die **DLL-Basisadresse:** Feld ist schreibgeschützt, es sei denn, das Ziel eine DLL-Datei ist.</span><span class="sxs-lookup"><span data-stu-id="7fca6-123">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7fca6-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7fca6-124">See also</span></span>

- [<span data-ttu-id="7fca6-125">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="7fca6-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="7fca6-126">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7fca6-126">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="7fca6-127">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="7fca6-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- <span data-ttu-id="7fca6-128">[Sn.exe (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="7fca6-128">[Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
