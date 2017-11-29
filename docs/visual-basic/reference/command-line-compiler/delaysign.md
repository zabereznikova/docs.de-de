---
title: /delaysign
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- /delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6c42e351808281d90eafdb6e61a3f1736ef15c9d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="delaysign"></a><span data-ttu-id="1a7aa-102">/delaysign</span><span class="sxs-lookup"><span data-stu-id="1a7aa-102">/delaysign</span></span>
<span data-ttu-id="1a7aa-103">Gibt an, ob die Assembly vollständig oder teilweise signiert wird.</span><span class="sxs-lookup"><span data-stu-id="1a7aa-103">Specifies whether the assembly will be fully or partially signed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a7aa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1a7aa-104">Syntax</span></span>  
  
```  
/delaysign[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="1a7aa-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="1a7aa-105">Arguments</span></span>  
 <span data-ttu-id="1a7aa-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="1a7aa-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="1a7aa-107">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="1a7aa-107">Optional.</span></span> <span data-ttu-id="1a7aa-108">Verwenden Sie `/delaysign-`, wenn die Assembly vollständig signiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1a7aa-108">Use `/delaysign-` if you want a fully signed assembly.</span></span> <span data-ttu-id="1a7aa-109">Verwendung `/delaysign+` Wenn Sie den öffentlichen Schlüssel in der Assembly und reservierte Speicherplatz für den signierten Hash platzieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1a7aa-109">Use `/delaysign+` if you want to place the public key in the assembly and reserve space for the signed hash.</span></span> <span data-ttu-id="1a7aa-110">Die Standardeinstellung ist `/delaysign-`.</span><span class="sxs-lookup"><span data-stu-id="1a7aa-110">The default is `/delaysign-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a7aa-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1a7aa-111">Remarks</span></span>  
 <span data-ttu-id="1a7aa-112">Die `/delaysign` Option hat keine Auswirkung, wenn nicht mit [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) oder [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="1a7aa-112">The `/delaysign` option has no effect unless used with [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) or [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span>  
  
 <span data-ttu-id="1a7aa-113">Wenn Sie eine vollständig signierte Assembly anfordern, wird vom Compiler der Hash der Datei mit dem Manifest (Assemblymetadaten) erstellt und mit dem privaten Schlüssel signiert.</span><span class="sxs-lookup"><span data-stu-id="1a7aa-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="1a7aa-114">Die sich ergebende digitale Signatur wird in der Datei mit dem Manifest gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1a7aa-114">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="1a7aa-115">Wenn eine Assembly verzögert signiert wird, wird der Compiler nicht berechnen und speichern die Signatur, sondern reserviert Speicherplatz in der Datei, damit die Signatur später hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="1a7aa-115">When an assembly is delay signed, the compiler does not compute and store the signature but reserves space in the file so the signature can be added later.</span></span>  
  
 <span data-ttu-id="1a7aa-116">Z. B. durch Verwendung `/delaysign+`, ein Entwickler in einer Organisation kann verteilen, ohne Vorzeichen Testversionen einer Assembly, die Tester mit dem globalen Assemblycache zu registrieren und verwenden können.</span><span class="sxs-lookup"><span data-stu-id="1a7aa-116">For example, by using `/delaysign+`, a developer in an organization can distribute unsigned test versions of an assembly that testers can register with the global assembly cache and use.</span></span> <span data-ttu-id="1a7aa-117">Bei der Arbeit für die Assembly abgeschlossen ist, kann für private Schlüssel der Organisation verantwortliche Person die Assembly vollständig signieren.</span><span class="sxs-lookup"><span data-stu-id="1a7aa-117">When work on the assembly is completed, the person responsible for the organization's private key can fully sign the assembly.</span></span> <span data-ttu-id="1a7aa-118">Diese Aufgliederung schützt private Schlüssel der Organisation vor Offenlegung, während alle es Entwicklern ermöglicht, auf die Assemblys zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="1a7aa-118">This compartmentalization protects the organization's private key from disclosure, while allowing all developers to work on the assemblies.</span></span>  
  
 <span data-ttu-id="1a7aa-119">Finden Sie unter [erstellen und Verwenden von Assemblys](https://msdn.microsoft.com/library/xwb8f617) für Weitere Informationen zum Signieren einer Assemblys.</span><span class="sxs-lookup"><span data-stu-id="1a7aa-119">See [Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617) for more information on signing an assembly.</span></span>  
  
### <a name="to-set-delaysign-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="1a7aa-120">Zum Festlegen von/delaysign / in Visual Studio integrierte Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="1a7aa-120">To set /delaysign in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="1a7aa-121">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="1a7aa-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="1a7aa-122">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="1a7aa-122">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="1a7aa-123">Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="1a7aa-123">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="1a7aa-124">Klicken Sie auf die Registerkarte **Signierung**.</span><span class="sxs-lookup"><span data-stu-id="1a7aa-124">Click the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="1a7aa-125">Legen Sie den Wert der **nur verzögerte Signierung** Feld.</span><span class="sxs-lookup"><span data-stu-id="1a7aa-125">Set the value in the **Delay sign only** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a7aa-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a7aa-126">See Also</span></span>  
 [<span data-ttu-id="1a7aa-127">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="1a7aa-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="1a7aa-128">/keyfile</span><span class="sxs-lookup"><span data-stu-id="1a7aa-128">/keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [<span data-ttu-id="1a7aa-129">/keycontainer</span><span class="sxs-lookup"><span data-stu-id="1a7aa-129">/keycontainer</span></span>](../../../visual-basic/reference/command-line-compiler/keycontainer.md)  
 [<span data-ttu-id="1a7aa-130">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="1a7aa-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
