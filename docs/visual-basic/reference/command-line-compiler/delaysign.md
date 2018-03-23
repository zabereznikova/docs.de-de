---
title: -delaysign
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d659e97f3b3a360456a1fcdaa9756934bb096334
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="-delaysign"></a><span data-ttu-id="0a8e6-102">-delaysign</span><span class="sxs-lookup"><span data-stu-id="0a8e6-102">-delaysign</span></span>
<span data-ttu-id="0a8e6-103">Gibt an, ob die Assembly vollständig oder teilweise signiert wird.</span><span class="sxs-lookup"><span data-stu-id="0a8e6-103">Specifies whether the assembly will be fully or partially signed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a8e6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a8e6-104">Syntax</span></span>  
  
```  
-delaysign[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0a8e6-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="0a8e6-105">Arguments</span></span>  
 <span data-ttu-id="0a8e6-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="0a8e6-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="0a8e6-107">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0a8e6-107">Optional.</span></span> <span data-ttu-id="0a8e6-108">Verwenden Sie `-delaysign-`, wenn die Assembly vollständig signiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="0a8e6-108">Use `-delaysign-` if you want a fully signed assembly.</span></span> <span data-ttu-id="0a8e6-109">Verwendung `-delaysign+` Wenn Sie den öffentlichen Schlüssel in der Assembly und reservierte Speicherplatz für den signierten Hash platzieren möchten.</span><span class="sxs-lookup"><span data-stu-id="0a8e6-109">Use `-delaysign+` if you want to place the public key in the assembly and reserve space for the signed hash.</span></span> <span data-ttu-id="0a8e6-110">Die Standardeinstellung ist `-delaysign-`.</span><span class="sxs-lookup"><span data-stu-id="0a8e6-110">The default is `-delaysign-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a8e6-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0a8e6-111">Remarks</span></span>  
 <span data-ttu-id="0a8e6-112">Die `-delaysign` Option hat keine Auswirkung, wenn nicht mit [- Keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) oder [- Keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="0a8e6-112">The `-delaysign` option has no effect unless used with [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) or [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span>  
  
 <span data-ttu-id="0a8e6-113">Wenn Sie eine vollständig signierte Assembly anfordern, wird vom Compiler der Hash der Datei mit dem Manifest (Assemblymetadaten) erstellt und mit dem privaten Schlüssel signiert.</span><span class="sxs-lookup"><span data-stu-id="0a8e6-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="0a8e6-114">Die sich ergebende digitale Signatur wird in der Datei mit dem Manifest gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0a8e6-114">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="0a8e6-115">Wenn eine Assembly verzögert signiert wird, wird der Compiler nicht berechnen und speichern die Signatur, sondern reserviert Speicherplatz in der Datei, damit die Signatur später hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0a8e6-115">When an assembly is delay signed, the compiler does not compute and store the signature but reserves space in the file so the signature can be added later.</span></span>  
  
 <span data-ttu-id="0a8e6-116">Z. B. durch Verwendung `-delaysign+`, ein Entwickler in einer Organisation kann verteilen, ohne Vorzeichen Testversionen einer Assembly, die Tester mit dem globalen Assemblycache zu registrieren und verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0a8e6-116">For example, by using `-delaysign+`, a developer in an organization can distribute unsigned test versions of an assembly that testers can register with the global assembly cache and use.</span></span> <span data-ttu-id="0a8e6-117">Bei der Arbeit für die Assembly abgeschlossen ist, kann für private Schlüssel der Organisation verantwortliche Person die Assembly vollständig signieren.</span><span class="sxs-lookup"><span data-stu-id="0a8e6-117">When work on the assembly is completed, the person responsible for the organization's private key can fully sign the assembly.</span></span> <span data-ttu-id="0a8e6-118">Diese Aufgliederung schützt private Schlüssel der Organisation vor Offenlegung, während alle es Entwicklern ermöglicht, auf die Assemblys zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="0a8e6-118">This compartmentalization protects the organization's private key from disclosure, while allowing all developers to work on the assemblies.</span></span>  
  
 <span data-ttu-id="0a8e6-119">Finden Sie unter [erstellen und Verwenden von Assemblys](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) für Weitere Informationen zum Signieren einer Assemblys.</span><span class="sxs-lookup"><span data-stu-id="0a8e6-119">See [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="0a8e6-120">-Delaysign in der integrierten Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="0a8e6-120">To set -delaysign in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="0a8e6-121">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="0a8e6-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="0a8e6-122">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="0a8e6-122">On the **Project** menu, click **Properties**.</span></span>   
  
2.  <span data-ttu-id="0a8e6-123">Klicken Sie auf die Registerkarte **Signierung**.</span><span class="sxs-lookup"><span data-stu-id="0a8e6-123">Click the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="0a8e6-124">Legen Sie den Wert der **nur verzögerte Signierung** Feld.</span><span class="sxs-lookup"><span data-stu-id="0a8e6-124">Set the value in the **Delay sign only** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a8e6-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a8e6-125">See Also</span></span>  
 [<span data-ttu-id="0a8e6-126">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="0a8e6-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="0a8e6-127">-keyfile</span><span class="sxs-lookup"><span data-stu-id="0a8e6-127">-keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [<span data-ttu-id="0a8e6-128">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="0a8e6-128">-keycontainer</span></span>](../../../visual-basic/reference/command-line-compiler/keycontainer.md)  
 [<span data-ttu-id="0a8e6-129">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="0a8e6-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
