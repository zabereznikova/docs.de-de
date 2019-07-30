---
title: 'Vorgehensweise: Verschieben von Daten in und aus einer Variablen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: df55f122c4ea029a383196f8d9684295ac8926aa
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631124"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a>Vorgehensweise: Verschieben von Daten in und aus einer Variablen (Visual Basic)

Sie speichern einen Wert in einer Variablen, indem Sie den Variablennamen auf der linken Seite einer Zuweisungsanweisung platzieren.

## <a name="putting-data-in-a-variable"></a>Einfügen von Daten in eine Variable

#### <a name="to-store-a-value-in-a-variable"></a>So speichern Sie einen Wert in einer Variablen

- Verwenden Sie den Variablennamen auf der linken Seite einer Zuweisungsanweisung.

    Im folgenden Beispiel wird der Wert der-Variablen `alpha`festgelegt.

    ```vb
    alpha = (beta * 6.27) / (gamma + 2.1)
    ```

    Der auf der rechten Seite der Zuweisungsanweisung generierte Wert wird in der Variablen gespeichert.

## <a name="getting-data-from-a-variable"></a>Erhalten von Daten aus einer Variablen

Sie rufen den Wert einer Variablen ab, indem Sie den Variablennamen in einen Ausdruck einschließen.

#### <a name="to-retrieve-a-value-from-a-variable"></a>So rufen Sie einen Wert aus einer Variablen ab

- Verwenden Sie den Variablennamen in einem Ausdruck. Sie können eine Variable überall dort verwenden, wo Sie eine Konstante oder einen Literalwert verwenden können, außer in einem Ausdruck, der den Wert einer Konstanten definiert.

  \- oder -

- Verwenden Sie den Variablennamen nach dem Gleichheitszeichen (`=`) in einer Zuweisungsanweisung.

  Im folgenden Beispiel wird der Wert der-Variablen `startValue` gelesen, und anschließend wird der Wert der `counter` -Variablen in einem Ausdruck verwendet.

  ```vb
  counter = startValue
  cellValue = (counter + 5) ^ 2
  ```

  Der Wert der-Variablen ist an dem Ausdruck genau wie eine Konstante beteiligt und wird dann in der Variablen oder der Eigenschaft auf der linken Seite der Zuweisungsanweisung gespeichert.

## <a name="see-also"></a>Siehe auch

- [Variablen](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
