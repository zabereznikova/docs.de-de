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
ms.openlocfilehash: c794d1fc1c9d20e22ffa747e3175c846341ad8ad
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097760"
---
# <a name="-baseaddress"></a><span data-ttu-id="4427a-102">-baseaddress</span><span class="sxs-lookup"><span data-stu-id="4427a-102">-baseaddress</span></span>

<span data-ttu-id="4427a-103">Gibt beim Erstellen einer DLL-Datei eine Standardbasisadresse an</span><span class="sxs-lookup"><span data-stu-id="4427a-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4427a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4427a-104">Syntax</span></span>  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="4427a-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="4427a-105">Arguments</span></span>  
  
|<span data-ttu-id="4427a-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="4427a-106">Term</span></span>|<span data-ttu-id="4427a-107">Definition</span><span class="sxs-lookup"><span data-stu-id="4427a-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="4427a-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4427a-108">Required.</span></span> <span data-ttu-id="4427a-109">Die Basisadresse für die DLL.</span><span class="sxs-lookup"><span data-stu-id="4427a-109">The base address for the DLL.</span></span> <span data-ttu-id="4427a-110">Diese Adresse muss als Hexadezimalzahl angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4427a-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4427a-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4427a-111">Remarks</span></span>  

 <span data-ttu-id="4427a-112">Die Standardbasisadresse für eine DLL-Datei wird durch das .NET Framework festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4427a-112">The default base address for a DLL is set by the .NET Framework.</span></span>  
  
 <span data-ttu-id="4427a-113">Denken Sie daran, dass das niederwertige Wort in dieser Adresse gerundet wird.</span><span class="sxs-lookup"><span data-stu-id="4427a-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="4427a-114">Wenn Sie zum Beispiel 0x11110001 angeben, wird dieser Wert auf 0x11110000 gerundet.</span><span class="sxs-lookup"><span data-stu-id="4427a-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="4427a-115">Verwenden Sie die `–R`-Option des Strong Name-Tool (Sn.exe), um den Signaturvorgang für die DLL-Datei abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4427a-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="4427a-116">Diese Option wird ignoriert, wenn das Ziel keine DLL-Datei ist.</span><span class="sxs-lookup"><span data-stu-id="4427a-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="4427a-117">So legen Sie -baseaddress in der Visual Studio-IDE fest</span><span class="sxs-lookup"><span data-stu-id="4427a-117">To set -baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="4427a-118">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="4427a-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="4427a-119">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="4427a-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="4427a-120">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="4427a-120">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="4427a-121">3.  Klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="4427a-121">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="4427a-122">4.  Ändern Sie den Wert im Feld **DLL-Basisadresse:** .</span><span class="sxs-lookup"><span data-stu-id="4427a-122">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="4427a-123">**Hinweis**:      Das Feld **DLL-Basisadresse:** ist schreibgeschützt, wenn das Ziel keine DLL-Datei ist.</span><span class="sxs-lookup"><span data-stu-id="4427a-123">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4427a-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4427a-124">See also</span></span>

- [<span data-ttu-id="4427a-125">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="4427a-125">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="4427a-126">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4427a-126">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="4427a-127">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="4427a-127">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- <span data-ttu-id="4427a-128">[Sn.exe (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="4427a-128">[Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
