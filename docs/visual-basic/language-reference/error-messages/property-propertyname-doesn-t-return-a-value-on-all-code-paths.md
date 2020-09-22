---
title: 'Die <propertyname>-Eigenschaft gibt nicht für alle Codepfade einen Wert zurück:'
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: 6a80a8275a7b9c5e3cbfa410ee219e0d16ce5918
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870951"
---
# <a name="property-propertyname-doesnt-return-a-value-on-all-code-paths"></a><span data-ttu-id="03726-102">Die \<propertyname>-Eigenschaft gibt nicht für alle Codepfade einen Wert zurück:</span><span class="sxs-lookup"><span data-stu-id="03726-102">Property '\<propertyname>' doesn't return a value on all code paths</span></span>

<span data-ttu-id="03726-103">Die-Eigenschaft \<propertyname> gibt nicht für alle Codepfade einen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="03726-103">Property '\<propertyname>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="03726-104">Wenn das Ergebnis verwendet wird, kann während der Laufzeit eine NULL-Verweisausnahme auftreten.</span><span class="sxs-lookup"><span data-stu-id="03726-104">A null reference exception could occur at run time when the result is used.</span></span>  
  
 <span data-ttu-id="03726-105">Eine Eigenschaften `Get` Prozedur weist mindestens einen möglichen Pfad durch Ihren Code auf, der keinen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="03726-105">A property `Get` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="03726-106">Sie können einen Wert aus einer Eigenschaften `Get` Prozedur mit einer der folgenden Methoden zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="03726-106">You can return a value from a property `Get` procedure in any of the following ways:</span></span>  
  
- <span data-ttu-id="03726-107">Weisen Sie dem Eigenschaftsnamen den Wert zu, und führen Sie dann eine- `Exit Property` Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="03726-107">Assign the value to the property name and then perform an `Exit Property` statement.</span></span>  
  
- <span data-ttu-id="03726-108">Weisen Sie dem Eigenschaftsnamen den Wert zu, und führen Sie dann die `End Get` Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="03726-108">Assign the value to the property name and then perform the `End Get` statement.</span></span>  
  
- <span data-ttu-id="03726-109">Fügen Sie den Wert in eine [Return-Anweisung](../statements/return-statement.md)ein.</span><span class="sxs-lookup"><span data-stu-id="03726-109">Include the value in a [Return Statement](../statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="03726-110">Wenn die Steuerung an `Exit Property` oder weitergeleitet `End Get` wird und Sie dem Eigenschaftsnamen keinen Wert zugewiesen haben, `Get` gibt die Prozedur den Standardwert des Datentyps der Eigenschaft zurück.</span><span class="sxs-lookup"><span data-stu-id="03726-110">If control passes to `Exit Property` or `End Get` and you have not assigned any value to the property name, the `Get` procedure returns the default value of the property's data type.</span></span> <span data-ttu-id="03726-111">Weitere Informationen finden Sie unter "Verhalten" in der [Function-Anweisung](../statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="03726-111">For more information, see "Behavior" in [Function Statement](../statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="03726-112">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="03726-112">By default, this message is a warning.</span></span> <span data-ttu-id="03726-113">Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="03726-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="03726-114">**Fehler-ID:** BC42107</span><span class="sxs-lookup"><span data-stu-id="03726-114">**Error ID:** BC42107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="03726-115">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="03726-115">To correct this error</span></span>  
  
- <span data-ttu-id="03726-116">Überprüfen Sie die Ablauf Steuerungslogik, und stellen Sie sicher, dass Sie vor jeder Anweisung, die eine Rückgabe auslöst, einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="03726-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="03726-117">Es ist einfacher sicherzustellen, dass jede Rückgabe von der Prozedur einen Wert zurückgibt, wenn Sie immer die- `Return` Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="03726-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="03726-118">Wenn Sie dies tun, sollte die letzte Anweisung vor `End Get` eine- `Return` Anweisung sein.</span><span class="sxs-lookup"><span data-stu-id="03726-118">If you do this, the last statement before `End Get` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03726-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="03726-119">See also</span></span>

- [<span data-ttu-id="03726-120">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="03726-120">Property Procedures</span></span>](../../programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="03726-121">Property Statement</span><span class="sxs-lookup"><span data-stu-id="03726-121">Property Statement</span></span>](../statements/property-statement.md)
- [<span data-ttu-id="03726-122">Get-Anweisung</span><span class="sxs-lookup"><span data-stu-id="03726-122">Get Statement</span></span>](../statements/get-statement.md)
