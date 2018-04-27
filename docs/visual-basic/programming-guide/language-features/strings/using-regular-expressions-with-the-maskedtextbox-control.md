---
title: Verwenden von regulären Ausdrücken mit dem MaskedTextBox-Steuerelement in Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], regular expressions
- strings [Visual Basic], masked edit
ms.assetid: 2a048fb0-7053-487d-b2c5-ffa5e22ed6f9
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c72542c05123ef62a8f95afbe1bb19cb823d1f21
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="using-regular-expressions-with-the-maskedtextbox-control-in-visual-basic"></a>Verwenden von regulären Ausdrücken mit dem MaskedTextBox-Steuerelement in Visual Basic
In diesem Beispiel wird veranschaulicht, wie einfache reguläre Ausdrücke mit konvertiert die <xref:System.Windows.Forms.MaskedTextBox> Steuerelement.  
  
## <a name="description-of-the-masking-language"></a>Beschreibung der Maskierungssprache  
 Der Standard <xref:System.Windows.Forms.MaskedTextBox> maskiert Sprache basiert auf von verwendet die `Masked Edit` steuern in Visual Basic 6.0 und sollte für Benutzer, die von dieser Plattform migrieren vertraut sein.  
  
 Die <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> Eigenschaft von der <xref:System.Windows.Forms.MaskedTextBox> Steuerelement gibt an, welche Eingabeformat verwenden. Die Maske muss eine Zeichenfolge besteht aus einem oder mehreren der Maskierung Elemente aus der folgenden Tabelle sein.  
  
|Maskierung-element|Beschreibung|Reguläre Ausdrücke-element|  
|---------------------|-----------------|--------------------------------|  
|0|Eine einzelne Ziffer zwischen 0 und 9. Eintrag erforderlich.|\d|  
|9|Ziffern oder Leerzeichen. Die Eingabe ist optional.|[\d]?|  
|#|Ziffern oder Leerzeichen. Die Eingabe ist optional. Wenn diese Position in der Maske leer ist, wird das Gerät als Leerzeichen gerendert werden. Pluszeichen (+) und Minuszeichen (-) sind zulässig.|[\d+-]?|  
|L|ASCII-Buchstaben. Eintrag erforderlich.|[a-zA-Z]|  
|?|ASCII-Buchstaben. Die Eingabe ist optional.|[a-zA-Z]?|  
|&|Zeichen Eintrag erforderlich.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]|  
|C|Zeichen Die Eingabe ist optional.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]?|  
|A|Alphanumerisch ist. Die Eingabe ist optional.|\W|  
|sein.|Kultur entsprechende dezimalplatzhalter.|Nicht verfügbar.|  
|,|Kultur entsprechende Tausende Platzhalter.|Nicht verfügbar.|  
|:|Kultur entsprechende Zeittrennzeichen.|Nicht verfügbar.|  
|/|Kultur entsprechende Datumstrennzeichen.|Nicht verfügbar.|  
|$|Kultur entsprechende Währungssymbol.|Nicht verfügbar.|  
|\<|Konvertiert alle Zeichen in Kleinbuchstaben.|Nicht verfügbar.|  
|>|Konvertiert alle Zeichen in Großbuchstaben konvertiert wurden.|Nicht verfügbar.|  
|&#124;|Macht eine vorherige Schicht oben oder unten verschieben.|Nicht verfügbar.|  
|\|Ein Zeichen zum Maskieren, wandelt sie in ein Literal mit Escapezeichen zu versehen. "\\\\" ist die Escapesequenz für einen umgekehrten Schrägstrich.|\|  
|Alle anderen Zeichen.|Literale. Alle Elemente von nicht-Maske werden angezeigt, als Sie selbst in <xref:System.Windows.Forms.MaskedTextBox>.|Alle anderen Zeichen.|  
  
 Das Dezimaltrennzeichen (.), Tausendstel-(,), Zeit (:), Datum (/) und Währung ($) werden standardmäßig die Symbole anzeigen, wie durch die Kultur der Anwendung definiert. Sie können erzwingen, sie zum Anzeigen von Symbolen für eine andere Kultur mithilfe der <xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A> Eigenschaft.  
  
## <a name="regular-expressions-and-masks"></a>Reguläre Ausdrücke und Masken  
 Obwohl reguläre Ausdrücke und Masken verwenden können, um Benutzereingaben zu überprüfen, sind sie nicht vollständig äquivalent. Reguläre Ausdrücke können komplexere Muster als Masken Ausdrücken, jedoch Masken können die gleiche Informationen express, prägnanter und in ein Format für relevant.  
  
 Die folgende Tabelle vergleicht die vier reguläre Ausdrücke und die entsprechende Maske für die einzelnen.  
  
|Regulärer Ausdruck|Format|Hinweise|  
|------------------------|----------|-----------|  
|`\d{2}/\d{2}/\d{4}`|`00/00/0000`|Die `/` Zeichen in der Maske ist ein logisches Datumstrennzeichen und wird für den Benutzer als das Trennzeichen für Datumsangaben, die aktuelle Kultur der Anwendung angezeigt.|  
|`\d{2}-[A-Z][a-z]{2}-\d{4}`|`00->L<LL-0000`|Ein Datum (Tag, Abkürzung für den Monat und Jahr) in den Vereinigten Staaten-Format, in dem die mit drei Buchstaben bestehende monatsabkürzung mit einem anfänglichen Großbuchstaben gefolgt von zwei Kleinbuchstaben angezeigt wird.|  
|`(\(\d{3}\)-)?\d{3}-d{4}`|`(999)-000-0000`|USA-Telefonnummer, Ortskennzahl optional. Wenn der Benutzer nicht die optionalen Zeichen eingeben möchten, können sie geben Sie ein Leerzeichen oder platzieren den Mauszeiger direkt an der Position in der Maske, die durch die erste 0 dargestellt.|  
|`$\d{6}.00`|`$999,999.00`|Ein Währungswert im Bereich von 0 bis 999999. Die Währung, Tausendstel und Dezimalzeichen werden zur Laufzeit durch ihre kulturspezifische-Entsprechungen ersetzt werden.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>  
 <xref:System.Windows.Forms.MaskedTextBox>  
 [Überprüfen von Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)  
 [MaskedTextBox-Steuerelement](../../../../framework/winforms/controls/maskedtextbox-control-windows-forms.md)
