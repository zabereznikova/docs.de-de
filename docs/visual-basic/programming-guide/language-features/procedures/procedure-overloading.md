---
title: Prozedurüberladung (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- signatures
- Overloads keyword [Visual Basic]
- hiding by signature
- Visual Basic code, procedures
- procedures [Visual Basic], signatures for
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- parameters [Visual Basic], lists
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- Shadows keyword [Visual Basic]
- procedure overloading
- procedures [Visual Basic], parameter lists
ms.assetid: fbc7fb18-e3b2-48b6-b554-64c00ed09d2a
ms.openlocfilehash: 0d1f2c4d8c88922659b3d91ed41d5e760e6e5233
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653913"
---
# <a name="procedure-overloading-visual-basic"></a><span data-ttu-id="cbdb6-102">Prozedurüberladung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cbdb6-102">Procedure Overloading (Visual Basic)</span></span>
<span data-ttu-id="cbdb6-103">*Überladen von* eine Prozedur bedeutet, dass es in mehreren Versionen, die mit dem gleichen Namen, aber unterschiedlichen Parameterlisten definiert.</span><span class="sxs-lookup"><span data-stu-id="cbdb6-103">*Overloading* a procedure means defining it in multiple versions, using the same name but different parameter lists.</span></span> <span data-ttu-id="cbdb6-104">Der Zweck des Überladens werden mehrere eng verwandte Versionen einer Prozedur definieren, ohne sie anhand des Namens zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="cbdb6-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span> <span data-ttu-id="cbdb6-105">Dazu müssen Sie die Parameterliste variabler.</span><span class="sxs-lookup"><span data-stu-id="cbdb6-105">You do this by varying the parameter list.</span></span>  
  
## <a name="overloading-rules"></a><span data-ttu-id="cbdb6-106">Überladen von Regeln</span><span class="sxs-lookup"><span data-stu-id="cbdb6-106">Overloading Rules</span></span>  
 <span data-ttu-id="cbdb6-107">Wenn Sie eine Prozedur zu überladen, gelten die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="cbdb6-107">When you overload a procedure, the following rules apply:</span></span>  
  
-   <span data-ttu-id="cbdb6-108">**Gleichnamigen**.</span><span class="sxs-lookup"><span data-stu-id="cbdb6-108">**Same Name**.</span></span> <span data-ttu-id="cbdb6-109">Jede überladene Version muss den gleichen Prozedurnamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="cbdb6-109">Each overloaded version must use the same procedure name.</span></span>  
  
-   <span data-ttu-id="cbdb6-110">**Andere Signatur**.</span><span class="sxs-lookup"><span data-stu-id="cbdb6-110">**Different Signature**.</span></span> <span data-ttu-id="cbdb6-111">Jede überladene Version muss sich von anderen überladenen Versionen in mindestens einer der folgenden Punkte unterscheiden:</span><span class="sxs-lookup"><span data-stu-id="cbdb6-111">Each overloaded version must differ from all other overloaded versions in at least one of the following respects:</span></span>  
  
    -   <span data-ttu-id="cbdb6-112">Anzahl von Parametern</span><span class="sxs-lookup"><span data-stu-id="cbdb6-112">Number of parameters</span></span>  
  
    -   <span data-ttu-id="cbdb6-113">Reihenfolge der Parameter</span><span class="sxs-lookup"><span data-stu-id="cbdb6-113">Order of the parameters</span></span>  
  
    -   <span data-ttu-id="cbdb6-114">Die Datentypen der Parameter</span><span class="sxs-lookup"><span data-stu-id="cbdb6-114">Data types of the parameters</span></span>  
  
    -   <span data-ttu-id="cbdb6-115">Anzahl der Typparameter (für eine generische Prozedur)</span><span class="sxs-lookup"><span data-stu-id="cbdb6-115">Number of type parameters (for a generic procedure)</span></span>  
  
    -   <span data-ttu-id="cbdb6-116">Rückgabetyp (nur für einen Konvertierungsoperator)</span><span class="sxs-lookup"><span data-stu-id="cbdb6-116">Return type (only for a conversion operator)</span></span>  
  
     <span data-ttu-id="cbdb6-117">Die vorherigen Elemente werden zusammen mit den Namen der Prozedur als bezeichnet den *Signatur* der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="cbdb6-117">Together with the procedure name, the preceding items are collectively called the *signature* of the procedure.</span></span> <span data-ttu-id="cbdb6-118">Wenn Sie eine überladene Prozedur aufrufen, verwendet der Compiler die Signatur überprüfen, ob der Aufruf der Definition übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="cbdb6-118">When you call an overloaded procedure, the compiler uses the signature to check that the call correctly matches the definition.</span></span>  
  
-   <span data-ttu-id="cbdb6-119">**Elemente, die nicht Teil der Signatur**.</span><span class="sxs-lookup"><span data-stu-id="cbdb6-119">**Items Not Part of Signature**.</span></span> <span data-ttu-id="cbdb6-120">Eine Prozedur kann nicht überladen werden, ohne die Signatur variieren.</span><span class="sxs-lookup"><span data-stu-id="cbdb6-120">You cannot overload a procedure without varying the signature.</span></span> <span data-ttu-id="cbdb6-121">Insbesondere können Sie Prozedur durch Variierung der nur eine oder mehrere der folgenden Elemente nicht überladen:</span><span class="sxs-lookup"><span data-stu-id="cbdb6-121">In particular, you cannot overload a procedure by varying only one or more of the following items:</span></span>  
  
    -   <span data-ttu-id="cbdb6-122">Schlüsselwörter für Prozedurmodifizierer, z. B. `Public`, `Shared`, und `Static`</span><span class="sxs-lookup"><span data-stu-id="cbdb6-122">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`</span></span>  
  
    -   <span data-ttu-id="cbdb6-123">Parameter oder Typ Parameternamen</span><span class="sxs-lookup"><span data-stu-id="cbdb6-123">Parameter or type parameter names</span></span>  
  
    -   <span data-ttu-id="cbdb6-124">Einschränkungen für Typparameter (für eine generische Prozedur)</span><span class="sxs-lookup"><span data-stu-id="cbdb6-124">Type parameter constraints (for a generic procedure)</span></span>  
  
    -   <span data-ttu-id="cbdb6-125">Parametermodifiziererschlüsselwörter, wie z. B. `ByRef` und `Optional`</span><span class="sxs-lookup"><span data-stu-id="cbdb6-125">Parameter modifier keywords, such as `ByRef` and `Optional`</span></span>  
  
    -   <span data-ttu-id="cbdb6-126">Gibt an, ob es sich um einen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="cbdb6-126">Whether it returns a value</span></span>  
  
    -   <span data-ttu-id="cbdb6-127">Der Datentyp des Rückgabewerts (mit Ausnahme eines Konvertierungsoperators)</span><span class="sxs-lookup"><span data-stu-id="cbdb6-127">The data type of the return value (except for a conversion operator)</span></span>  
  
     <span data-ttu-id="cbdb6-128">Die Elemente in der vorangehenden Liste aufgeführt sind nicht Teil der Signatur.</span><span class="sxs-lookup"><span data-stu-id="cbdb6-128">The items in the preceding list are not part of the signature.</span></span> <span data-ttu-id="cbdb6-129">Obwohl Sie sie verwenden können, um zwischen überladenen Versionen zu unterscheiden, können Sie diese überladenen Versionen variieren, die ordnungsgemäß durch ihre Signaturen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="cbdb6-129">Although you cannot use them to differentiate between overloaded versions, you can vary them among overloaded versions that are properly differentiated by their signatures.</span></span>  
  
-   <span data-ttu-id="cbdb6-130">**Spät gebundene Argumente**.</span><span class="sxs-lookup"><span data-stu-id="cbdb6-130">**Late-Bound Arguments**.</span></span> <span data-ttu-id="cbdb6-131">Wenn Sie beabsichtigen, eine spät gebundenen Objektvariable an eine überladene Version zu übergeben, müssen Sie die entsprechende Parameter als deklarieren <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="cbdb6-131">If you intend to pass a late bound object variable to an overloaded version, you must declare the appropriate parameter as <xref:System.Object>.</span></span>  
  
## <a name="multiple-versions-of-a-procedure"></a><span data-ttu-id="cbdb6-132">Mehrere Versionen einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="cbdb6-132">Multiple Versions of a Procedure</span></span>  
 <span data-ttu-id="cbdb6-133">Angenommen, Sie schreiben eine `Sub` Verfahren zum Bereitstellen einer Transaktions für ein Kunde Balance, und Sie sollten an den Kunden nach Name oder der Kontonummer verweisen können.</span><span class="sxs-lookup"><span data-stu-id="cbdb6-133">Suppose you are writing a `Sub` procedure to post a transaction against a customer's balance, and you want to be able to refer to the customer either by name or by account number.</span></span> <span data-ttu-id="cbdb6-134">Um dies zu berücksichtigen, können Sie definieren zwei verschiedene `Sub` Prozeduren, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="cbdb6-134">To accommodate this, you can define two different `Sub` procedures, as in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#73](./codesnippet/VisualBasic/procedure-overloading_1.vb)]  
  
### <a name="overloaded-versions"></a><span data-ttu-id="cbdb6-135">Überladene Versionen</span><span class="sxs-lookup"><span data-stu-id="cbdb6-135">Overloaded Versions</span></span>  
 <span data-ttu-id="cbdb6-136">Eine Alternative besteht, einen Namen für die einzelnen Prozedur zu überladen.</span><span class="sxs-lookup"><span data-stu-id="cbdb6-136">An alternative is to overload a single procedure name.</span></span> <span data-ttu-id="cbdb6-137">Sie können die [überlädt](../../../../visual-basic/language-reference/modifiers/overloads.md) Schlüsselwort, um eine Version der Prozedur für jede Parameterliste wie folgt definieren:</span><span class="sxs-lookup"><span data-stu-id="cbdb6-137">You can use the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword to define a version of the procedure for each parameter list, as follows:</span></span>  
  
 [!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/procedure-overloading_2.vb)]  
  
#### <a name="additional-overloads"></a><span data-ttu-id="cbdb6-138">Zusätzliche Überladungen</span><span class="sxs-lookup"><span data-stu-id="cbdb6-138">Additional Overloads</span></span>  
 <span data-ttu-id="cbdb6-139">Wenn Sie zudem soll demonstriert werden eine Transaktion Menge entweder akzeptiert `Decimal` oder `Single`, überladen Sie weitere `post` um diese Variante zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="cbdb6-139">If you also wanted to accept a transaction amount in either `Decimal` or `Single`, you could further overload `post` to allow for this variation.</span></span> <span data-ttu-id="cbdb6-140">Wenn Sie dies auf jede der Überladungen im vorherigen Beispiel, würden Sie haben vier `Sub` -Prozeduren mit dem gleichen Namen mit vier unterschiedlichen Signaturen möglich.</span><span class="sxs-lookup"><span data-stu-id="cbdb6-140">If you did this to each of the overloads in the preceding example, you would have four `Sub` procedures, all with the same name but with four different signatures.</span></span>  
  
## <a name="advantages-of-overloading"></a><span data-ttu-id="cbdb6-141">Vorteile des Überladens</span><span class="sxs-lookup"><span data-stu-id="cbdb6-141">Advantages of Overloading</span></span>  
 <span data-ttu-id="cbdb6-142">Der Vorteil der überladen einer Prozedur ist die Flexibilität des Aufrufs.</span><span class="sxs-lookup"><span data-stu-id="cbdb6-142">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="cbdb6-143">Verwenden der `post` Prozedur deklariert, im vorherigen Beispiel der aufrufende Code erhalten die Kunden-ID als ein `String` oder ein `Integer`, und rufen Sie anschließend in beiden Fällen das gleiche Verfahren.</span><span class="sxs-lookup"><span data-stu-id="cbdb6-143">To use the `post` procedure declared in the preceding example, the calling code can obtain the customer identification as either a `String` or an `Integer`, and then call the same procedure in either case.</span></span> <span data-ttu-id="cbdb6-144">Dies wird anhand des folgenden Beispiels veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="cbdb6-144">The following example illustrates this:</span></span>  
  
 [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/procedure-overloading_3.vb)]  
  
 [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/procedure-overloading_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="cbdb6-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cbdb6-145">See Also</span></span>  
 [<span data-ttu-id="cbdb6-146">Verfahren</span><span class="sxs-lookup"><span data-stu-id="cbdb6-146">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="cbdb6-147">Gewusst wie: Definieren mehrerer Versionen einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="cbdb6-147">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)  
 [<span data-ttu-id="cbdb6-148">Gewusst wie: Aufrufen einer überladenen Prozedur</span><span class="sxs-lookup"><span data-stu-id="cbdb6-148">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)  
 [<span data-ttu-id="cbdb6-149">Gewusst wie: Überladen einer Prozedur mit optionalen Parametern</span><span class="sxs-lookup"><span data-stu-id="cbdb6-149">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [<span data-ttu-id="cbdb6-150">Gewusst wie: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern</span><span class="sxs-lookup"><span data-stu-id="cbdb6-150">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [<span data-ttu-id="cbdb6-151">Überlegungen zur Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="cbdb6-151">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)  
 [<span data-ttu-id="cbdb6-152">Überladungsauflösung</span><span class="sxs-lookup"><span data-stu-id="cbdb6-152">Overload Resolution</span></span>](./overload-resolution.md)  
 [<span data-ttu-id="cbdb6-153">Overloads</span><span class="sxs-lookup"><span data-stu-id="cbdb6-153">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [<span data-ttu-id="cbdb6-154">Generische Typen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cbdb6-154">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
