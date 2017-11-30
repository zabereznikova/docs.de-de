---
title: Typkonvertierungstabellen in .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- widening conversions
- narrowing conversions
- type conversion, table
- converting types, narrowing conversions
- converting types, widening conversions
- base types, converting
- tables [.NET Framework], type conversions
- data types [.NET Framework], converting
ms.assetid: 0ea65c59-85eb-4a52-94ca-c36d3bd13058
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 327469f9a151b6ef7e1c42f6669c0a9dae7016fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="type-conversion-tables-in-net"></a>Typkonvertierungstabellen in .NET
Eine erweiternde Konvertierung tritt auf, wenn ein Wert eines bestimmten Typs in einen anderen Typ konvertiert wird, der gleich groß oder größer ist. Eine einschränkende Konvertierung tritt auf, wenn ein Wert eines bestimmten Typs in einen anderen Typ konvertiert wird, der kleiner ist. Die Tabellen in diesem Thema veranschaulichen die Verhaltensweisen dieser beiden Konvertierungsarten.  
  
## <a name="widening-conversions"></a>Erweiterungskonvertierungen  
 Die folgende Tabelle beschreibt die erweiternden Konvertierungen, die ohne den Verlust von Informationen erfolgen können.  
  
|Typ|Kann ohne Datenverlust konvertiert werden in|  
|----------|-------------------------------------------|  
|<xref:System.Byte>|<xref:System.UInt16>, <xref:System.Int16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.SByte>|<xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Int16>|<xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.UInt16>|<xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Char>|<xref:System.UInt16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Int32>|<xref:System.Int64>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.UInt32>|<xref:System.Int64>, <xref:System.UInt64>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Int64>|<xref:System.Decimal>|  
|<xref:System.UInt64>|<xref:System.Decimal>|  
|<xref:System.Single>|<xref:System.Double>|  
  
 Einige erweiternde Konvertierungen in <xref:System.Single> oder <xref:System.Double> kann einem Genauigkeitsverlust führen. Die folgende Tabelle beschreibt die erweiternden Konvertierungen, die einen Informationsverlust nach sich ziehen können.  
  
|Typ|Kann konvertiert werden in|  
|----------|-------------------------|  
|<xref:System.Int32>|<xref:System.Single>|  
|<xref:System.UInt32>|<xref:System.Single>|  
|<xref:System.Int64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.UInt64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.Decimal>|<xref:System.Single>, <xref:System.Double>|  
  
## <a name="narrowing-conversions"></a>Eingrenzungskonvertierungen  
 Eine einschränkende Konvertierung in <xref:System.Single> oder <xref:System.Double> kann einen Datenverlust verursachen. Wenn der Zieltyp die Quelle nicht mit der gleichen Detailgenauigkeit und im gleichen Umfang wiedergeben kann, wird der resultierende Typ auf die Konstante `PositiveInfinity` oder `NegativeInfinity` festgelegt. `PositiveInfinity`Ergebnis der Division einer positiven Zahl durch 0 (null) und wird auch zurückgegeben, wenn der Wert des eine <xref:System.Single> oder <xref:System.Double> überschreitet den Wert von der `MaxValue` Feld. `NegativeInfinity`Ergebnis der Division einer negativen Zahl durch 0 (null) und wird auch zurückgegeben, wenn der Wert des eine <xref:System.Single> oder <xref:System.Double> unterschreitet den Wert des der `MinValue` Feld. Eine Konvertierung von einem <xref:System.Double> auf eine <xref:System.Single> unter Umständen `PositiveInfinity` oder `NegativeInfinity`.  
  
 Eine einschränkende Konvertierung kann auch zum Verlust von Informationen für andere Datentypen führen. Allerdings ein <xref:System.OverflowException> wird ausgelöst, wenn der Wert eines Typs, der konvertiert wird außerhalb des Bereichs, die gemäß des Zieltyps liegt `MaxValue` und `MinValue` Felder sowie die Konvertierung von der Laufzeit, um sicherzustellen, dass den Wert des Ziels aktiviert ist Typ nicht überschreitet die `MaxValue` oder `MinValue`. Konvertierungen, die mit ausgeführt werden die <xref:System.Convert?displayProperty=nameWithType> Klasse immer auf diese Weise überprüft werden.  
  
 Die folgende Tabelle enthält die Konvertierungen, die Auslösen einer <xref:System.OverflowException> mit <xref:System.Convert?displayProperty=nameWithType> oder eine Konvertierung überprüft, wenn der Wert des konvertierten Typs außerhalb des definierten Bereichs des resultierenden Typs ist.  
  
|Typ|Kann konvertiert werden in|  
|----------|-------------------------|  
|<xref:System.Byte>|<xref:System.SByte>|  
|<xref:System.SByte>|<xref:System.Byte>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64>|  
|<xref:System.Int16>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.UInt16>|  
|<xref:System.UInt16>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>|  
|<xref:System.Int32>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>,<xref:System.UInt32>|  
|<xref:System.UInt32>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>|  
|<xref:System.Int64>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>,<xref:System.UInt32>,<xref:System.UInt64>|  
|<xref:System.UInt64>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>|  
|<xref:System.Decimal>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64>|  
|<xref:System.Single>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64>|  
|<xref:System.Double>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64>|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Convert?displayProperty=nameWithType>  
 [Typkonvertierung in .NET](../../../docs/standard/base-types/type-conversion.md)
