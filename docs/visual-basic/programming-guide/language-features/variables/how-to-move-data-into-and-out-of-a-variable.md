---
title: 'Gewusst wie: Verschieben von Daten in und aus einer Variablen'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: bc5a7377a5e2e4c7ebe7291fd5f0093c4d6e996d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346903"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a>Gewusst wie: Verschieben von Daten in und aus einer Variablen (Visual Basic)

Sie speichern einen Wert in einer Variablen, indem Sie den Variablennamen auf der linken Seite einer Zuweisungsanweisung platzieren.

## <a name="putting-data-in-a-variable"></a>Einfügen von Daten in eine Variable

#### <a name="to-store-a-value-in-a-variable"></a>So speichern Sie einen Wert in einer Variablen

- Verwenden Sie den Variablennamen auf der linken Seite einer Zuweisungsanweisung.

    Im folgenden Beispiel wird der Wert der Variablen `alpha`festgelegt.

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

  Im folgenden Beispiel wird der Wert der Variablen `startValue` gelesen und dann der Wert der Variablen `counter` in einem Ausdruck verwendet.

  ```vb
  counter = startValue
  cellValue = (counter + 5) ^ 2
  ```

  Der Wert der-Variablen ist an dem Ausdruck genau wie eine Konstante beteiligt und wird dann in der Variablen oder der Eigenschaft auf der linken Seite der Zuweisungsanweisung gespeichert.

## <a name="see-also"></a>Siehe auch

- [Variablen](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
