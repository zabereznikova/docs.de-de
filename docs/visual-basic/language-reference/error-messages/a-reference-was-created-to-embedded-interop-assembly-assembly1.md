---
title: Es wurde ein Verweis auf die eingebettete Interopassembly '<assembly1>' aufgrund eines indirekten Verweises auf diese Assembly aus Assembly '<assembly2>' erstellt.
ms.date: 07/20/2015
f1_keywords:
- vbc40059
- bc40059
helpviewer_keywords:
- VBC40059
- BC40059
ms.assetid: 520e39cb-8ab6-46f5-aa00-08afd51b4b7c
ms.openlocfilehash: c0b4f56e3d1613486dd1198976557831ce657e1b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58837545"
---
# <a name="a-reference-was-created-to-embedded-interop-assembly-assembly1-because-of-an-indirect-reference-to-that-assembly-from-assembly-assembly2"></a><span data-ttu-id="cc826-102">Ein Verweis auf eingebettete Interop-Assembly erstellt wurde "\<assembly1 >' aufgrund eines indirekten Verweises auf diese Assembly aus Assembly '\<assembly2 >'</span><span class="sxs-lookup"><span data-stu-id="cc826-102">A reference was created to embedded interop assembly '\<assembly1>' because of an indirect reference to that assembly from assembly '\<assembly2>'</span></span>
<span data-ttu-id="cc826-103">Es wurde ein Verweis auf die eingebettete Interopassembly „\<assembly1>“ aufgrund eines indirekten Verweises auf diese Assembly aus Assembly „\<assembly2>“ erstellt.</span><span class="sxs-lookup"><span data-stu-id="cc826-103">A reference was created to embedded interop assembly '\<assembly1>' because of an indirect reference to that assembly from assembly '\<assembly2>'.</span></span> <span data-ttu-id="cc826-104">Ändern Sie ggf. für beide Assembly die Eigenschaft 'Interoptypen einbetten'.</span><span class="sxs-lookup"><span data-stu-id="cc826-104">Consider changing the 'Embed Interop Types' property on either assembly.</span></span>  
  
 <span data-ttu-id="cc826-105">Sie haben einen Verweis auf eine Assembly (assembly1) hinzugefügt, deren `Embed Interop Types`-Eigenschaft auf `True` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="cc826-105">You have added a reference to an assembly (assembly1) that has the `Embed Interop Types` property set to `True`.</span></span> <span data-ttu-id="cc826-106">Dadurch wird der Compiler angewiesen, Interoptypinformationen von dieser Assembly einzubetten.</span><span class="sxs-lookup"><span data-stu-id="cc826-106">This instructs the compiler to embed interop type information from that assembly.</span></span> <span data-ttu-id="cc826-107">Der Compiler kann jedoch keine Interoptypinformationen von dieser Assembly einbetten, da eine andere Assembly, auf die verwiesen wird (assembly2), ebenfalls auf diese Assembly verweist (assembly1) und die `Embed Interop Types`-Eigenschaft auf `False` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="cc826-107">However, the compiler cannot embed interop type information from that assembly because another assembly that you have referenced (assembly2) also references that assembly (assembly1) and has the `Embed Interop Types` property set to `False`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc826-108">Das Festlegen der `Embed Interop Types`-Eigenschaft in einem Assemblyverweis auf `True` entspricht dem Verweisen auf die Assembly mit der `/link`-Option für den Befehlszeilencompiler.</span><span class="sxs-lookup"><span data-stu-id="cc826-108">Setting the `Embed Interop Types` property on an assembly reference to `True` is equivalent to referencing the assembly by using the `/link` option for the command-line compiler.</span></span>  
  
 <span data-ttu-id="cc826-109">**Fehler-ID:** BC40059</span><span class="sxs-lookup"><span data-stu-id="cc826-109">**Error ID:** BC40059</span></span>  
  
### <a name="to-address-this-warning"></a><span data-ttu-id="cc826-110">So reagieren Sie auf diese Warnung</span><span class="sxs-lookup"><span data-stu-id="cc826-110">To address this warning</span></span>  
  
-   <span data-ttu-id="cc826-111">Um Interoptypinformationen für beide Assemblys einzubetten, legen Sie die `Embed Interop Types`-Eigenschaft in allen Verweisen auf assembly1 auf `True` fest.</span><span class="sxs-lookup"><span data-stu-id="cc826-111">To embed interop type information for both assemblies, set the `Embed Interop Types` property on all references to assembly1 to `True`.</span></span>  
  
-   <span data-ttu-id="cc826-112">Um die Warnung zu entfernen, können Sie die `Embed Interop Types`-Eigenschaft von assembly1 auf `False` festlegen.</span><span class="sxs-lookup"><span data-stu-id="cc826-112">To remove the warning, you can set the `Embed Interop Types` property of assembly1 to `False`.</span></span> <span data-ttu-id="cc826-113">In diesem Fall werden Interoptypinformationen von eine primäre Interopassembly (PIA) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="cc826-113">In this case, interop type information is provided by a primary interop assembly (PIA).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc826-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc826-114">See also</span></span>

- [<span data-ttu-id="cc826-115">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc826-115">/link (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/link.md)
- [<span data-ttu-id="cc826-116">Interoperabilität mit nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="cc826-116">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)
