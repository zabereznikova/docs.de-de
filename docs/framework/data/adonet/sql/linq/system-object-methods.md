---
title: System.Object-Methoden
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5397fca0-689e-443e-802f-e1cbdc866427
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6998c2b00a2b8e83bc79ae7ba1dd01ea549cf5df
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="systemobject-methods"></a>System.Object-Methoden
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]unterstützt die folgenden <xref:System.Object> Methoden.  
  
|||  
|-|-|  
|<xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>|<xref:System.Object.Equals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType>||  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt die folgenden <xref:System.Object>-Methoden nicht.  
  
|||  
|-|-|  
|<xref:System.Object.GetHashCode?displayProperty=nameWithType>|<xref:System.Object.ReferenceEquals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.MemberwiseClone?displayProperty=nameWithType>|<xref:System.Object.GetType?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType> für binäre Typen wie `BINARY`, `VARBINARY`, `IMAGE` und `TIMESTAMP`.||  
  
## <a name="differences-from-net"></a>Unterschiede zu .NET  
 Die Ausgabe des <xref:System.Object.ToString?displayProperty=nameWithType> für Double SQL verwendet `CONVERT`(NVARCHAR(30), @x, 2) in SQL. SQL verwendet in diesem Fall immer 16 Ziffern und wissenschaftliche Schreibweise (z. B. "0.000000000000000e+000" für 0). Im Ergebnis erzeugt die <xref:System.Object.ToString?displayProperty=nameWithType>-Konvertierung nicht die gleiche Zeichenfolge wie <xref:System.Convert.ToString%2A?displayProperty=nameWithType> im .NET Framework.  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypen und Funktionen](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
