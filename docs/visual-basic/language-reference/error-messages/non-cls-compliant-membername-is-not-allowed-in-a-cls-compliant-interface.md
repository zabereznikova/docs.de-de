---
title: "Nicht CLS-kompatible &lt;Membername&gt; ist in einer CLS-kompatiblen Schnittstelle unzulässig | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40033
- vbc40033
dev_langs:
- VB
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
caps.latest.revision: 9
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
ms.openlocfilehash: 27e83344c68d73c992d2395ab5d1bfcdb67520b0
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="non-cls-compliant-ltmembernamegt-is-not-allowed-in-a-cls-compliant-interface"></a><span data-ttu-id="d5ff5-102">Nicht CLS-kompatible &lt;Membername&gt; ist in einer CLS-kompatiblen Schnittstelle nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="d5ff5-102">Non-CLS-compliant &lt;membername&gt; is not allowed in a CLS-compliant interface</span></span>
<span data-ttu-id="d5ff5-103">Eine Eigenschaft, eine Prozedur oder ein Ereignis in einer Schnittstelle ist als markiert `<CLSCompliant(True)>` Wenn die Schnittstelle selbst markiert ist, als `<CLSCompliant(False)>` oder gar nicht markiert ist.</span><span class="sxs-lookup"><span data-stu-id="d5ff5-103">A property, procedure, or event in an interface is marked as `<CLSCompliant(True)>` when the interface itself is marked as `<CLSCompliant(False)>` or is not marked.</span></span>  
  
 <span data-ttu-id="d5ff5-104">Für eine Schnittstelle, kompatibel mit der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](https://msdn.microsoft.com/library/12a7a7h3) (CLS), alle seine Member müssen kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="d5ff5-104">For an interface to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), all its members must be compliant.</span></span>  
  
 <span data-ttu-id="d5ff5-105">Beim Anwenden der <xref:System.CLSCompliantAttribute>auf ein Programmierelement, legen Sie des Attributs `isCompliant` Parameter entweder `True` oder `False` an Kompatibilität oder Nichtkompatibilität.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="d5ff5-105">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="d5ff5-106">Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="d5ff5-106">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="d5ff5-107">Wenn Sie nicht anwenden der <xref:System.CLSCompliantAttribute>auf ein Element gilt nicht kompatibel ist.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="d5ff5-107">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="d5ff5-108">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="d5ff5-108">By default, this message is a warning.</span></span> <span data-ttu-id="d5ff5-109">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="d5ff5-109">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="d5ff5-110">**Fehler-ID:** BC40033</span><span class="sxs-lookup"><span data-stu-id="d5ff5-110">**Error ID:** BC40033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d5ff5-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="d5ff5-111">To correct this error</span></span>  
  
-   <span data-ttu-id="d5ff5-112">Wenn Sie CLS-Kompatibilität erfordert und haben die Kontrolle über den Quellcode für die Schnittstelle, markieren Sie die Schnittstelle als `<CLSCompliant(True)>` Wenn alle seine Member kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="d5ff5-112">If you require CLS compliance and have control over the interface source code, mark the interface as `<CLSCompliant(True)>` if all its members are compliant.</span></span>  
  
-   <span data-ttu-id="d5ff5-113">Definieren Sie Wenn Sie CLS-Kompatibilität erfordert und haben keine Kontrolle über den Quellcode für die Schnittstelle oder nicht qualifiziert wird, kompatibel ist, dieser Member innerhalb einer anderen Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d5ff5-113">If you require CLS compliance and do not have control over the interface source code, or if it does not qualify to be compliant, define this member within a different interface.</span></span>  
  
-   <span data-ttu-id="d5ff5-114">Wenn Sie dieses Element in der aktuellen Schnittstelle verbleiben müssen, entfernen Sie die <xref:System.CLSCompliantAttribute>aus der Definition oder markieren Sie ihn als `<CLSCompliant(False)>`.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="d5ff5-114">If you require that this member remain within its current interface, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5ff5-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5ff5-115">See Also</span></span>  
 <span data-ttu-id="d5ff5-116">[Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md) </span><span class="sxs-lookup"><span data-stu-id="d5ff5-116">[Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) </span></span>  
<span data-ttu-id="d5ff5-117"> [\<PAVE über > CLS-kompatiblen Code schreiben](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span><span class="sxs-lookup"><span data-stu-id="d5ff5-117"> [\<PAVE OVER> Writing CLS-Compliant Code](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span></span>
