---
title: System.String-Methoden
ms.date: 03/30/2017
ms.assetid: ce307f14-87e6-4816-8694-8a4147f6b784
ms.openlocfilehash: c988bf7f04b284b0d352cd9e495931543980fdba
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64613761"
---
# <a name="systemstring-methods"></a>System.String-Methoden
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt die folgenden <xref:System.String>-Methoden nicht.  
  
## <a name="unsupported-systemstring-methods-in-general"></a>Nicht unterstützte System.String-Methoden im Allgemeinen  
 Nicht unterstützte <xref:System.String>-Methoden im Allgemeinen:  
  
- Kulturbewusste Überladungen (Methoden, die eine `CultureInfo`  /  `StringComparison`  /  `IFormatProvider`).  
  
- Methoden, die ein `char`-Array verwenden oder erzeugen.  
  
## <a name="unsupported-systemstring-static-methods"></a>Nicht unterstützte statische System.String-Methoden  
  
|Nicht unterstützte statische System.String-Methoden|  
|----------------------------------------------|  
|<xref:System.String.Copy%28System.String%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.String%29?displayProperty=nameWithType>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|  
  
## <a name="unsupported-systemstring-non-static-methods"></a>Nicht unterstützte nicht statische System.String-Methoden  
  
|Nicht unterstützte nicht statische System.String-Methoden|  
|---------------------------------------------------|  
|<xref:System.String.IndexOfAny%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
|<xref:System.String.Split%2A?displayProperty=nameWithType>|  
|<xref:System.String.ToCharArray?displayProperty=nameWithType>|  
|<xref:System.String.ToUpper%28System.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.TrimEnd%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
|<xref:System.String.TrimStart%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
  
## <a name="differences-from-net"></a>Unterschiede zu .NET  
  
- Abfragen berücksichtigen keine SQL Server-Zusammenstellungen, die möglicherweise auf dem Server aktiv sind. Aus diesem Grund werden standardmäßig kulturbewusste Vergleiche mit Berücksichtigung der Schreibweise erstellt. Dieses Verhalten unterscheidet sich von der standardmäßigen Semantik mit Groß-/Kleinschreibung von .NET Framework.  
  
- Wenn `LastIndexOf` 0 zurückgibt, entweder die Zeichenfolge `NULL` oder die gefundene Position ist 0.  
  
- Die Verkettung oder andere Operationen mit Zeichenfolgen fester Länge (`CHAR`, `NCHAR`) kann zu unerwarteten Ergebnissen führen, da diese Typen in der Datenbank automatisches Padding verwenden.  
  
- Da viele Methoden, wie `Replace`, `ToLower`, `ToUpper` und die Zeichenindizierung keine gültige Übersetzung für die `TEXT`-Spalte oder die `NTEXT`-Spalte und XML aufweisen, kommt es bei normaler Übersetzung zu `SqlExceptions`. Dieses Verhalten gilt für diese Typen als akzeptabel. Alle Zeichenfolgenoperationen müssen jedoch zur Common Language Runtime (CLR)-Semantik für `VARCHAR`, `NVARCHAR`, `VARCHAR(max)` und `NVARCHAR(max)` passen.  
  
## <a name="see-also"></a>Siehe auch

- [Datentypen und Funktionen](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
