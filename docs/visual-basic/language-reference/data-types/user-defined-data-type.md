---
title: Benutzerdefinierter Datentyp
ms.date: 07/20/2015
f1_keywords:
- UserDefined
- UDT
- vb.UDT
- User-Defined
- vb.UserDefined
- vb.User-Defined
helpviewer_keywords:
- user-defined data types [Visual Basic], Visual Basic
- user-defined types
- structures [Visual Basic], as user-defined data types
- user-defined types [Visual Basic], Visual Basic
- user-defined types [Visual Basic], structure declaration
- user-defined types [Visual Basic], structures in Visual Basic
- user-defined data types [Visual Basic], structure declaration
- data types [Visual Basic], assigning
- Structure statement [Visual Basic]
- data types [Visual Basic], user-defined
- user-defined data types [Visual Basic], structures in Visual Basic
- user-defined data types
- types [Visual Basic], user-defined
ms.assetid: be913dca-a364-4a51-96a1-549a1b390b0a
ms.openlocfilehash: fbd9536a54d7fb471d6cb2e130b14a84e40a4940
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415491"
---
# <a name="user-defined-data-type"></a>Benutzerdefinierter Datentyp

Enthält Daten in einem Format, das Sie definieren. Die- `Structure` Anweisung definiert das Format.

In früheren Versionen von Visual Basic wird der benutzerdefinierte Typ (User-Defined Type, UDT) unterstützt. Die aktuelle Version erweitert den UDT in eine- *Struktur*. Eine Struktur ist eine Verkettung von einem *oder mehreren Membern verschiedener Daten* Typen. Visual Basic behandelt eine Struktur als eine Einheit, obwohl Sie auch einzeln auf die Member zugreifen können.

## <a name="remarks"></a>Bemerkungen

Definieren und verwenden Sie einen Structure-Datentyp, wenn Sie verschiedene Datentypen in einer einzelnen Einheit kombinieren müssen, oder wenn keiner der elementaren Datentypen Ihren Anforderungen entspricht.

Der Standardwert eines Structure-Datentyps besteht aus der Kombination der Standardwerte der einzelnen Member.

## <a name="declaration-format"></a>Deklarations Format

Eine Struktur Deklaration beginnt mit der [Structure-Anweisung](../statements/structure-statement.md) und endet mit der- `End Structure` Anweisung. Die- `Structure` Anweisung gibt den Namen der Struktur an, die auch der Bezeichner des Datentyps ist, den die Struktur definiert. Andere Teile des Codes können diesen Bezeichner verwenden, um Variablen, Parameter und Funktions Rückgabewerte für den Datentyp dieser Struktur zu deklarieren.

Die Deklarationen zwischen der `Structure` -Anweisung und der- `End Structure` Anweisung definieren die Member der-Struktur.

## <a name="member-access-levels"></a>Mitglieds Zugriffsebenen

Sie müssen jeden Member mithilfe einer [Dim-Anweisung](../statements/dim-statement.md) oder einer-Anweisung, die die Zugriffsebene angibt, wie z. b. [Public](../modifiers/public.md), [Friend](../modifiers/friend.md)oder [private](../modifiers/private.md), deklarieren. Wenn Sie eine- `Dim` Anweisung verwenden, ist die Zugriffsebene standardmäßig auf Public eingestellt.

## <a name="programming-tips"></a>Programmiertipps

- **Arbeitsspeicher Nutzung.** Wie bei allen zusammengesetzten Datentypen können Sie den gesamten Speicherverbrauch auch bei Strukturen nicht dadurch zuverlässig berechnen, indem Sie die nominalen Speicherbelegungen ihrer Member addieren. Darüber hinaus können Sie nicht davon ausgehen, dass die Member im Speicher in derselben Reihenfolge wie in der Deklaration angeordnet sind. Wenn Sie das Speicherlayout einer Struktur steuern müssen, können Sie das <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut auf die `Structure`-Anweisung anwenden.

- **Interop-Überlegungen.** Wenn Sie mit Komponenten verbunden sind, die nicht für die .NET Framework geschrieben wurden (z. b. Automatisierungs-oder COM-Objekte), beachten Sie, dass benutzerdefinierte Typen in anderen Umgebungen nicht mit Visual Basic Strukturtypen kompatibel sind.

- **Tet.** Es gibt keine automatische Konvertierung in oder aus einem Struktur Datentyp. Mithilfe der [Operator-Anweisung](../statements/operator-statement.md)können Sie Konvertierungs Operatoren für die Struktur definieren, und Sie können jeden Konvertierungs Operator als oder deklarieren `Widening` `Narrowing` .

- **Geben Sie Zeichen ein.** Struktur Datentypen haben kein Literaltyp Zeichen oder Bezeichnertyp Zeichen.

- **Framework-Typ.** In der .NET Framework ist kein entsprechender Typ vorhanden. Alle-Strukturen erben von der .NET Framework-Klasse <xref:System.ValueType?displayProperty=nameWithType> , aber keine einzelne Struktur entspricht <xref:System.ValueType?displayProperty=nameWithType> .

## <a name="example"></a>Beispiel

Das folgende Paradigma zeigt den Umriss der Deklaration einer-Struktur.

```vb
[Public | Protected | Friend | Protected Friend | Private] Structure structname
    {Dim | Public | Friend | Private} member1 As datatype1
    ' ...
    {Dim | Public | Friend | Private} memberN As datatypeN
End Structure
```

## <a name="see-also"></a>Weitere Informationen

- <xref:System.ValueType>
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- [Datentypen](index.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../keywords/conversion-summary.md)
- [Structure Statement](../statements/structure-statement.md)
- [Widening](../modifiers/widening.md)
- [Narrowing](../modifiers/narrowing.md)
- [Strukturen](../../programming-guide/language-features/data-types/structures.md)
- [Effiziente Verwendung von Datentypen](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
