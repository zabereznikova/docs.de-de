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
ms.openlocfilehash: 6e8d1fa72c60c4fa3d2237ad24c2d1b4891a7bf2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58828237"
---
# <a name="procedure-overloading-visual-basic"></a><span data-ttu-id="c11fd-102">Prozedurüberladung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c11fd-102">Procedure Overloading (Visual Basic)</span></span>
<span data-ttu-id="c11fd-103">*Überladen von* eine Prozedur bedeutet, dass es in mehreren Versionen, die mit dem gleichen Namen, aber unterschiedlichen Parameterlisten definiert.</span><span class="sxs-lookup"><span data-stu-id="c11fd-103">*Overloading* a procedure means defining it in multiple versions, using the same name but different parameter lists.</span></span> <span data-ttu-id="c11fd-104">Der Zweck des Überladens werden mehrere eng verwandte Versionen einer Prozedur zu definieren, ohne dass sie anhand des Namens zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="c11fd-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span> <span data-ttu-id="c11fd-105">Dazu müssen Sie die Parameterliste variieren.</span><span class="sxs-lookup"><span data-stu-id="c11fd-105">You do this by varying the parameter list.</span></span>  
  
## <a name="overloading-rules"></a><span data-ttu-id="c11fd-106">Überladen von Regeln</span><span class="sxs-lookup"><span data-stu-id="c11fd-106">Overloading Rules</span></span>  
 <span data-ttu-id="c11fd-107">Wenn Sie eine Prozedur zu überladen, gelten die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="c11fd-107">When you overload a procedure, the following rules apply:</span></span>  
  
-   <span data-ttu-id="c11fd-108">**Gleichnamigen**.</span><span class="sxs-lookup"><span data-stu-id="c11fd-108">**Same Name**.</span></span> <span data-ttu-id="c11fd-109">Jede überladene Version, muss die Namen der gleichen Prozedur verwenden.</span><span class="sxs-lookup"><span data-stu-id="c11fd-109">Each overloaded version must use the same procedure name.</span></span>  
  
-   <span data-ttu-id="c11fd-110">**Andere Signatur**.</span><span class="sxs-lookup"><span data-stu-id="c11fd-110">**Different Signature**.</span></span> <span data-ttu-id="c11fd-111">Jede überladene Version muss alle anderen überladenen Versionen in mindestens einem der folgenden Aspekte unterscheiden:</span><span class="sxs-lookup"><span data-stu-id="c11fd-111">Each overloaded version must differ from all other overloaded versions in at least one of the following respects:</span></span>  
  
    -   <span data-ttu-id="c11fd-112">Anzahl von Parametern</span><span class="sxs-lookup"><span data-stu-id="c11fd-112">Number of parameters</span></span>  
  
    -   <span data-ttu-id="c11fd-113">Reihenfolge der Parameter</span><span class="sxs-lookup"><span data-stu-id="c11fd-113">Order of the parameters</span></span>  
  
    -   <span data-ttu-id="c11fd-114">Die Datentypen der Parameter</span><span class="sxs-lookup"><span data-stu-id="c11fd-114">Data types of the parameters</span></span>  
  
    -   <span data-ttu-id="c11fd-115">Anzahl der Typparameter (für eine generische Prozedur)</span><span class="sxs-lookup"><span data-stu-id="c11fd-115">Number of type parameters (for a generic procedure)</span></span>  
  
    -   <span data-ttu-id="c11fd-116">Der Rückgabetyp (nur für eines Konvertierungsoperators)</span><span class="sxs-lookup"><span data-stu-id="c11fd-116">Return type (only for a conversion operator)</span></span>  
  
     <span data-ttu-id="c11fd-117">Zusammen mit den Namen der Prozedur, die vorherigen Elemente werden als bezeichnet die *Signatur* der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="c11fd-117">Together with the procedure name, the preceding items are collectively called the *signature* of the procedure.</span></span> <span data-ttu-id="c11fd-118">Wenn Sie eine überladene Prozedur aufrufen, verwendet der Compiler die Signatur zu um überprüfen, ob der Aufruf mit der Definition übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="c11fd-118">When you call an overloaded procedure, the compiler uses the signature to check that the call correctly matches the definition.</span></span>  
  
-   <span data-ttu-id="c11fd-119">**Elemente, die nicht Teil der Signatur**.</span><span class="sxs-lookup"><span data-stu-id="c11fd-119">**Items Not Part of Signature**.</span></span> <span data-ttu-id="c11fd-120">Sie können sich keine Prozedur überladen, ohne die Signatur variieren.</span><span class="sxs-lookup"><span data-stu-id="c11fd-120">You cannot overload a procedure without varying the signature.</span></span> <span data-ttu-id="c11fd-121">Sie können insbesondere Prozedur durch die Änderung nur eine oder mehrere der folgenden Elemente nicht überladen:</span><span class="sxs-lookup"><span data-stu-id="c11fd-121">In particular, you cannot overload a procedure by varying only one or more of the following items:</span></span>  
  
    -   <span data-ttu-id="c11fd-122">Schlüsselwörter für Prozedurmodifizierer, z. B. `Public`, `Shared`, und `Static`</span><span class="sxs-lookup"><span data-stu-id="c11fd-122">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`</span></span>  
  
    -   <span data-ttu-id="c11fd-123">Parameternamen für Parameter oder Typ</span><span class="sxs-lookup"><span data-stu-id="c11fd-123">Parameter or type parameter names</span></span>  
  
    -   <span data-ttu-id="c11fd-124">Einschränkungen für Typparameter (für eine generische Prozedur)</span><span class="sxs-lookup"><span data-stu-id="c11fd-124">Type parameter constraints (for a generic procedure)</span></span>  
  
    -   <span data-ttu-id="c11fd-125">Parametermodifiziererschlüsselwörter, z. B. `ByRef` und `Optional`</span><span class="sxs-lookup"><span data-stu-id="c11fd-125">Parameter modifier keywords, such as `ByRef` and `Optional`</span></span>  
  
    -   <span data-ttu-id="c11fd-126">Gibt an, ob es sich um einen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="c11fd-126">Whether it returns a value</span></span>  
  
    -   <span data-ttu-id="c11fd-127">Der Datentyp des Rückgabewerts (mit Ausnahme eines Konvertierungsoperators)</span><span class="sxs-lookup"><span data-stu-id="c11fd-127">The data type of the return value (except for a conversion operator)</span></span>  
  
     <span data-ttu-id="c11fd-128">Die Elemente in der vorherigen Liste sind nicht Teil der Signatur.</span><span class="sxs-lookup"><span data-stu-id="c11fd-128">The items in the preceding list are not part of the signature.</span></span> <span data-ttu-id="c11fd-129">Obwohl Sie sie verwenden können, um zwischen überladenen Versionen zu unterscheiden, können Sie sie zwischen überladenen Versionen variieren, die ordnungsgemäß durch ihre Signaturen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="c11fd-129">Although you cannot use them to differentiate between overloaded versions, you can vary them among overloaded versions that are properly differentiated by their signatures.</span></span>  
  
-   <span data-ttu-id="c11fd-130">**Spät gebundene Argumente**.</span><span class="sxs-lookup"><span data-stu-id="c11fd-130">**Late-Bound Arguments**.</span></span> <span data-ttu-id="c11fd-131">Wenn Sie eine spät gebundenen Objektvariable an eine überladene Version übergeben möchten, müssen Sie die entsprechende Parameter als deklarieren <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="c11fd-131">If you intend to pass a late bound object variable to an overloaded version, you must declare the appropriate parameter as <xref:System.Object>.</span></span>  
  
## <a name="multiple-versions-of-a-procedure"></a><span data-ttu-id="c11fd-132">Mehrere Versionen einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="c11fd-132">Multiple Versions of a Procedure</span></span>  
 <span data-ttu-id="c11fd-133">Angenommen, Sie schreiben eine `Sub` Verfahren zum Veröffentlichen einer Transaktions anhand eines Kunden, und Sie möchten, entweder nach Name oder Nummer eines Kontos für den Kunden zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="c11fd-133">Suppose you are writing a `Sub` procedure to post a transaction against a customer's balance, and you want to be able to refer to the customer either by name or by account number.</span></span> <span data-ttu-id="c11fd-134">Um dies zu berücksichtigen, können Sie definieren zwei verschiedene `Sub` Prozeduren, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="c11fd-134">To accommodate this, you can define two different `Sub` procedures, as in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#73)]  
  
### <a name="overloaded-versions"></a><span data-ttu-id="c11fd-135">Überladene Versionen</span><span class="sxs-lookup"><span data-stu-id="c11fd-135">Overloaded Versions</span></span>  
 <span data-ttu-id="c11fd-136">Eine Alternative ist, einen Namen für die einzelnen Prozedur zu überladen.</span><span class="sxs-lookup"><span data-stu-id="c11fd-136">An alternative is to overload a single procedure name.</span></span> <span data-ttu-id="c11fd-137">Sie können die [Überladungen](../../../../visual-basic/language-reference/modifiers/overloads.md) Schlüsselwort, um eine Version der Prozedur für jede Parameterliste wie folgt definieren:</span><span class="sxs-lookup"><span data-stu-id="c11fd-137">You can use the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword to define a version of the procedure for each parameter list, as follows:</span></span>  
  
 [!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]  
  
#### <a name="additional-overloads"></a><span data-ttu-id="c11fd-138">Zusätzliche Überladungen</span><span class="sxs-lookup"><span data-stu-id="c11fd-138">Additional Overloads</span></span>  
 <span data-ttu-id="c11fd-139">Wenn Sie auch Transaktionsbetrags entweder akzeptieren möchten `Decimal` oder `Single`, überladen Sie weitere `post` um diese Variante zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c11fd-139">If you also wanted to accept a transaction amount in either `Decimal` or `Single`, you could further overload `post` to allow for this variation.</span></span> <span data-ttu-id="c11fd-140">In diesem Fall auf jede der Überladungen im vorherigen Beispiel, würden Sie haben vier `Sub` -Prozeduren mit dem gleichen Namen mit vier unterschiedlichen Signaturen.</span><span class="sxs-lookup"><span data-stu-id="c11fd-140">If you did this to each of the overloads in the preceding example, you would have four `Sub` procedures, all with the same name but with four different signatures.</span></span>  
  
## <a name="advantages-of-overloading"></a><span data-ttu-id="c11fd-141">Vorteile des Überladens</span><span class="sxs-lookup"><span data-stu-id="c11fd-141">Advantages of Overloading</span></span>  
 <span data-ttu-id="c11fd-142">Der Vorteil der überladen einer Prozedur ist die Flexibilität des Aufrufs.</span><span class="sxs-lookup"><span data-stu-id="c11fd-142">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="c11fd-143">Verwenden der `post` Prozedur deklariert, im vorherigen Beispiel der aufrufende Code erhalten die Kunden-ID als ein `String` oder `Integer`, und rufen Sie dann in beiden Fällen das gleiche Verfahren.</span><span class="sxs-lookup"><span data-stu-id="c11fd-143">To use the `post` procedure declared in the preceding example, the calling code can obtain the customer identification as either a `String` or an `Integer`, and then call the same procedure in either case.</span></span> <span data-ttu-id="c11fd-144">Dies wird anhand des folgenden Beispiels veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="c11fd-144">The following example illustrates this:</span></span>  
  
 [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
 [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
## <a name="see-also"></a><span data-ttu-id="c11fd-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c11fd-145">See also</span></span>

- [<span data-ttu-id="c11fd-146">Verfahren</span><span class="sxs-lookup"><span data-stu-id="c11fd-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="c11fd-147">Vorgehensweise: Definieren Sie mehrerer Versionen einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="c11fd-147">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="c11fd-148">Vorgehensweise: Aufrufen einer überladenen Prozedur</span><span class="sxs-lookup"><span data-stu-id="c11fd-148">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="c11fd-149">Vorgehensweise: Überladen einer Prozedur mit optionalen Parametern</span><span class="sxs-lookup"><span data-stu-id="c11fd-149">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="c11fd-150">Vorgehensweise: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern</span><span class="sxs-lookup"><span data-stu-id="c11fd-150">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="c11fd-151">Überlegungen zur Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="c11fd-151">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="c11fd-152">Überladungsauflösung</span><span class="sxs-lookup"><span data-stu-id="c11fd-152">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="c11fd-153">Overloads</span><span class="sxs-lookup"><span data-stu-id="c11fd-153">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="c11fd-154">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c11fd-154">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
