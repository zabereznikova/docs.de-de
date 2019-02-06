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
ms.openlocfilehash: 733013c8eca75bad0dc0bdf1d76f1468b1d903a8
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2019
ms.locfileid: "55759391"
---
# <a name="-baseaddress"></a><span data-ttu-id="bfe3a-102">-baseaddress</span><span class="sxs-lookup"><span data-stu-id="bfe3a-102">-baseaddress</span></span>
<span data-ttu-id="bfe3a-103">Gibt einen Standard-Basisadresse an, beim Erstellen einer DLL.</span><span class="sxs-lookup"><span data-stu-id="bfe3a-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfe3a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bfe3a-104">Syntax</span></span>  
  
```  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="bfe3a-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="bfe3a-105">Arguments</span></span>  
  
|<span data-ttu-id="bfe3a-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="bfe3a-106">Term</span></span>|<span data-ttu-id="bfe3a-107">Definition</span><span class="sxs-lookup"><span data-stu-id="bfe3a-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="bfe3a-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bfe3a-108">Required.</span></span> <span data-ttu-id="bfe3a-109">Die Basisadresse für die DLL.</span><span class="sxs-lookup"><span data-stu-id="bfe3a-109">The base address for the DLL.</span></span> <span data-ttu-id="bfe3a-110">Diese Adresse muss als hexadezimale Zahl angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bfe3a-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfe3a-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bfe3a-111">Remarks</span></span>  
 <span data-ttu-id="bfe3a-112">Die Standard-Basisadresse für eine DLL-Datei wird festgelegt, durch die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfe3a-112">The default base address for a DLL is set by the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>  
  
 <span data-ttu-id="bfe3a-113">Denken Sie daran, dass das niederwertige Wort in dieser Adresse gerundet wird.</span><span class="sxs-lookup"><span data-stu-id="bfe3a-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="bfe3a-114">Wenn Sie 0 x 11110001 angeben, wird es beispielsweise auf 0 x 11110000 gerundet.</span><span class="sxs-lookup"><span data-stu-id="bfe3a-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="bfe3a-115">Um die Signatur für eine DLL abzuschließen, verwenden Sie die `–R` Möglichkeit, das Strong Name-Tool (Sn.exe).</span><span class="sxs-lookup"><span data-stu-id="bfe3a-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="bfe3a-116">Diese Option wird ignoriert, wenn das Ziel nicht um eine DLL-Datei ist.</span><span class="sxs-lookup"><span data-stu-id="bfe3a-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="bfe3a-117">-Baseaddress in Visual Studio-IDE festlegen</span><span class="sxs-lookup"><span data-stu-id="bfe3a-117">To set -baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="bfe3a-118">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="bfe3a-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="bfe3a-119">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="bfe3a-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="bfe3a-120">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="bfe3a-120">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="bfe3a-121">3.  Klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="bfe3a-121">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="bfe3a-122">4.  Ändern Sie den Wert in der **DLL-Basisadresse:** Feld.</span><span class="sxs-lookup"><span data-stu-id="bfe3a-122">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="bfe3a-123">**Hinweis**:      Die **DLL-Basisadresse:** Feld ist schreibgeschützt, es sei denn, das Ziel eine DLL-Datei ist.</span><span class="sxs-lookup"><span data-stu-id="bfe3a-123">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bfe3a-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bfe3a-124">See also</span></span>
- [<span data-ttu-id="bfe3a-125">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="bfe3a-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="bfe3a-126">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bfe3a-126">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="bfe3a-127">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="bfe3a-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- <span data-ttu-id="bfe3a-128">[Sn.exe (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="bfe3a-128">[Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
