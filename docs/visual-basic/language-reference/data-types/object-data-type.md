---
title: Object Data Type
ms.date: 07/20/2015
f1_keywords:
- vb.Object
- vb.Variant
helpviewer_keywords:
- object variables [Visual Basic], Object type
- data types [Visual Basic], assigning
- Object data type
- Object data type [Visual Basic], reference
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
ms.openlocfilehash: 14770e74a0169dba3a45a04845dd32323e6201e3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415582"
---
# <a name="object-data-type"></a>Object Data Type

Enthält Adressen, die auf-Objekte verweisen. Sie können einem beliebigen Verweistyp (Zeichenfolge, Array, Klasse oder Schnittstelle) eine `Object` Variable zuweisen. Eine `Object` Variable kann auch auf Daten eines beliebigen Werttyps (numerisch, `Boolean` , `Char` , `Date` , Struktur oder Enumeration) verweisen.

## <a name="remarks"></a>Bemerkungen

Der- `Object` Datentyp kann auf Daten eines beliebigen Datentyps verweisen, einschließlich aller von Ihrer Anwendung erkannten Objektinstanzen. Verwenden `Object` Sie, wenn Sie zum Zeitpunkt der Kompilierung nicht wissen, auf welchen Datentyp die Variable verweisen könnte.

Der Standardwert von `Object` ist `Nothing` (ein NULL-Verweis).

## <a name="data-types"></a>Datentypen

Sie können einer Variablen eine Variable, eine Konstante oder einen Ausdruck eines beliebigen Datentyps zuweisen `Object` . Zum Ermitteln des Datentyps `Object` , auf den sich derzeit eine Variable bezieht, können Sie die- <xref:System.Type.GetTypeCode%2A> Methode der-Klasse verwenden <xref:System.Type?displayProperty=nameWithType> . Dies wird anhand des folgenden Beispiels veranschaulicht.

```vb
Dim myObject As Object
' Suppose myObject has now had something assigned to it.
Dim datTyp As Integer
datTyp = Type.GetTypeCode(myObject.GetType())
```

Beim `Object` Datentyp handelt es sich um einen Verweistyp. Visual Basic behandelt eine Variable jedoch `Object` als Werttyp, wenn Sie auf Daten eines Werttyps verweist.

## <a name="storage"></a>Storage

Jeder Datentyp, auf den er verweist, `Object` enthält eine Variable nicht den Daten Wert selbst, sondern einen Zeiger auf den Wert. Es werden immer vier Bytes im Arbeitsspeicher des Computers verwendet. Dies schließt jedoch nicht den Speicher für die Daten ein, die den Wert der Variablen darstellen. Aufgrund des Codes, in dem der-Zeiger verwendet wird, um die Daten zu suchen, `Object` sind Variablen, die Werttypen verwenden, etwas langsamer als die explizit typisierten Variablen.

## <a name="programming-tips"></a>Programmiertipps

- **Interop-Überlegungen.** Wenn Sie mit Komponenten verbunden sind, die nicht für die .NET Framework geschrieben wurden (z. b. Automatisierungs-oder COM-Objekte), beachten Sie, dass Zeiger Typen in anderen Umgebungen nicht mit dem Visual Basic Typ kompatibel sind `Object` .

- **Leistung:** Eine Variable, die Sie mit dem-Typ deklarieren `Object` , ist flexibel genug, um einen Verweis auf jedes Objekt zu enthalten. Wenn Sie jedoch eine Methode oder Eigenschaft für eine solche Variable aufrufen, wird immer eine *späte Bindung* (zur Laufzeit) verursacht. Um eine *frühe Bindung* (zur Kompilierzeit) und eine bessere Leistung zu erzwingen, deklarieren Sie die Variable mit einem bestimmten Klassennamen, oder wandeln Sie Sie in den spezifischen Datentyp um.

  Wenn Sie eine Objekt Variable deklarieren, versuchen Sie, einen bestimmten Klassentyp zu verwenden, z <xref:System.OperatingSystem> . b. anstelle des generalisierten `Object` Typs. Sie sollten auch die spezifischere verfügbare Klasse verwenden, z <xref:System.Windows.Forms.TextBox> . b. anstelle von <xref:System.Windows.Forms.Control> , damit Sie auf die Eigenschaften und Methoden zugreifen können. In der Regel können Sie die Liste **Klassen** im **Objektkatalog** verwenden, um nach verfügbaren Klassennamen zu suchen.

- **Tet.** Alle Datentypen und alle Verweis Typen werden auf den- `Object` Datentyp erweitert. Dies bedeutet, dass Sie jeden Typ in konvertieren können, `Object` ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType> Fehler auftritt.

  Wenn Sie jedoch zwischen Werttypen und konvertieren `Object` , führt Visual Basic Vorgänge mit dem Namen *Boxing* und *Unboxing*aus, wodurch die Ausführung langsamer wird.

- **Geben Sie Zeichen ein.** `Object`weist kein Literaltyp Zeichen oder Bezeichnertyp Zeichen auf.

- **Framework-Typ.** Der entsprechende Typ in der .NET Framework ist die- <xref:System.Object?displayProperty=nameWithType> Klasse.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine `Object` Variable veranschaulicht, die auf eine Objektinstanz verweist.

```vb
Dim objDb As Object
Dim myCollection As New Collection()
' Suppose myCollection has now been populated.
objDb = myCollection.Item(1)
```

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Object>
- [Datentypen](index.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../keywords/conversion-summary.md)
- [Effiziente Verwendung von Datentypen](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Vorgehensweise: Bestimmen des Bezugs zwischen zwei Objekten](../../programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Vorgehensweise: Bestimmen der Gleichheit zweier Objekte](../../programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
