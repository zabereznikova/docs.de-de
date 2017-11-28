---
title: Namen &lt;Membername&gt; ist nicht CLS-kompatibel.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords: BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7f574c2ebd71dbe06c4a687728e7812a18c8a949
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="name-ltmembernamegt-is-not-cls-compliant"></a><span data-ttu-id="f9918-102">Namen &lt;Membername&gt; ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="f9918-102">Name &lt;membername&gt; is not CLS-compliant</span></span>
<span data-ttu-id="f9918-103">Eine Assembly ist als markiert `<CLSCompliant(True)>` aber macht ein Element mit einem Namen, die mit einem Unterstrich beginnt (`_`).</span><span class="sxs-lookup"><span data-stu-id="f9918-103">An assembly is marked as `<CLSCompliant(True)>` but exposes a member with a name that begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="f9918-104">Ein Programmierelement kann ein oder mehrere Unterstriche enthalten, doch werden zum Einhalten der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](https://msdn.microsoft.com/library/12a7a7h3) (CLS), es muss nicht mit einem Unterstrich beginnen.</span><span class="sxs-lookup"><span data-stu-id="f9918-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="f9918-105">Finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="f9918-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="f9918-106">Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f9918-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="f9918-107">Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="f9918-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="f9918-108">Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.</span><span class="sxs-lookup"><span data-stu-id="f9918-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="f9918-109">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="f9918-109">By default, this message is a warning.</span></span> <span data-ttu-id="f9918-110">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="f9918-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="f9918-111">**Fehler-ID:** BC40031</span><span class="sxs-lookup"><span data-stu-id="f9918-111">**Error ID:** BC40031</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f9918-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="f9918-112">To correct this error</span></span>  
  
-   <span data-ttu-id="f9918-113">Wenn Sie die Kontrolle über den Quellcode haben, ändern Sie den Membernamen, damit er nicht mit einem Unterstrich beginnt.</span><span class="sxs-lookup"><span data-stu-id="f9918-113">If you have control over the source code, change the member name so that it does not begin with an underscore.</span></span>  
  
-   <span data-ttu-id="f9918-114">Wenn Sie festlegen, dass es sich bei der Membernamen unverändert bleiben, entfernen Sie die <xref:System.CLSCompliantAttribute> aus seiner Definition oder kennzeichnen Sie ihn als `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="f9918-114">If you require that the member name remain unchanged, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span> <span data-ttu-id="f9918-115">Sie können weiterhin die Assembly als kennzeichnen `<CLSCompliant(True)>`.</span><span class="sxs-lookup"><span data-stu-id="f9918-115">You can still mark the assembly as `<CLSCompliant(True)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9918-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9918-116">See Also</span></span>  
 [<span data-ttu-id="f9918-117">Namen deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="f9918-117">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="f9918-118">Visual Basic-Benennungskonventionen</span><span class="sxs-lookup"><span data-stu-id="f9918-118">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [<span data-ttu-id="f9918-119">\<PAVE über > Schreiben von CLS-kompatiblem Code</span><span class="sxs-lookup"><span data-stu-id="f9918-119">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
