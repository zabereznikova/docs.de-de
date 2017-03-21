---
title: Konvertierungen zwischen Zeichenfolgen und anderen Typen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- data type conversion, string
- conversions, type
- string conversion
- conversions, data type
- type conversion, string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
caps.latest.revision: 16
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2d0a5fc7327ecd6339b5021e1b4cb87cc54bd2bc
ms.lasthandoff: 03/13/2017

---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a>Konvertierungen zwischen Zeichenfolgen und anderen Typen (Visual Basic)
Sie können eine numerische konvertieren `Boolean`, oder Datum/Uhrzeit-Wert, der eine `String`. Sie können auch in umgekehrter Richtung konvertieren – aus einem Zeichenfolgenwert numerischen, `Boolean`, oder `Date` – sofern der Inhalt der Zeichenfolge als gültiger Wert des Zieldatentyps interpretiert werden können. Ist dies nicht möglich, tritt ein Laufzeitfehler auf.  
  
 Die Konvertierungen für alle diese Aufgaben in beide Richtungen annähernde. You should use the type conversion keywords (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, and `CType`). Die <xref:Microsoft.VisualBasic.Strings.Format%2A>und <xref:Microsoft.VisualBasic.Conversion.Val%2A>Funktionen erhalten Sie zusätzliche Kontrolle über Konvertierungen zwischen Zeichenfolgen und Zahlen.</xref:Microsoft.VisualBasic.Conversion.Val%2A> </xref:Microsoft.VisualBasic.Strings.Format%2A>  
  
 Wenn Sie eine Klasse oder Struktur definiert haben, können Sie definieren, dass Typkonvertierungsoperatoren zwischen `String` und den Typ der Klasse bzw. Struktur. Weitere Informationen finden Sie unter [Gewusst wie: Definieren eines Konvertierungsoperators](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="conversion-of-numbers-to-strings"></a>Konvertieren von Zahlen in Zeichenfolgen  
 Können Sie die `Format` -Funktion zum Umwandeln einer Zahl in eine formatierte Zeichenfolge, die nicht nur die entsprechenden Ziffern enthalten, können jedoch auch die Formatierungssymbole, wie Währungszeichen (z. B. `$`), Tausende Trennzeichen oder *Ziffer gruppieren Symbole* (z. B. `,`), und ein Dezimaltrennzeichen (z. B. `.`). `Format`verwendet automatisch die entsprechenden Symbole gemäß der **regionale** Einstellungen in Windows **Systemsteuerung**.  
  
 Beachten Sie, dass die Verkettung (`&`) konvertieren kann eine Zahl in eine Zeichenfolge implizit, wie im folgenden Beispiel gezeigt.  
  
```  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a>Konvertierung von Zeichenfolgen in Zahlen  
 Sie können die `Val` Funktion, die Ziffern in einer Zeichenfolge explizit in eine Zahl zu konvertieren. `Val`liest die Zeichenfolge, bis ein anderes Zeichen als eine Ziffer, Leerzeichen, Tabstoppzeichen, Line feed, oder Zeitraum auftritt. Die Sequenzen "& O" und "& H" ändern die Basis des Systems Anzahl und beenden die Überprüfung. Bis sie gelesen wird, stoppt `Val` alle entsprechende Zeichen in einen numerischen Wert konvertiert. Die folgende Anweisung gibt z. B. den Wert `141.825`.  
  
 `Val("   14   1.825 miles")`  
  
 Wenn [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] konvertiert eine Zeichenfolge in einen numerischen Wert, verwendet der **regionale** Einstellungen in Windows **Systemsteuerung** Tausendertrennzeichen interpretiert Trennzeichen, Dezimaltrennzeichen und Währungssymbol. Dies bedeutet, dass eine Konvertierung möglicherweise unter einem, jedoch nicht in einer anderen Einstellung erfolgreich ausgeführt. Z. B. `"$14.20"` akzeptabel ist in Englisch (USA) jedoch nicht in Gebietsschemas Französisch.  
  
## <a name="see-also"></a>Siehe auch  
 [Typumwandlungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Gewusst wie: Konvertieren eines Objekts in einen anderen Typ in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)   
 [Arraykonvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)   
 [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Einführung in internationale Anwendungen basierend auf .NET Framework](https://docs.microsoft.com/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
