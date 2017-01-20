---
title: "Byte Data Type (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Byte"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Byte data type"
  - "data types [Visual Basic], assigning"
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Byte Data Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Speichert 8\-Bit\-\(1\-Byte\)\-Ganzzahlen ohne Vorzeichen, deren Werte im Bereich von 0 bis 255 liegen.  
  
## Hinweise  
 Verwenden Sie den `Byte`\-Datentyp für Binärdaten.  
  
 Der Standardwert von `Byte` ist 0 \(null\).  
  
## Programmiertipps  
  
-   **Negative Zahlen.** Da `Byte` ein Typ ohne Vorzeichen ist, kann er keine negativen Zahlen darstellen.  Wenn Sie den unären Minusoperator \(`-`\) in einem Ausdruck verwenden, der vom Typ `Byte` ist, wandelt Visual Basic den Ausdruck zunächst in den `Short`\-Typ um.  
  
-   **Formatkonvertierungen.** Wenn Visual Basic Dateien liest oder schreibt bzw. DLLs, Methoden und Eigenschaften aufruft, können die Datenformate automatisch konvertiert werden.  Die in `Byte`\-Variablen und in Arrays gespeicherten binären Daten bleiben bei solchen Formatkonvertierungen erhalten.  Sie sollten für binäre Daten keine `String`\-Variable verwenden, da der Inhalt bei der Konvertierung von ANSI in Unicode beschädigt werden kann.  
  
-   **Erweiterung.** Der `Byte`\-Datentyp wird zu `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single` oder `Double` erweitert.  Dies bedeutet, dass Sie `Byte` in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=fullName>\-Fehler auftritt.  
  
-   **Typzeichen.** `Byte` hat kein Literaltypzeichen oder Typkennzeichen.  
  
-   **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.Byte?displayProperty=fullName>\-Struktur.  
  
## Beispiel  
 Im folgenden Beispiel ist `b` eine `Byte`\-Variable.  Die Anweisungen veranschaulichen den Bereich der Variablen und die Anwendung von Bitschiebeoperatoren auf die Variable.  
  
 [!code-vb[VbVbalrDataTypes#16](../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/byte-data-type_1.vb)]  
  
## Siehe auch  
 <xref:System.Byte?displayProperty=fullName>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)