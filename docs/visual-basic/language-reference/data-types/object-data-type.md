---
title: Object-Datentyp (Visual Basic)
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
ms.openlocfilehash: 1ac906494c49810e3d389591b1044f412e7320bc
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2019
ms.locfileid: "68513046"
---
# <a name="object-data-type"></a>Object Data Type

Enthält Adressen, die auf-Objekte verweisen. Sie können einem beliebigen Verweistyp (Zeichenfolge, Array, Klasse oder Schnittstelle) eine `Object` Variable zuweisen. Eine `Object` Variable kann auch auf Daten eines beliebigen Werttyps (numerisch `Char`, `Date` `Boolean`,,, Struktur oder Enumeration) verweisen.

## <a name="remarks"></a>Hinweise

Der `Object` -Datentyp kann auf Daten eines beliebigen Datentyps verweisen, einschließlich aller von Ihrer Anwendung erkannten Objektinstanzen. Verwenden `Object` Sie, wenn Sie zum Zeitpunkt der Kompilierung nicht wissen, auf welchen Datentyp die Variable verweisen könnte.

Der Standardwert von `Object` ist `Nothing` (ein NULL-Verweis).

## <a name="data-types"></a>Datentypen

Sie können einer `Object` Variablen eine Variable, eine Konstante oder einen Ausdruck eines beliebigen Datentyps zuweisen. Zum Ermitteln des Datentyps, auf den sich derzeit eine `Object` Variable bezieht, können Sie die <xref:System.Type.GetTypeCode%2A> -Methode der <xref:System.Type?displayProperty=nameWithType> -Klasse verwenden. Dies wird anhand des folgenden Beispiels veranschaulicht.

```vb
Dim myObject As Object
' Suppose myObject has now had something assigned to it.
Dim datTyp As Integer
datTyp = Type.GetTypeCode(myObject.GetType())
```

Beim `Object` Datentyp handelt es sich um einen Verweistyp. Visual Basic behandelt eine `Object` Variable jedoch als Werttyp, wenn Sie auf Daten eines Werttyps verweist.

## <a name="storage"></a>Speicher

Jeder Datentyp, auf den er verweist `Object` , enthält eine Variable nicht den Daten Wert selbst, sondern einen Zeiger auf den Wert. Es werden immer vier Bytes im Arbeitsspeicher des Computers verwendet. Dies schließt jedoch nicht den Speicher für die Daten ein, die den Wert der Variablen darstellen. Aufgrund des Codes, in dem der-Zeiger verwendet wird, um `Object` die Daten zu suchen, sind Variablen, die Werttypen verwenden, etwas langsamer als die explizit typisierten Variablen.

## <a name="programming-tips"></a>Programmiertipps

- **Interop-Überlegungen.** Wenn Sie mit Komponenten verbunden sind, die nicht für die .NET Framework geschrieben wurden (z. b. Automatisierungs-oder COM-Objekte), beachten Sie, dass Zeiger Typen in anderen `Object` Umgebungen nicht mit dem Visual Basic Typ kompatibel sind.

- **Leistung:** Eine Variable, die Sie mit `Object` dem-Typ deklarieren, ist flexibel genug, um einen Verweis auf jedes Objekt zu enthalten. Wenn Sie jedoch eine Methode oder Eigenschaft für eine solche Variable aufrufen, wird immer eine *späte Bindung* (zur Laufzeit) verursacht. Um eine *frühe Bindung* (zur Kompilierzeit) und eine bessere Leistung zu erzwingen, deklarieren Sie die Variable mit einem bestimmten Klassennamen, oder wandeln Sie Sie in den spezifischen Datentyp um.

  Wenn Sie eine Objekt Variable deklarieren, versuchen Sie, einen bestimmten Klassentyp zu <xref:System.OperatingSystem>verwenden, z. b `Object` . anstelle des generalisierten Typs. Sie sollten auch die spezifischere verfügbare Klasse verwenden, z <xref:System.Windows.Forms.TextBox> . b <xref:System.Windows.Forms.Control>. anstelle von, damit Sie auf die Eigenschaften und Methoden zugreifen können. In der Regel können Sie die Liste **Klassen** im **Objektkatalog** verwenden, um nach verfügbaren Klassennamen zu suchen.

- **Tet.** Alle Datentypen und alle Verweis Typen werden auf den `Object` -Datentyp erweitert. Dies bedeutet, dass Sie jeden Typ in `Object` konvertieren können, <xref:System.OverflowException?displayProperty=nameWithType> ohne dass ein Fehler auftritt.

  Wenn Sie jedoch zwischen Werttypen und `Object`konvertieren, führt Visual Basic Vorgänge mit dem Namen *Boxing* und *Unboxing*aus, wodurch die Ausführung langsamer wird.

- **Geben Sie Zeichen ein.** `Object`weist kein Literaltyp Zeichen oder Bezeichnertyp Zeichen auf.

- **Frameworktyp.** Der entsprechende Typ in der .NET Framework ist die <xref:System.Object?displayProperty=nameWithType> -Klasse.

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
- [Vorgehensweise: Bestimmen, ob zwei Objekte verknüpft sind](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Vorgehensweise: Bestimmen, ob zwei Objekte identisch sind](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
