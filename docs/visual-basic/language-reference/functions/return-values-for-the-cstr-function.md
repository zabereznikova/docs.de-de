---
title: "Rückgabewerte für die CStr-Funktion (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b498c9b1b7916467c96ed2c645c7131192a5e8b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a>Rückgabewerte für die CStr-Funktion (Visual Basic)
Die folgende Tabelle beschreibt die Rückgabewerte für `CStr` für verschiedene Datentypen der `expression`.  
  
|Wenn `expression` Typ ist|`CStr`Gibt zurück|  
|-----------------------------|--------------------|  
|[Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Eine Zeichenfolge mit "True" oder "False".|  
|[Date-Datentyp](../../../visual-basic/language-reference/data-types/date-data-type.md)|Eine Zeichenfolge mit einem `Date` Wert (Datum und Uhrzeit) im kurzen Datumsformat Ihres Systems.|  
|[Numerische Datentypen](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|Eine Zeichenfolge, die die Anzahl darstellt.|  
  
## <a name="cstr-and-date"></a>CStr und Datum  
 Die `Date` Typ enthält immer die Datums-und Uhrzeitinformationen. Zwecken Typumwandlung berücksichtigt Visual Basic 1/1/0001 (1. Januar des Jahres 1), werden eine *neutrale Wert* für das Datum und 00:00:00 (Mitternacht) für die Zeit ein neutrale Wert sein. `CStr`umfasst nicht neutral Werte in die resultierende Zeichenfolge. Angenommen, Sie konvertieren `#January 1, 0001 9:30:00#` in eine Zeichenfolge das Ergebnis "9:30:00 AM"; die Datumsinformationen unterdrückt wird. Die Datumsinformationen ist jedoch weiterhin vorhanden, in der ursprünglichen `Date` Wert und können mit Funktionen wie z. B. wiederhergestellt werden <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.  
  
> [!NOTE]
>  Die `CStr` -Funktion führt die Konvertierung auf Grundlage der aktuellen kultureinstellungen für die Anwendung. Um die Zeichenfolgendarstellung einer Zahl in einer bestimmten Kultur abzurufen, verwenden Sie der Anzahl `ToString(IFormatProvider)` Methode. Verwenden Sie z. B. <xref:System.Double.ToString%2A?displayProperty=nameWithType> beim Konvertieren eines Werts vom Typ `Double` zu einem `String`.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [Date-Datentyp](../../../visual-basic/language-reference/data-types/date-data-type.md)
