---
title: 'Vorgehensweise: Verwenden eines Rasters für automatisches Layout'
ms.date: 03/30/2017
helpviewer_keywords:
- grids [WPF], automatic layout
- automatic layout [WPF], grid use
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
ms.openlocfilehash: 590ad7292fea572b20ccaa09ce2886724e004a6a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227117"
---
# <a name="how-to-use-a-grid-for-automatic-layout"></a>Vorgehensweise: Verwenden eines Rasters für automatisches Layout
Dieses Beispiel beschreibt, wie ein Raster im automatischen Layoutansatz zum Erstellen einer lokalisierbaren Anwendung verwendet wird.  
  
 Lokalisierung von einer [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] kann ein zeitaufwändiger Prozess sein. Oft müssen Lokalisierungsexperten die Größe von Elementen ändern und sie neu positionieren, um Text zu übersetzen. In der Vergangenheit jede Sprache, die eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für musste angepasst wurde. Jetzt mit den Funktionen von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] können Sie Elemente, die die Notwendigkeit der Anpassung reduzieren entwerfen. Der Ansatz zum Schreiben von Anwendungen, die leichter Größe und neu positioniert werden können, heißt `auto layout`.  
  
 Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] wird veranschaulicht, wie ein Raster zum Positionieren einiger Schaltflächen und Text. Beachten Sie, die die Höhe und Breite der Zellen, um festgelegt werden `Auto`; aus diesem Grund die Zelle mit der Schaltfläche mit einem Bild passt, das Bild angepasst. Da die <xref:System.Windows.Controls.Grid> Element kann anpassen, an dessen Inhalt, es kann hilfreich sein, beim Erstellen von automatischen Layoutansatz zum Entwerfen von Anwendungen, die lokalisiert werden können.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von eines Rasters.  
  
 [!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 Die folgende Grafik zeigt die Ausgabe des Codebeispiels.  
  
 ![Rasterbeispiel](./media/glob-grid.png "Glob_grid")  
Raster  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Verwendung eines automatischen Layouts](use-automatic-layout-overview.md)
- [Verwenden des automatischen Layouts zum Erstellen einer Schaltfläche](how-to-use-automatic-layout-to-create-a-button.md)
