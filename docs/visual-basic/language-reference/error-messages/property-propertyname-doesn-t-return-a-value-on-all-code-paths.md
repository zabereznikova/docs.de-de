---
title: "Eigenschaft &quot;&lt;Propertyname&gt;&quot; nicht für alle Codepfade einen Wert zurück | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42107
- vbc42107
dev_langs:
- VB
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
caps.latest.revision: 7
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
ms.openlocfilehash: 64bacc2a2494160b3f9bbaec0915179f40735ef0
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="property-39ltpropertynamegt39-doesn39t-return-a-value-on-all-code-paths"></a><span data-ttu-id="d11f4-102">Eigenschaft '&lt;Propertyname&gt;' nicht für alle Codepfade einen Wert zurück</span><span class="sxs-lookup"><span data-stu-id="d11f4-102">Property &#39;&lt;propertyname&gt;&#39; doesn&#39;t return a value on all code paths</span></span>
<span data-ttu-id="d11f4-103">Eigenschaft '\<Propertyname >' nicht für alle Codepfade einen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="d11f4-103">Property '\<propertyname>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="d11f4-104">Wenn das Ergebnis verwendet wird, kann während der Laufzeit eine NULL-Verweisausnahme auftreten.</span><span class="sxs-lookup"><span data-stu-id="d11f4-104">A null reference exception could occur at run time when the result is used.</span></span>  
  
 <span data-ttu-id="d11f4-105">Eine Eigenschaft `Get` Prozedur verfügt über mindestens einen möglichen Codepfad auf, die keinen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d11f4-105">A property `Get` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="d11f4-106">Sie können einen Wert zurückgeben, von einer Eigenschaft `Get` Verfahren in den folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="d11f4-106">You can return a value from a property `Get` procedure in any of the following ways:</span></span>  
  
-   <span data-ttu-id="d11f4-107">Weisen Sie den Wert auf den Eigenschaftennamen, und führen Sie dann eine `Exit Property` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d11f4-107">Assign the value to the property name and then perform an `Exit Property` statement.</span></span>  
  
-   <span data-ttu-id="d11f4-108">Weisen Sie den Wert auf den Eigenschaftennamen, und führen Sie dann die `End Get` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d11f4-108">Assign the value to the property name and then perform the `End Get` statement.</span></span>  
  
-   <span data-ttu-id="d11f4-109">Fügen Sie den Wert in einem [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d11f4-109">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="d11f4-110">Wenn die Steuerung an `Exit Property` oder `End Get` und Sie den Namen der Eigenschaft einen Wert zugewiesen haben die `Get` Prozedur gibt den Standardwert des Datentyps der Eigenschaft zurück.</span><span class="sxs-lookup"><span data-stu-id="d11f4-110">If control passes to `Exit Property` or `End Get` and you have not assigned any value to the property name, the `Get` procedure returns the default value of the property's data type.</span></span> <span data-ttu-id="d11f4-111">Weitere Informationen finden Sie unter "Verhalten" in [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d11f4-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="d11f4-112">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="d11f4-112">By default, this message is a warning.</span></span> <span data-ttu-id="d11f4-113">Weitere Informationen zu Ausblenden von Warnungen oder Warnungen als Fehler behandeln, finden Sie unter [Konfigurieren von Warnungen in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="d11f4-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="d11f4-114">**Fehler-ID:** BC42107</span><span class="sxs-lookup"><span data-stu-id="d11f4-114">**Error ID:** BC42107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d11f4-115">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="d11f4-115">To correct this error</span></span>  
  
-   <span data-ttu-id="d11f4-116">Überprüfen Sie die Ablaufsteuerungslogik, und stellen Sie sicher, dass Sie vor jeder Anweisung einen Wert zuweisen, der eine Rückgabe verursacht.</span><span class="sxs-lookup"><span data-stu-id="d11f4-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="d11f4-117">Es ist einfacher sicherstellen, dass bei jeder Beendigung der Prozedur einen Wert zurückgibt, wenn Sie immer verwenden die `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d11f4-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="d11f4-118">Wenn Sie die letzte Anweisung vor dazu `End Get` sollte eine `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d11f4-118">If you do this, the last statement before `End Get` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d11f4-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d11f4-119">See Also</span></span>  
 <span data-ttu-id="d11f4-120">[Property-Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="d11f4-120">[Property Procedures](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md) </span></span>  
<span data-ttu-id="d11f4-121"> [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="d11f4-121"> [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="d11f4-122"> [Get-Anweisung](../../../visual-basic/language-reference/statements/get-statement.md)</span><span class="sxs-lookup"><span data-stu-id="d11f4-122"> [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md)</span></span>
