---
title: Eigenschaft &#39; &lt;Propertyname&gt; &#39; ist nicht&#39;t für alle Codepfade einen Wert zurück
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: 72bc7e45cadd2528f29c88bf6e80ee5f381052dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594213"
---
# <a name="property-39ltpropertynamegt39-doesn39t-return-a-value-on-all-code-paths"></a><span data-ttu-id="a543c-102">Eigenschaft &#39; &lt;Propertyname&gt; &#39; ist nicht&#39;t für alle Codepfade einen Wert zurück</span><span class="sxs-lookup"><span data-stu-id="a543c-102">Property &#39;&lt;propertyname&gt;&#39; doesn&#39;t return a value on all code paths</span></span>
<span data-ttu-id="a543c-103">Eigenschaft '\<Propertyname >' ist nicht für alle Codepfade einen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="a543c-103">Property '\<propertyname>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="a543c-104">Wenn das Ergebnis verwendet wird, kann während der Laufzeit eine NULL-Verweisausnahme auftreten.</span><span class="sxs-lookup"><span data-stu-id="a543c-104">A null reference exception could occur at run time when the result is used.</span></span>  
  
 <span data-ttu-id="a543c-105">Eine Eigenschaft `Get` Prozedur hat mindestens einen möglichen Pfad durch ihren Code, die keinen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="a543c-105">A property `Get` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="a543c-106">Sie können einen Wert aus einer Eigenschaft zurückgeben `Get` Prozedur in einem der folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="a543c-106">You can return a value from a property `Get` procedure in any of the following ways:</span></span>  
  
-   <span data-ttu-id="a543c-107">Weisen Sie den Wert des Eigenschaftennamens und führen Sie dann eine `Exit Property` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a543c-107">Assign the value to the property name and then perform an `Exit Property` statement.</span></span>  
  
-   <span data-ttu-id="a543c-108">Weisen Sie den Wert des Eigenschaftennamens und führen Sie dann die `End Get` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a543c-108">Assign the value to the property name and then perform the `End Get` statement.</span></span>  
  
-   <span data-ttu-id="a543c-109">Schließen Sie den Wert in einer [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a543c-109">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="a543c-110">Wenn die Steuerung an übergibt `Exit Property` oder `End Get` und des Eigenschaftennamens nicht ausnahmslos zugewiesene der `Get` Prozedur gibt den Standardwert des Datentyps für die Eigenschaft zurück.</span><span class="sxs-lookup"><span data-stu-id="a543c-110">If control passes to `Exit Property` or `End Get` and you have not assigned any value to the property name, the `Get` procedure returns the default value of the property's data type.</span></span> <span data-ttu-id="a543c-111">Weitere Informationen finden Sie unter "Verhalten" in [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a543c-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="a543c-112">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="a543c-112">By default, this message is a warning.</span></span> <span data-ttu-id="a543c-113">Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="a543c-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="a543c-114">**Fehler-ID:** BC42107</span><span class="sxs-lookup"><span data-stu-id="a543c-114">**Error ID:** BC42107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a543c-115">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a543c-115">To correct this error</span></span>  
  
-   <span data-ttu-id="a543c-116">Überprüfen Sie Ihre Ablaufsteuerungslogik, und stellen Sie sicher, dass Sie vor jeder Anweisung einen Wert zuweisen, die bewirkt, eine Rückgabe dass.</span><span class="sxs-lookup"><span data-stu-id="a543c-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="a543c-117">Es ist einfacher, um sicherzustellen, dass jede Rückgabe aus der Prozedur einen Wert zurückgibt, wenn Sie immer verwenden die `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a543c-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="a543c-118">Wenn Sie die letzte Anweisung vor dazu `End Get` sollte eine `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a543c-118">If you do this, the last statement before `End Get` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a543c-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a543c-119">See Also</span></span>  
 [<span data-ttu-id="a543c-120">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="a543c-120">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [<span data-ttu-id="a543c-121">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a543c-121">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="a543c-122">Get-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a543c-122">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
