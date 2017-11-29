---
title: Ein Verweis erstellt wurde, die eingebettete Interopassembly &#39; &lt;assembly1&gt;&#39; aufgrund eines indirekten Verweises auf diese Assembly aus Assembly &#39;&lt; Assembly2&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40059
- bc40059
helpviewer_keywords:
- VBC40059
- BC40059
ms.assetid: 520e39cb-8ab6-46f5-aa00-08afd51b4b7c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bc2fbb044fc839aa24abf3dc1ea864457efb0653
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="a-reference-was-created-to-embedded-interop-assembly-39ltassembly1gt39-because-of-an-indirect-reference-to-that-assembly-from-assembly-39ltassembly2gt39"></a><span data-ttu-id="26659-102">Ein Verweis erstellt wurde, die eingebettete Interopassembly &#39; &lt;assembly1&gt;&#39; aufgrund eines indirekten Verweises auf diese Assembly aus Assembly &#39;&lt; Assembly2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="26659-102">A reference was created to embedded interop assembly &#39;&lt;assembly1&gt;&#39; because of an indirect reference to that assembly from assembly &#39;&lt;assembly2&gt;&#39;</span></span>
<span data-ttu-id="26659-103">Es wurde ein Verweis auf die eingebettete Interopassembly „\<assembly1>“ aufgrund eines indirekten Verweises auf diese Assembly aus Assembly „\<assembly2>“ erstellt.</span><span class="sxs-lookup"><span data-stu-id="26659-103">A reference was created to embedded interop assembly '\<assembly1>' because of an indirect reference to that assembly from assembly '\<assembly2>'.</span></span> <span data-ttu-id="26659-104">Ändern Sie ggf. für beide Assembly die Eigenschaft 'Interoptypen einbetten'.</span><span class="sxs-lookup"><span data-stu-id="26659-104">Consider changing the 'Embed Interop Types' property on either assembly.</span></span>  
  
 <span data-ttu-id="26659-105">Sie haben einen Verweis auf eine Assembly (assembly1) hinzugefügt, deren `Embed Interop Types`-Eigenschaft auf `True` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="26659-105">You have added a reference to an assembly (assembly1) that has the `Embed Interop Types` property set to `True`.</span></span> <span data-ttu-id="26659-106">Dadurch wird der Compiler angewiesen, Interoptypinformationen von dieser Assembly einzubetten.</span><span class="sxs-lookup"><span data-stu-id="26659-106">This instructs the compiler to embed interop type information from that assembly.</span></span> <span data-ttu-id="26659-107">Der Compiler kann jedoch keine Interoptypinformationen von dieser Assembly einbetten, da eine andere Assembly, auf die verwiesen wird (assembly2), ebenfalls auf diese Assembly verweist (assembly1) und die `Embed Interop Types`-Eigenschaft auf `False` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="26659-107">However, the compiler cannot embed interop type information from that assembly because another assembly that you have referenced (assembly2) also references that assembly (assembly1) and has the `Embed Interop Types` property set to `False`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26659-108">Das Festlegen der `Embed Interop Types`-Eigenschaft in einem Assemblyverweis auf `True` entspricht dem Verweisen auf die Assembly mit der `/link`-Option für den Befehlszeilencompiler.</span><span class="sxs-lookup"><span data-stu-id="26659-108">Setting the `Embed Interop Types` property on an assembly reference to `True` is equivalent to referencing the assembly by using the `/link` option for the command-line compiler.</span></span>  
  
 <span data-ttu-id="26659-109">**Fehler-ID:** BC40059</span><span class="sxs-lookup"><span data-stu-id="26659-109">**Error ID:** BC40059</span></span>  
  
### <a name="to-address-this-warning"></a><span data-ttu-id="26659-110">So reagieren Sie auf diese Warnung</span><span class="sxs-lookup"><span data-stu-id="26659-110">To address this warning</span></span>  
  
-   <span data-ttu-id="26659-111">Um Interoptypinformationen für beide Assemblys einzubetten, legen Sie die `Embed Interop Types`-Eigenschaft in allen Verweisen auf assembly1 auf `True` fest.</span><span class="sxs-lookup"><span data-stu-id="26659-111">To embed interop type information for both assemblies, set the `Embed Interop Types` property on all references to assembly1 to `True`.</span></span>  
  
-   <span data-ttu-id="26659-112">Um die Warnung zu entfernen, können Sie die `Embed Interop Types`-Eigenschaft von assembly1 auf `False` festlegen.</span><span class="sxs-lookup"><span data-stu-id="26659-112">To remove the warning, you can set the `Embed Interop Types` property of assembly1 to `False`.</span></span> <span data-ttu-id="26659-113">In diesem Fall werden Interoptypinformationen von eine primäre Interopassembly (PIA) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="26659-113">In this case, interop type information is provided by a primary interop assembly (PIA).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26659-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26659-114">See Also</span></span>  
 [<span data-ttu-id="26659-115">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26659-115">/link (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/link.md)  
 [<span data-ttu-id="26659-116">Programming with Primary Interop Assemblies (Programmieren mit primären Interop-Assemblys)</span><span class="sxs-lookup"><span data-stu-id="26659-116">Programming with Primary Interop Assemblies</span></span>](http://msdn.microsoft.com/en-us/306fa1d6-0703-4004-9e93-d0a57f1be81e)
