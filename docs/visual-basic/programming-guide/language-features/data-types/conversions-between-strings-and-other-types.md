---
title: Konvertierungen zwischen Zeichenfolgen und anderen Typen (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- data type conversion [Visual Basic], string
- conversions [Visual Basic], type
- string conversion [Visual Basic]
- conversions [Visual Basic], data type
- type conversion [Visual Basic], string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 82473d59d6b6aac21f2d7f2a0c9748217a61985f
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a>Konvertierungen zwischen Zeichenfolgen und anderen Typen (Visual Basic)
Sie können einen numerischen konvertieren `Boolean`, oder Datum/Uhrzeit-Wert, der eine `String`. Sie können auch in umgekehrter Richtung konvertieren – aus einem Zeichenfolgenwert numerischen, `Boolean`, oder `Date` – sofern der Inhalt der Zeichenfolge als gültiger Wert des Zieldatentyps interpretiert werden können. Wenn dies nicht möglich, tritt ein Laufzeitfehler auf.  
  
 Die Konvertierungen für alle diese Zuweisungen in beide Richtungen annähernde. Verwenden Sie Schlüsselwörter für die typkonvertierung (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, und `CType`). Die <xref:Microsoft.VisualBasic.Strings.Format%2A> und <xref:Microsoft.VisualBasic.Conversion.Val%2A> -Funktionen geben Ihnen zusätzliche Kontrolle darüber, Konvertierungen zwischen Zeichenfolgen und Zahlen.  
  
 Wenn Sie eine Klasse oder Struktur definiert haben, können Sie definieren, dass Typkonvertierungsoperatoren zwischen `String` und den Typ der Klasse oder Struktur. Weitere Informationen finden Sie unter [wie: Definieren eines Konvertierungsoperators](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="conversion-of-numbers-to-strings"></a>Konvertierung von Zahlen in Zeichenfolgen  
 Können Sie die `Format` Funktion, um eine Zahl in eine formatierte Zeichenfolge zu konvertieren, der nicht nur die entsprechenden Ziffern umfassen kann jedoch auch die Formatierungssymbole, z. B. ein Währungssymbol (z. B. `$`), Tausende Trennzeichen oder *Tausender Symbole* (z. B. `,`), und ein Dezimaltrennzeichen (z. B. `.`). `Format` verwendet automatisch die entsprechenden Symbole gemäß der **regionale** in Windows angegebenen Einstellungen **Systemsteuerung**.  
  
 Beachten Sie, dass die Verkettung (`&`)-Operator kann konvertiert eine Zahl in eine Zeichenfolge implizit, wie im folgenden Beispiel gezeigt.  
  
```  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a>Konvertierung von Zeichenfolgen in Zahlen  
 Sie können die `Val` Funktion explizit die Ziffern in einer Zeichenfolge in eine Zahl zu konvertieren. `Val` liest die Zeichenfolge an, bis er erkennt, dass ein anderes Zeichen als ein Ziffern, Leerzeichen, Tabstopp, Line feed, Wagenrücklauf oder Zeitraum. Die Sequenzen "& O" und "& H" ändern Sie die Basis des Systems Anzahl und die Überprüfung zu beenden. Bis er beendet das Lesen, wird `Val` alle entsprechende Zeichen in einen numerischen Wert konvertiert. Die folgende Anweisung gibt z. B. den Wert `141.825`.  
  
 `Val("   14   1.825 miles")`  
  
 Visual Basic eine Zeichenfolge in einen numerischen Wert konvertiert, verwendet der **regionale** Einstellungen angegeben, die in Windows **Systemsteuerung** zum Interpretieren von Tausenden Separator, Dezimaltrennzeichen, und Währungssymbol. Dies bedeutet, dass eine Konvertierung unter einer Einstellung, aber nicht in einer anderen erfolgreich ausgeführt werden kann. Beispielsweise `"$14.20"` akzeptabel ist in das Gebietsschema Englisch (Vereinigte Staaten), aber nicht im Gebietsschemas Französisch.  
  
## <a name="see-also"></a>Siehe auch  
 [Konvertierungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Vorgehensweise: Konvertieren eines Objekts in einen anderen Typ in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [Arraykonvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Einführung in internationale Anwendungen basierend auf .NET Framework](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
