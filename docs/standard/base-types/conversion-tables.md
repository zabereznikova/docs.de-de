---
title: Typkonvertierungstabellen in .NET
ms.date: 03/30/2017
helpviewer_keywords:
- widening conversions
- narrowing conversions
- type conversion, table
- converting types, narrowing conversions
- converting types, widening conversions
- base types, converting
- tables [.NET], type conversions
- data types [.NET], converting
ms.assetid: 0ea65c59-85eb-4a52-94ca-c36d3bd13058
ms.openlocfilehash: dc98a326155273805e3157d99755de2e97f83a46
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730213"
---
# <a name="type-conversion-tables-in-net"></a>Typkonvertierungstabellen in .NET

Eine erweiternde Konvertierung tritt auf, wenn ein Wert eines bestimmten Typs in einen anderen Typ konvertiert wird, der gleich groß oder größer ist. Eine einschränkende Konvertierung tritt auf, wenn ein Wert eines bestimmten Typs in einen anderen Typ konvertiert wird, der kleiner ist. Die Tabellen in diesem Thema veranschaulichen die Verhaltensweisen dieser beiden Konvertierungsarten.  
  
## <a name="widening-conversions"></a>Erweiternde Konvertierungen  

 Die folgende Tabelle beschreibt die erweiternden Konvertierungen, die ohne Informationsverlust ausgeführt werden können.  
  
|Geben Sie Folgendes ein:|Kann ohne Datenverlust konvertiert werden in|  
|----------|-------------------------------------------|  
|<xref:System.Byte>|<xref:System.UInt16>, <xref:System.Int16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.SByte>|<xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Int16>|<xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.UInt16>|<xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Char>|<xref:System.UInt16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Int32>|<xref:System.Int64>ist <xref:System.Double>ist <xref:System.Decimal>|  
|<xref:System.UInt32>|<xref:System.Int64>, <xref:System.UInt64>, <xref:System.Double>, <xref:System.Decimal>|  
|<xref:System.Int64>|<xref:System.Decimal>|  
|<xref:System.UInt64>|<xref:System.Decimal>|  
|<xref:System.Single>|<xref:System.Double>|  
  
 Einige erweiternde Konvertierungen zu <xref:System.Single> oder <xref:System.Double> können zu einem Genauigkeitsverlust führen. Die folgende Tabelle beschreibt die erweiternden Konvertierungen, die einen Informationsverlust nach sich ziehen können.  
  
|Geben Sie Folgendes ein:|Kann konvertiert werden in|  
|----------|-------------------------|  
|<xref:System.Int32>|<xref:System.Single>|  
|<xref:System.UInt32>|<xref:System.Single>|  
|<xref:System.Int64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.UInt64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.Decimal>|<xref:System.Single>, <xref:System.Double>|  
  
## <a name="narrowing-conversions"></a>Einschränkende Konvertierungen  

 Eine einschränkende Konvertierung in <xref:System.Single> oder <xref:System.Double> kann zu einem Informationsverlust führen. Wenn der Zieltyp die Quelle nicht mit der gleichen Detailgenauigkeit und im gleichen Umfang wiedergeben kann, wird der resultierende Typ auf die Konstante `PositiveInfinity` oder `NegativeInfinity` festgelegt. `PositiveInfinity` resultiert aus der Division einer positiven Zahl durch null und wird auch zurückgegeben, wenn der Wert eines <xref:System.Single>- oder <xref:System.Double>-Typs den Wert des Felds `MaxValue` überschreitet. `NegativeInfinity` resultiert aus der Division einer negativen Zahl durch null und wird auch zurückgegeben, wenn der Wert eines <xref:System.Single>- oder <xref:System.Double>-Typs den Wert des Felds `MinValue` unterschreitet. Eine Konvertierung aus einem <xref:System.Double>- in einen <xref:System.Single>-Typ kann zu `PositiveInfinity` oder `NegativeInfinity` führen.  
  
 Eine einschränkende Konvertierung kann auch zum Verlust von Informationen für andere Datentypen führen. Es wird jedoch eine <xref:System.OverflowException> ausgelöst, wenn der Wert eines zu konvertierenden Typs außerhalb des von den Feldern `MaxValue` und `MinValue` des Zieltyps angegebenen Bereichs liegt und die Konvertierung von der Runtime geprüft wird, um sicherzustellen, dass der Wert des Zieltyps den `MaxValue` oder `MinValue` nicht überschreitet. Konvertierungen, die mit der <xref:System.Convert?displayProperty=nameWithType>-Klasse ausgeführt werden, werden immer auf diese Weise überprüft.  
  
 Die folgende Tabelle enthält Konvertierungen, die eine <xref:System.OverflowException> über <xref:System.Convert?displayProperty=nameWithType> oder eine andere Konvertierungsprüfung auslösen, wenn der Wert des zu konvertierenden Typs außerhalb des definierten Bereichs des resultierenden Typs liegt.  
  
|Geben Sie Folgendes ein:|Kann konvertiert werden in|  
|----------|-------------------------|  
|<xref:System.Byte>|<xref:System.SByte>|  
|<xref:System.SByte>|<xref:System.Byte>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64>|  
|<xref:System.Int16>|<xref:System.Byte>ist <xref:System.SByte>ist <xref:System.UInt16>|  
|<xref:System.UInt16>|<xref:System.Byte>ist <xref:System.SByte>ist <xref:System.Int16>|  
|<xref:System.Int32>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>,<xref:System.UInt32>|  
|<xref:System.UInt32>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>|  
|<xref:System.Int64>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>,<xref:System.UInt32>,<xref:System.UInt64>|  
|<xref:System.UInt64>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>|  
|<xref:System.Decimal>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64>|  
|<xref:System.Single>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64>|  
|<xref:System.Double>|<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64>|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Convert?displayProperty=nameWithType>
- [Typkonvertierung in .NET](type-conversion.md)
