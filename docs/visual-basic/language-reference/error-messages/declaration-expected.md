---
title: Deklaration erwartet.
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: 2755f5afcb96ca7a6c4d140908649390dd66d571
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162699"
---
# <a name="bc30188-declaration-expected"></a>BC30188: Deklaration erwartet

Eine nicht deklarative Anweisung, z. b. eine Zuweisungs-oder Schleifen Anweisung, findet außerhalb der Prozeduren statt. Nur Deklarationen sind außerhalb der Prozeduren zulässig.

 Alternativ wird ein Programmier Element ohne Deklarations Schlüsselwort, wie z `Dim` . b. oder, deklariert `Const` .

 **Fehler-ID:** BC30188

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Verschieben Sie die nicht deklarative Anweisung in den Text einer Prozedur.

- Beginnen Sie die Deklaration mit einem entsprechenden Deklarations Schlüsselwort.

- Stellen Sie sicher, dass ein Deklarations Schlüsselwort falsch geschrieben ist.

## <a name="see-also"></a>Siehe auch

- [Vorgehensweisen](../../programming-guide/language-features/procedures/index.md)
- [Dim-Anweisung](../statements/dim-statement.md)
