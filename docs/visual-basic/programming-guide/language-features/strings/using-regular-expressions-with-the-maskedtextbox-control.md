---
title: Verwenden von regulären Ausdrücken mit dem MaskedTextBox-Steuerelement in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], regular expressions
- strings [Visual Basic], masked edit
ms.assetid: 2a048fb0-7053-487d-b2c5-ffa5e22ed6f9
ms.openlocfilehash: 25bdfaef300b001d1c052aeea4e1ad3547a6d3d7
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43803808"
---
# <a name="using-regular-expressions-with-the-maskedtextbox-control-in-visual-basic"></a>Verwenden von regulären Ausdrücken mit dem MaskedTextBox-Steuerelement in Visual Basic
In diesem Beispiel wird veranschaulicht, wie einfache reguläre Ausdrücke für die Arbeit mit konvertieren die <xref:System.Windows.Forms.MaskedTextBox> Steuerelement.  
  
## <a name="description-of-the-masking-language"></a>Beschreibung der Maskierungssprache  
 Der Standard <xref:System.Windows.Forms.MaskedTextBox> maskiert Sprache basiert auf dem die `Masked Edit` in Visual Basic 6.0 zu steuern und für Benutzer, die von dieser Plattform migrieren vertraut.  
  
 Die <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> Eigenschaft der <xref:System.Windows.Forms.MaskedTextBox> Steuerelement gibt an, welche zu verwendende Eingabemaske. Die Maske muss eine Zeichenfolge, die eine oder mehrere Elemente aus der folgenden Tabelle wird der maskierungssatz bestehen.  
  
|Maskierung-element|Beschreibung|Reguläre Ausdrücke-element|  
|---------------------|-----------------|--------------------------------|  
|0|Eine einzelne Ziffer zwischen 0 und 9. Eintrag erforderlich.|\d|  
|9|Ziffern oder Leerzeichen. Die Eingabe ist optional.|[\d]?|  
|#|Ziffern oder Leerzeichen. Die Eingabe ist optional. Wenn diese Position in der Maske leer gelassen wird, wird es als Leerzeichen gerendert werden. Pluszeichen (+) und minus (-) Zeichen sind zulässig.|[\d+-]?|  
|L|ASCII-Buchstabe. Eintrag erforderlich.|[a-zA-Z]|  
|?|ASCII-Buchstabe. Die Eingabe ist optional.|[a-zA-Z]?|  
|&|Zeichen Eintrag erforderlich.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]|  
|C|Zeichen Die Eingabe ist optional.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]?|  
|A|Alphanumerisch. Die Eingabe ist optional.|\W|  
|sein.|Kultur entsprechende dezimalplatzhalter.|Nicht verfügbar.|  
|,|Tausende Kultur entsprechende Platzhalter.|Nicht verfügbar.|  
|:|Kultur entsprechende Zeittrennzeichen.|Nicht verfügbar.|  
|/|Kultur entsprechende Datumstrennzeichen.|Nicht verfügbar.|  
|$|Kultur entsprechende Währungssymbol.|Nicht verfügbar.|  
|\<|Konvertiert alle Zeichen in Kleinbuchstaben.|Nicht verfügbar.|  
|>|Konvertiert alle Zeichen, die in Großbuchstaben folgen.|Nicht verfügbar.|  
|&#124;|Macht ein nach oben oder unten verschieben.|Nicht verfügbar.|  
|&#92;|Ein Zeichen zum Maskieren, wandelt sie in ein Literal mit Escapezeichen zu versehen. "\\\\" ist die Escapesequenz für einen umgekehrten Schrägstrich.|&#92;|  
|Alle anderen Zeichen.|Literale. Alle nicht-Maske Elemente werden angezeigt, als Sie selbst in <xref:System.Windows.Forms.MaskedTextBox>.|Alle anderen Zeichen.|  
  
 Das Dezimaltrennzeichen (.), Tausendstel-(,), Zeit (:), Datum (/) und Währung ($) werden standardmäßig diese Symbole angezeigt, wie die Kultur der Anwendung definiert. Sie können erzwingen, Anzeigen von einer anderen Kultur mithilfe der <xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A> Eigenschaft.  
  
## <a name="regular-expressions-and-masks"></a>Reguläre Ausdrücke und Masken  
 Obwohl reguläre Ausdrücke und Masken verwenden können, um Benutzereingaben zu überprüfen, sind sie nicht vollständig entspricht. Reguläre Ausdrücke können komplexere Muster als Masken Ausdrücken, aber Masken können die gleiche Informationen Ausdrücken, präziser und in ein Format für relevant.  
  
 Die folgende Tabelle vergleicht die vier reguläre Ausdrücke und die entsprechende Maske für die einzelnen.  
  
|Regulärer Ausdruck|Format|Hinweise|  
|------------------------|----------|-----------|  
|`\d{2}/\d{2}/\d{4}`|`00/00/0000`|Die `/` Zeichen in der Maske ist ein logisches Datumstrennzeichen aus, und es als das Datumstrennzeichen zur aktuellen Kultur der Anwendung, die dem Benutzer angezeigt.|  
|`\d{2}-[A-Z][a-z]{2}-\d{4}`|`00->L<LL-0000`|Ein Datum (Tag, Abkürzung für den Monat und Jahr) in den USA-Format, in dem die drei Buchstaben bestehenden monatsabkürzung mit einem anfänglichen Großbuchstaben gefolgt von zwei Kleinbuchstaben angezeigt wird.|  
|`(\(\d{3}\)-)?\d{3}-d{4}`|`(999)-000-0000`|Vereinigte Staaten Telefonnummer angeben, die Vorwahl ist optional. Wenn der Benutzer nicht die optionale Zeichen eingeben möchten, können sie Leerzeichen eingegeben oder platzieren Sie den Mauszeiger-auf direkt an der Position in der Maske, die durch die ersten 0 dargestellt.|  
|`$\d{6}.00`|`$999,999.00`|Ein Währungswert im Bereich von 0 bis 999999. Die Währung, Tausendstel und dezimale Zeichen werden zur Laufzeit durch die kulturspezifischen-äquivalente ersetzt werden.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>  
 <xref:System.Windows.Forms.MaskedTextBox>  
 [Überprüfen von Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)  
 [MaskedTextBox-Steuerelement](../../../../framework/winforms/controls/maskedtextbox-control-windows-forms.md)
