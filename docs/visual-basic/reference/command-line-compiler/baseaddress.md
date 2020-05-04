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
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002388"
---
# <a name="-baseaddress"></a><span data-ttu-id="c4983-102">-baseaddress</span><span class="sxs-lookup"><span data-stu-id="c4983-102">-baseaddress</span></span>
<span data-ttu-id="c4983-103">Gibt beim Erstellen einer DLL-Datei eine Standardbasisadresse an</span><span class="sxs-lookup"><span data-stu-id="c4983-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4983-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4983-104">Syntax</span></span>  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="c4983-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="c4983-105">Arguments</span></span>  
  
|<span data-ttu-id="c4983-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="c4983-106">Term</span></span>|<span data-ttu-id="c4983-107">Definition</span><span class="sxs-lookup"><span data-stu-id="c4983-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="c4983-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c4983-108">Required.</span></span> <span data-ttu-id="c4983-109">Die Basisadresse für die DLL.</span><span class="sxs-lookup"><span data-stu-id="c4983-109">The base address for the DLL.</span></span> <span data-ttu-id="c4983-110">Diese Adresse muss als Hexadezimalzahl angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c4983-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4983-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c4983-111">Remarks</span></span>  
 <span data-ttu-id="c4983-112">Die Standardbasisadresse für eine DLL-Datei wird durch das .NET Framework festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c4983-112">The default base address for a DLL is set by the .NET Framework.</span></span>  
  
 <span data-ttu-id="c4983-113">Denken Sie daran, dass das niederwertige Wort in dieser Adresse gerundet wird.</span><span class="sxs-lookup"><span data-stu-id="c4983-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="c4983-114">Wenn Sie zum Beispiel 0x11110001 angeben, wird dieser Wert auf 0x11110000 gerundet.</span><span class="sxs-lookup"><span data-stu-id="c4983-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="c4983-115">Verwenden Sie die `–R`-Option des Strong Name-Tool (Sn.exe), um den Signaturvorgang für die DLL-Datei abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="c4983-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="c4983-116">Diese Option wird ignoriert, wenn das Ziel keine DLL-Datei ist.</span><span class="sxs-lookup"><span data-stu-id="c4983-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="c4983-117">So legen Sie -baseaddress in der Visual Studio-IDE fest</span><span class="sxs-lookup"><span data-stu-id="c4983-117">To set -baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="c4983-118">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="c4983-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c4983-119">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="c4983-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="c4983-120">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="c4983-120">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="c4983-121">3.  Klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="c4983-121">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="c4983-122">4.  Ändern Sie den Wert im Feld **DLL-Basisadresse:** .</span><span class="sxs-lookup"><span data-stu-id="c4983-122">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="c4983-123">**Hinweis**:      Das Feld **DLL-Basisadresse:** ist schreibgeschützt, wenn das Ziel keine DLL-Datei ist.</span><span class="sxs-lookup"><span data-stu-id="c4983-123">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c4983-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4983-124">See also</span></span>

- [<span data-ttu-id="c4983-125">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="c4983-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="c4983-126">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4983-126">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="c4983-127">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="c4983-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- <span data-ttu-id="c4983-128">[Sn.exe (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="c4983-128">[Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
