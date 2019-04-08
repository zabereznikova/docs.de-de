---
title: System.Object-Methoden
ms.date: 03/30/2017
ms.assetid: 5397fca0-689e-443e-802f-e1cbdc866427
ms.openlocfilehash: 3a52f081f1c0c6e6c5218550009c736d0ed60514
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097667"
---
# <a name="systemobject-methods"></a>System.Object-Methoden
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt die folgenden <xref:System.Object> Methoden.  
  
|||  
|-|-|  
|<xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>|<xref:System.Object.Equals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType>||  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt nicht die folgenden <xref:System.Object> Methoden.  
  
|||  
|-|-|  
|<xref:System.Object.GetHashCode?displayProperty=nameWithType>|<xref:System.Object.ReferenceEquals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.MemberwiseClone?displayProperty=nameWithType>|<xref:System.Object.GetType?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType> für binäre Typen wie z. B. `BINARY`, `VARBINARY`, `IMAGE`, und `TIMESTAMP`.||  
  
## <a name="differences-from-net"></a>Unterschiede zu .NET  
 Die Ausgabe des <xref:System.Object.ToString?displayProperty=nameWithType> für Double SQL verwendet `CONVERT`(NVARCHAR(30), @x, 2) in SQL. SQL verwendet in diesem Fall immer 16 Ziffern und wissenschaftliche Schreibweise (z. B. "0.000000000000000e+000" für 0). Im Ergebnis erzeugt die <xref:System.Object.ToString?displayProperty=nameWithType>-Konvertierung nicht die gleiche Zeichenfolge wie <xref:System.Convert.ToString%2A?displayProperty=nameWithType> im .NET Framework.  
  
## <a name="see-also"></a>Siehe auch

- [Datentypen und Funktionen](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
