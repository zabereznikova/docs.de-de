---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 50d5a768393e90d28d150b451405e35e6f4c7953
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583040"
---
# <a name="withevents-visual-basic"></a>WithEvents (Visual Basic)
Gibt an, dass eine oder mehrere deklarierte Element Variablen auf eine Instanz einer Klasse verweisen, die Ereignisse hervorrufen kann.

## <a name="remarks"></a>Hinweise

Wenn eine Variable mithilfe von `WithEvents` definiert wird, können Sie deklarativ angeben, dass eine Methode die Ereignisse der Variablen mithilfe des Schlüssel Worts `Handles` behandelt.

Sie können `WithEvents` nur auf Klassen-oder Modulebene verwenden. Dies bedeutet, dass der Deklarations Kontext für eine `WithEvents` Variable eine Klasse oder ein Modul sein muss und weder eine Quelldatei noch ein Namespace, eine Struktur oder eine Prozedur sein darf.

Sie können `WithEvents` für einen Strukturmember nicht verwenden.

Sie können nur einzelne Variablen – keine Arrays – mit `WithEvents` deklarieren.

## <a name="rules"></a>Regeln

**Element Typen.** Sie müssen `WithEvents` Variablen als Objektvariablen deklarieren, damit Sie Klassen Instanzen akzeptieren können. Sie können Sie jedoch nicht als `Object` deklarieren. Sie müssen Sie als eine bestimmte Klasse deklarieren, die die Ereignisse hervorrufen kann.

Der `WithEvents` Modifizierer kann in diesem Kontext verwendet werden: [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)

## <a name="example"></a>Beispiel

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a>Siehe auch

- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Stichwörter](../../../visual-basic/language-reference/keywords/index.md)
- [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)
