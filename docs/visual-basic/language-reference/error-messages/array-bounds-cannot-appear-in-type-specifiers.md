---
title: Arraygrenzen können nicht in Typbezeichnern stehen.
ms.date: 07/20/2015
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
ms.openlocfilehash: 951f710160ae1023671773c21c73946f5ae94c2b
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512762"
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a>Arraygrenzen können nicht in Typbezeichnern stehen.

Array Größen können nicht als Teil eines Datentyp Spezifizierers deklariert werden.

**Fehler-ID:** BC30638

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Geben Sie die Größe des Arrays direkt nach dem Variablennamen an, anstatt die Array Größe nach dem Typ zu platzieren, wie im folgenden Beispiel gezeigt.

  ```vb
  Dim Array(8) As Integer
  ```

- Definieren Sie ein Array, und initialisieren Sie es mit der gewünschten Anzahl von Elementen, wie im folgenden Beispiel gezeigt.

  ```vb
  Dim Array2() As Integer = New Integer(8) {}
  ```

## <a name="see-also"></a>Siehe auch

- [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)
