---
title: 'Region- und #End Region-Anweisungen sind im Methodentext/in mehrzeiligen Lambda-Ausdrücken ungültig.'
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: c792fa1a42bde22959ae21439cb2a0a1e4be343f
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162283"
---
# <a name="bc32025-region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>BC32025: die Anweisungen "#Region" und "#End Region" sind innerhalb von Methoden Texten/mehrzeiligen Lambdas ungültig.

Der- `#Region` Block muss auf Klassen-, Modul-oder Namespace Ebene deklariert werden. Ein reduzierbarer Bereich kann eine oder mehrere Prozeduren enthalten, aber er kann nicht innerhalb einer Prozedur beginnen oder enden.

 **Fehler-ID:** BC32025

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Stellen Sie sicher, dass die vorherige Prozedur mit einer-oder-Anweisung ordnungsgemäß beendet wird `End Function` `End Sub` .

2. Stellen Sie sicher, dass `#Region` sich die-und- `#End Region` Direktiven im gleichen Codeblock befinden.

## <a name="see-also"></a>Siehe auch

- [#Region-Direktive](../directives/region-directive.md)
