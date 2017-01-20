---
title: "Return Values for the CStr Function (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "times, CStr Function return values"
  - "type conversion"
  - "dates [Visual Basic], CStr Function return values"
  - "CStr function"
  - "strings [Visual Basic], return value"
  - "Date data type, converting"
  - "dates [Visual Basic]"
  - "String data type, converting"
ms.assetid: 3aa744e7-1419-45d5-85e3-e5abc2953673
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Return Values for the CStr Function (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

In der folgenden Tabelle werden die Rückgabewerte für `CStr` bei unterschiedlichen `expression`\-Datenypen beschrieben.  
  
|Wenn `expression` den folgenden Datentyp hat:|ist der Rückgabewert von `CStr`|  
|---------------------------------------------------|-------------------------------------|  
|[Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Eine Zeichenfolge, die den Wert **True** oder **False** enthält.|  
|[Date Data Type](../../../visual-basic/language-reference/data-types/date-data-type.md)|Eine Zeichenfolge, die einen `Date`\-Wert \(Datum und Uhrzeit\) im kurzen Datumsformat des Systems enthält.|  
|[Numeric Data Types](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|Eine Zeichenfolge, die die Zahl enthält.|  
  
## CStr und Datum  
 Der `Date`\-Datentyp enthält immer sowohl Datums\- als auch Uhrzeitinformationen.  Für die Typkonvertierung verwendet Visual Basic 1\/1\/0001 \(1. Januar des Jahres 1\) als *neutralen Wert* für das Datum und 00:00:00 \(Mitternacht\) als neutralen Wert für die Uhrzeit.  `CStr` schließt keine neutralen Werte in die Ergebniszeichenfolge ein.  Wenn beispielsweise `#January 1, 0001 9:30:00#` in eine Zeichenfolge umgewandelt wird, lautet das Ergebnis "9:30:00 AM"; die Datumsinformationen werden unterdrückt.  Die Datumsinformationen sind dabei im ursprünglichen `Date`\-Wert noch enthalten und können mit Funktionen wie <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> wiederhergestellt werden.  
  
> [!NOTE]
>  Die `CStr`\-Funktion führt die Konvertierung auf der Grundlage der aktuellen Kultureinstellungen für die Anwendung aus.  Um die Zeichenfolgenentsprechung einer Zahl in einer bestimmten Kultur abzurufen, verwenden Sie `ToString(IFormatProvider)`\-Methode der Zahl.  Verwenden Sie beispielsweise <xref:System.Double.ToString%2A?displayProperty=fullName>, wenn Sie einen Wert des Typs `Double` in einen `String`\-Wert konvertieren.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md)   
 [Date Data Type](../../../visual-basic/language-reference/data-types/date-data-type.md)