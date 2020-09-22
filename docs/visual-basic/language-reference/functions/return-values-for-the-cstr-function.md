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
ms.openlocfilehash: cc5e5cc437175e9aebfba559488ca74283faa9ad
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870161"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a>Rückgabewerte für die CStr-Funktion (Visual Basic)

In der folgenden Tabelle werden die Rückgabewerte für `CStr` unterschiedliche Datentypen von beschrieben `expression` .  
  
|Wenn der `expression` Typ ist|`CStr`-Rückgaben|  
|-----------------------------|--------------------|  
|[Boolean-Datentyp](../data-types/boolean-data-type.md)|Eine Zeichenfolge, die "true" oder "false" enthält.|  
|[Date-Datentyp](../data-types/date-data-type.md)|Eine Zeichenfolge mit einem `Date` Wert (Datum und Uhrzeit) im kurzen Datumsformat Ihres Systems.|  
|[Numerische Datentypen](../../programming-guide/language-features/data-types/numeric-data-types.md)|Eine Zeichenfolge, die die Zahl darstellt.|  
  
## <a name="cstr-and-date"></a>CStr und Datum  

 Der- `Date` Typ enthält immer Datums-und Uhrzeit Informationen. Für den Zweck der Typkonvertierung berücksichtigt Visual Basic 1/1/0001 (1. Januar des Jahres 1) als *neutralen Wert* für das Datum und 00:00:00 (Mitternacht) als neutralen Wert für die Zeit. `CStr` schließt keine neutralen Werte in die resultierende Zeichenfolge ein. Wenn Sie z `#January 1, 0001 9:30:00#` . b. in eine Zeichenfolge konvertieren, ist das Ergebnis "9:30:00 am"; die Datumsinformationen werden unterdrückt. Die Datumsinformationen sind jedoch weiterhin im ursprünglichen `Date` Wert vorhanden und können mit Funktionen wie wieder hergestellt werden <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> .  
  
> [!NOTE]
> Die- `CStr` Funktion führt die Konvertierung basierend auf den aktuellen Kultur Einstellungen für die Anwendung aus. Um die Zeichen folgen Darstellung einer Zahl in einer bestimmten Kultur zu erhalten, verwenden Sie die-Methode der Zahl `ToString(IFormatProvider)` . Verwenden Sie beispielsweise, <xref:System.Double.ToString%2A?displayProperty=nameWithType> Wenn Sie einen Wert vom Typ in einen-Wert umrechnen `Double` `String` .  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [Type Conversion Functions](type-conversion-functions.md)
- [Boolean-Datentyp](../data-types/boolean-data-type.md)
- [Date-Datentyp](../data-types/date-data-type.md)
