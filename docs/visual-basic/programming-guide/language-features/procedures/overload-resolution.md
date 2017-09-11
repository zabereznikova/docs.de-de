---
title: "Überladungsauflösung (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- overload resolution
- procedures, overloading
- procedures, calling
- procedure overloading, overload resolution
- signatures, procedure
- overloads, resolution
ms.assetid: 766115d1-4352-45fb-859f-6063e0de0ec0
caps.latest.revision: 21
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
ms.openlocfilehash: a4f350af0f7d964df45974990991a2e94b26551e
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="overload-resolution-visual-basic"></a><span data-ttu-id="fafa3-102">Überladungsauflösung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fafa3-102">Overload Resolution (Visual Basic)</span></span>
<span data-ttu-id="fafa3-103">Wenn die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler erkennt einen Aufruf an eine Prozedur, die in mehreren überladenen Versionen definiert ist, muss der Compiler entscheiden, welche Überladung aufrufen.</span><span class="sxs-lookup"><span data-stu-id="fafa3-103">When the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler encounters a call to a procedure that is defined in several overloaded versions, the compiler must decide which of the overloads to call.</span></span> <span data-ttu-id="fafa3-104">Dazu werden die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="fafa3-104">It does this by performing the following steps:</span></span>  
  
1.  <span data-ttu-id="fafa3-105">**Eingabehilfen.**</span><span class="sxs-lookup"><span data-stu-id="fafa3-105">**Accessibility.**</span></span> <span data-ttu-id="fafa3-106">Überladung mit der Zugriffsebene, die verhindert, dass den aufrufenden Code Aufrufen dieser beseitigt.</span><span class="sxs-lookup"><span data-stu-id="fafa3-106">It eliminates any overload with an access level that prevents the calling code from calling it.</span></span>  
  
2.  <span data-ttu-id="fafa3-107">**Anzahl von Parametern.**</span><span class="sxs-lookup"><span data-stu-id="fafa3-107">**Number of Parameters.**</span></span> <span data-ttu-id="fafa3-108">Überladung, die eine andere Anzahl von Parametern definiert als geliefert werden im Aufruf beseitigt.</span><span class="sxs-lookup"><span data-stu-id="fafa3-108">It eliminates any overload that defines a different number of parameters than are supplied in the call.</span></span>  
  
3.  <span data-ttu-id="fafa3-109">**Parameter-Datentypen.**</span><span class="sxs-lookup"><span data-stu-id="fafa3-109">**Parameter Data Types.**</span></span> <span data-ttu-id="fafa3-110">Der Compiler zieht Instanzmethoden gegenüber Erweiterungsmethoden.</span><span class="sxs-lookup"><span data-stu-id="fafa3-110">The compiler gives instance methods preference over extension methods.</span></span> <span data-ttu-id="fafa3-111">Wenn eine beliebige Instanzmethode, erfordert nur erweiterungskonvertierungen entsprechend den Prozeduraufruf gefunden wird, alle Erweiterungsmethoden gelöscht, und der Compiler fährt mit der Instanzmethoden.</span><span class="sxs-lookup"><span data-stu-id="fafa3-111">If any instance method is found that requires only widening conversions to match the procedure call, all extension methods are dropped and the compiler continues with only the instance method candidates.</span></span> <span data-ttu-id="fafa3-112">Wenn keine solche Instanzmethode gefunden wird, weiterhin mit der Instanz und Erweiterungsmethoden.</span><span class="sxs-lookup"><span data-stu-id="fafa3-112">If no such instance method is found, it continues with both instance and extension methods.</span></span>  
  
     <span data-ttu-id="fafa3-113">In diesem Schritt schließt es eine Überladung für die die Datentypen der aufrufenden Argumente nicht in die Parametertypen, die in der Überladung definiert konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="fafa3-113">In this step, it eliminates any overload for which the data types of the calling arguments cannot be converted to the parameter types defined in the overload.</span></span>  
  
4.  <span data-ttu-id="fafa3-114">**Einschränkende Konvertierungen.**</span><span class="sxs-lookup"><span data-stu-id="fafa3-114">**Narrowing Conversions.**</span></span> <span data-ttu-id="fafa3-115">Überladung, die eine einschränkende Konvertierung aus der aufrufenden Argumenttypen mit den Parametertypen definierten erfordert beseitigt.</span><span class="sxs-lookup"><span data-stu-id="fafa3-115">It eliminates any overload that requires a narrowing conversion from the calling argument types to the defined parameter types.</span></span> <span data-ttu-id="fafa3-116">Dies ist der Fall, ob die Überprüfung des Typs wechseln ([Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) ist `On` oder `Off`.</span><span class="sxs-lookup"><span data-stu-id="fafa3-116">This is true whether the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `On` or `Off`.</span></span>  
  
5.  <span data-ttu-id="fafa3-117">**Geringste Erweiterung.**</span><span class="sxs-lookup"><span data-stu-id="fafa3-117">**Least Widening.**</span></span> <span data-ttu-id="fafa3-118">Der Compiler betrachtet die verbleibenden Überladungen paarweise.</span><span class="sxs-lookup"><span data-stu-id="fafa3-118">The compiler considers the remaining overloads in pairs.</span></span> <span data-ttu-id="fafa3-119">Für jedes Paar werden die Datentypen der definierten Parameter verglichen.</span><span class="sxs-lookup"><span data-stu-id="fafa3-119">For each pair, it compares the data types of the defined parameters.</span></span> <span data-ttu-id="fafa3-120">Wenn die entsprechenden Typen in den anderen Typen in einer Überladung alle erweitert werden, beseitigt der Compiler die letztere.</span><span class="sxs-lookup"><span data-stu-id="fafa3-120">If the types in one of the overloads all widen to the corresponding types in the other, the compiler eliminates the latter.</span></span> <span data-ttu-id="fafa3-121">Wird beibehalten, also die Überladung, die am wenigsten erweiternde erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="fafa3-121">That is, it retains the overload that requires the least amount of widening.</span></span>  
  
6.  <span data-ttu-id="fafa3-122">**Einzelne Betrachtung.**</span><span class="sxs-lookup"><span data-stu-id="fafa3-122">**Single Candidate.**</span></span> <span data-ttu-id="fafa3-123">Angesichts Überladungen paarweise bis nur eine bleibt Überladung und der Aufruf in diese Überladung löst wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="fafa3-123">It continues considering overloads in pairs until only one overload remains, and it resolves the call to that overload.</span></span> <span data-ttu-id="fafa3-124">Wenn der Compiler die Überladungen, die einem einzelnen Kandidaten reduziert werden kann, wird einen Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="fafa3-124">If the compiler cannot reduce the overloads to a single candidate, it generates an error.</span></span>  
  
 <span data-ttu-id="fafa3-125">Die folgende Abbildung zeigt den Prozess, der bestimmt, welche eine Gruppe von überladenen Versionen aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="fafa3-125">The following illustration shows the process that determines which of a set of overloaded versions to call.</span></span>  
  
 <span data-ttu-id="fafa3-126">![Flussdiagramm des überladungsauflösungsprozesses](./media/overloadres.gif "OverloadRes")</span><span class="sxs-lookup"><span data-stu-id="fafa3-126">![Flow diagram of overload resolution process](./media/overloadres.gif "OverloadRes")</span></span>  
<span data-ttu-id="fafa3-127">Auflösung bei überladenen Versionen</span><span class="sxs-lookup"><span data-stu-id="fafa3-127">Resolving among overloaded versions</span></span>  
  
 <span data-ttu-id="fafa3-128">Das folgende Beispiel veranschaulicht diese überladungsauflösungsprozesses.</span><span class="sxs-lookup"><span data-stu-id="fafa3-128">The following example illustrates this overload resolution process.</span></span>  
  
 <span data-ttu-id="fafa3-129">[!code-vb[VbVbcnProcedures&#62;](./codesnippet/VisualBasic/overload-resolution_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="fafa3-129">[!code-vb[VbVbcnProcedures#62](./codesnippet/VisualBasic/overload-resolution_1.vb)]</span></span>  
  
 <span data-ttu-id="fafa3-130">[!code-vb[VbVbcnProcedures&#63;](./codesnippet/VisualBasic/overload-resolution_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="fafa3-130">[!code-vb[VbVbcnProcedures#63](./codesnippet/VisualBasic/overload-resolution_2.vb)]</span></span>  
  
 <span data-ttu-id="fafa3-131">Im ersten Aufruf beseitigt der Compiler die erste Überladung, da der Typ des ersten Arguments (`Short`) wird in den Typ des entsprechenden Parameters (`Byte`).</span><span class="sxs-lookup"><span data-stu-id="fafa3-131">In the first call, the compiler eliminates the first overload because the type of the first argument (`Short`) narrows to the type of the corresponding parameter (`Byte`).</span></span> <span data-ttu-id="fafa3-132">Klicken Sie dann die dritte Überladung beseitigt, da jeder Argumenttyp der zweiten Überladung (`Short` und `Single`) in den entsprechenden Typ der dritten Überladung erweitert (`Integer` und `Single`).</span><span class="sxs-lookup"><span data-stu-id="fafa3-132">It then eliminates the third overload because each argument type in the second overload (`Short` and `Single`) widens to the corresponding type in the third overload (`Integer` and `Single`).</span></span> <span data-ttu-id="fafa3-133">Die zweite Überladung eine geringere Erweiterung erfordert, damit der Compiler für den Aufruf verwendet.</span><span class="sxs-lookup"><span data-stu-id="fafa3-133">The second overload requires less widening, so the compiler uses it for the call.</span></span>  
  
 <span data-ttu-id="fafa3-134">Im zweiten Aufruf kann nicht der Compiler keine Überladung durch Einschränken beseitigen.</span><span class="sxs-lookup"><span data-stu-id="fafa3-134">In the second call, the compiler cannot eliminate any of the overloads on the basis of narrowing.</span></span> <span data-ttu-id="fafa3-135">Die dritte Überladung beseitigt aus demselben Grund wie im ersten Aufruf, da die zweite Überladung mit geringerer Erweiterung der Argumenttypen aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="fafa3-135">It eliminates the third overload for the same reason as in the first call, because it can call the second overload with less widening of the argument types.</span></span> <span data-ttu-id="fafa3-136">Jedoch kann der Compiler zwischen der ersten und zweiten Überladung nicht auflösen.</span><span class="sxs-lookup"><span data-stu-id="fafa3-136">However, the compiler cannot resolve between the first and second overloads.</span></span> <span data-ttu-id="fafa3-137">Jede verfügt über einen definierten Parametertyp, der in den entsprechenden Typ in einer anderen erweitert wird (`Byte` auf `Short`, aber `Single` , `Double`).</span><span class="sxs-lookup"><span data-stu-id="fafa3-137">Each has one defined parameter type that widens to the corresponding type in the other (`Byte` to `Short`, but `Single` to `Double`).</span></span> <span data-ttu-id="fafa3-138">Aus diesem Grund generiert der Compiler einen Überladungsauflösungsfehler.</span><span class="sxs-lookup"><span data-stu-id="fafa3-138">The compiler therefore generates an overload resolution error.</span></span>  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a><span data-ttu-id="fafa3-139">Überladene optionale und ParamArray-Argumente</span><span class="sxs-lookup"><span data-stu-id="fafa3-139">Overloaded Optional and ParamArray Arguments</span></span>  
 <span data-ttu-id="fafa3-140">Wenn zwei Überladungen einer Prozedur identische Signaturen verfügen, mit der Ausnahme, dass der letzte Parameter deklariert ist [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) in einem und [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in einer anderen, löst der Compiler einen Aufruf an die Prozedur wie folgt:</span><span class="sxs-lookup"><span data-stu-id="fafa3-140">If two overloads of a procedure have identical signatures except that the last parameter is declared [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) in one and [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in the other, the compiler resolves a call to that procedure as follows:</span></span>  
  
|<span data-ttu-id="fafa3-141">Wenn der Aufruf wird des letzten Arguments als</span><span class="sxs-lookup"><span data-stu-id="fafa3-141">If the call supplies the last argument as</span></span>|<span data-ttu-id="fafa3-142">Der Compiler löst den Aufruf an die Überladung, die das letzte Argument als deklarieren</span><span class="sxs-lookup"><span data-stu-id="fafa3-142">The compiler resolves the call to the overload declaring the last argument as</span></span>|  
|---|---|  
|<span data-ttu-id="fafa3-143">Kein Wert (Argument ausgelassen)</span><span class="sxs-lookup"><span data-stu-id="fafa3-143">No value (argument omitted)</span></span>|`Optional`|  
|<span data-ttu-id="fafa3-144">Ein einzelner Wert</span><span class="sxs-lookup"><span data-stu-id="fafa3-144">A single value</span></span>|`Optional`|  
|<span data-ttu-id="fafa3-145">Zwei oder mehr Werte in einer durch Trennzeichen getrennte Liste</span><span class="sxs-lookup"><span data-stu-id="fafa3-145">Two or more values in a comma-separated list</span></span>|`ParamArray`|  
|<span data-ttu-id="fafa3-146">Ein Array von beliebiger Länge (einschließlich eines leeren Arrays)</span><span class="sxs-lookup"><span data-stu-id="fafa3-146">An array of any length (including an empty array)</span></span>|`ParamArray`|  
  
## <a name="see-also"></a><span data-ttu-id="fafa3-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fafa3-147">See Also</span></span>  
 <span data-ttu-id="fafa3-148">[Optionale Parameter](./optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="fafa3-148">[Optional Parameters](./optional-parameters.md) </span></span>  
<span data-ttu-id="fafa3-149"> [Parameterarrays](./parameter-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="fafa3-149"> [Parameter Arrays](./parameter-arrays.md) </span></span>  
<span data-ttu-id="fafa3-150"> [Prozedurüberladung](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="fafa3-150"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="fafa3-151"> [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="fafa3-151"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="fafa3-152"> [Gewusst wie: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="fafa3-152"> [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md) </span></span>  
<span data-ttu-id="fafa3-153"> [Gewusst wie: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="fafa3-153"> [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md) </span></span>  
<span data-ttu-id="fafa3-154"> [Gewusst wie: überladen eine Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="fafa3-154"> [How to: Overload a Procedure that Takes Optional Parameters](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span></span>  
<span data-ttu-id="fafa3-155"> [Gewusst wie: überladen eine Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="fafa3-155"> [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span></span>  
<span data-ttu-id="fafa3-156"> [Überlegungen zur prozedurüberladung](./considerations-in-overloading-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="fafa3-156"> [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md) </span></span>  
<span data-ttu-id="fafa3-157"> [Überladungen](../../../../visual-basic/language-reference/modifiers/overloads.md) </span><span class="sxs-lookup"><span data-stu-id="fafa3-157"> [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) </span></span>  
<span data-ttu-id="fafa3-158"> [Erweiterungsmethoden](./extension-methods.md)</span><span class="sxs-lookup"><span data-stu-id="fafa3-158"> [Extension Methods](./extension-methods.md)</span></span>
