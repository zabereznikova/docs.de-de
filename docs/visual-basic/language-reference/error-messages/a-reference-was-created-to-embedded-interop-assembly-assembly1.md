---
title: Ein Verweis auf eingebettete Interop-Assembly erstellt wurde &#39; &lt;assembly1&gt; &#39; aufgrund eines indirekten Verweises auf diese Assembly aus Assembly &#39; &lt;assembly2&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc40059
- bc40059
helpviewer_keywords:
- VBC40059
- BC40059
ms.assetid: 520e39cb-8ab6-46f5-aa00-08afd51b4b7c
ms.openlocfilehash: 43a441b6b99988ae1b47969dde9c4bc815820767
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588131"
---
# <a name="a-reference-was-created-to-embedded-interop-assembly-39ltassembly1gt39-because-of-an-indirect-reference-to-that-assembly-from-assembly-39ltassembly2gt39"></a><span data-ttu-id="30dab-102">Ein Verweis auf eingebettete Interop-Assembly erstellt wurde &#39; &lt;assembly1&gt; &#39; aufgrund eines indirekten Verweises auf diese Assembly aus Assembly &#39; &lt;assembly2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="30dab-102">A reference was created to embedded interop assembly &#39;&lt;assembly1&gt;&#39; because of an indirect reference to that assembly from assembly &#39;&lt;assembly2&gt;&#39;</span></span>
<span data-ttu-id="30dab-103">Es wurde ein Verweis auf die eingebettete Interopassembly „\<assembly1>“ aufgrund eines indirekten Verweises auf diese Assembly aus Assembly „\<assembly2>“ erstellt.</span><span class="sxs-lookup"><span data-stu-id="30dab-103">A reference was created to embedded interop assembly '\<assembly1>' because of an indirect reference to that assembly from assembly '\<assembly2>'.</span></span> <span data-ttu-id="30dab-104">Ändern Sie ggf. für beide Assembly die Eigenschaft 'Interoptypen einbetten'.</span><span class="sxs-lookup"><span data-stu-id="30dab-104">Consider changing the 'Embed Interop Types' property on either assembly.</span></span>  
  
 <span data-ttu-id="30dab-105">Sie haben einen Verweis auf eine Assembly (assembly1) hinzugefügt, deren `Embed Interop Types`-Eigenschaft auf `True` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="30dab-105">You have added a reference to an assembly (assembly1) that has the `Embed Interop Types` property set to `True`.</span></span> <span data-ttu-id="30dab-106">Dadurch wird der Compiler angewiesen, Interoptypinformationen von dieser Assembly einzubetten.</span><span class="sxs-lookup"><span data-stu-id="30dab-106">This instructs the compiler to embed interop type information from that assembly.</span></span> <span data-ttu-id="30dab-107">Der Compiler kann jedoch keine Interoptypinformationen von dieser Assembly einbetten, da eine andere Assembly, auf die verwiesen wird (assembly2), ebenfalls auf diese Assembly verweist (assembly1) und die `Embed Interop Types`-Eigenschaft auf `False` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="30dab-107">However, the compiler cannot embed interop type information from that assembly because another assembly that you have referenced (assembly2) also references that assembly (assembly1) and has the `Embed Interop Types` property set to `False`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30dab-108">Das Festlegen der `Embed Interop Types`-Eigenschaft in einem Assemblyverweis auf `True` entspricht dem Verweisen auf die Assembly mit der `/link`-Option für den Befehlszeilencompiler.</span><span class="sxs-lookup"><span data-stu-id="30dab-108">Setting the `Embed Interop Types` property on an assembly reference to `True` is equivalent to referencing the assembly by using the `/link` option for the command-line compiler.</span></span>  
  
 <span data-ttu-id="30dab-109">**Fehler-ID:** BC40059</span><span class="sxs-lookup"><span data-stu-id="30dab-109">**Error ID:** BC40059</span></span>  
  
### <a name="to-address-this-warning"></a><span data-ttu-id="30dab-110">So reagieren Sie auf diese Warnung</span><span class="sxs-lookup"><span data-stu-id="30dab-110">To address this warning</span></span>  
  
-   <span data-ttu-id="30dab-111">Um Interoptypinformationen für beide Assemblys einzubetten, legen Sie die `Embed Interop Types`-Eigenschaft in allen Verweisen auf assembly1 auf `True` fest.</span><span class="sxs-lookup"><span data-stu-id="30dab-111">To embed interop type information for both assemblies, set the `Embed Interop Types` property on all references to assembly1 to `True`.</span></span>  
  
-   <span data-ttu-id="30dab-112">Um die Warnung zu entfernen, können Sie die `Embed Interop Types`-Eigenschaft von assembly1 auf `False` festlegen.</span><span class="sxs-lookup"><span data-stu-id="30dab-112">To remove the warning, you can set the `Embed Interop Types` property of assembly1 to `False`.</span></span> <span data-ttu-id="30dab-113">In diesem Fall werden Interoptypinformationen von eine primäre Interopassembly (PIA) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="30dab-113">In this case, interop type information is provided by a primary interop assembly (PIA).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30dab-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30dab-114">See Also</span></span>  
 [<span data-ttu-id="30dab-115">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30dab-115">/link (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/link.md)  
 [<span data-ttu-id="30dab-116">Interoperabilität mit nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="30dab-116">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)
