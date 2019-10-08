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
ms.openlocfilehash: 6ee842dbe65cbd9d147e77ec523a2b031d303738
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002388"
---
# <a name="-baseaddress"></a><span data-ttu-id="4d569-102">-baseaddress</span><span class="sxs-lookup"><span data-stu-id="4d569-102">-baseaddress</span></span>
<span data-ttu-id="4d569-103">Gibt beim Erstellen einer DLL eine Standardbasis Adresse an.</span><span class="sxs-lookup"><span data-stu-id="4d569-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d569-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4d569-104">Syntax</span></span>  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="4d569-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="4d569-105">Arguments</span></span>  
  
|<span data-ttu-id="4d569-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="4d569-106">Term</span></span>|<span data-ttu-id="4d569-107">Definition</span><span class="sxs-lookup"><span data-stu-id="4d569-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="4d569-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4d569-108">Required.</span></span> <span data-ttu-id="4d569-109">Die Basisadresse für die DLL.</span><span class="sxs-lookup"><span data-stu-id="4d569-109">The base address for the DLL.</span></span> <span data-ttu-id="4d569-110">Diese Adresse muss als hexadezimal Zahl angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4d569-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d569-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4d569-111">Remarks</span></span>  
 <span data-ttu-id="4d569-112">Die Standard-Basisadresse für eine DLL wird vom-.NET Framework festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4d569-112">The default base address for a DLL is set by the .NET Framework.</span></span>  
  
 <span data-ttu-id="4d569-113">Beachten Sie, dass das niedrigere Wort in dieser Adresse gerundet wird.</span><span class="sxs-lookup"><span data-stu-id="4d569-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="4d569-114">Wenn Sie z. b. 0x11110001 angeben, wird es auf 0x11110000 gerundet.</span><span class="sxs-lookup"><span data-stu-id="4d569-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="4d569-115">Verwenden Sie die Option `–R` des Strong Naming Tool (Sn. exe), um den Signatur Vorgang für eine DLL abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4d569-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="4d569-116">Diese Option wird ignoriert, wenn das Ziel keine dll ist.</span><span class="sxs-lookup"><span data-stu-id="4d569-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="4d569-117">To Set-BaseAddress in der Visual Studio-IDE</span><span class="sxs-lookup"><span data-stu-id="4d569-117">To set -baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="4d569-118">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="4d569-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="4d569-119">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="4d569-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="4d569-120">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="4d569-120">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="4d569-121">3.  Klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="4d569-121">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="4d569-122">4.  Ändern Sie den Wert im Feld **DLL-Basisadresse:** .</span><span class="sxs-lookup"><span data-stu-id="4d569-122">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="4d569-123">**Hinweis**:      Das Feld **DLL-Basisadresse:** ist schreibgeschützt, es sei denn, das Ziel ist eine DLL.</span><span class="sxs-lookup"><span data-stu-id="4d569-123">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4d569-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d569-124">See also</span></span>

- [<span data-ttu-id="4d569-125">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="4d569-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="4d569-126">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d569-126">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="4d569-127">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="4d569-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- <span data-ttu-id="4d569-128">[Sn.exe (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="4d569-128">[Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
