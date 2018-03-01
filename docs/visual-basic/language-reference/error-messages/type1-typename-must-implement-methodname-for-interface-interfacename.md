---
title: "&lt;Typ1&gt;&#39;&lt; TypeName&gt;&#39; muss implementieren &#39;&lt; Methodenname&gt;&#39; für Schnittstelle &#39;&lt; Schnittstellenname&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e803ec7d0054f2fa1b9ed2a731fd30c9c3060468
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmethodnamegt39-for-interface-39ltinterfacenamegt39"></a><span data-ttu-id="62c65-102">&lt;Typ1&gt;&#39;&lt; TypeName&gt;&#39; muss implementieren &#39;&lt; Methodenname&gt;&#39; für Schnittstelle &#39;&lt; Schnittstellenname&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="62c65-102">&lt;type1&gt;&#39;&lt;typename&gt;&#39; must implement &#39;&lt;methodname&gt;&#39; for interface &#39;&lt;interfacename&gt;&#39;</span></span>
<span data-ttu-id="62c65-103">Eine Klasse oder Struktur Ansprüche an, um eine Schnittstelle zu implementieren, implementiert jedoch keine Prozedur, die von der Schnittstelle definiert.</span><span class="sxs-lookup"><span data-stu-id="62c65-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="62c65-104">Jeder Member der Schnittstelle muss implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="62c65-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="62c65-105">**Fehler-ID:** BC30149</span><span class="sxs-lookup"><span data-stu-id="62c65-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="62c65-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="62c65-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="62c65-107">Deklarieren Sie eine Prozedur mit demselben Namen und derselben Signatur wie in der Schnittstelle definiert.</span><span class="sxs-lookup"><span data-stu-id="62c65-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="62c65-108">Schließen Sie unbedingt mit mindestens der `End Function` oder `End Sub` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="62c65-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="62c65-109">Hinzufügen einer `Implements` -Klausel, um das Ende der `Function` oder `Sub` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="62c65-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="62c65-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="62c65-110">For example:</span></span>  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="62c65-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62c65-111">See Also</span></span>  
 [<span data-ttu-id="62c65-112">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="62c65-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [<span data-ttu-id="62c65-113">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="62c65-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
