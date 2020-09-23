---
title: 'Vorgehensweise: Übergeben von Argumenten an eine Prozedur'
ms.date: 07/20/2015
helpviewer_keywords:
- arguments [Visual Basic], passing to procedures
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], calling
- argument passing [Visual Basic], procedures
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
ms.openlocfilehash: 816d6388a0dbb7ae346074d258ff651c793c5e0e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071507"
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a>Gewusst wie: Übergeben von Argumenten an eine Prozedur (Visual Basic)

Wenn Sie eine Prozedur aufzurufen, befolgen Sie den Namen der Prozedur mit einer Argumentliste in Klammern. Sie geben ein Argument an, das allen erforderlichen Parametern entspricht, die die Prozedur definiert, und Sie können optional Argumente für die Parameter bereitstellen `Optional` . Wenn Sie im-Befehl keinen- `Optional` Parameter angeben, müssen Sie ein Komma einschließen, um die Position in der Argumentliste zu markieren, wenn Sie nachfolgende Argumente angeben.  
  
 Wenn Sie beabsichtigen, ein Argument eines Datentyps zu übergeben, das sich von dem des entsprechenden Parameters unterscheidet (z. b. `Byte` in) `String` , können Sie den Schalter für die Typüberprüfung ([Option Strict-Anweisung](../../../language-reference/statements/option-strict-statement.md)) auf festlegen `Off` . Wenn `Option Strict` ist `On` , müssen Sie entweder Erweiterungs Konvertierungen oder explizite Konvertierungs Schlüsselwörter verwenden. Weitere Informationen finden Sie unter [erweiternde und einschränkende Konvertierungen](../data-types/widening-and-narrowing-conversions.md) und [Typkonvertierungs Funktionen](../../../language-reference/functions/type-conversion-functions.md).  
  
 Weitere Informationen finden Sie unter [Prozedur Parameter und-Argumente](./procedure-parameters-and-arguments.md).  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a>So übergeben Sie ein oder mehrere Argumente an eine Prozedur  
  
1. Befolgen Sie in der aufrufenden Anweisung den Prozedur Namen mit Klammern.  
  
2. Fügen Sie innerhalb der Klammern eine Argumentliste ein. Fügen Sie ein Argument für jeden erforderlichen Parameter ein, der von der Prozedur definiert wird, und trennen Sie die Argumente durch Kommas.  
  
3. Stellen Sie sicher, dass jedes Argument ein gültiger Ausdruck ist, der einen-Datentyp ergibt, der in den Typ konvertiert wird, den die Prozedur für den entsprechenden Parameter definiert.  
  
4. Wenn ein Parameter als [optional](../../../language-reference/modifiers/optional.md)definiert ist, können Sie ihn entweder in die Argumentliste einschließen oder ihn weglassen. Wenn Sie es weglassen, verwendet die Prozedur den für diesen Parameter definierten Standardwert.  
  
5. Wenn Sie ein Argument für einen Parameter weglassen `Optional` und in der Parameterliste ein weiterer Parameter vorhanden ist, können Sie die Position des ausgelassenen Arguments mit einem zusätzlichen Komma in der Argumentliste markieren.  
  
     Im folgenden Beispiel wird die Visual Basic- <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> Funktion aufgerufen.  
  
     [!code-vb[VbVbcnProcedures#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#34)]  
  
     Im vorangehenden Beispiel wird das erforderliche erste Argument angegeben, das die anzuzeigende Meldungs Zeichenfolge ist. Es lässt ein Argument für den optionalen zweiten Parameter aus, das die Schaltflächen angibt, die im Meldungs Feld angezeigt werden sollen. Da der-Befehl keinen Wert bereitstellt, `MsgBox` verwendet den Standardwert, `MsgBoxStyle.OKOnly` , der nur eine Schaltfläche " **OK** " anzeigt.  
  
     Das zweite Komma in der Argumentliste markiert die Stelle des ausgelassenen zweiten Arguments, und die letzte Zeichenfolge wird an den optionalen dritten Parameter von übergeben `MsgBox` . Dies ist der Text, der in der Titelleiste angezeigt werden soll.  
  
## <a name="see-also"></a>Siehe auch

- [Sub-Prozeduren](./sub-procedures.md)
- [Function-Prozeduren](./function-procedures.md)
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Operatorprozeduren](./operator-procedures.md)
- [Vorgehensweise: Definieren eines Parameters für eine Prozedur](./how-to-define-a-parameter-for-a-procedure.md)
- [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)
- [Rekursive Prozeduren](./recursive-procedures.md)
- [Prozedurüberladung](./procedure-overloading.md)
- [Objekte und Klassen](../objects-and-classes/index.md)
- [Objektorientierte Programmierung (Visual Basic)](../../concepts/object-oriented-programming.md)
