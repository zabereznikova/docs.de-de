---
title: Die Anweisung ist innerhalb einer Methode oder eines mehrzeiligen Lambda-Ausdrucks nicht gültig.
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: cef992c3eaa2b82bbf5e8993f9fccd64ae388c95
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159676"
---
# <a name="bc30024-statement-is-not-valid-inside-a-methodmultiline-lambda"></a>BC30024: die Anweisung ist innerhalb einer Methode/eines mehrzeiligen Lambda-Ausdrucks ungültig.

Die-Anweisung ist in einer-,-,-oder-Eigenschaften `Sub` `Function` Prozedur ungültig `Get` `Set` . Einige-Anweisungen können auf Modul-oder Klassenebene platziert werden. Andere, wie z `Option Strict` . b., müssen sich auf der Namespace Ebene befinden und vor allen anderen Deklarationen stehen.

 **Fehler-ID:** BC30024

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Entfernen Sie die-Anweisung aus der Prozedur.

## <a name="see-also"></a>Siehe auch

- [Sub-Anweisung](../statements/sub-statement.md)
- [Function-Anweisung](../statements/function-statement.md)
- [Get-Anweisung](../statements/get-statement.md)
- [Set-Anweisung](../statements/set-statement.md)
