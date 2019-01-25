---
title: '&lt;type1&gt;&#39;&lt;Typename&gt; &#39; müssen implementieren &#39; &lt;Membername&gt; &#39; für Schnittstelle &#39; &lt;Schnittstellenname&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 14e7bd199215764676a4b563eafc68bd6dabadc7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574741"
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmembernamegt39-for-interface-39ltinterfacenamegt39"></a><span data-ttu-id="9357a-102">&lt;type1&gt;&#39;&lt;Typename&gt; &#39; müssen implementieren &#39; &lt;Membername&gt; &#39; für Schnittstelle &#39; &lt;Schnittstellenname&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="9357a-102">&lt;type1&gt;&#39;&lt;typename&gt;&#39; must implement &#39;&lt;membername&gt;&#39; for interface &#39;&lt;interfacename&gt;&#39;</span></span>
<span data-ttu-id="9357a-103">"\<Typename >" implementieren muss '\<Membername >' für die Schnittstelle "\<Schnittstellenname >'.</span><span class="sxs-lookup"><span data-stu-id="9357a-103">'\<typename>' must implement '\<membername>' for interface '\<interfacename>'.</span></span> <span data-ttu-id="9357a-104">Die implementierende Eigenschaft müssen übereinstimmen 'ReadOnly' / 'WriteOnly' Spezifizierer.</span><span class="sxs-lookup"><span data-stu-id="9357a-104">Implementing property must have matching 'ReadOnly'/'WriteOnly' specifiers.</span></span>  
  
 <span data-ttu-id="9357a-105">Eine Klasse oder Struktur vorgibt, eine Schnittstelle zu implementieren, aber eine Prozedur, Eigenschaft oder das Ereignis definiert, die von der Schnittstelle nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="9357a-105">A class or structure claims to implement an interface but does not implement a procedure, property, or event defined by the interface.</span></span> <span data-ttu-id="9357a-106">Jeder Member der Schnittstelle muss implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="9357a-106">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="9357a-107">**Fehler-ID:** BC30154</span><span class="sxs-lookup"><span data-stu-id="9357a-107">**Error ID:** BC30154</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9357a-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="9357a-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="9357a-109">Deklarieren Sie ein Element mit dem gleichen Namen und die gleiche Signatur wie in der Schnittstelle definiert.</span><span class="sxs-lookup"><span data-stu-id="9357a-109">Declare a member with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="9357a-110">Müssen Sie mindestens die `End Function`, `End Sub`, oder `End Property` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9357a-110">Be sure to include at least the `End Function`, `End Sub`, or `End Property` statement.</span></span>  
  
2.  <span data-ttu-id="9357a-111">Hinzufügen einer `Implements` Klausel am Ende der `Function`, `Sub`, `Property`, oder `Event` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9357a-111">Add an `Implements` clause to the end of the `Function`, `Sub`, `Property`, or `Event` statement.</span></span> <span data-ttu-id="9357a-112">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9357a-112">For example:</span></span>  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  <span data-ttu-id="9357a-113">Wenn Sie eine Eigenschaft zu implementieren, stellen sicher, dass `ReadOnly` oder `WriteOnly` wird verwendet, auf die gleiche Weise wie die Schnittstellendefinition.</span><span class="sxs-lookup"><span data-stu-id="9357a-113">When implementing a property, make sure that `ReadOnly` or `WriteOnly` is used in the same way as in the interface definition.</span></span>  
  
4.  <span data-ttu-id="9357a-114">Wenn Sie eine Eigenschaft implementieren möchten, deklarieren `Get` und `Set` Verfahren nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="9357a-114">When implementing a property, declare `Get` and `Set` procedures, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9357a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9357a-115">See also</span></span>
- [<span data-ttu-id="9357a-116">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9357a-116">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="9357a-117">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9357a-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
