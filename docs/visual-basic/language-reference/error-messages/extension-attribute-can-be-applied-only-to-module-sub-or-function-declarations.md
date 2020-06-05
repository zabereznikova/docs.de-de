---
title: Das Extension-Attribut darf nur in Module-, Sub- oder Function-Deklarationen verwendet werden
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: 9b8f49c498699a8f7d1c4b329e82258501aa0c47
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363097"
---
# <a name="extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a>Das Extension-Attribut darf nur in Module-, Sub- oder Function-Deklarationen verwendet werden

Die einzige Möglichkeit zum Erweitern eines Datentyps in Visual Basic besteht darin, eine Erweiterungsmethode in einem Standardmodul zu definieren. Bei der Erweiterungsmethode kann es sich um eine `Sub` Prozedur oder eine `Function` Prozedur handeln. Alle Erweiterungs Methoden müssen mit dem Erweiterungs Attribut, `<Extension()>` , aus dem- <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> Namespace gekennzeichnet werden. Optional kann ein Modul, das eine Erweiterungsmethode enthält, auf dieselbe Weise gekennzeichnet werden. Keine andere Verwendung des Erweiterungs Attributs ist gültig.

**Fehler-ID:** BC36550

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Entfernen Sie das Erweiterungs Attribut.

- Entwerfen Sie Ihre Erweiterung als eine Methode, die in einem umschließenden Modul definiert ist.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine- `Print` Methode für den- `String` Datentyp definiert.

```vb
Imports StringUtility
Imports System.Runtime.CompilerServices
Namespace StringUtility
    <Extension()>
    Module StringExtensions
        <Extension()>
        Public Sub Print (ByVal str As String)
            Console.WriteLine(str)
        End Sub
    End Module
End Namespace
```

## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Attribute](../../programming-guide/concepts/attributes/index.md)
- [Erweiterungsmethoden](../../programming-guide/language-features/procedures/extension-methods.md)
- [Module-Anweisung](../statements/module-statement.md)
