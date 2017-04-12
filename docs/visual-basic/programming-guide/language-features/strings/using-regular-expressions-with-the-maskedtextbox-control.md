---
title: "Mithilfe von regulären Ausdrücken mit dem MaskedTextBox-Steuerelement in Visual Basic | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], regular expressions
- strings [Visual Basic], masked edit
ms.assetid: 2a048fb0-7053-487d-b2c5-ffa5e22ed6f9
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 15d8f131aa834321fcf7e8ca633929385c666e6a
ms.lasthandoff: 03/13/2017

---
# <a name="using-regular-expressions-with-the-maskedtextbox-control-in-visual-basic"></a>Verwenden von regulären Ausdrücken mit dem MaskedTextBox-Steuerelement in Visual Basic
In diesem Beispiel wird veranschaulicht, wie einfache reguläre Ausdrücke für die Arbeit mit konvertieren die <xref:System.Windows.Forms.MaskedTextBox>Steuerelement.</xref:System.Windows.Forms.MaskedTextBox>  
  
## <a name="description-of-the-masking-language"></a>Beschreibung der Maskierungssprache  
 Der Standard <xref:System.Windows.Forms.MaskedTextBox>maskiert Sprache basiert auf von verwendet die `Masked Edit` -Steuerelement in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 6.0 und für Benutzer, die von dieser Plattform migrieren vertraut sein.</xref:System.Windows.Forms.MaskedTextBox>  
  
 Die <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>Eigenschaft der <xref:System.Windows.Forms.MaskedTextBox>Steuerelement gibt an, welche zu verwendende Eingabemaske.</xref:System.Windows.Forms.MaskedTextBox> </xref:System.Windows.Forms.MaskedTextBox.Mask%2A> Die Maske muss eine Zeichenfolge aus einem oder mehreren der Maskierung Elemente aus der folgenden Tabelle sein.  
  
|Masking-element|Beschreibung|Element eines regulären Ausdrucks|  
|---------------------|-----------------|--------------------------------|  
|0|Eine einzelne Ziffer zwischen 0 und 9. Eingabe erforderlich.|\d|  
|9|Ziffer oder Leerzeichen. Die Eingabe ist optional.|[ \d]?|  
|#|Ziffer oder Leerzeichen. Die Eingabe ist optional. Wenn diese Position in der Maske leer ist, wird sie als Leerzeichen gerendert werden. Pluszeichen (+) und Minuszeichen (-) sind zulässig.|[ \d+-]?|  
|L|ASCII-Buchstaben. Eingabe erforderlich.|[a-zA-Z]|  
|?|ASCII-Buchstaben. Die Eingabe ist optional.|[a-zA-Z]?|  
|&|Zeichen Eingabe erforderlich.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo]}|  
|A|Zeichen Die Eingabe ist optional.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]?|  
|A|Alphanumerisch ist. Die Eingabe ist optional.|\W|  
|.|Der jeweiligen Kultur entsprechendes Dezimaltrennzeichen.|Nicht verfügbar.|  
|,|Tausende Kultur entsprechende Platzhalter.|Nicht verfügbar.|  
|:|Kultur entsprechende Zeittrennzeichen.|Nicht verfügbar.|  
|/|Der jeweiligen Kultur entsprechendes Datumstrennzeichen.|Nicht verfügbar.|  
|$|Der jeweiligen Kultur entsprechendes Währungssymbol.|Nicht verfügbar.|  
|\<|Konvertiert alle nachfolgenden Zeichen in Kleinbuchstaben.|Nicht verfügbar.|  
|>|Konvertiert alle Zeichen, die in Großbuchstaben.|Nicht verfügbar.|  
|&#124;|Macht eine vorherige Schicht oben oder unten verschieben.|Nicht verfügbar.|  
|\|Ein Zeichen zum Maskieren, wandelt es in ein Literal mit Escapezeichen zu versehen. "\\\\" ist die Escapesequenz für einen umgekehrten Schrägstrich.|\|  
|Alle anderen Zeichen.|Literale. Alle nicht maskierten Elemente werden angezeigt in <xref:System.Windows.Forms.MaskedTextBox>.</xref:System.Windows.Forms.MaskedTextBox>|Alle anderen Zeichen.|  
  
 Dezimaltrennzeichen (.), Tausendstel-(,), Zeit (:), Datum (/) und Währungssymbol ($) werden standardmäßig die Symbole angezeigt, wie durch die Kultur der Anwendung definiert. Sie können erzwingen, Anzeigen von einer anderen Kultur mithilfe der <xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A>-Eigenschaft.</xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A>  
  
## <a name="regular-expressions-and-masks"></a>Reguläre Ausdrücke und Masken  
 Obwohl reguläre Ausdrücke und Masken verwenden können, um Benutzereingaben zu überprüfen, sind sie nicht vollständig äquivalent. Reguläre Ausdrücke können komplexere Muster als Masken, aber Masken können dieselbe Informationen prägnanter und in das entsprechende Format.  
  
 In der folgenden Tabelle werden vier reguläre Ausdrücke mit den entsprechenden Masken für jede verglichen.  
  
|Regulärer Ausdruck|Format|Notizen|  
|------------------------|----------|-----------|  
|`\d{2}/\d{2}/\d{4}`|`00/00/0000`|Die `/` Zeichen in der Maske ist ein logisches Datumstrennzeichen und wird für den Benutzer als das Datumstrennzeichen aktuelle Kultur der Anwendung angezeigt.|  
|`\d{2}-[A-Z][a-z]{2}-\d{4}`|`00->L<LL-0000`|Ein Datum (Tag, Abkürzung für den Monat und Jahr) im US-Format, in dem mit drei Buchstaben bestehende monatsabkürzung mit einem großen Anfangsbuchstaben gefolgt von zwei Kleinbuchstaben angezeigt wird.|  
|`(\(\d{3}\)-)?\d{3}-d{4}`|`(999)-000-0000`|USA-Telefonnummer, Ortskennzahl optional. Wenn der Benutzer nicht die optionalen Zeichen eingeben möchten, können sie Leerzeichen eingegeben oder platzieren den Mauszeiger auf direkt an der Position in der Maske, die durch die erste 0 dargestellt.|  
|`$\d{6}.00`|`$999,999.00`|Ein Währungswert im Bereich von 0 bis 999999. Die Währung, Tausendstel und Dezimalzeichen werden zur Laufzeit den entsprechenden kulturspezifische ersetzt.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A></xref:System.Windows.Forms.MaskedTextBox.Mask%2A>   
 <xref:System.Windows.Forms.MaskedTextBox></xref:System.Windows.Forms.MaskedTextBox>   
 [Überprüfen von Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)   
 [MaskedTextBox-Steuerelement](http://msdn.microsoft.com/library/235d6121-027d-481d-8d59-4f6794d15d0c)
