---
title: Konvertierungen zwischen Zeichenfolgen und anderen Typen
ms.date: 07/20/2015
helpviewer_keywords:
- data type conversion [Visual Basic], string
- conversions [Visual Basic], type
- string conversion [Visual Basic]
- conversions [Visual Basic], data type
- type conversion [Visual Basic], string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
ms.openlocfilehash: 823931f7d6beb8218e8b99d4a8d45716b7214304
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077149"
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a>Konvertierungen zwischen Zeichenfolgen und anderen Typen (Visual Basic)

Sie können einen numerischen-, `Boolean` -oder Datums-/Uhrzeitwert in einen konvertieren `String` . Sie können auch in umgekehrter Richtung konvertieren – von einem Zeichen folgen Wert zu numeric, `Boolean` oder `Date` –, wenn der Inhalt der Zeichenfolge als gültiger Wert des Ziel Datentyps interpretiert werden kann. Wenn dies nicht möglich ist, tritt ein Laufzeitfehler auf.  
  
 Bei den Konvertierungen für alle diese Zuweisungen in beide Richtungen handelt es sich um einschränkende Konvertierungen. Verwenden Sie die Schlüsselwörter für die Typkonvertierung ( `CBool` , `CByte` , `CDate` , `CDbl` , `CDec` , `CInt` , `CLng` , `CSByte` , `CShort` , `CSng` , `CStr` , `CUInt` , `CULng` , `CUShort` und `CType` ). Mit der <xref:Microsoft.VisualBasic.Strings.Format%2A> -Funktion und der- <xref:Microsoft.VisualBasic.Conversion.Val%2A> Funktion haben Sie zusätzliche Kontrolle über Konvertierungen zwischen Zeichen folgen und Zahlen  
  
 Wenn Sie eine Klasse oder Struktur definiert haben, können Sie Typkonvertierungs Operatoren zwischen `String` und dem Typ der Klasse oder Struktur definieren. Weitere Informationen finden Sie unter [How to: Define a Conversion Operator](../procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="conversion-of-numbers-to-strings"></a>Konvertieren von Zahlen in Zeichen folgen  

 Sie können die- `Format` Funktion verwenden, um eine Zahl in eine formatierte Zeichenfolge zu konvertieren, die nicht nur die entsprechenden Ziffern enthält, sondern auch Symbole wie ein Währungszeichen (z. b. `$` ), Tausende Trennzeichen oder *zifferngruppierungssymbole* (z. b `,` .) und ein Dezimaltrennzeichen (z. b.) formatieren kann `.` . `Format`verwendet automatisch die entsprechenden Symbole gemäß den in der Windows- **Systemsteuerung**angegebenen Einstellungen für **regionale Optionen** .  
  
 Beachten Sie, dass der Concatenations ( `&` )-Operator eine Zahl implizit in eine Zeichenfolge konvertieren kann, wie im folgenden Beispiel gezeigt.  
  
```vb  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a>Konvertierung von Zeichen folgen in Zahlen  

 Sie können die- `Val` Funktion verwenden, um die Ziffern in einer Zeichenfolge explizit in eine Zahl zu konvertieren. `Val` liest die Zeichenfolge, bis Sie auf ein anderes Zeichen als Ziffern, Leerzeichen, Tabstopps, Zeilenvorschub oder Zeitraum trifft. Die Sequenzen "&O" und "&H" ändern die Basis des Zahlen Systems und beenden das Scannen. Bis zum Beenden der Lesevorgänge `Val` konvertiert alle entsprechenden Zeichen in einen numerischen Wert. Beispielsweise gibt die folgende-Anweisung den-Wert zurück `141.825` .  
  
 `Val("   14   1.825 miles")`  
  
 Wenn Visual Basic eine Zeichenfolge in einen numerischen Wert konvertiert, werden die in der Windows- **Systemsteuerung** angegebenen **regionalen Options** Einstellungen verwendet, um das Tausender Trennzeichen, das Dezimaltrennzeichen und das Währungssymbol zu interpretieren. Dies bedeutet, dass eine Konvertierung möglicherweise unter einer Einstellung erfolgreich verläuft, aber nicht in einer anderen. Beispielsweise `"$14.20"` ist im Gebiets Schema Englisch (USA) zulässig, jedoch nicht in einem französischen Gebiets Schema.  
  
## <a name="see-also"></a>Siehe auch

- [Typkonvertierung in Visual Basic](type-conversions.md)
- [Widening and Narrowing Conversions](widening-and-narrowing-conversions.md)
- [Implizite und explizite Konvertierungen](implicit-and-explicit-conversions.md)
- [Gewusst wie: Konvertieren eines Objekts in einen anderen Typ in Visual Basic](how-to-convert-an-object-to-another-type.md)
- [Arraykonvertierungen](array-conversions.md)
- [Datentypen](../../../language-reference/data-types/index.md)
- [Type Conversion Functions](../../../language-reference/functions/type-conversion-functions.md)
- [Entwickeln von globalisierten und lokalisierten Apps](/visualstudio/ide/globalizing-and-localizing-applications)
