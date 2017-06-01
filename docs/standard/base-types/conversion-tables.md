---
title: "Typkonvertierungstabellen in .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Erweiterungskonvertierungen"
  - "Eingrenzungskonvertierungen"
  - "Typkonvertierung, Tabelle"
  - "Konvertieren von Typen, Einschränken von Konvertierungen"
  - "Konvertieren von Typen, Erweitern von Konvertierungen"
  - "Basistypen, konvertieren"
  - "Tabellen [.NET Framework], Typkonvertierungen"
  - "Datentypen [.NET Framework], konvertieren"
ms.assetid: 0ea65c59-85eb-4a52-94ca-c36d3bd13058
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Typkonvertierungstabellen in .NET Framework
Eine Erweiterungskonvertierung liegt vor, wenn der Wert eines bestimmten Typs in einen anderen, mindestens ebenso großen Typ konvertiert wird.  Eine Eingrenzungskonvertierung liegt vor, wenn ein Wert eines bestimmten Typs in einen anderen, kleineren Typ konvertiert wird.  Die Tabellen zu diesem Thema veranschaulichen die Besonderheiten und Merkmale beider Konvertierungsarten.  
  
## Erweiternde Konvertierungen  
 In der folgenden Tabelle werden die Erweiterungskonvertierungen aufgelistet, die ohne Datenverlust durchgeführt werden können.  
  
|Typ|Kann ohne Datenverlust konvertiert werden in|  
|---------|--------------------------------------------------|  
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
  
 Einige Erweiterungskonvertierungen in <xref:System.Single> oder <xref:System.Double> können zu einer verringerten Genauigkeit führen.  Die folgende Tabelle enthält diejenigen Erweiterungskonvertierungen, die u. U. zum Verlust von Informationen führen können.  
  
|Typ|Kann konvertiert werden in|  
|---------|--------------------------------|  
|<xref:System.Int32>|<xref:System.Single>|  
|<xref:System.UInt32>|<xref:System.Single>|  
|<xref:System.Int64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.UInt64>|<xref:System.Single>, <xref:System.Double>|  
|<xref:System.Decimal>|<xref:System.Single>, <xref:System.Double>|  
  
## Eingrenzende Konvertierungen  
 Eine Eingrenzungskonvertierung in <xref:System.Single> oder <xref:System.Double> können zu einem Verlust von Informationen führen.  Ist der Wert des Ausgangstyps größer als der des Zieltyps und kann daher nicht korrekt ausgedrückt werden, erhält der Zieltyp als Wert die Konstante `PositiveInfinity` oder `NegativeInfinity`.  Der Wert `PositiveInfinity` ist das Ergebnis der Division einer positiven Zahl durch 0 \(null\) und wird auch dann zurückgegeben, wenn der Wert von <xref:System.Single> oder <xref:System.Double> größer ist als der Wert des `MaxValue`\-Felds.  Der Wert `NegativeInfinity` ist das Ergebnis der Division einer negativen Zahl durch 0 \(null\) und wird auch dann zurückgegeben, wenn der Wert von <xref:System.Single> oder <xref:System.Double> kleiner ist als der Wert des `MinValue`\-Felds.  Eine Konvertierung von <xref:System.Double> in <xref:System.Single> kann zu `PositiveInfinity` oder `NegativeInfinity` führen.  
  
 Eine Eingrenzungskonvertierung kann auch bei anderen Datentypen zu Informationsverlust führen.  Wenn der Wert eines Typs, der konvertiert wird, jedoch außerhalb des Bereichs liegt, der vom `MaxValue`\-Feld und vom `MinValue`\-Feld des Zieltyps angegeben wird, wird eine <xref:System.OverflowException> ausgelöst. Außerdem wird die Konvertierung von der Common Language Runtime überprüft, um sicherzustellen, dass der Wert des Zieltyps nicht größer als `MaxValue` oder kleiner als `MinValue` ist.  Eine solche Überprüfung wird bei Konvertierungen, die mithilfe der <xref:System.Convert?displayProperty=fullName>\-Klasse durchgeführt wurden, immer vorgenommen.  
  
 Die folgende Tabelle enthält die Konvertierungen, die eine <xref:System.OverflowException> mit <xref:System.Convert?displayProperty=fullName> oder irgendein geprüftes Konvertierungsverfahren auslösen, wenn der Wert des konvertierten Typs außerhalb des definierten Bereichs des resultierenden Typs liegt.  
  
|Typ|Kann konvertiert werden in|  
|---------|--------------------------------|  
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
  
## Siehe auch  
 <xref:System.Convert?displayProperty=fullName>   
 [Typkonvertierung in .NET Framework](../../../docs/standard/base-types/type-conversion.md)