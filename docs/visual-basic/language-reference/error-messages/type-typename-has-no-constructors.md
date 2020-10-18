---
title: Der Typ "<typename>" hat keinen Konstruktor.
ms.date: 07/20/2015
f1_keywords:
- bc30251
- vbc30251
helpviewer_keywords:
- BC30251
ms.assetid: aff3e1df-abe6-4bc0-9abc-a1e70514c561
ms.openlocfilehash: 249bcb7020f26c7c43d560e91ef7a34e4dc64470
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161178"
---
# <a name="bc30251-type-typename-has-no-constructors"></a>BC30251: der Typ " \<typename> " hat keine Konstruktoren.

Ein Typ unterstützt nicht den Aufruf von `Sub New()`. Eine mögliche Ursache ist ein beschädigter Compiler oder eine fehlerhafte Binärdatei.

 **Fehler-ID:** BC30251

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Wenn sich der Typ in einem anderen Projekt oder in einer referenzierten Datei befindet, installieren Sie das Projekt oder die Datei erneut.

2. Wenn sich der Typ im gleichen Projekt befindet, kompilieren Sie die Assembly mit dem Typ neu.

3. Wenn der Fehler erneut auftritt, installieren Sie den Visual Basic-Compiler neu.

4. Wenn der Fehler weiterhin besteht, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.

## <a name="see-also"></a>Siehe auch

- [Objekte und Klassen](../../programming-guide/language-features/objects-and-classes/index.md)
- [Sprechen Sie mit uns](/visualstudio/ide/feedback-options)
