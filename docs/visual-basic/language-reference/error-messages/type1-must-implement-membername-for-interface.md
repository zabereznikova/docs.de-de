---
title: '&lt;Typ1&gt;&#39;&lt;Typename&gt; &#39; implementieren müssen &#39; &lt;Membername&gt; &#39; für Schnittstelle &#39; &lt;Schnittstellenname&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 0f93bd137bdc21268cbca139ae739843561350ac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmembernamegt39-for-interface-39ltinterfacenamegt39"></a><span data-ttu-id="e95c1-102">&lt;Typ1&gt;&#39;&lt;Typename&gt; &#39; implementieren müssen &#39; &lt;Membername&gt; &#39; für Schnittstelle &#39; &lt;Schnittstellenname&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="e95c1-102">&lt;type1&gt;&#39;&lt;typename&gt;&#39; must implement &#39;&lt;membername&gt;&#39; for interface &#39;&lt;interfacename&gt;&#39;</span></span>
<span data-ttu-id="e95c1-103">"\<Typename >" implementieren müssen "\<Membername >' für die Schnittstelle"\<Schnittstellenname >'.</span><span class="sxs-lookup"><span data-stu-id="e95c1-103">'\<typename>' must implement '\<membername>' for interface '\<interfacename>'.</span></span> <span data-ttu-id="e95c1-104">Implementieren die Eigenschaft müssen übereinstimmen "ReadOnly" / "WriteOnly" Spezifizierer.</span><span class="sxs-lookup"><span data-stu-id="e95c1-104">Implementing property must have matching 'ReadOnly'/'WriteOnly' specifiers.</span></span>  
  
 <span data-ttu-id="e95c1-105">Eine Klasse oder Struktur Ansprüche an, um eine Schnittstelle zu implementieren, aber eine Prozedur, Eigenschaft oder Ereignis definiert, durch die Schnittstelle nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="e95c1-105">A class or structure claims to implement an interface but does not implement a procedure, property, or event defined by the interface.</span></span> <span data-ttu-id="e95c1-106">Jeder Member der Schnittstelle muss implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="e95c1-106">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="e95c1-107">**Fehler-ID:** BC30154</span><span class="sxs-lookup"><span data-stu-id="e95c1-107">**Error ID:** BC30154</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e95c1-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="e95c1-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="e95c1-109">Deklarieren Sie einen Member mit demselben Namen und derselben Signatur wie in der Schnittstelle definiert.</span><span class="sxs-lookup"><span data-stu-id="e95c1-109">Declare a member with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="e95c1-110">Schließen Sie unbedingt mit mindestens der `End Function`, `End Sub`, oder `End Property` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="e95c1-110">Be sure to include at least the `End Function`, `End Sub`, or `End Property` statement.</span></span>  
  
2.  <span data-ttu-id="e95c1-111">Hinzufügen einer `Implements` -Klausel, um das Ende der `Function`, `Sub`, `Property`, oder `Event` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="e95c1-111">Add an `Implements` clause to the end of the `Function`, `Sub`, `Property`, or `Event` statement.</span></span> <span data-ttu-id="e95c1-112">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e95c1-112">For example:</span></span>  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  <span data-ttu-id="e95c1-113">Wenn Sie eine Eigenschaft zu implementieren, stellen sicher, dass `ReadOnly` oder `WriteOnly` auf die gleiche Weise wie in der Schnittstellendefinition verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e95c1-113">When implementing a property, make sure that `ReadOnly` or `WriteOnly` is used in the same way as in the interface definition.</span></span>  
  
4.  <span data-ttu-id="e95c1-114">Beim Implementieren einer Eigenschaft deklarieren `Get` und `Set` Prozeduren nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="e95c1-114">When implementing a property, declare `Get` and `Set` procedures, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e95c1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e95c1-115">See Also</span></span>  
 [<span data-ttu-id="e95c1-116">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e95c1-116">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [<span data-ttu-id="e95c1-117">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e95c1-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
