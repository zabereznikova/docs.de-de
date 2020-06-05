---
title: WithEvents
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 48261e27de302c1809c9725e6e2fc0705a803930
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84386775"
---
# <a name="withevents-visual-basic"></a>WithEvents (Visual Basic)
Gibt an, dass eine oder mehrere deklarierte Element Variablen auf eine Instanz einer Klasse verweisen, die Ereignisse hervorrufen kann.

## <a name="remarks"></a>Bemerkungen

Wenn eine Variable mithilfe von definiert wird `WithEvents` , können Sie deklarativ angeben, dass eine Methode die Ereignisse der Variablen mithilfe des `Handles` Schlüssel Worts behandelt.

Sie können `WithEvents` nur auf Klassen-oder Modulebene verwenden. Dies bedeutet, dass der Deklarations Kontext für eine `WithEvents` Variable eine Klasse oder ein Modul sein muss und weder eine Quelldatei noch ein Namespace, eine Struktur oder eine Prozedur sein darf.

Sie können nicht `WithEvents` für einen Strukturmember verwenden.

Sie können nur einzelne Variablen – keine Arrays – mit deklarieren `WithEvents` .

## <a name="rules"></a>Regeln

**Element Typen.** Sie müssen `WithEvents` Variablen als Objektvariablen deklarieren, damit Sie Klassen Instanzen akzeptieren können. Sie können Sie jedoch nicht als deklarieren `Object` . Sie müssen Sie als eine bestimmte Klasse deklarieren, die die Ereignisse hervorrufen kann.

Der- `WithEvents` Modifizierer kann in diesem Kontext verwendet werden: [Dim-Anweisung](../statements/dim-statement.md)

## <a name="example"></a>Beispiel

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a>Weitere Informationen

- [Ziehpunkte](../statements/handles-clause.md)
- [Schlüsselwörter](../keywords/index.md)
- [Ereignisse](../../programming-guide/language-features/events/index.md)
