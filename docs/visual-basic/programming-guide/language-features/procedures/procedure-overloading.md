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
ms.openlocfilehash: f8accc74fbdd9b1d8cf9bc3d8f6ddd26f73452b8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363875"
---
# <a name="procedure-overloading-visual-basic"></a><span data-ttu-id="08646-102">Prozedurüberladung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08646-102">Procedure Overloading (Visual Basic)</span></span>

<span data-ttu-id="08646-103">Das *überladen* einer Prozedur bedeutet, dass Sie in mehreren Versionen definiert wird, wobei der gleiche Name, aber unterschiedliche Parameterlisten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="08646-103">*Overloading* a procedure means defining it in multiple versions, using the same name but different parameter lists.</span></span> <span data-ttu-id="08646-104">Der Zweck der Überladung besteht darin, mehrere eng verwandte Versionen einer Prozedur zu definieren, ohne Sie nach Namen zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="08646-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span> <span data-ttu-id="08646-105">Zu diesem Zweck verändern Sie die Parameterliste.</span><span class="sxs-lookup"><span data-stu-id="08646-105">You do this by varying the parameter list.</span></span>

## <a name="overloading-rules"></a><span data-ttu-id="08646-106">Überladen von Regeln</span><span class="sxs-lookup"><span data-stu-id="08646-106">Overloading Rules</span></span>

<span data-ttu-id="08646-107">Wenn Sie eine Prozedur überladen, gelten die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="08646-107">When you overload a procedure, the following rules apply:</span></span>

- <span data-ttu-id="08646-108">**Gleicher Name**.</span><span class="sxs-lookup"><span data-stu-id="08646-108">**Same Name**.</span></span> <span data-ttu-id="08646-109">Jede überladene Version muss denselben Prozedur Namen verwenden.</span><span class="sxs-lookup"><span data-stu-id="08646-109">Each overloaded version must use the same procedure name.</span></span>

- <span data-ttu-id="08646-110">**Andere Signatur**.</span><span class="sxs-lookup"><span data-stu-id="08646-110">**Different Signature**.</span></span> <span data-ttu-id="08646-111">Jede überladene Version muss sich von allen anderen überladenen Versionen in mindestens einem der folgenden Aspekte unterscheiden:</span><span class="sxs-lookup"><span data-stu-id="08646-111">Each overloaded version must differ from all other overloaded versions in at least one of the following respects:</span></span>

  - <span data-ttu-id="08646-112">Anzahl von Parametern</span><span class="sxs-lookup"><span data-stu-id="08646-112">Number of parameters</span></span>

  - <span data-ttu-id="08646-113">Reihenfolge der Parameter</span><span class="sxs-lookup"><span data-stu-id="08646-113">Order of the parameters</span></span>

  - <span data-ttu-id="08646-114">Datentypen der Parameter</span><span class="sxs-lookup"><span data-stu-id="08646-114">Data types of the parameters</span></span>

  - <span data-ttu-id="08646-115">Anzahl der Typparameter (für eine generische Prozedur)</span><span class="sxs-lookup"><span data-stu-id="08646-115">Number of type parameters (for a generic procedure)</span></span>

  - <span data-ttu-id="08646-116">Rückgabetyp (nur für einen Konvertierungs Operator)</span><span class="sxs-lookup"><span data-stu-id="08646-116">Return type (only for a conversion operator)</span></span>

  <span data-ttu-id="08646-117">Zusammen mit dem Namen der Prozedur werden die vorangehenden Elemente kollektiv als *Signatur* der Prozedur bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="08646-117">Together with the procedure name, the preceding items are collectively called the *signature* of the procedure.</span></span> <span data-ttu-id="08646-118">Wenn Sie eine überladene Prozedur aufzurufen, prüft der Compiler mithilfe der Signatur, ob der-Befehl ordnungsgemäß mit der Definition übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="08646-118">When you call an overloaded procedure, the compiler uses the signature to check that the call correctly matches the definition.</span></span>

- <span data-ttu-id="08646-119">**Elemente sind nicht Teil der Signatur**.</span><span class="sxs-lookup"><span data-stu-id="08646-119">**Items Not Part of Signature**.</span></span> <span data-ttu-id="08646-120">Eine Prozedur kann nicht überladen werden, ohne die Signatur zu verändern.</span><span class="sxs-lookup"><span data-stu-id="08646-120">You cannot overload a procedure without varying the signature.</span></span> <span data-ttu-id="08646-121">Insbesondere ist es nicht möglich, eine Prozedur zu überladen, indem Sie nur ein oder mehrere der folgenden Elemente unterscheiden:</span><span class="sxs-lookup"><span data-stu-id="08646-121">In particular, you cannot overload a procedure by varying only one or more of the following items:</span></span>

  - <span data-ttu-id="08646-122">Modifiziererschlüsselwörter für Prozeduren, wie `Public` , `Shared` und`Static`</span><span class="sxs-lookup"><span data-stu-id="08646-122">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`</span></span>

  - <span data-ttu-id="08646-123">Parameternamen oder Typparameter Namen</span><span class="sxs-lookup"><span data-stu-id="08646-123">Parameter or type parameter names</span></span>

  - <span data-ttu-id="08646-124">Typparameter Einschränkungen (für eine generische Prozedur)</span><span class="sxs-lookup"><span data-stu-id="08646-124">Type parameter constraints (for a generic procedure)</span></span>

  - <span data-ttu-id="08646-125">Parametermodifiziererschlüsselwörter wie `ByRef` und`Optional`</span><span class="sxs-lookup"><span data-stu-id="08646-125">Parameter modifier keywords, such as `ByRef` and `Optional`</span></span>

  - <span data-ttu-id="08646-126">Ob ein Wert zurückgegeben wird</span><span class="sxs-lookup"><span data-stu-id="08646-126">Whether it returns a value</span></span>

  - <span data-ttu-id="08646-127">Der Datentyp des Rückgabewerts (mit Ausnahme eines Konvertierungs Operators).</span><span class="sxs-lookup"><span data-stu-id="08646-127">The data type of the return value (except for a conversion operator)</span></span>

  <span data-ttu-id="08646-128">Die Elemente in der vorangehenden Liste sind nicht Teil der Signatur.</span><span class="sxs-lookup"><span data-stu-id="08646-128">The items in the preceding list are not part of the signature.</span></span> <span data-ttu-id="08646-129">Obwohl Sie Sie nicht verwenden können, um zwischen überladenen Versionen zu unterscheiden, können Sie Sie von überladenen Versionen unterscheiden, die sich durch ihre Signaturen ordnungsgemäß</span><span class="sxs-lookup"><span data-stu-id="08646-129">Although you cannot use them to differentiate between overloaded versions, you can vary them among overloaded versions that are properly differentiated by their signatures.</span></span>

- <span data-ttu-id="08646-130">**Spät gebundene Argumente**.</span><span class="sxs-lookup"><span data-stu-id="08646-130">**Late-Bound Arguments**.</span></span> <span data-ttu-id="08646-131">Wenn Sie beabsichtigen, eine spät gebundene Objekt Variable an eine überladene Version zu übergeben, müssen Sie den entsprechenden Parameter als deklarieren <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="08646-131">If you intend to pass a late bound object variable to an overloaded version, you must declare the appropriate parameter as <xref:System.Object>.</span></span>

## <a name="multiple-versions-of-a-procedure"></a><span data-ttu-id="08646-132">Mehrere Versionen einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="08646-132">Multiple Versions of a Procedure</span></span>

<span data-ttu-id="08646-133">Angenommen, Sie schreiben eine `Sub` Prozedur, um eine Transaktion für den Saldo eines Kunden zu veröffentlichen, und Sie möchten auf den Kunden entweder über den Namen oder die Kontonummer verweisen können.</span><span class="sxs-lookup"><span data-stu-id="08646-133">Suppose you are writing a `Sub` procedure to post a transaction against a customer's balance, and you want to be able to refer to the customer either by name or by account number.</span></span> <span data-ttu-id="08646-134">Um dies zu ermöglichen, können Sie zwei verschiedene `Sub` Prozeduren definieren, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="08646-134">To accommodate this, you can define two different `Sub` procedures, as in the following example:</span></span>

[!code-vb[VbVbcnProcedures#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#73)]

### <a name="overloaded-versions"></a><span data-ttu-id="08646-135">Überladene Versionen</span><span class="sxs-lookup"><span data-stu-id="08646-135">Overloaded Versions</span></span>

<span data-ttu-id="08646-136">Eine Alternative besteht darin, einen einzelnen Prozedur Namen zu überladen.</span><span class="sxs-lookup"><span data-stu-id="08646-136">An alternative is to overload a single procedure name.</span></span> <span data-ttu-id="08646-137">Sie können das [Overloads](../../../language-reference/modifiers/overloads.md) -Schlüsselwort verwenden, um eine Version der Prozedur für jede Parameterliste wie folgt zu definieren:</span><span class="sxs-lookup"><span data-stu-id="08646-137">You can use the [Overloads](../../../language-reference/modifiers/overloads.md) keyword to define a version of the procedure for each parameter list, as follows:</span></span>

[!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]

#### <a name="additional-overloads"></a><span data-ttu-id="08646-138">Zusätzliche über Ladungen</span><span class="sxs-lookup"><span data-stu-id="08646-138">Additional Overloads</span></span>

<span data-ttu-id="08646-139">Wenn Sie auch einen Transaktionsbetrag in oder akzeptieren möchten `Decimal` `Single` , können Sie eine weitere Überlastung durchlaufen, `post` um diese Abweichung zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="08646-139">If you also wanted to accept a transaction amount in either `Decimal` or `Single`, you could further overload `post` to allow for this variation.</span></span> <span data-ttu-id="08646-140">Wenn Sie dies für jede der über Ladungen im vorherigen Beispiel durchgeführt haben, verfügen Sie über vier `Sub` Prozeduren mit demselben Namen, aber mit vier unterschiedlichen Signaturen.</span><span class="sxs-lookup"><span data-stu-id="08646-140">If you did this to each of the overloads in the preceding example, you would have four `Sub` procedures, all with the same name but with four different signatures.</span></span>

## <a name="advantages-of-overloading"></a><span data-ttu-id="08646-141">Vorteile von überladen</span><span class="sxs-lookup"><span data-stu-id="08646-141">Advantages of Overloading</span></span>

<span data-ttu-id="08646-142">Der Vorteil beim Überladen einer Prozedur ist die Flexibilität des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="08646-142">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="08646-143">Um die `post` im vorherigen Beispiel deklarierte Prozedur zu verwenden, kann der aufrufende Code die Kunden Identifizierung entweder als `String` oder als `Integer` Abrufen und dann die gleiche Prozedur in beiden Fällen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="08646-143">To use the `post` procedure declared in the preceding example, the calling code can obtain the customer identification as either a `String` or an `Integer`, and then call the same procedure in either case.</span></span> <span data-ttu-id="08646-144">Das folgende Beispiel veranschaulicht dies:</span><span class="sxs-lookup"><span data-stu-id="08646-144">The following example illustrates this:</span></span>

[!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]

[!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]

## <a name="see-also"></a><span data-ttu-id="08646-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="08646-145">See also</span></span>

- [<span data-ttu-id="08646-146">Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="08646-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="08646-147">Vorgehensweise: Definieren mehrerer Versionen einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="08646-147">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="08646-148">Vorgehensweise: Aufrufen einer überladenen Prozedur</span><span class="sxs-lookup"><span data-stu-id="08646-148">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="08646-149">Vorgehensweise: Überladen einer Prozedur mit optionalen Parametern</span><span class="sxs-lookup"><span data-stu-id="08646-149">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="08646-150">Vorgehensweise: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern</span><span class="sxs-lookup"><span data-stu-id="08646-150">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="08646-151">Überlegungen zur Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="08646-151">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="08646-152">Überladungs Auflösung</span><span class="sxs-lookup"><span data-stu-id="08646-152">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="08646-153">Overloads</span><span class="sxs-lookup"><span data-stu-id="08646-153">Overloads</span></span>](../../../language-reference/modifiers/overloads.md)
- [<span data-ttu-id="08646-154">Generische Typen in Visual Basic (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08646-154">Generic Types in Visual Basic</span></span>](../data-types/generic-types.md)
