---
title: / delaysign | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- /delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
caps.latest.revision: 19
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
ms.openlocfilehash: bcc819e08ca7731d91dc77dc831060bcf00a4425
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="delaysign"></a><span data-ttu-id="ad327-102">/delaysign</span><span class="sxs-lookup"><span data-stu-id="ad327-102">/delaysign</span></span>
<span data-ttu-id="ad327-103">Gibt an, ob die Assembly vollständig oder teilweise signiert wird.</span><span class="sxs-lookup"><span data-stu-id="ad327-103">Specifies whether the assembly will be fully or partially signed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad327-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ad327-104">Syntax</span></span>  
  
```  
/delaysign[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="ad327-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="ad327-105">Arguments</span></span>  
 <span data-ttu-id="ad327-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="ad327-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="ad327-107">Optional.</span><span class="sxs-lookup"><span data-stu-id="ad327-107">Optional.</span></span> <span data-ttu-id="ad327-108">Verwenden Sie `/delaysign-`, wenn die Assembly vollständig signiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ad327-108">Use `/delaysign-` if you want a fully signed assembly.</span></span> <span data-ttu-id="ad327-109">Verwendung `/delaysign+` Wenn Sie den öffentlichen Schlüssel in der Assembly, und reservieren Speicherplatz für den signierten Hash platzieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ad327-109">Use `/delaysign+` if you want to place the public key in the assembly and reserve space for the signed hash.</span></span> <span data-ttu-id="ad327-110">Die Standardeinstellung ist `/delaysign-`.</span><span class="sxs-lookup"><span data-stu-id="ad327-110">The default is `/delaysign-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad327-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ad327-111">Remarks</span></span>  
 <span data-ttu-id="ad327-112">Die `/delaysign` Option hat keine Auswirkung, wenn Sie mit [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) oder [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="ad327-112">The `/delaysign` option has no effect unless used with [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) or [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span>  
  
 <span data-ttu-id="ad327-113">Wenn Sie eine vollständig signierte Assembly anfordern, wandelt der Compiler die Datei, die das Manifest (Assemblymetadaten) enthält und signiert dieses Hash mit dem privaten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="ad327-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="ad327-114">Die sich ergebende digitale Signatur wird in der Datei mit dem Manifest gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ad327-114">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="ad327-115">Wenn eine Assembly verzögert signiert wird, wird der Compiler nicht berechnet und die Signatur sondern reserviert Speicherplatz in der Datei speichern, damit die Signatur später hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ad327-115">When an assembly is delay signed, the compiler does not compute and store the signature but reserves space in the file so the signature can be added later.</span></span>  
  
 <span data-ttu-id="ad327-116">Zum Beispiel mithilfe von `/delaysign+`, ein Entwickler in einer Organisation kann verteilen, nicht signierte Testversionen einer Assembly, die Tester für den globalen Assemblycache registrieren und verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ad327-116">For example, by using `/delaysign+`, a developer in an organization can distribute unsigned test versions of an assembly that testers can register with the global assembly cache and use.</span></span> <span data-ttu-id="ad327-117">Bei der Arbeit an der Assembly abgeschlossen ist, kann die für den privaten Schlüssel der Organisation verantwortliche Person die Assembly vollständig signiert.</span><span class="sxs-lookup"><span data-stu-id="ad327-117">When work on the assembly is completed, the person responsible for the organization's private key can fully sign the assembly.</span></span> <span data-ttu-id="ad327-118">Diese Trennung verhindert Offenlegung, wobei alle Entwickler auf die Assemblys privaten Schlüssel der Organisation.</span><span class="sxs-lookup"><span data-stu-id="ad327-118">This compartmentalization protects the organization's private key from disclosure, while allowing all developers to work on the assemblies.</span></span>  
  
 <span data-ttu-id="ad327-119">Finden Sie unter [erstellen und Assemblys mit starkem Namen](https://msdn.microsoft.com/library/xwb8f617) für Weitere Informationen zum Signieren einer Assemblys.</span><span class="sxs-lookup"><span data-stu-id="ad327-119">See [Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617) for more information on signing an assembly.</span></span>  
  
### <a name="to-set-delaysign-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="ad327-120">Zum Festlegen von/delaysign in Visual Studio integrierte Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="ad327-120">To set /delaysign in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="ad327-121">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="ad327-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="ad327-122">Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ad327-122">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="ad327-123">Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="ad327-123">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="ad327-124">Klicken Sie auf die **Signierung** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="ad327-124">Click the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="ad327-125">Legen Sie den Wert der **nur verzögerte Signierung** Feld.</span><span class="sxs-lookup"><span data-stu-id="ad327-125">Set the value in the **Delay sign only** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad327-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad327-126">See Also</span></span>  
 <span data-ttu-id="ad327-127">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="ad327-127">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="ad327-128"> [/ keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) </span><span class="sxs-lookup"><span data-stu-id="ad327-128"> [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) </span></span>  
<span data-ttu-id="ad327-129"> [/ keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) </span><span class="sxs-lookup"><span data-stu-id="ad327-129"> [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) </span></span>  
<span data-ttu-id="ad327-130"> [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="ad327-130"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
