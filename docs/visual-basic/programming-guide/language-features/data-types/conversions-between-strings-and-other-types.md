---
title: Konvertierungen zwischen Zeichenfolgen und anderen Typen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data type conversion [Visual Basic], string
- conversions [Visual Basic], type
- string conversion [Visual Basic]
- conversions [Visual Basic], data type
- type conversion [Visual Basic], string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
ms.openlocfilehash: 38acd9056f9517e6d8b62691cdeb1a2960bec800
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516573"
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a>Konvertierungen zwischen Zeichenfolgen und anderen Typen (Visual Basic)
Sie können numerische, konvertieren `Boolean`, oder Datum/Uhrzeit-Wert, der eine `String`. Sie können auch in umgekehrter Richtung konvertieren, aus einem Zeichenfolgenwert in "Numerisch", `Boolean`, oder `Date` – sofern der Inhalt der Zeichenfolge als gültigen Wert des Zieltyps Daten interpretiert werden können. Ist dies nicht möglich, tritt ein Laufzeitfehler auf.  
  
 Die Konvertierungen für alle diese Zuweisungen in beide Richtungen einschränkende Konvertierungen. Verwenden Sie Schlüsselwörter für die typkonvertierung (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, und `CType`). Die <xref:Microsoft.VisualBasic.Strings.Format%2A> und <xref:Microsoft.VisualBasic.Conversion.Val%2A> Funktionen bieten Ihnen zusätzliche Kontrolle darüber, Konvertierungen zwischen Zeichenfolgen und Zahlen.  
  
 Wenn Sie eine Klasse oder Struktur definiert haben, können Sie definieren, dass Typkonvertierungsoperatoren zwischen `String` und den Typ der Klasse oder Struktur. Weitere Informationen finden Sie unter [wie: Definieren eines Konvertierungsoperators](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="conversion-of-numbers-to-strings"></a>Konvertierung von Zahlen in Zeichenfolgen  
 Können Sie die `Format` Funktion, um eine Zahl in eine formatierte Zeichenfolge zu konvertieren, z. nicht nur die entsprechenden Ziffern b., sondern die Symbole, z. B. Währungszeichen (z. B. `$`), Tausende Trennzeichen oder *Tausender Symbole* (z. B. `,`), und ein Dezimaltrennzeichen (z. B. `.`). `Format` verwendet automatisch die entsprechenden Symbole gemäß der **Ländereinstellungen** Einstellungen in der Windows **Systemsteuerung**.  
  
 Beachten Sie, dass die Verkettung (`&`) Operator Zahl implizit, wie im folgenden Beispiel gezeigt in eine Zeichenfolge konvertieren kann.  
  
```  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a>Konvertierung von Zeichenfolgen in Zahlen  
 Sie können die `Val` Funktion, um die Ziffern in einer Zeichenfolge explizit in eine Zahl zu konvertieren. `Val` liest die Zeichenfolge an, bis ein anderes Zeichen als ein Ziffern, Leerzeichen, Registerkarte, Zeilenvorschub oder Zeitraum erreicht. Die Sequenzen "& O" und "& H" die Basis des Zahlensystems ändern und beenden die Überprüfung. Bis zu seinem lesen Ende `Val` alle entsprechende Zeichen in einen numerischen Wert konvertiert. Die folgende Anweisung gibt z. B. den Wert `141.825`.  
  
 `Val("   14   1.825 miles")`  
  
 Wenn Visual Basic eine Zeichenfolge in einen numerischen Wert konvertiert, verwendet es die **regionale Einstellungen** Einstellungen in der Windows **Systemsteuerung** zum Interpretieren von Tausenden Trennzeichen, Dezimaltrennzeichen und Währungssymbol. Dies bedeutet, dass eine Konvertierung eines festlegen, aber nicht in einer anderen erfolgreich ausgeführt werden kann. Z. B. `"$14.20"` ist akzeptabel, in das Gebietsschema Englisch (Vereinigte Staaten), aber nicht in Gebietsschemas Französisch.  
  
## <a name="see-also"></a>Siehe auch  
 [Typkonvertierung in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Vorgehensweise: Konvertieren eines Objekts in einen anderen Typ in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [Arraykonvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [Datentypen](../../../../visual-basic/language-reference/data-types/index.md)  
 [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Einführung in internationale Anwendungen basierend auf .NET Framework](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
