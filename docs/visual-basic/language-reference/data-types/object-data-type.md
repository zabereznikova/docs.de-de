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
ms.openlocfilehash: 2ccb9b69b865c259d078ed9642d63c7f83514756
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343965"
---
# <a name="object-data-type"></a>Object Data Type

Enthält Adressen, die auf-Objekte verweisen. Sie können einen beliebigen Verweistyp (Zeichenfolge, Array, Klasse oder Schnittstelle) einer `Object` Variablen zuweisen. Eine `Object` Variable kann auch auf Daten eines beliebigen Werttyps (numerisch, `Boolean`, `Char`, `Date`, Struktur oder Enumeration) verweisen.

## <a name="remarks"></a>Hinweise

Der `Object`-Datentyp kann auf Daten eines beliebigen Datentyps verweisen, einschließlich aller von Ihrer Anwendung erkannten Objektinstanzen. Verwenden Sie `Object`, wenn Sie zum Zeitpunkt der Kompilierung nicht wissen, auf welchen Datentyp die Variable verweisen könnte.

Der Standardwert `Object` ist `Nothing` (ein NULL-Verweis).

## <a name="data-types"></a>Datentypen

Sie können einer `Object` Variablen eine Variable, eine Konstante oder einen Ausdruck eines beliebigen Datentyps zuweisen. Zum Ermitteln des Datentyps, auf den sich eine `Object` Variable derzeit bezieht, können Sie die <xref:System.Type.GetTypeCode%2A>-Methode der <xref:System.Type?displayProperty=nameWithType>-Klasse verwenden. Dies wird anhand des folgenden Beispiels veranschaulicht.

```vb
Dim myObject As Object
' Suppose myObject has now had something assigned to it.
Dim datTyp As Integer
datTyp = Type.GetTypeCode(myObject.GetType())
```

Der `Object`-Datentyp ist ein Referenztyp. Visual Basic behandelt jedoch eine `Object` Variable als Werttyp, wenn Sie auf Daten eines Werttyps verweist.

## <a name="storage"></a>Speicher

Jeder Datentyp, auf den er verweist, eine `Object` Variable enthält nicht den Daten Wert selbst, sondern einen Zeiger auf den Wert. Es werden immer vier Bytes im Arbeitsspeicher des Computers verwendet. Dies schließt jedoch nicht den Speicher für die Daten ein, die den Wert der Variablen darstellen. Aufgrund des Codes, in dem der-Zeiger zum Suchen der Daten verwendet wird, sind `Object` Variablen, die Werttypen verwenden, etwas langsamer für den Zugriff als explizit typisierte Variablen.

## <a name="programming-tips"></a>Programmiertipps

- **Interop-Überlegungen.** Wenn Sie mit Komponenten verbunden sind, die nicht für die .NET Framework geschrieben wurden (z. b. Automatisierungs-oder COM-Objekte), beachten Sie, dass Zeiger Typen in anderen Umgebungen nicht mit dem Visual Basic `Object` Typ kompatibel sind.

- **Leistung** Eine Variable, die Sie mit dem `Object`-Typ deklarieren, ist flexibel genug, um einen Verweis auf jedes Objekt zu enthalten. Wenn Sie jedoch eine Methode oder Eigenschaft für eine solche Variable aufrufen, wird immer eine *späte Bindung* (zur Laufzeit) verursacht. Um eine *frühe Bindung* (zur Kompilierzeit) und eine bessere Leistung zu erzwingen, deklarieren Sie die Variable mit einem bestimmten Klassennamen, oder wandeln Sie Sie in den spezifischen Datentyp um.

  Wenn Sie eine Objekt Variable deklarieren, versuchen Sie, einen bestimmten Klassentyp, z. b. <xref:System.OperatingSystem>, anstelle des generalisierten `Object` Typs zu verwenden. Sie sollten auch die spezifischere verfügbare Klasse verwenden, wie z. b. <xref:System.Windows.Forms.TextBox> anstelle von <xref:System.Windows.Forms.Control>, damit Sie auf die Eigenschaften und Methoden zugreifen können. In der Regel können Sie die Liste **Klassen** im **Objektkatalog** verwenden, um nach verfügbaren Klassennamen zu suchen.

- **Tet.** Alle Datentypen und alle Verweis Typen werden auf den Datentyp `Object` erweitert. Dies bedeutet, dass Sie jeden Typ in `Object` konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType> Fehler auftritt.

  Wenn Sie jedoch zwischen Werttypen und `Object`konvertieren, führt Visual Basic Vorgänge aus, die als *Boxing* und *Unboxing*bezeichnet werden. Dadurch wird die Ausführung langsamer.

- **Geben Sie Zeichen ein.** `Object` hat kein Literaltyp Zeichen oder Bezeichnertyp Zeichen.

- **Frameworktyp.** Der entsprechende Typ in der .NET Framework ist die <xref:System.Object?displayProperty=nameWithType> Klasse.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine `Object` Variable veranschaulicht, die auf eine Objektinstanz verweist.

```vb
Dim objDb As Object
Dim myCollection As New Collection()
' Suppose myCollection has now been populated.
objDb = myCollection.Item(1)
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Object>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Gewusst wie: Bestimmen des Bezugs zwischen zwei Objekten](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Gewusst wie: Bestimmen der Gleichheit zweier Objekte](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
