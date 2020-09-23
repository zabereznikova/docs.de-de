---
title: Verwenden von regulären Ausdrücken mit dem MaskedTextBox-Steuerelement
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], regular expressions
- strings [Visual Basic], masked edit
ms.assetid: 2a048fb0-7053-487d-b2c5-ffa5e22ed6f9
ms.openlocfilehash: 493da7b8583b5cc73a9832afa81b7b1d84742f2d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072430"
---
# <a name="using-regular-expressions-with-the-maskedtextbox-control-in-visual-basic"></a>Verwenden von regulären Ausdrücken mit dem MaskedTextBox-Steuerelement in Visual Basic

In diesem Beispiel wird veranschaulicht, wie einfache reguläre Ausdrücke konvertiert werden, um mit dem-Steuerelement zu arbeiten <xref:System.Windows.Forms.MaskedTextBox> .  
  
## <a name="description-of-the-masking-language"></a>Beschreibung der Maskierungs Sprache  

 Die Standard <xref:System.Windows.Forms.MaskedTextBox> Maskierungs Sprache basiert auf derjenigen, die von dem `Masked Edit` Steuerelement in Visual Basic 6,0 verwendet wird, und sollte Benutzern vertraut sein, die von dieser Plattform migrieren.  
  
 Die- <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> Eigenschaft des- <xref:System.Windows.Forms.MaskedTextBox> Steuer Elements gibt an, welche Eingabemaske verwendet werden soll. Die Maske muss eine Zeichenfolge sein, die aus einem oder mehreren der Maskierungs Elemente aus der folgenden Tabelle besteht.  
  
|Maskierungs Element|BESCHREIBUNG|Reguläres Expression-Element|  
|---------------------|-----------------|--------------------------------|  
|0|Eine beliebige einzelne Ziffer zwischen 0 und 9. Der Eintrag ist erforderlich.|\d|  
|9|Ziffern oder Leerzeichen. Der Eintrag ist optional.|[\d]?|  
|#|Ziffern oder Leerzeichen. Der Eintrag ist optional. Wenn diese Position in der Maske leer gelassen wird, wird Sie als Leerzeichen gerendert. Plus Zeichen (+) und Minuszeichen (-) sind zulässig.|[\d +-]?|  
|L|ASCII-Buchstabe. Der Eintrag ist erforderlich.|[a-zA-Z]|  
|?|ASCII-Buchstabe. Der Eintrag ist optional.|[a-zA-Z]?|  
|&|Zeichen Der Eintrag ist erforderlich.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]|  
|C|Zeichen Der Eintrag ist optional.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]?|  
|Ein|Alphanumerische. Der Eintrag ist optional.|\W|  
|.|Kultur geeigneter dezimaler Platzhalter.|Nicht verfügbar.|  
|,|Kultur geeigneter Tausender Platzhalter.|Nicht verfügbar.|  
|:|Kultur geeignetes Zeit Trennzeichen.|Nicht verfügbar.|  
|/|Das Kultur passende Datums Trennzeichen.|Nicht verfügbar.|  
|$|Kultur geeignetes Währungssymbol.|Nicht verfügbar.|  
|\<|Konvertiert alle Zeichen, die Folgen, in Kleinbuchstaben.|Nicht verfügbar.|  
|>|Konvertiert alle Zeichen, die Folgen, in Großbuchstaben.|Nicht verfügbar.|  
|&#124;|Macht eine vorherige Verschiebung nach oben oder nach unten zurück.|Nicht verfügbar.|  
|&#92;|Schützt ein Masken Zeichen und verwandelt es in ein Literalzeichen. " \\ \\ " ist die Escapesequenz für einen umgekehrten Schrägstrich.|&#92;|  
|Alle anderen Zeichen.|Literale. Alle nicht Masken Elemente werden innerhalb von als sich selbst angezeigt <xref:System.Windows.Forms.MaskedTextBox> .|Alle anderen Zeichen.|  
  
 Die Symbole Decimal (.), Tausendstel (,), time (:), Date (/) und Currency ($) werden standardmäßig so angezeigt, wie Sie in der Kultur der Anwendung definiert sind. Mithilfe der-Eigenschaft können Sie erzwingen, dass Symbole für eine andere Kultur angezeigt werden <xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A> .  
  
## <a name="regular-expressions-and-masks"></a>Reguläre Ausdrücke und Masken  

 Obwohl Sie reguläre Ausdrücke und Masken zum Validieren von Benutzereingaben verwenden können, sind Sie nicht vollständig Äquivalent. Reguläre Ausdrücke können komplexere Muster als Masken Ausdrücken, aber Masken können dieselben Informationen ausführlicher und in einem kulturrelevanten Format ausdrücken.  
  
 In der folgenden Tabelle werden vier reguläre Ausdrücke und die entsprechende Maske für jeden verglichen.  
  
|Regular Expression|Mask|Hinweise|  
|------------------------|----------|-----------|  
|`\d{2}/\d{2}/\d{4}`|`00/00/0000`|Das `/` Zeichen in der Maske ist ein logisches Datums Trennzeichen und wird dem Benutzer als Datums Trennzeichen angezeigt, das der aktuellen Kultur der Anwendung entspricht.|  
|`\d{2}-[A-Z][a-z]{2}-\d{4}`|`00->L<LL-0000`|Ein Datum (Tag, Monats Abkürzung und Jahr) in USA Format, in dem die drei buchstabige Monats Abkürzung mit einem ersten Großbuchstaben, gefolgt von zwei Kleinbuchstaben, angezeigt wird.|  
|`(\(\d{3}\)-)?\d{3}-d{4}`|`(999)-000-0000`|USA Telefonnummer, flächencode optional. Wenn der Benutzer die optionalen Zeichen nicht eingeben möchte, kann er entweder Leerzeichen eingeben oder den Mauszeiger direkt an der Position in der Maske platzieren, die durch den ersten 0 dargestellt wird.|  
|`$\d{6}.00`|`$999,999.00`|Ein Währungswert im Bereich von 0 bis 999999. Die Währungs-, Tausendstel-und Dezimalzeichen werden zur Laufzeit durch ihre kulturspezifischen Entsprechungen ersetzt.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>
- <xref:System.Windows.Forms.MaskedTextBox>
- [Überprüfen von Zeichenfolgen in Visual Basic](validating-strings.md)
- [MaskedTextBox-Steuerelement](/dotnet/desktop/winforms/controls/maskedtextbox-control-windows-forms)
