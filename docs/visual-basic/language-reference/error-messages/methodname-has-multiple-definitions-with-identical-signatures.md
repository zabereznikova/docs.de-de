---
title: <methodname> hat mehrere Definitionen mit identischen Signaturen.
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: 663b22421d1a0e401cfb3c135c99bd097163a78b
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160365"
---
# <a name="bc30269-methodname-has-multiple-definitions-with-identical-signatures"></a>BC30269: " \<methodname> " hat mehrere Definitionen mit identischen Signaturen.

Eine- `Function` oder- `Sub` Prozedur Deklaration verwendet den identischen Prozedur Namen und die gleiche Argumentliste als vorherige Deklaration. Eine mögliche Ursache ist ein Versuch, die ursprüngliche Prozedur zu überladen. Überladene Prozeduren müssen verschiedene Argumentlisten aufweisen.

 **Fehler-ID:** BC30269

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Ändern Sie den Namen der Prozedur oder die Argumentliste, oder entfernen Sie die doppelte Deklaration.

## <a name="see-also"></a>Siehe auch

- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Überlegungen zur Prozedurüberladung](../../programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
