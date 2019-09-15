---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: 6d3c89d598714446e04ba40155951f771d474866
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2019
ms.locfileid: "70971989"
---
# <a name="-delaysign"></a><span data-ttu-id="f9389-102">-delaysign</span><span class="sxs-lookup"><span data-stu-id="f9389-102">-delaysign</span></span>
<span data-ttu-id="f9389-103">Gibt an, ob die Assembly vollständig oder teilweise signiert wird.</span><span class="sxs-lookup"><span data-stu-id="f9389-103">Specifies whether the assembly will be fully or partially signed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9389-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9389-104">Syntax</span></span>  
  
```  
-delaysign[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="f9389-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="f9389-105">Arguments</span></span>  
 <span data-ttu-id="f9389-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="f9389-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="f9389-107">Optional.</span><span class="sxs-lookup"><span data-stu-id="f9389-107">Optional.</span></span> <span data-ttu-id="f9389-108">Verwenden Sie `-delaysign-`, wenn die Assembly vollständig signiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f9389-108">Use `-delaysign-` if you want a fully signed assembly.</span></span> <span data-ttu-id="f9389-109">Verwenden `-delaysign+` Sie, wenn Sie den öffentlichen Schlüssel in der Assembly platzieren und Speicherplatz für den signierten Hash reservieren möchten.</span><span class="sxs-lookup"><span data-stu-id="f9389-109">Use `-delaysign+` if you want to place the public key in the assembly and reserve space for the signed hash.</span></span> <span data-ttu-id="f9389-110">Die Standardeinstellung ist `-delaysign-`.</span><span class="sxs-lookup"><span data-stu-id="f9389-110">The default is `-delaysign-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9389-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f9389-111">Remarks</span></span>  
 <span data-ttu-id="f9389-112">Die `-delaysign` -Option hat keine Auswirkung, wenn Sie nicht mit [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) oder [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f9389-112">The `-delaysign` option has no effect unless used with [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) or [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span>  
  
 <span data-ttu-id="f9389-113">Wenn Sie eine vollständig signierte Assembly anfordern, wird vom Compiler der Hash der Datei mit dem Manifest (Assemblymetadaten) erstellt und mit dem privaten Schlüssel signiert.</span><span class="sxs-lookup"><span data-stu-id="f9389-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="f9389-114">Die sich ergebende digitale Signatur wird in der Datei mit dem Manifest gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f9389-114">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="f9389-115">Wenn eine Assembly mit Verzögerung signiert wird, wird die Signatur vom Compiler nicht berechnet und gespeichert, sondern es wird ein Speicherplatz in der Datei reserviert, damit die Signatur später hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f9389-115">When an assembly is delay signed, the compiler does not compute and store the signature but reserves space in the file so the signature can be added later.</span></span>  
  
 <span data-ttu-id="f9389-116">Mithilfe `-delaysign+`von kann ein Entwickler in einer Organisation z. b. nicht signierte Testversionen einer Assembly verteilen, die Tester mit dem globalen Assemblycache registrieren und verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f9389-116">For example, by using `-delaysign+`, a developer in an organization can distribute unsigned test versions of an assembly that testers can register with the global assembly cache and use.</span></span> <span data-ttu-id="f9389-117">Wenn die Arbeit an der Assembly abgeschlossen ist, kann die Person, die für den privaten Schlüssel der Organisation zuständig ist, die Assembly vollständig signieren.</span><span class="sxs-lookup"><span data-stu-id="f9389-117">When work on the assembly is completed, the person responsible for the organization's private key can fully sign the assembly.</span></span> <span data-ttu-id="f9389-118">Diese gliementalisierung schützt den privaten Schlüssel der Organisation vor der Offenlegung und ermöglicht allen Entwicklern, an den Assemblys zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="f9389-118">This compartmentalization protects the organization's private key from disclosure, while allowing all developers to work on the assemblies.</span></span>  
  
 <span data-ttu-id="f9389-119">Weitere Informationen zum Signieren einer Assembly finden [Sie unter Erstellen und verwenden](../../../standard/assembly/create-use-strong-named.md) von Assemblys mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="f9389-119">See [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) for more information on signing an assembly.</span></span>  
  
### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="f9389-120">So legen Sie-Delta Sign in der integrierten Entwicklungsumgebung von Visual Studio fest</span><span class="sxs-lookup"><span data-stu-id="f9389-120">To set -delaysign in the Visual Studio integrated development environment</span></span>  
  
1. <span data-ttu-id="f9389-121">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="f9389-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="f9389-122">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="f9389-122">On the **Project** menu, click **Properties**.</span></span>   
  
2. <span data-ttu-id="f9389-123">Klicken Sie auf die Registerkarte **Signierung**.</span><span class="sxs-lookup"><span data-stu-id="f9389-123">Click the **Signing** tab.</span></span>  
  
3. <span data-ttu-id="f9389-124">Legen Sie den Wert im Feld **Verzögertes Signieren** fest.</span><span class="sxs-lookup"><span data-stu-id="f9389-124">Set the value in the **Delay sign only** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9389-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9389-125">See also</span></span>

- [<span data-ttu-id="f9389-126">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="f9389-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="f9389-127">-keyfile</span><span class="sxs-lookup"><span data-stu-id="f9389-127">-keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [<span data-ttu-id="f9389-128">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="f9389-128">-keycontainer</span></span>](../../../visual-basic/reference/command-line-compiler/keycontainer.md)
- [<span data-ttu-id="f9389-129">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="f9389-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
