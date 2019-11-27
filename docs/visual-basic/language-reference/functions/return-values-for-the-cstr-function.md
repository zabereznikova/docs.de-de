---
title: Rückgabewerte für die CStr-Funktion
ms.date: 07/20/2015
helpviewer_keywords:
- times [Visual Basic], CStr Function return values
- type conversion [Visual Basic]
- dates [Visual Basic], CStr Function return values
- CStr function
- strings [Visual Basic], return value
- Date data type [Visual Basic], converting
- dates [Visual Basic]
- String data type [Visual Basic], converting
ms.assetid: 3aa744e7-1419-45d5-85e3-e5abc2953673
ms.openlocfilehash: 4a40777c7290ec6d8c0d032f2edca5d889e20f04
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349992"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a>Rückgabewerte für die CStr-Funktion (Visual Basic)
In der folgenden Tabelle werden die Rückgabewerte für `CStr` für verschiedene Datentypen von `expression`beschrieben.  
  
|Wenn `expression` Typ ist|`CStr`-Rückgaben|  
|-----------------------------|--------------------|  
|[Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Eine Zeichenfolge, die "true" oder "false" enthält.|  
|[Date-Datentyp](../../../visual-basic/language-reference/data-types/date-data-type.md)|Eine Zeichenfolge mit einem `Date` Wert (Datum und Uhrzeit) im kurzen Datumsformat Ihres Systems.|  
|[Numerische Datentypen](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|Eine Zeichenfolge, die die Zahl darstellt.|  
  
## <a name="cstr-and-date"></a>CStr und Datum  
 Der `Date`-Typ enthält immer Datums-und Uhrzeit Informationen. Für den Zweck der Typkonvertierung berücksichtigt Visual Basic 1/1/0001 (1. Januar des Jahres 1) als *neutralen Wert* für das Datum und 00:00:00 (Mitternacht) als neutralen Wert für die Zeit. `CStr` enthält keine neutralen Werte in die resultierende Zeichenfolge. Wenn Sie `#January 1, 0001 9:30:00#` z. b. in eine Zeichenfolge konvertieren, ist das Ergebnis "9:30:00 am"; die Datumsinformationen werden unterdrückt. Die Datumsinformationen sind jedoch weiterhin im ursprünglichen `Date` Wert vorhanden und können mit Funktionen wie <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>wieder hergestellt werden.  
  
> [!NOTE]
> Die `CStr`-Funktion führt die Konvertierung basierend auf den aktuellen Kultur Einstellungen für die Anwendung aus. Um die Zeichen folgen Darstellung einer Zahl in einer bestimmten Kultur zu erhalten, verwenden Sie die `ToString(IFormatProvider)`-Methode der Zahl. Verwenden Sie z. b. <xref:System.Double.ToString%2A?displayProperty=nameWithType>, wenn Sie einen Wert vom Typ `Double` in einen `String`-Wert umrechnen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Date-Datentyp](../../../visual-basic/language-reference/data-types/date-data-type.md)
