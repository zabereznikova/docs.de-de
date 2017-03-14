---
title: "Conversions Between Strings and Other Types (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "data type conversion, string"
  - "conversions, type"
  - "string conversion"
  - "conversions, data type"
  - "type conversion, string"
  - "regional options"
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Conversions Between Strings and Other Types (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Numerische, `Boolean` sowie Datum\-\/Uhrzeitwerte können in `String` konvertiert werden.  Eine Konvertierung in die umgekehrte Richtung, also von String in einen numerischen, `Boolean` oder einen `Date`\-Wert, ist ebenfalls möglich, sofern der Inhalt von String als gültiger Wert des Zieldatentyps interpretiert werden kann.  Anderenfalls tritt ein Laufzeitfehler auf.  
  
 Bei den Konvertierungen \(in beide Richtungen\) für alle diese Zuweisungen handelt es sich um einschränkende Konvertierungen.  Verwenden Sie die Typkonvertierungsschlüsselwörter \(`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort` und `CType`\).  Mithilfe der <xref:Microsoft.VisualBasic.Strings.Format%2A>\-Funktion und der <xref:Microsoft.VisualBasic.Conversion.Val%2A>\-Funktion können Sie die Konvertierungen zwischen Zeichenfolgen und Zahlen zusätzlich steuern.  
  
 Wenn Sie eine Klasse oder Struktur definiert haben, können Sie Typkonvertierungsoperatoren zwischen `String` und dem Typ der Klasse bzw. Struktur definieren.  Weitere Informationen finden Sie unter [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## Konvertierung von Zahlen in Zeichenfolgen  
 Sie können eine Zahl mithilfe der `Format`\-Funktion in eine formatierte Zeichenfolge konvertieren, die neben den entsprechenden Ziffern auch Formatierungssymbole enthalten kann, wie etwa ein Währungszeichen \(z. B. `$`\), Tausendertrennzeichen, *Symbole für die Zifferngruppierung* \(z. B. `,`\) oder ein Dezimaltrennzeichen \(z. B. `.`\).  `Format` verwendet automatisch die passenden Symbole entsprechend den in der **Systemsteuerung** unter **Ländereinstellungen** festgelegten Einstellungen.  
  
 Beachten Sie, dass der Verkettungsoperator \(`&`\) eine Zahl implizit in eine Zeichenfolge konvertieren kann, wie im folgenden Beispiel dargestellt.  
  
```  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## Konvertierung von Zeichenfolgen in Zahlen  
 Mit der `Val`\-Funktion können Sie die Ziffern in einer Zeichenfolge explizit in eine Zahl konvertieren.  `Val` liest die Zeichenfolge, bis ein anderes Zeichen als eine Ziffer, ein Leerzeichen, ein Tabulator, ein Zeilenvorschub oder ein Punkt gefunden wird.  Die Zeichenfolgen "&O" sowie "&H" ändern die Basis des Zahlensystems und beenden die Überprüfung.  Bis die `Val`\-Funktion das Lesen der Zeichenfolge beendet, konvertiert sie alle entsprechenden Zeichen in einen numerischen Wert.  Die folgende Anweisung gibt z. B. den Wert `141.825` zurück.  
  
 `Val("   14   1.825 miles")`  
  
 Bei der Konvertierung einer Zeichenfolge in einen numerischen Wert verwendet [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] für die Interpretation des Tausendertrennzeichens, des Dezimaltrennzeichens und des Währungssymbols die in der **Systemsteuerung** unter **Ländereinstellungen** festgelegten Einstellungen.  Als Folge dessen kann eine Konvertierung unter einer Einstellung erfolgreich sein, während sie unter einer anderen fehlschlägt.  So ist beispielsweise `"$14.20"` für das Gebietsschema "Englisch \(USA\)" zulässig, nicht jedoch für die Gebietsschemas "Französisch".  
  
## Siehe auch  
 [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [How to: Convert an Object to Another Type in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)   
 [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)   
 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Einführung in internationale Anwendungen basierend auf .NET Framework](/visual-studio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)