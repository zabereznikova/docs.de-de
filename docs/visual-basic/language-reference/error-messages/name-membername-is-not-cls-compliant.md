---
title: Namen &lt;Membername&gt; ist nicht CLS-kompatibel. | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40031
- vbc40031
dev_langs:
- VB
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
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
ms.openlocfilehash: cbe0a8db6d801a0d083a6828af75342f15f0178d
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="name-ltmembernamegt-is-not-cls-compliant"></a><span data-ttu-id="f9173-102">Namen &lt;Membername&gt; ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="f9173-102">Name &lt;membername&gt; is not CLS-compliant</span></span>
<span data-ttu-id="f9173-103">Eine Assembly ist als markiert `<CLSCompliant(True)>` macht ein Element mit einem Namen, die mit einem Unterstrich beginnt jedoch (`_`).</span><span class="sxs-lookup"><span data-stu-id="f9173-103">An assembly is marked as `<CLSCompliant(True)>` but exposes a member with a name that begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="f9173-104">Ein Programmierelement kann ein oder mehrere Unterstriche enthalten, doch zum kompatibel sein, mit der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](https://msdn.microsoft.com/library/12a7a7h3) (CLS), es muss nicht mit einem Unterstrich beginnen.</span><span class="sxs-lookup"><span data-stu-id="f9173-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="f9173-105">Finden Sie unter [deklarierten Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="f9173-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="f9173-106">Beim Anwenden der <xref:System.CLSCompliantAttribute>auf ein Programmierelement legen Sie des Attributs `isCompliant` Parameter entweder `True` oder `False` an Kompatibilität oder Nichtkompatibilität.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="f9173-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="f9173-107">Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="f9173-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="f9173-108">Wenn Sie nicht anwenden der <xref:System.CLSCompliantAttribute>auf ein Element gilt nicht kompatibel ist.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="f9173-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="f9173-109">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="f9173-109">By default, this message is a warning.</span></span> <span data-ttu-id="f9173-110">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="f9173-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="f9173-111">**Fehler-ID:** BC40031</span><span class="sxs-lookup"><span data-stu-id="f9173-111">**Error ID:** BC40031</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f9173-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="f9173-112">To correct this error</span></span>  
  
-   <span data-ttu-id="f9173-113">Wenn Sie die Kontrolle über den Quellcode verfügen, ändern Sie den Membernamen, damit er nicht mit einem Unterstrich beginnt.</span><span class="sxs-lookup"><span data-stu-id="f9173-113">If you have control over the source code, change the member name so that it does not begin with an underscore.</span></span>  
  
-   <span data-ttu-id="f9173-114">Wenn der Elementname unverändert bleiben muss, entfernen Sie die <xref:System.CLSCompliantAttribute>aus der Definition oder markieren Sie ihn als `<CLSCompliant(False)>`.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="f9173-114">If you require that the member name remain unchanged, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span> <span data-ttu-id="f9173-115">Sie können weiterhin markieren Sie die Assembly als `<CLSCompliant(True)>`.</span><span class="sxs-lookup"><span data-stu-id="f9173-115">You can still mark the assembly as `<CLSCompliant(True)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9173-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9173-116">See Also</span></span>  
 <span data-ttu-id="f9173-117">[Namen deklarierter Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span><span class="sxs-lookup"><span data-stu-id="f9173-117">[Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span></span>  
<span data-ttu-id="f9173-118"> [Visual Basic-Benennungskonventionen](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="f9173-118"> [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span></span>  
<span data-ttu-id="f9173-119"> [\<PAVE über > CLS-kompatiblen Code schreiben](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span><span class="sxs-lookup"><span data-stu-id="f9173-119"> [\<PAVE OVER> Writing CLS-Compliant Code](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span></span>
