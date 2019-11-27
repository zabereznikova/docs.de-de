---
title: Prozedurüberladung
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
ms.openlocfilehash: 41a971896fe726cbe9849fd46334910e7288afe0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352586"
---
# <a name="procedure-overloading-visual-basic"></a><span data-ttu-id="bbc10-102">Prozedurüberladung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bbc10-102">Procedure Overloading (Visual Basic)</span></span>

<span data-ttu-id="bbc10-103">Das *überladen* einer Prozedur bedeutet, dass Sie in mehreren Versionen definiert wird, wobei der gleiche Name, aber unterschiedliche Parameterlisten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bbc10-103">*Overloading* a procedure means defining it in multiple versions, using the same name but different parameter lists.</span></span> <span data-ttu-id="bbc10-104">Der Zweck der Überladung besteht darin, mehrere eng verwandte Versionen einer Prozedur zu definieren, ohne Sie nach Namen zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="bbc10-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span> <span data-ttu-id="bbc10-105">Zu diesem Zweck verändern Sie die Parameterliste.</span><span class="sxs-lookup"><span data-stu-id="bbc10-105">You do this by varying the parameter list.</span></span>

## <a name="overloading-rules"></a><span data-ttu-id="bbc10-106">Überladen von Regeln</span><span class="sxs-lookup"><span data-stu-id="bbc10-106">Overloading Rules</span></span>

<span data-ttu-id="bbc10-107">Wenn Sie eine Prozedur überladen, gelten die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="bbc10-107">When you overload a procedure, the following rules apply:</span></span>

- <span data-ttu-id="bbc10-108">**Gleicher Name**.</span><span class="sxs-lookup"><span data-stu-id="bbc10-108">**Same Name**.</span></span> <span data-ttu-id="bbc10-109">Jede überladene Version muss denselben Prozedur Namen verwenden.</span><span class="sxs-lookup"><span data-stu-id="bbc10-109">Each overloaded version must use the same procedure name.</span></span>

- <span data-ttu-id="bbc10-110">**Andere Signatur**.</span><span class="sxs-lookup"><span data-stu-id="bbc10-110">**Different Signature**.</span></span> <span data-ttu-id="bbc10-111">Jede überladene Version muss sich von allen anderen überladenen Versionen in mindestens einem der folgenden Aspekte unterscheiden:</span><span class="sxs-lookup"><span data-stu-id="bbc10-111">Each overloaded version must differ from all other overloaded versions in at least one of the following respects:</span></span>

  - <span data-ttu-id="bbc10-112">Anzahl von Parametern</span><span class="sxs-lookup"><span data-stu-id="bbc10-112">Number of parameters</span></span>

  - <span data-ttu-id="bbc10-113">Reihenfolge der Parameter</span><span class="sxs-lookup"><span data-stu-id="bbc10-113">Order of the parameters</span></span>

  - <span data-ttu-id="bbc10-114">Datentypen der Parameter</span><span class="sxs-lookup"><span data-stu-id="bbc10-114">Data types of the parameters</span></span>

  - <span data-ttu-id="bbc10-115">Anzahl der Typparameter (für eine generische Prozedur)</span><span class="sxs-lookup"><span data-stu-id="bbc10-115">Number of type parameters (for a generic procedure)</span></span>

  - <span data-ttu-id="bbc10-116">Rückgabetyp (nur für einen Konvertierungs Operator)</span><span class="sxs-lookup"><span data-stu-id="bbc10-116">Return type (only for a conversion operator)</span></span>

  <span data-ttu-id="bbc10-117">Zusammen mit dem Namen der Prozedur werden die vorangehenden Elemente kollektiv als *Signatur* der Prozedur bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="bbc10-117">Together with the procedure name, the preceding items are collectively called the *signature* of the procedure.</span></span> <span data-ttu-id="bbc10-118">Wenn Sie eine überladene Prozedur aufzurufen, prüft der Compiler mithilfe der Signatur, ob der-Befehl ordnungsgemäß mit der Definition übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="bbc10-118">When you call an overloaded procedure, the compiler uses the signature to check that the call correctly matches the definition.</span></span>

- <span data-ttu-id="bbc10-119">**Elemente sind nicht Teil der Signatur**.</span><span class="sxs-lookup"><span data-stu-id="bbc10-119">**Items Not Part of Signature**.</span></span> <span data-ttu-id="bbc10-120">Eine Prozedur kann nicht überladen werden, ohne die Signatur zu verändern.</span><span class="sxs-lookup"><span data-stu-id="bbc10-120">You cannot overload a procedure without varying the signature.</span></span> <span data-ttu-id="bbc10-121">Insbesondere ist es nicht möglich, eine Prozedur zu überladen, indem Sie nur ein oder mehrere der folgenden Elemente unterscheiden:</span><span class="sxs-lookup"><span data-stu-id="bbc10-121">In particular, you cannot overload a procedure by varying only one or more of the following items:</span></span>

  - <span data-ttu-id="bbc10-122">Modifiziererschlüsselwörter für Prozeduren, z. b. `Public``Shared`und `Static`</span><span class="sxs-lookup"><span data-stu-id="bbc10-122">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`</span></span>

  - <span data-ttu-id="bbc10-123">Parameternamen oder Typparameter Namen</span><span class="sxs-lookup"><span data-stu-id="bbc10-123">Parameter or type parameter names</span></span>

  - <span data-ttu-id="bbc10-124">Typparameter Einschränkungen (für eine generische Prozedur)</span><span class="sxs-lookup"><span data-stu-id="bbc10-124">Type parameter constraints (for a generic procedure)</span></span>

  - <span data-ttu-id="bbc10-125">Parametermodifiziererschlüsselwörter wie `ByRef` und `Optional`</span><span class="sxs-lookup"><span data-stu-id="bbc10-125">Parameter modifier keywords, such as `ByRef` and `Optional`</span></span>

  - <span data-ttu-id="bbc10-126">Ob ein Wert zurückgegeben wird</span><span class="sxs-lookup"><span data-stu-id="bbc10-126">Whether it returns a value</span></span>

  - <span data-ttu-id="bbc10-127">Der Datentyp des Rückgabewerts (mit Ausnahme eines Konvertierungs Operators).</span><span class="sxs-lookup"><span data-stu-id="bbc10-127">The data type of the return value (except for a conversion operator)</span></span>

  <span data-ttu-id="bbc10-128">Die Elemente in der vorangehenden Liste sind nicht Teil der Signatur.</span><span class="sxs-lookup"><span data-stu-id="bbc10-128">The items in the preceding list are not part of the signature.</span></span> <span data-ttu-id="bbc10-129">Obwohl Sie Sie nicht verwenden können, um zwischen überladenen Versionen zu unterscheiden, können Sie Sie von überladenen Versionen unterscheiden, die sich durch ihre Signaturen ordnungsgemäß</span><span class="sxs-lookup"><span data-stu-id="bbc10-129">Although you cannot use them to differentiate between overloaded versions, you can vary them among overloaded versions that are properly differentiated by their signatures.</span></span>

- <span data-ttu-id="bbc10-130">**Spät gebundene Argumente**.</span><span class="sxs-lookup"><span data-stu-id="bbc10-130">**Late-Bound Arguments**.</span></span> <span data-ttu-id="bbc10-131">Wenn Sie beabsichtigen, eine spät gebundene Objekt Variable an eine überladene Version zu übergeben, müssen Sie den entsprechenden Parameter als <xref:System.Object>deklarieren.</span><span class="sxs-lookup"><span data-stu-id="bbc10-131">If you intend to pass a late bound object variable to an overloaded version, you must declare the appropriate parameter as <xref:System.Object>.</span></span>

## <a name="multiple-versions-of-a-procedure"></a><span data-ttu-id="bbc10-132">Mehrere Versionen einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="bbc10-132">Multiple Versions of a Procedure</span></span>

<span data-ttu-id="bbc10-133">Angenommen, Sie schreiben eine `Sub` Prozedur, um eine Transaktion für den Saldo eines Kunden zu veröffentlichen, und Sie möchten auf den Kunden entweder über den Namen oder die Kontonummer verweisen können.</span><span class="sxs-lookup"><span data-stu-id="bbc10-133">Suppose you are writing a `Sub` procedure to post a transaction against a customer's balance, and you want to be able to refer to the customer either by name or by account number.</span></span> <span data-ttu-id="bbc10-134">Um dies zu ermöglichen, können Sie zwei verschiedene `Sub` Prozeduren definieren, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="bbc10-134">To accommodate this, you can define two different `Sub` procedures, as in the following example:</span></span>

[!code-vb[VbVbcnProcedures#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#73)]

### <a name="overloaded-versions"></a><span data-ttu-id="bbc10-135">Überladene Versionen</span><span class="sxs-lookup"><span data-stu-id="bbc10-135">Overloaded Versions</span></span>

<span data-ttu-id="bbc10-136">Eine Alternative besteht darin, einen einzelnen Prozedur Namen zu überladen.</span><span class="sxs-lookup"><span data-stu-id="bbc10-136">An alternative is to overload a single procedure name.</span></span> <span data-ttu-id="bbc10-137">Sie können das [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) -Schlüsselwort verwenden, um eine Version der Prozedur für jede Parameterliste wie folgt zu definieren:</span><span class="sxs-lookup"><span data-stu-id="bbc10-137">You can use the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword to define a version of the procedure for each parameter list, as follows:</span></span>

[!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]

#### <a name="additional-overloads"></a><span data-ttu-id="bbc10-138">Zusätzliche über Ladungen</span><span class="sxs-lookup"><span data-stu-id="bbc10-138">Additional Overloads</span></span>

<span data-ttu-id="bbc10-139">Wenn Sie auch einen Transaktionsbetrag entweder in `Decimal` oder `Single`akzeptieren möchten, können Sie die `post` überladen, um diese Abweichung zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="bbc10-139">If you also wanted to accept a transaction amount in either `Decimal` or `Single`, you could further overload `post` to allow for this variation.</span></span> <span data-ttu-id="bbc10-140">Wenn Sie dies für jede der über Ladungen im vorherigen Beispiel getan haben, verfügen Sie über vier `Sub` Prozeduren, die denselben Namen haben, jedoch mit vier unterschiedlichen Signaturen.</span><span class="sxs-lookup"><span data-stu-id="bbc10-140">If you did this to each of the overloads in the preceding example, you would have four `Sub` procedures, all with the same name but with four different signatures.</span></span>

## <a name="advantages-of-overloading"></a><span data-ttu-id="bbc10-141">Vorteile von überladen</span><span class="sxs-lookup"><span data-stu-id="bbc10-141">Advantages of Overloading</span></span>

<span data-ttu-id="bbc10-142">Der Vorteil beim Überladen einer Prozedur ist die Flexibilität des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="bbc10-142">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="bbc10-143">Um die im vorherigen Beispiel deklarierte `post` Prozedur zu verwenden, kann der aufrufende Code die Kunden Identifizierung entweder als `String` oder als `Integer`abrufen und dann die gleiche Prozedur in beiden Fällen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="bbc10-143">To use the `post` procedure declared in the preceding example, the calling code can obtain the customer identification as either a `String` or an `Integer`, and then call the same procedure in either case.</span></span> <span data-ttu-id="bbc10-144">Dies wird anhand des folgenden Beispiels veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="bbc10-144">The following example illustrates this:</span></span>

[!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]

[!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]

## <a name="see-also"></a><span data-ttu-id="bbc10-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bbc10-145">See also</span></span>

- [<span data-ttu-id="bbc10-146">Verfahren</span><span class="sxs-lookup"><span data-stu-id="bbc10-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="bbc10-147">Gewusst wie: Definieren mehrerer Versionen einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="bbc10-147">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="bbc10-148">Gewusst wie: Aufrufen einer überladenen Prozedur</span><span class="sxs-lookup"><span data-stu-id="bbc10-148">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="bbc10-149">Gewusst wie: Überladen einer Prozedur mit optionalen Parametern</span><span class="sxs-lookup"><span data-stu-id="bbc10-149">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="bbc10-150">Gewusst wie: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern</span><span class="sxs-lookup"><span data-stu-id="bbc10-150">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="bbc10-151">Überlegungen zur Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="bbc10-151">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="bbc10-152">Überladungsauflösung</span><span class="sxs-lookup"><span data-stu-id="bbc10-152">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="bbc10-153">Overloads</span><span class="sxs-lookup"><span data-stu-id="bbc10-153">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="bbc10-154">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bbc10-154">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
