---
title: "Using Regular Expressions with the MaskedTextBox Control in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "strings [Visual Basic], regular expressions"
  - "strings [Visual Basic], masked edit"
ms.assetid: 2a048fb0-7053-487d-b2c5-ffa5e22ed6f9
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Using Regular Expressions with the MaskedTextBox Control in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

In diesem Beispiel wird veranschaulicht, wie einfache reguläre Ausdrücke für die Verwendung mit dem <xref:System.Windows.Forms.MaskedTextBox>\-Steuerelement konvertiert werden.  
  
## Beschreibung der Maskingsprache  
 Die Standardmaskingsprache für <xref:System.Windows.Forms.MaskedTextBox> beruht auf der vom `Masked Edit`\-Steuerelement in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 6.0 verwendeten Maskingsprache, und Benutzer, die von dieser Plattform migrieren, sollten damit vertraut sein.  
  
 Die <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>\-Eigenschaft des <xref:System.Windows.Forms.MaskedTextBox>\-Steuerelements gibt die zu verwendende Eingabemaske an.  Die Maske muss eine Zeichenfolge sein, die aus einem oder mehreren Maskierungselementen in der folgenden Tabelle besteht.  
  
|Maskierungselement|Beschreibung|Element eines regulären Ausdrucks|  
|------------------------|------------------|---------------------------------------|  
|0|Beliebige einzelne Ziffer zwischen 0 und 9.  Eingabe erforderlich.|\\d|  
|9|Ziffer oder Leerzeichen.  Eingabe optional.|\[ \\d\]?|  
|\#|Ziffer oder Leerzeichen.  Eingabe optional.  Wenn diese Position in der Maske leer gelassen wird, wird sie als Leerzeichen gerendert.  Pluszeichen \(\+\) und Minuszeichen \(\-\) sind zulässig.|\[ \\d\+\-\]?|  
|L|ASCII\-Buchstabe.  Eingabe erforderlich.|\[a\-zA\-Z\]|  
|?|ASCII\-Buchstabe.  Eingabe optional.|\[a\-zA\-Z\]?|  
|&|Char  Eingabe erforderlich.|\[\\p{Ll}\\p{Lu}\\p{Lt}\\p{Lm}\\p{Lo}\]|  
|C|Char  Eingabe optional.|\[\\p{Ll}\\p{Lu}\\p{Lt}\\p{Lm}\\p{Lo}\]?|  
|A|Alphanumerisch.  Eingabe optional.|\\W|  
|.|Der jeweiligen Kultur entsprechendes Dezimaltrennzeichen.|Nicht verfügbar.|  
|,|Der jeweiligen Kultur entsprechendes Tausendertrennzeichen.|Nicht verfügbar.|  
|:|Der jeweiligen Kultur entsprechendes Trennzeichen für Zeitangaben.|Nicht verfügbar.|  
|\/|Der jeweiligen Kultur entsprechendes Datumstrennzeichen.|Nicht verfügbar.|  
|$|Der jeweiligen Kultur entsprechendes Währungssymbol.|Nicht verfügbar.|  
|\<|Konvertiert alle nachfolgenden Zeichen in Kleinbuchstaben.|Nicht verfügbar.|  
|\>|Konvertiert alle nachfolgenden Zeichen in Großbuchstaben.|Nicht verfügbar.|  
|&#124;|Macht ein vorheriges Drücken der UMSCHALTTASTE rückgängig.|Nicht verfügbar.|  
|\\|Versieht ein Maskenzeichen mit Escapezeichen und wandelt es in ein Literal um. "  \\\\" ist die Escapesequenz für einen umgekehrten Schrägstrich.|\\|  
|Alle anderen Zeichen.|Literale.  Alle nicht maskierten Elemente werden in <xref:System.Windows.Forms.MaskedTextBox> in ihrer ursprünglichen Form angezeigt.|Alle anderen Zeichen.|  
  
 Dezimaltrennzeichen \(.\), Tausendertrennzeichen \(,\), Trennzeichen für Zeitangaben \(:\), Datumstrennzeichen \(\/\) und Währungssymbol \($\) werden standardmäßig als die durch die Kultur der Anwendung definierten Zeichen angezeigt.  Mit der <xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A>\-Eigenschaft können Sie erzwingen, dass diese Zeichen als Zeichen einer anderen Kultur angezeigt werden.  
  
## Reguläre Ausdrücke und Masken  
 Obwohl Sie Benutzereingaben mit regulären Ausdrücken und Masken überprüfen können, entsprechen sich diese beiden Verfahren nicht vollständig.  Reguläre Ausdrücke können komplexere Muster als Masken wiedergeben, doch mit Masken können dieselben Informationen prägnanter und in einem der jeweiligen Kultur entsprechenden Format wiedergegeben werden.  
  
 In der folgenden Tabelle werden vier reguläre Ausdrücke mit den entsprechenden Masken verglichen.  
  
|Regulärer Ausdruck|Format|Hinweise|  
|------------------------|------------|--------------|  
|`\d{2}/\d{2}/\d{4}`|`00/00/0000`|Das `/`\-Zeichen in der Maske ist ein logisches Datumstrennzeichen und wird für den Benutzer als das Datumstrennzeichen angezeigt, das der aktuellen Kultur der Anwendung entspricht.|  
|`\d{2}-[A-Z][a-z]{2}-\d{4}`|`00->L<LL-0000`|Ein Datum \(Tag, Monatsabkürzung und Jahr\) im US\-Format, in dem die aus drei Buchstaben bestehende Abkürzung für den Monat mit einem großen Anfangsbuchstaben gefolgt von zwei Kleinbuchstaben angezeigt wird.|  
|`(\(\d{3}\)-)?  \d{3}-d{4}`|`(999)-000-0000`|US\-Telefonnummer, optionale Ortskennzahl.  Wenn der Benutzer die optionalen Zeichen nicht eingeben möchte, können Leerzeichen eingegeben werden, oder der Mauszeiger kann direkt auf die durch die erste 0 dargestellte Position in der Maske gesetzt werden.|  
|`$\d{6}.00`|`$999,999.00`|Ein Währungswert im Bereich von 0 bis 999999.  Das Währungssymbol sowie das Tausender\- und Dezimaltrennzeichen werden zur Laufzeit durch ihre kulturspezifischen Entsprechungen ersetzt.|  
  
## Siehe auch  
 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>   
 <xref:System.Windows.Forms.MaskedTextBox>   
 [Validating Strings in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)   
 [MaskedTextBox\-Steuerelement](../Topic/MaskedTextBox%20Control%20\(Windows%20Forms\).md)