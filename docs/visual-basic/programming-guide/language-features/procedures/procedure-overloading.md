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
# <a name="procedure-overloading-visual-basic"></a>Prozedurüberladung (Visual Basic)

Das *überladen* einer Prozedur bedeutet, dass Sie in mehreren Versionen definiert wird, wobei der gleiche Name, aber unterschiedliche Parameterlisten verwendet werden. Der Zweck der Überladung besteht darin, mehrere eng verwandte Versionen einer Prozedur zu definieren, ohne Sie nach Namen zu unterscheiden. Zu diesem Zweck verändern Sie die Parameterliste.

## <a name="overloading-rules"></a>Überladen von Regeln

Wenn Sie eine Prozedur überladen, gelten die folgenden Regeln:

- **Gleicher Name**. Jede überladene Version muss denselben Prozedur Namen verwenden.

- **Andere Signatur**. Jede überladene Version muss sich von allen anderen überladenen Versionen in mindestens einem der folgenden Aspekte unterscheiden:

  - Anzahl von Parametern

  - Reihenfolge der Parameter

  - Datentypen der Parameter

  - Anzahl der Typparameter (für eine generische Prozedur)

  - Rückgabetyp (nur für einen Konvertierungs Operator)

  Zusammen mit dem Namen der Prozedur werden die vorangehenden Elemente kollektiv als *Signatur* der Prozedur bezeichnet. Wenn Sie eine überladene Prozedur aufzurufen, prüft der Compiler mithilfe der Signatur, ob der-Befehl ordnungsgemäß mit der Definition übereinstimmt.

- **Elemente sind nicht Teil der Signatur**. Eine Prozedur kann nicht überladen werden, ohne die Signatur zu verändern. Insbesondere ist es nicht möglich, eine Prozedur zu überladen, indem Sie nur ein oder mehrere der folgenden Elemente unterscheiden:

  - Modifiziererschlüsselwörter für Prozeduren, wie `Public` , `Shared` und`Static`

  - Parameternamen oder Typparameter Namen

  - Typparameter Einschränkungen (für eine generische Prozedur)

  - Parametermodifiziererschlüsselwörter wie `ByRef` und`Optional`

  - Ob ein Wert zurückgegeben wird

  - Der Datentyp des Rückgabewerts (mit Ausnahme eines Konvertierungs Operators).

  Die Elemente in der vorangehenden Liste sind nicht Teil der Signatur. Obwohl Sie Sie nicht verwenden können, um zwischen überladenen Versionen zu unterscheiden, können Sie Sie von überladenen Versionen unterscheiden, die sich durch ihre Signaturen ordnungsgemäß

- **Spät gebundene Argumente**. Wenn Sie beabsichtigen, eine spät gebundene Objekt Variable an eine überladene Version zu übergeben, müssen Sie den entsprechenden Parameter als deklarieren <xref:System.Object> .

## <a name="multiple-versions-of-a-procedure"></a>Mehrere Versionen einer Prozedur

Angenommen, Sie schreiben eine `Sub` Prozedur, um eine Transaktion für den Saldo eines Kunden zu veröffentlichen, und Sie möchten auf den Kunden entweder über den Namen oder die Kontonummer verweisen können. Um dies zu ermöglichen, können Sie zwei verschiedene `Sub` Prozeduren definieren, wie im folgenden Beispiel gezeigt:

[!code-vb[VbVbcnProcedures#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#73)]

### <a name="overloaded-versions"></a>Überladene Versionen

Eine Alternative besteht darin, einen einzelnen Prozedur Namen zu überladen. Sie können das [Overloads](../../../language-reference/modifiers/overloads.md) -Schlüsselwort verwenden, um eine Version der Prozedur für jede Parameterliste wie folgt zu definieren:

[!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]

#### <a name="additional-overloads"></a>Zusätzliche über Ladungen

Wenn Sie auch einen Transaktionsbetrag in oder akzeptieren möchten `Decimal` `Single` , können Sie eine weitere Überlastung durchlaufen, `post` um diese Abweichung zuzulassen. Wenn Sie dies für jede der über Ladungen im vorherigen Beispiel durchgeführt haben, verfügen Sie über vier `Sub` Prozeduren mit demselben Namen, aber mit vier unterschiedlichen Signaturen.

## <a name="advantages-of-overloading"></a>Vorteile von überladen

Der Vorteil beim Überladen einer Prozedur ist die Flexibilität des Aufrufes. Um die `post` im vorherigen Beispiel deklarierte Prozedur zu verwenden, kann der aufrufende Code die Kunden Identifizierung entweder als `String` oder als `Integer` Abrufen und dann die gleiche Prozedur in beiden Fällen aufrufen. Das folgende Beispiel veranschaulicht dies:

[!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]

[!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]

## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweisen](./index.md)
- [Vorgehensweise: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md)
- [Vorgehensweise: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md)
- [Vorgehensweise: Überladen einer Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Vorgehensweise: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Überlegungen zur Prozedurüberladung](./considerations-in-overloading-procedures.md)
- [Überladungs Auflösung](./overload-resolution.md)
- [Overloads](../../../language-reference/modifiers/overloads.md)
- [Generische Typen in Visual Basic (Visual Basic)](../data-types/generic-types.md)
