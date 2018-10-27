---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: 1459484b858137836fcfdcd9db46d8e99a06e9c7
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185208"
---
# <a name="-delaysign"></a><span data-ttu-id="77da9-102">-delaysign</span><span class="sxs-lookup"><span data-stu-id="77da9-102">-delaysign</span></span>
<span data-ttu-id="77da9-103">Gibt an, ob die Assembly vollständig oder teilweise signiert wird.</span><span class="sxs-lookup"><span data-stu-id="77da9-103">Specifies whether the assembly will be fully or partially signed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77da9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="77da9-104">Syntax</span></span>  
  
```  
-delaysign[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="77da9-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="77da9-105">Arguments</span></span>  
 <span data-ttu-id="77da9-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="77da9-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="77da9-107">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="77da9-107">Optional.</span></span> <span data-ttu-id="77da9-108">Verwenden Sie `-delaysign-`, wenn die Assembly vollständig signiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="77da9-108">Use `-delaysign-` if you want a fully signed assembly.</span></span> <span data-ttu-id="77da9-109">Verwendung `-delaysign+` sollten Sie den öffentlichen Schlüssel in der Assembly und der reservierte Speicherplatz für den signierten Hash zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="77da9-109">Use `-delaysign+` if you want to place the public key in the assembly and reserve space for the signed hash.</span></span> <span data-ttu-id="77da9-110">Die Standardeinstellung ist `-delaysign-`.</span><span class="sxs-lookup"><span data-stu-id="77da9-110">The default is `-delaysign-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77da9-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="77da9-111">Remarks</span></span>  
 <span data-ttu-id="77da9-112">Die `-delaysign` Option hat keine Auswirkung, wenn Sie mit [- Keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) oder [- Keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="77da9-112">The `-delaysign` option has no effect unless used with [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) or [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span>  
  
 <span data-ttu-id="77da9-113">Wenn Sie eine vollständig signierte Assembly anfordern, wird vom Compiler der Hash der Datei mit dem Manifest (Assemblymetadaten) erstellt und mit dem privaten Schlüssel signiert.</span><span class="sxs-lookup"><span data-stu-id="77da9-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="77da9-114">Die sich ergebende digitale Signatur wird in der Datei mit dem Manifest gespeichert.</span><span class="sxs-lookup"><span data-stu-id="77da9-114">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="77da9-115">Wenn eine Assembly verzögert signiert wird, der Compiler nicht berechnet und speichern die Signatur aber reserviert Speicherplatz in der Datei, damit die Signatur später hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="77da9-115">When an assembly is delay signed, the compiler does not compute and store the signature but reserves space in the file so the signature can be added later.</span></span>  
  
 <span data-ttu-id="77da9-116">Z. B. durch Verwendung `-delaysign+`, ein Entwickler in einer Organisation verteilen ohne Vorzeichen Testversionen einer Assembly, die Tester mit dem globalen Assemblycache zu registrieren und verwenden können.</span><span class="sxs-lookup"><span data-stu-id="77da9-116">For example, by using `-delaysign+`, a developer in an organization can distribute unsigned test versions of an assembly that testers can register with the global assembly cache and use.</span></span> <span data-ttu-id="77da9-117">Wenn für die Assembly abgeschlossen ist, kann für private Schlüssel der Organisation verantwortliche Person die Assembly vollständig signiert.</span><span class="sxs-lookup"><span data-stu-id="77da9-117">When work on the assembly is completed, the person responsible for the organization's private key can fully sign the assembly.</span></span> <span data-ttu-id="77da9-118">Diese Trennung schützt die privaten Schlüssel der Organisation vor Offenlegung, gleichzeitig alle Entwickler arbeiten, auf die Assemblys.</span><span class="sxs-lookup"><span data-stu-id="77da9-118">This compartmentalization protects the organization's private key from disclosure, while allowing all developers to work on the assemblies.</span></span>  
  
 <span data-ttu-id="77da9-119">Finden Sie unter [erstellen und Assemblys mit starkem Namen](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) für Weitere Informationen zum Signieren einer Assemblys.</span><span class="sxs-lookup"><span data-stu-id="77da9-119">See [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="77da9-120">-Delaysign in der integrierten Entwicklungsumgebung von Visual Studio festlegen.</span><span class="sxs-lookup"><span data-stu-id="77da9-120">To set -delaysign in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="77da9-121">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="77da9-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="77da9-122">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="77da9-122">On the **Project** menu, click **Properties**.</span></span>   
  
2.  <span data-ttu-id="77da9-123">Klicken Sie auf die Registerkarte **Signierung**.</span><span class="sxs-lookup"><span data-stu-id="77da9-123">Click the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="77da9-124">Legen Sie den Wert der **nur verzögerte Signierung** Feld.</span><span class="sxs-lookup"><span data-stu-id="77da9-124">Set the value in the **Delay sign only** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77da9-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77da9-125">See Also</span></span>  
 [<span data-ttu-id="77da9-126">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="77da9-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="77da9-127">-keyfile</span><span class="sxs-lookup"><span data-stu-id="77da9-127">-keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [<span data-ttu-id="77da9-128">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="77da9-128">-keycontainer</span></span>](../../../visual-basic/reference/command-line-compiler/keycontainer.md)  
 [<span data-ttu-id="77da9-129">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="77da9-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
