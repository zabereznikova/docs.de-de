---
title: 'Vorgehensweise: Verschieben von Daten in eine und aus einer Variablen'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: fe19a6160623aa9ea867becdf7a15b51319abf45
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410437"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a>Gewusst wie: Verschieben von Daten in und aus einer Variablen (Visual Basic)

Sie speichern einen Wert in einer Variablen, indem Sie den Variablennamen auf der linken Seite einer Zuweisungsanweisung platzieren.

## <a name="putting-data-in-a-variable"></a>Einfügen von Daten in eine Variable

#### <a name="to-store-a-value-in-a-variable"></a>So speichern Sie einen Wert in einer Variablen

- Verwenden Sie den Variablennamen auf der linken Seite einer Zuweisungsanweisung.

    Im folgenden Beispiel wird der Wert der-Variablen festgelegt `alpha` .

    ```vb
    alpha = (beta * 6.27) / (gamma + 2.1)
    ```

    Der auf der rechten Seite der Zuweisungsanweisung generierte Wert wird in der Variablen gespeichert.

## <a name="getting-data-from-a-variable"></a>Erhalten von Daten aus einer Variablen

Sie rufen den Wert einer Variablen ab, indem Sie den Variablennamen in einen Ausdruck einschließen.

#### <a name="to-retrieve-a-value-from-a-variable"></a>So rufen Sie einen Wert aus einer Variablen ab

- Verwenden Sie den Variablennamen in einem Ausdruck. Sie können eine Variable überall dort verwenden, wo Sie eine Konstante oder einen Literalwert verwenden können, außer in einem Ausdruck, der den Wert einer Konstanten definiert.

  \- oder -

- Verwenden Sie den Variablennamen nach dem Gleichheits `=` Zeichen () in einer Zuweisungsanweisung.

  Im folgenden Beispiel wird der Wert der-Variablen gelesen, `startValue` und anschließend wird der Wert der-Variablen `counter` in einem Ausdruck verwendet.

  ```vb
  counter = startValue
  cellValue = (counter + 5) ^ 2
  ```

  Der Wert der-Variablen ist an dem Ausdruck genau wie eine Konstante beteiligt und wird dann in der Variablen oder der Eigenschaft auf der linken Seite der Zuweisungsanweisung gespeichert.

## <a name="see-also"></a>Weitere Informationen

- [Variablen](index.md)
- [Variablen Deklaration](variable-declaration.md)
- [Objektvariablen](object-variables.md)
