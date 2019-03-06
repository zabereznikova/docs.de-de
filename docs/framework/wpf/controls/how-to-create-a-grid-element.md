---
title: 'Vorgehensweise: Erstellen eines Grid-Elements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], grid instance
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
ms.openlocfilehash: 5aa0e5b617d952fd5df1f80ae0ff146a6899aa32
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379509"
---
# <a name="how-to-create-a-grid-element"></a>Vorgehensweise: Erstellen eines Grid-Elements
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt das Erstellen und verwenden Sie eine Instanz des <xref:System.Windows.Controls.Grid> entweder [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] oder Code. In diesem Beispiel verwendet drei <xref:System.Windows.Controls.ColumnDefinition> Objekte und drei <xref:System.Windows.Controls.RowDefinition> Objekte zum Erstellen eines Rasters, das neun Zellen, z. B. in einem Arbeitsblatt. Jede Zelle enthält einen <xref:System.Windows.Controls.TextBlock> Element, das darstellt, Daten, und die oberste Zeile enthält einen <xref:System.Windows.Controls.TextBlock> mit der <xref:System.Windows.Controls.Grid.ColumnSpan%2A> Eigenschaft angewendet. Zum Anzeigen der Grenzen jeder Zelle, die <xref:System.Windows.Controls.Grid.ShowGridLines%2A> -Eigenschaft aktiviert ist.  
  
 [!code-csharp[Grid#3](~/samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xaml[Grid#3](~/samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
  Beide Vorgehensweisen generiert eine Benutzeroberfläche, die viel identisch, wie folgt aussieht.

  ![ein Screenshot zeigt eine WPF-Benutzeroberfläche enthält ein Raster in drei Spalten unterteilt ist.  Er trägt die Überschrift "2018 Produkte geliefert" umfasst alle Spalten der obersten Zeile und verfügt über drei Spalten mit Verkaufszahlen für einen bestimmten Quartal.  Die letzte Zeile verfügt über Text umfasst zwei Spalten mit der Meldung "Gesamteinheiten: 300,000'](././media/how-to-create-a-grid-element/how-to-create-a-grid-element.png)
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.Grid>
- [Übersicht über Panel-Elemente](panels-overview.md)
