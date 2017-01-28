---
title: Typkonvertierungstabellen
description: Typkonvertierungstabellen
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/22/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: d602f260-e7cf-49c8-a37f-731f40e4a538
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 16f38150f26b477de5685d2d3b0ef18afb94c236

---

# <a name="type-conversion-tables"></a>Typkonvertierungstabellen

Eine erweiternde Konvertierung tritt auf, wenn ein Wert eines bestimmten Typs in einen anderen Typ konvertiert wird, der gleich groß oder größer ist. Eine einschränkende Konvertierung tritt auf, wenn ein Wert eines bestimmten Typs in einen anderen Typ konvertiert wird, der kleiner ist. Die Tabellen in diesem Thema veranschaulichen die Verhaltensweisen dieser beiden Konvertierungsarten.

## <a name="widening-conversions"></a>Erweiternde Konvertierungen

Typ | Kann ohne Datenverlust konvertiert werden in
---- | -------------------------------------
[Byte](xref:System.Byte) | [UInt16](xref:System.UInt16), [Int16](xref:System.Int16), [UInt32](xref:System.UInt32), [Int32](xref:System.Int32), [UInt64](xref:System.UInt64), [Int64](xref:System.Int64), [Single](xref:System.Single), [Double](xref:System.Double), [Decimal](xref:System.Decimal)
[SByte](xref:System.SByte) | [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [Single](xref:System.Single), [Double](xref:System.Double), [Decimal](xref:System.Decimal)
[Int16](xref:System.Int16) | [Int32](xref:System.Int32), [Int64](xref:System.Int64), [Single](xref:System.Single), [Double](xref:System.Double), [Decimal](xref:System.Decimal)
[UInt16](xref:System.UInt16) | [UInt32](xref:System.UInt32), [Int32](xref:System.Int32), [UInt64](xref:System.UInt64), [Int64](xref:System.Int64), [Single](xref:System.Single), [Double](xref:System.Double), [Decimal](xref:System.Decimal)
[Char](xref:System.Char) | [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), [Int32](xref:System.Int32), [UInt64](xref:System.UInt64), [Int64](xref:System.Int64), [Single](xref:System.Single), [Double](xref:System.Double), [Decimal](xref:System.Decimal)
[Int32](xref:System.Int32) | [Int64](xref:System.Int64), [Double](xref:System.Double), [Decimal](xref:System.Decimal)
[UInt32](xref:System.UInt32) | [Int64](xref:System.Int64), [UInt64](xref:System.UInt64), [Double](xref:System.Double), [Decimal](xref:System.Decimal)
[Int64](xref:System.Int64) | [Decimal](xref:System.Decimal)
[UInt64](xref:System.UInt64) | [Decimal](xref:System.Decimal)
[Single](xref:System.Single) | [Double](xref:System.Double)

Einige erweiternde Konvertierungen zu [Single](xref:System.Single) oder [Double](xref:System.Double) können zu einem Genauigkeitsverlust führen. Die folgende Tabelle beschreibt die erweiternden Konvertierungen, die einen Informationsverlust nach sich ziehen können.

Typ | Kann konvertiert werden in
---- | -------------------
[Int32](xref:System.Int32) | [Single](xref:System.Single)
[UInt32](xref:System.UInt32) | [Single](xref:System.Single)
[Int64](xref:System.Int64) | [Single](xref:System.Single), [Double](xref:System.Double)
[UInt64](xref:System.UInt64) | [Single](xref:System.Single), [Double](xref:System.Double)
[Decimal](xref:System.Decimal) | [Single](xref:System.Single), [Double](xref:System.Double)

## <a name="narrowing-conversions"></a>Einschränkende Konvertierungen

Eine einschränkende Konvertierung in [Single](xref:System.Single) oder [Double](xref:System.Double) kann zu einem Informationsverlust führen. Wenn der Zieltyp die Quelle nicht mit der gleichen Detailgenauigkeit und im gleichen Umfang wiedergeben kann, wird der resultierende Typ auf die Konstante `PositiveInfinity` oder `NegativeInfinity` festgelegt. `PositiveInfinity` resultiert aus der Division einer positiven Zahl durch null und wird auch zurückgegeben, wenn der Wert eines [Single](xref:System.Single)- oder [Double](xref:System.Double)-Typs den Wert des Felds `MaxValue` überschreitet. `NegativeInfinity` resultiert aus der Division einer negativen Zahl durch null und wird auch zurückgegeben, wenn der Wert eines [Single](xref:System.Single)- oder [Double](xref:System.Double)-Typs den Wert des Felds `MinValue` unterschreitet. Eine Konvertierung aus einem [Double](xref:System.Double)- in einen [Single](xref:System.Single)-Typ kann zu `PositiveInfinity` oder `NegativeInfinity` führen.

Eine einschränkende Konvertierung kann auch zum Verlust von Informationen für andere Datentypen führen. Es wird jedoch eine [OverflowException](xref:System.OverflowException) ausgelöst, wenn der Wert eines zu konvertierenden Typs außerhalb des von den Feldern `MaxValue` und `MinValue` des Zieltyps angegebenen Bereichs liegt und die Konvertierung von der Runtime geprüft wird, um sicherzustellen, dass der Wert des Zieltyps den `MaxValue` oder `MinValue` nicht überschreitet. Konvertierungen, die mit der [System.Convert](xref:System.Convert)-Klasse ausgeführt werden, werden immer auf diese Weise überprüft.

Die folgende Tabelle enthält Konvertierungen, die über [System.Convert](xref:System.Convert) oder eine andere Konvertierungsprüfung eine [OverflowException](xref:System.OverflowException) auslösen, wenn der Wert des zu konvertierenden Typs außerhalb des definierten Bereichs des resultierenden Typs liegt.

Typ | Kann konvertiert werden in
---- | -------------------
[Byte](xref:System.Byte) | [SByte](xref:System.SByte)
[SByte](xref:System.SByte) | [Byte](xref:System.Byte), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), [UInt64](xref:System.UInt64)
[Int16](xref:System.Int16) | [Byte](xref:System.Byte), [SByte](xref:System.SByte), [UInt16](xref:System.UInt16)
[UInt16](xref:System.UInt16) | [Byte](xref:System.Byte), [SByte](xref:System.SByte), [Int16](xref:System.Int16)
[Int32](xref:System.Int32) | [Byte](xref:System.Byte), [SByte](xref:System.SByte), [Int16](xref:System.Int16), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32)
[UInt32](xref:System.UInt32) | [Byte](xref:System.Byte), [SByte](xref:System.SByte), [Int16](xref:System.Int16), [UInt16](xref:System.UInt16), [Int32](xref:System.Int32)
[Int64](xref:System.Int64) | [Byte](xref:System.Byte), [SByte](xref:System.SByte), [Int16](xref:System.Int16), [UInt16](xref:System.UInt16), [Int32](xref:System.Int32), [UInt32](xref:System.UInt32), [UInt64](xref:System.UInt64)
[UInt64](xref:System.UInt64) | [Byte](xref:System.Byte), [SByte](xref:System.SByte), [Int16](xref:System.Int16), [UInt16](xref:System.UInt16), [Int32](xref:System.Int32), [UInt32](xref:System.UInt32), [Int64](xref:System.Int64)
[Decimal](xref:System.Decimal) | [Byte](xref:System.Byte), [SByte](xref:System.SByte), [Int16](xref:System.Int16), [UInt16](xref:System.UInt16), [Int32](xref:System.Int32), [UInt32](xref:System.UInt32), [Int64](xref:System.Int64), [UInt64](xref:System.UInt64)
[Single](xref:System.Single) | [Byte](xref:System.Byte), [SByte](xref:System.SByte), [Int16](xref:System.Int16), [UInt16](xref:System.UInt16), [Int32](xref:System.Int32), [UInt32](xref:System.UInt32), [Int64](xref:System.Int64), [UInt64](xref:System.UInt64)
[Double](xref:System.Double) | [Byte](xref:System.Byte), [SByte](xref:System.SByte), [Int16](xref:System.Int16), [UInt16](xref:System.UInt16), [Int32](xref:System.Int32), [UInt32](xref:System.UInt32), [Int64](xref:System.Int64), [UInt64](xref:System.UInt64)

## <a name="see-also"></a>Siehe auch

[System.Convert](xref:System.Convert)

[Typkonvertierung](type-conversion.md)




<!--HONumber=Nov16_HO3-->


