---
title: '&#39;&lt;Schnittstellenname&gt;.&lt; Membername&gt; &#39; wird bereits von der Basisklasse implementiert &#39; &lt;Basisklassenname&gt;&#39;. Die erneute Implementierung von &lt;Typ&gt; davon ausgegangen, dass'
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 9054c293ede9db4637f23579407f2f76db29f2ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588969"
---
# <a name="39ltinterfacenamegtltmembernamegt39-is-already-implemented-by-the-base-class-39ltbaseclassnamegt39-re-implementation-of-lttypegt-assumed"></a><span data-ttu-id="dd3c4-103">&#39;&lt;Schnittstellenname&gt;.&lt; Membername&gt; &#39; wird bereits von der Basisklasse implementiert &#39; &lt;Basisklassenname&gt;&#39;.</span><span class="sxs-lookup"><span data-stu-id="dd3c4-103">&#39;&lt;interfacename&gt;.&lt;membername&gt;&#39; is already implemented by the base class &#39;&lt;baseclassname&gt;&#39;.</span></span> <span data-ttu-id="dd3c4-104">Die erneute Implementierung von &lt;Typ&gt; davon ausgegangen, dass</span><span class="sxs-lookup"><span data-stu-id="dd3c4-104">Re-implementation of &lt;type&gt; assumed</span></span>
<span data-ttu-id="dd3c4-105">Eine Eigenschaft, eine Prozedur oder ein Ereignis in einer abgeleiteten Klasse verwendet eine `Implements` -Klausel eines Schnittstellenmembers, die bereits in der Basisklasse implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="dd3c4-105">A property, procedure, or event in a derived class uses an `Implements` clause specifying an interface member that is already implemented in the base class.</span></span>  
  
 <span data-ttu-id="dd3c4-106">Ein Schnittstellenmember, der von seiner Basisklasse implementiert wird, kann von einer abgeleiteten Klasse erneut implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="dd3c4-106">A derived class can reimplement an interface member that is implemented by its base class.</span></span> <span data-ttu-id="dd3c4-107">Dieser Vorgang ist nicht identisch mit dem Überschreiben der Basisklassenimplementierung.</span><span class="sxs-lookup"><span data-stu-id="dd3c4-107">This is not the same as overriding the base class implementation.</span></span> <span data-ttu-id="dd3c4-108">Weitere Informationen finden Sie unter [implementiert](../../../visual-basic/language-reference/statements/implements-clause.md).</span><span class="sxs-lookup"><span data-stu-id="dd3c4-108">For more information, see [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).</span></span>  
  
 <span data-ttu-id="dd3c4-109">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="dd3c4-109">By default, this message is a warning.</span></span> <span data-ttu-id="dd3c4-110">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="dd3c4-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="dd3c4-111">**Fehler-ID:** BC42015</span><span class="sxs-lookup"><span data-stu-id="dd3c4-111">**Error ID:** BC42015</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dd3c4-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="dd3c4-112">To correct this error</span></span>  
  
-   <span data-ttu-id="dd3c4-113">Wenn Sie beabsichtigen, den Schnittstellenmember erneut zu implementieren, müssen Sie keine Maßnahme ergreifen.</span><span class="sxs-lookup"><span data-stu-id="dd3c4-113">If you intend to reimplement the interface member, you do not need to take any action.</span></span> <span data-ttu-id="dd3c4-114">Code in der abgeleiteten Klasse greift auf die neu Member, es sei denn, Sie verwenden die `MyBase` Schlüsselwort, um die Implementierung der Basisklasse zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="dd3c4-114">Code in your derived class accesses the reimplemented member unless you use the `MyBase` keyword to access the base class implementation.</span></span>  
  
-   <span data-ttu-id="dd3c4-115">Wenn Sie keine erneute Implementierung des Schnittstellenmembers beabsichtigen, entfernen Sie die `Implements` -Klausel aus der Deklaration der Eigenschaft, Prozedur oder des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="dd3c4-115">If you do not intend to reimplement the interface member, remove the `Implements` clause from the property, procedure, or event declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd3c4-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd3c4-116">See Also</span></span>  
 [<span data-ttu-id="dd3c4-117">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="dd3c4-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
