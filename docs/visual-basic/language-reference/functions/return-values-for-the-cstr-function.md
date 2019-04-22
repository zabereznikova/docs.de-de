---
title: Rückgabewerte für die CStr-Funktion (Visual Basic)
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
ms.openlocfilehash: 3653194c7e48533e664ac7513ca7f4f48d1c69f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819514"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a>Rückgabewerte für die CStr-Funktion (Visual Basic)
Die folgende Tabelle beschreibt die Rückgabewerte für `CStr` für verschiedene Datentypen der `expression`.  
  
|Wenn `expression` Typ ist|`CStr`-Rückgaben|  
|-----------------------------|--------------------|  
|[Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Eine Zeichenfolge, die mit "True" oder "False".|  
|[Date-Datentyp](../../../visual-basic/language-reference/data-types/date-data-type.md)|Eine Zeichenfolge mit einem `Date` Wert (Datum und Uhrzeit), in dem kurzen Datumsformat Ihres Systems.|  
|[Numerische Datentypen](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|Eine Zeichenfolge, die die Anzahl darstellt.|  
  
## <a name="cstr-and-date"></a>Datum und die CStr  
 Die `Date` geben immer sowohl Datums-und Uhrzeitinformationen enthält. Für Zwecke der typkonvertierung berücksichtigt Visual Basic 1/1/0001 (1. Januar des Jahres 1), werden eine *neutrale Wert* für das Datum und 00:00:00 (Mitternacht) einen neutralen Wert für die Zeit sein. `CStr` umfasst nicht neutrale Werte in die resultierende Zeichenfolge. Wenn Sie konvertieren, z. B. `#January 1, 0001 9:30:00#` in eine Zeichenfolge, das Ergebnis "9:30:00 Uhr"; die Datumsinformationen unterdrückt wird. Die Datumsinformationen ist jedoch weiterhin vorhanden, in der ursprünglichen `Date` Wert und kann mit Funktionen wiederhergestellt werden, z. B. <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.  
  
> [!NOTE]
>  Die `CStr` Funktion führt die Konvertierung, die basierend auf den Einstellungen der aktuellen Kultur für die Anwendung. Um die Zeichenfolgendarstellung einer Zahl in einer bestimmten Kultur zu erhalten, verwenden Sie der Anzahl der `ToString(IFormatProvider)` Methode. Verwenden Sie z. B. <xref:System.Double.ToString%2A?displayProperty=nameWithType> beim Konvertieren eines Werts vom Typ `Double` zu einem `String`.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Date-Datentyp](../../../visual-basic/language-reference/data-types/date-data-type.md)
