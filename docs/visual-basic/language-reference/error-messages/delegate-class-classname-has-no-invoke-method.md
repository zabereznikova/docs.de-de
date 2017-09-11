---
title: Delegatklasse&lt;Classname&gt;&quot; hat keine Invoke-Methode ein Ausdruck dieses Typs das Ziel eines Methodenaufrufs | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30220
- bc30220
dev_langs:
- VB
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
caps.latest.revision: 10
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
ms.openlocfilehash: 54cd62bc2b4cafa89873728ba4e5b31c46f1aab1
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="delegate-class-39ltclassnamegt39-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="78b2a-102">Delegatklasse&lt;Classname&gt;' hat keine Invoke-Methode ein Ausdruck dieses Typs das Ziel eines Methodenaufrufs</span><span class="sxs-lookup"><span data-stu-id="78b2a-102">Delegate class &#39;&lt;classname&gt;&#39; has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>
<span data-ttu-id="78b2a-103">Ein Aufruf von `Invoke` über einen Delegaten ist fehlgeschlagen, da `Invoke` nicht in der Delegatklasse implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="78b2a-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>  
  
 <span data-ttu-id="78b2a-104">**Fehler-ID:** BC30220</span><span class="sxs-lookup"><span data-stu-id="78b2a-104">**Error ID:** BC30220</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="78b2a-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="78b2a-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="78b2a-106">Stellen Sie sicher, dass eine Instanz der Delegatklasse mit erstellt wurde eine `Dim` -Anweisung, und dass eine Prozedur der Delegatinstanz mit zugewiesen wurde die `AddressOf` Operator.</span><span class="sxs-lookup"><span data-stu-id="78b2a-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>  
  
2.  <span data-ttu-id="78b2a-107">Suchen Sie den Code, der die Delegatklasse implementiert, und stellen Sie sicher, dass er implementiert die `Invoke` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="78b2a-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78b2a-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78b2a-108">See Also</span></span>  
 <span data-ttu-id="78b2a-109">[Delegaten](../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="78b2a-109">[Delegates](../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="78b2a-110"> [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md) </span><span class="sxs-lookup"><span data-stu-id="78b2a-110"> [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) </span></span>  
<span data-ttu-id="78b2a-111"> [AddressOf-Operator](../../../visual-basic/language-reference/operators/addressof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="78b2a-111"> [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md) </span></span>  
<span data-ttu-id="78b2a-112"> [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="78b2a-112"> [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>
