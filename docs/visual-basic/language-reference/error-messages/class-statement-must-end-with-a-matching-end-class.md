---
title: "\"Class\" muss mit einem entsprechenden \"End Class\" abgeschlossen werden."
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: 6889e97aad913f6911ce438892752542de0d10f0
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163193"
---
# <a name="bc30481-class-statement-must-end-with-a-matching-end-class"></a>BC30481: die "Class"-Anweisung muss mit einem entsprechenden "End Class" abgeschlossen werden.

`Class` wird zum Initiieren eines- `Class` Blocks verwendet und kann daher nur am Anfang des Blocks angezeigt werden, wobei eine entsprechende- `End Class` Anweisung den Block beendet. Sie haben entweder eine redundante- `Class` Anweisung, oder Sie haben den- `Class` Block nicht mit beendet `End Class` .

 **Fehler-ID:** BC30481

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Suchen und entfernen Sie die unnötige `Class` -Anweisung.

- Schließen Sie den `Class` Block mit einem übereinstimmenden ab `End Class` .

## <a name="see-also"></a>Siehe auch

- [End- \<keyword> Anweisung](../statements/end-keyword-statement.md)
- [Class-Anweisung](../statements/class-statement.md)
