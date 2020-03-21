---
title: Verwenden von regulären Ausdrücken mit dem MaskedTextBox-Steuerelement
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], regular expressions
- strings [Visual Basic], masked edit
ms.assetid: 2a048fb0-7053-487d-b2c5-ffa5e22ed6f9
ms.openlocfilehash: b997f6f495fca51e888bb995fee0361d29d68048
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148283"
---
# <a name="using-regular-expressions-with-the-maskedtextbox-control-in-visual-basic"></a>Verwenden von regulären Ausdrücken mit dem MaskedTextBox-Steuerelement in Visual Basic
In diesem Beispiel wird veranschaulicht, wie <xref:System.Windows.Forms.MaskedTextBox> einfache reguläre Ausdrücke konvertiert werden, um mit dem Steuerelement zu arbeiten.  
  
## <a name="description-of-the-masking-language"></a>Beschreibung der Maskierungssprache  
 Die <xref:System.Windows.Forms.MaskedTextBox> Standardmaskierungssprache basiert auf der `Masked Edit` Sprache, die vom Steuerelement in Visual Basic 6.0 verwendet wird, und sollte Benutzern vertraut sein, die von dieser Plattform migrieren.  
  
 Die <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> Eigenschaft <xref:System.Windows.Forms.MaskedTextBox> des Steuerelements gibt an, welche Eingabemaske verwendet werden soll. Die Maske muss eine Zeichenfolge sein, die aus einem oder mehreren maskierenden Elementen aus der folgenden Tabelle besteht.  
  
|Maskierungselement|Beschreibung|Element des regulären Ausdrucks|  
|---------------------|-----------------|--------------------------------|  
|0|Jede einzelne Ziffer zwischen 0 und 9. Eintrag erforderlich.|\d|  
|9|Ziffer oder Raum. Eintrag optional.|[ d]?|  
|#|Ziffer oder Raum. Eintrag optional. Wenn diese Position in der Maske leer bleibt, wird sie als Leerzeichen gerendert. Plus (+) und Minuszeichen (-) sind zulässig.|[ d+-]?|  
|L|ASCII-Buchstabe. Eintrag erforderlich.|[a-zA-Z]|  
|?|ASCII-Buchstabe. Eintrag optional.|[a-zA-Z]?|  
|&|Zeichen Eintrag erforderlich.|[-p-Ll-P-Lu-P-Lt-P-Lm-P-L-P-Lo-]|  
|C|Zeichen Eintrag optional.|[-p-Ll-P-Lu-P-Lt-P-Lm-P-Lo-]?|  
|Ein|Alphanumerische. Eintrag optional.|\W|  
|.|Kulturgerechter Dezimalstelleninhaber.|Nicht verfügbar.|  
|,|Kulturgerechte Tausende Platzhalter.|Nicht verfügbar.|  
|:|Kulturgerechtes Zeittrennzeichen.|Nicht verfügbar.|  
|/|Kulturgerechtes Datumstrennzeichen.|Nicht verfügbar.|  
|$|Kulturgerechtes Währungssymbol.|Nicht verfügbar.|  
|\<|Konvertiert alle Zeichen, die folgen, in Kleinbuchstaben.|Nicht verfügbar.|  
|>|Konvertiert alle Zeichen, die folgen, in Großbuchstaben.|Nicht verfügbar.|  
|&#124;|Macht eine vorherige Verschiebung nach oben oder nach unten.|Nicht verfügbar.|  
|&#92;|Entkommt einem Maskenzeichen und verwandelt es in ein Literal. "\\\\ist die Escape-Sequenz für einen umgekehrten Schrägstrich.|&#92;|  
|Alle anderen Zeichen.|Literale. Alle Elemente ohne Maske werden <xref:System.Windows.Forms.MaskedTextBox>als sich selbst in angezeigt.|Alle anderen Zeichen.|  
  
 Die Dezimalsymbole (.), tausendstel (,), die Zeit (:), das Datum (/) und die Währung ()- Symbole werden standardmäßig in der Durchlage dieser Symbole angezeigt, wie sie in der Kultur der Anwendung definiert sind. Sie können erzwingen, dass Symbole für <xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A> eine andere Kultur angezeigt werden, indem Sie die Eigenschaft verwenden.  
  
## <a name="regular-expressions-and-masks"></a>Reguläre Ausdrücke und Masken  
 Obwohl Sie reguläre Ausdrücke und Masken verwenden können, um Benutzereingaben zu überprüfen, sind sie nicht vollständig gleichwertig. Reguläre Ausdrücke können komplexere Muster als Masken ausdrücken, aber Masken können dieselben Informationen prägnanter und in einem kulturell relevanten Format ausdrücken.  
  
 In der folgenden Tabelle werden vier reguläre Ausdrücke und die entsprechende Maske für jeden verglichen.  
  
|Regular Expression|Mask|Notizen|  
|------------------------|----------|-----------|  
|`\d{2}/\d{2}/\d{4}`|`00/00/0000`|Das `/` Zeichen in der Maske ist ein logisches Datumstrennzeichen und wird dem Benutzer als Datumstrennzeichen angezeigt, das der aktuellen Kultur der Anwendung entspricht.|  
|`\d{2}-[A-Z][a-z]{2}-\d{4}`|`00->L<LL-0000`|Ein Datum (Tag, Monatsabkürzung und Jahr) im FORMAT der Vereinigten Staaten, in dem die Abkürzung für den Drei-Buchstaben-Monat mit einem anfangs großformatigen Buchstaben gefolgt von zwei Kleinbuchstaben angezeigt wird.|  
|`(\(\d{3}\)-)?\d{3}-d{4}`|`(999)-000-0000`|Telefonnummer der Vereinigten Staaten, Vorwahl optional. Wenn der Benutzer die optionalen Zeichen nicht eingeben möchte, kann er entweder Leerzeichen eingeben oder den Mauszeiger direkt an der Position in der Maske platzieren, die durch die erste 0 dargestellt wird.|  
|`$\d{6}.00`|`$999,999.00`|Ein Währungswert im Bereich von 0 bis 999999. Die Währung, das tausendste und das Dezimalzeichen werden zur Laufzeit durch ihre kulturspezifischen Entsprechungen ersetzt.|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>
- <xref:System.Windows.Forms.MaskedTextBox>
- [Überprüfen von Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
- [MaskedTextBox-Steuerelement](../../../../framework/winforms/controls/maskedtextbox-control-windows-forms.md)
