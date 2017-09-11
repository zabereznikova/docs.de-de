---
title: '&quot;&lt;Classname&gt;&quot;ist nicht CLS-kompatibel, da die Schnittstelle&quot;&lt;Interfacename&gt;&quot; Es implementiert ist nicht CLS-kompatibel. | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40029
- vbc40029
dev_langs:
- VB
helpviewer_keywords:
- BC40029
ms.assetid: 178452f3-5575-4da0-9d6c-53bcddb6a338
caps.latest.revision: 13
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
ms.openlocfilehash: d2819bf2dc76291cbaf7ca9215608a11b1a98b3a
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="39ltclassnamegt39-is-not-cls-compliant-because-the-interface-39ltinterfacenamegt39-it-implements-is-not-cls-compliant"></a><span data-ttu-id="671b3-102">'&lt;Classname&gt;"ist nicht CLS-kompatibel, da die Schnittstelle"&lt;Interfacename&gt;' Es implementiert ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="671b3-102">&#39;&lt;classname&gt;&#39; is not CLS-compliant because the interface &#39;&lt;interfacename&gt;&#39; it implements is not CLS-compliant</span></span>
<span data-ttu-id="671b3-103">Eine Klasse oder Schnittstelle wird als `<CLSCompliant(True)>` gekennzeichnet, wenn sie von einem Typ abgeleitet ist oder einen Typ implementiert, der als `<CLSCompliant(False)>` oder gar nicht gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="671b3-103">A class or interface is marked as `<CLSCompliant(True)>` when it derives from or implements a type that is marked as `<CLSCompliant(False)>` or is not marked.</span></span>  
  
 <span data-ttu-id="671b3-104">Für eine Klasse oder Schnittstelle, um die Kompatibilität mit der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](https://msdn.microsoft.com/library/12a7a7h3) (CLS), ihre gesamte Vererbungshierarchie kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="671b3-104">For a class or interface to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), its entire inheritance hierarchy must be compliant.</span></span> <span data-ttu-id="671b3-105">Das bedeutet, dass jeder Typ, von dem sie direkt oder indirekt erbt, kompatibel sein muss.</span><span class="sxs-lookup"><span data-stu-id="671b3-105">That means every type from which it inherits, directly or indirectly, must be compliant.</span></span> <span data-ttu-id="671b3-106">Analog dazu muss eine Klasse, wenn sie eine oder mehrere Schnittstellen implementiert, deren Konformität durch alle Vererbungshierarchien sicherstellen.</span><span class="sxs-lookup"><span data-stu-id="671b3-106">Similarly, if a class implements one or more interfaces, they must all be compliant throughout their inheritance hierarchies.</span></span>  
  
 <span data-ttu-id="671b3-107">Beim Anwenden der <xref:System.CLSCompliantAttribute>auf ein Programmierelement legen Sie des Attributs `isCompliant` Parameter entweder `True` oder `False` an Kompatibilität oder Nichtkompatibilität.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="671b3-107">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="671b3-108">Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="671b3-108">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="671b3-109">Wenn Sie nicht anwenden der <xref:System.CLSCompliantAttribute>auf ein Element gilt nicht kompatibel ist.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="671b3-109">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="671b3-110">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="671b3-110">By default, this message is a warning.</span></span> <span data-ttu-id="671b3-111">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="671b3-111">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="671b3-112">**Fehler-ID:** BC40029</span><span class="sxs-lookup"><span data-stu-id="671b3-112">**Error ID:** BC40029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="671b3-113">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="671b3-113">To correct this error</span></span>  
  
-   <span data-ttu-id="671b3-114">Wenn Sie CLS-Konformität benötigen, definieren Sie diesen Typ innerhalb einer anderen Vererbungshierarchie oder eines anderen Implementierungsschemas.</span><span class="sxs-lookup"><span data-stu-id="671b3-114">If you require CLS compliance, define this type within a different inheritance hierarchy or implementation scheme.</span></span>  
  
-   <span data-ttu-id="671b3-115">Wenn dieser Typ innerhalb der aktuellen Vererbung oder Schema verbleiben muss, entfernen Sie die <xref:System.CLSCompliantAttribute>aus der Definition oder markieren Sie ihn als `<CLSCompliant(False)>`.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="671b3-115">If you require that this type remain within its current inheritance hierarchy or implementation scheme, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="671b3-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="671b3-116">See Also</span></span>  
 [<span data-ttu-id="671b3-117">\<PAVE über > CLS-kompatiblen Code schreiben</span><span class="sxs-lookup"><span data-stu-id="671b3-117">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
