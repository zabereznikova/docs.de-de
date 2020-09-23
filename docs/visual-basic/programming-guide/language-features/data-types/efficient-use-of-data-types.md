---
title: Effiziente Verwendung von Datentypen
ms.date: 07/20/2015
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function [Visual Basic], preferred to Asc
- data types [Visual Basic], using efficiently
- optimization [Visual Basic], data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function [Visual Basic], preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
ms.openlocfilehash: 7f446b264dcb5c05ed6ddfba34acbbf66be0e447
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91084111"
---
# <a name="efficient-use-of-data-types-visual-basic"></a>Effiziente Verwendung von Datentypen (Visual Basic)

Nicht deklarierte Variablen und Variablen, die ohne Datentyp deklariert werden, wird der- `Object` Datentyp zugewiesen. Dies vereinfacht das schnelle Schreiben von Programmen, kann jedoch dazu führen, dass Sie langsamer ausgeführt werden.

## <a name="strong-typing"></a>Starke Typisierung

 Das Angeben von Datentypen für alle Variablen wird als *starke Typisierung*bezeichnet. Die Verwendung der starken Typisierung bietet mehrere Vorteile:

- Sie ermöglicht die IntelliSense-Unterstützung für die Variablen. Dies ermöglicht es Ihnen, ihre Eigenschaften und andere Member anzuzeigen, während Sie den Code eingeben.

- Es nutzt die Compilertypüberprüfung. Dadurch werden Anweisungen abgefangen, die zur Laufzeit aufgrund von Fehlern wie einem Überlauf fehlschlagen können. Sie fängt auch Aufrufe von Methoden für Objekte ab, die Sie nicht unterstützen.

- Dies führt zu einer schnelleren Ausführung des Codes.

## <a name="most-efficient-data-types"></a>Effizienteste Datentypen

 Für Variablen, die niemals Bruchteile enthalten, sind die ganzzahligen Datentypen effizienter als die nicht ganzzahligen Typen. In Visual Basic `Integer` sind und `UInteger` die effizientesten numerischen Typen.

 Bei Bruchzahlen `Double` ist der effizienteste Datentyp, da die Prozessoren auf aktuellen Plattformen Gleit Komma Vorgänge mit doppelter Genauigkeit ausführen. Vorgänge mit sind jedoch `Double` nicht so schnell wie bei den ganzzahligen Typen wie `Integer` .

## <a name="specifying-data-type"></a>Angeben von Datentyp

 Verwenden Sie die [Dim-Anweisung](../../../language-reference/statements/dim-statement.md) , um eine Variable eines bestimmten Typs zu deklarieren. Sie können die Zugriffsebene gleichzeitig mithilfe des Schlüssel Worts [Public](../../../language-reference/modifiers/public.md), [Protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md)oder [private](../../../language-reference/modifiers/private.md) angeben, wie im folgenden Beispiel gezeigt.

```vb
Private x As Double
Protected s As String
```

## <a name="character-conversion"></a>Zeichen Konvertierung

 Die `AscW` `ChrW` Funktionen und funktionieren in Unicode. Sie sollten diese bevorzugt für und verwenden `Asc` `Chr` , die in und aus Unicode übersetzt werden müssen.

## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [Datentypen](index.md)
- [Numerische Datentypen](numeric-data-types.md)
- [Variablen Deklaration](../variables/variable-declaration.md)
- [Verwenden von IntelliSense](/visualstudio/ide/using-intellisense)
