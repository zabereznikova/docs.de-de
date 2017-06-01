---
title: "System.Object-Methoden | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5397fca0-689e-443e-802f-e1cbdc866427
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# System.Object-Methoden
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt die folgenden <xref:System.Object>\-Methoden.  
  
|||  
|-|-|  
|<xref:System.Object.Equals%28System.Object%29?displayProperty=fullName>|<xref:System.Object.Equals%28System.Object%2CSystem.Object%29?displayProperty=fullName>|  
|<xref:System.Object.ToString?displayProperty=fullName>||  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt die folgenden <xref:System.Object>\-Methoden nicht.  
  
|||  
|-|-|  
|<xref:System.Object.GetHashCode?displayProperty=fullName>|<xref:System.Object.ReferenceEquals%28System.Object%2CSystem.Object%29?displayProperty=fullName>|  
|<xref:System.Object.MemberwiseClone?displayProperty=fullName>|<xref:System.Object.GetType?displayProperty=fullName>|  
|<xref:System.Object.ToString?displayProperty=fullName> für binäre Typen wie `BINARY`, `VARBINARY`, `IMAGE` und `TIMESTAMP`.||  
  
## Unterschiede zu .NET  
 Die Ausgabe von <xref:System.Object.ToString?displayProperty=fullName> für double verwendet SQL `CONVERT`\(NVARCHAR\(30\), @x, 2\) unter SQL.  SQL verwendet in diesem Fall immer 16 Ziffern und wissenschaftliche Schreibweise \(z. B. "0.000000000000000e\+000" für 0\).  Im Ergebnis erzeugt die <xref:System.Object.ToString?displayProperty=fullName>\-Konvertierung nicht die gleiche Zeichenfolge wie <xref:System.Convert.ToString%2A?displayProperty=fullName> im .NET Framework.  
  
## Siehe auch  
 [Datentypen und Funktionen](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)