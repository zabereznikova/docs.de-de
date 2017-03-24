---
title: "How to: Validate Strings That Represent Dates or Times (Visual Basic) | Microsoft Docs"
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
  - "strings [Visual Basic], validating"
  - "String data type, validation"
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# How to: Validate Strings That Represent Dates or Times (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Im folgenden Codebeispiel wird ein `Boolean`\-Wert festgelegt, der angibt, ob eine Zeichenfolge ein gültiges Datum oder eine gültige Uhrzeit darstellt.  
  
## Beispiel  
 [!code-vb[VbVbcnRegEx#2](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-strings-that-represent-dates-or-times_1.vb)]  
  
## Kompilieren des Codes  
 Ersetzen Sie `("01/01/03")` und `"9:30 PM"` durch die Werte für Datum und Uhrzeit, die Sie überprüfen möchten.  Sie können die Zeichenfolge durch eine andere hartcodierte Zeichenfolge, eine `String`\-Variable oder eine Methode ersetzen, die eine Zeichenfolge zurückgibt, z. B. `InputBox`.  
  
## Robuste Programmierung  
 Verwenden Sie diese Methode, um die Zeichenfolge zu überprüfen, bevor Sie versuchen, den `String` in eine `DateTime`\-Variable zu konvertieren.  Wenn Sie zunächst das Datum oder die Uhrzeit überprüfen, können Sie das Generieren einer Ausnahme zur Laufzeit vermeiden.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Information.IsDate%2A>   
 <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>   
 [Validating Strings in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)