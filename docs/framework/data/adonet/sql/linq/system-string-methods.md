---
title: "System.String-Methoden | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ce307f14-87e6-4816-8694-8a4147f6b784
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# System.String-Methoden
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt die folgenden <xref:System.String>\-Methoden nicht.  
  
## Nicht unterstützte System.String\-Methoden im Allgemeinen  
 Nicht unterstützte <xref:System.String>\-Methoden im Allgemeinen:  
  
-   Kulturbewusste Überladungen \(Methoden, die einen `CultureInfo`\/`StringComparison`\/`IFormatProvider` verwenden\).  
  
-   Methoden, die ein `char`\-Array verwenden oder erzeugen.  
  
## Nicht unterstützte statische System.String\-Methoden  
  
|Nicht unterstützte statische System.String\-Methoden|  
|----------------------------------------------------------|  
|<xref:System.String.Copy%28System.String%29?displayProperty=fullName>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=fullName>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=fullName>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%29?displayProperty=fullName>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=fullName>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.String%29?displayProperty=fullName>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>|  
|<xref:System.String.Format%2A?displayProperty=fullName>|  
|<xref:System.String.Join%2A?displayProperty=fullName>|  
  
## Nicht unterstützte nicht statische System.String\-Methoden  
  
|Nicht unterstützte nicht statische System.String\-Methoden|  
|----------------------------------------------------------------|  
|[String.IndexOfAny\(Char\<xref:System.String.IndexOfAny%28System.Char%5B%5D%29?displayProperty=fullName>|  
|<xref:System.String.Split%2A?displayProperty=fullName>|  
|<xref:System.String.ToCharArray?displayProperty=fullName>|  
|<xref:System.String.ToUpper%28System.Globalization.CultureInfo%29?displayProperty=fullName>|  
|[String.TrimEnd\(Char\<xref:System.String.TrimEnd%28System.Char%5B%5D%29?displayProperty=fullName>|  
|[String.TrimStart\(Char\<xref:System.String.TrimStart%28System.Char%5B%5D%29?displayProperty=fullName>|  
  
## Unterschiede zu .NET  
  
-   Abfragen berücksichtigen keine SQL Server\-Zusammenstellungen, die möglicherweise auf dem Server aktiv sind. Aus diesem Grund werden standardmäßig kulturbewusste Vergleiche mit Berücksichtigung der Schreibweise erstellt.  Dieses Verhalten unterscheidet sich von der standardmäßigen Semantik mit Groß\-\/Kleinschreibung von .NET Framework.  
  
-   Wenn  `LastIndexOf` 0 zurückgibt, ist entweder die Zeichenfolge `NULL`, oder die gefundene Position ist 0.  
  
-   Die Verkettung oder andere Operationen mit Zeichenfolgen fester Länge \(`CHAR`, `NCHAR`\) kann zu unerwarteten Ergebnissen führen, da diese Typen in der Datenbank automatisches Padding verwenden.  
  
-   Da viele Methoden, wie `Replace`, `ToLower`, `ToUpper` und die Zeichenindizierung keine gültige Übersetzung für die `TEXT`\-Spalte oder die `NTEXT`\-Spalte und XML aufweisen, kommt es bei normaler Übersetzung zu `SqlExceptions`.  Dieses Verhalten gilt für diese Typen als akzeptabel.  Alle Zeichenfolgenoperationen müssen jedoch zur Common Language Runtime \(CLR\)\-Semantik für `VARCHAR`, `NVARCHAR`, `VARCHAR(max)` und `NVARCHAR(max)` passen.  
  
## Siehe auch  
 [Datentypen und Funktionen](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)