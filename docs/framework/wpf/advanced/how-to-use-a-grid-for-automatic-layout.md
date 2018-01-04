---
title: "Gewusst wie: Verwenden eines Rasters für automatisches Layout"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- grids [WPF], automatic layout
- automatic layout [WPF], grid use
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bbd8bd7e36b7b773837b839e77ec88a8e7c8f0d6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-grid-for-automatic-layout"></a>Gewusst wie: Verwenden eines Rasters für automatisches Layout
Dieses Beispiel beschreibt, wie ein Raster im automatischen Layoutansatz zum Erstellen einer lokalisierbaren Anwendung verwendet wird.  
  
 Lokalisierung von einem [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] kann zeitaufwändig sein. Oft müssen Lokalisierungsexperten die Größe von Elementen ändern und sie neu positionieren, um Text zu übersetzen. In der Vergangenheit jede Sprache, die eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für erforderliche Anpassung angepasst wurde. Jetzt mit den Funktionen von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] können Sie Elemente, die die Notwendigkeit einer Anpassung reduzieren entwerfen. Der Ansatz zum Schreiben von Anwendungen, die leichter die Größe und neu positioniert werden können heißt `auto layout`.  
  
 Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beispiel veranschaulicht die Verwendung von einem Raster einige Schaltflächen und Text zu positionieren. Beachten Sie, dass die Höhe und Breite der Zellen werden zu `Auto`; daher wird die Zelle mit der Schaltfläche mit einem Bild, das Bild angepasst. Da die <xref:System.Windows.Controls.Grid> Element kann anpassen, an dessen Inhalt, es kann hilfreich sein, wenn das automatische Layout Ansatz zum Entwerfen von Anwendungen, die lokalisiert werden kann.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von eines Rasters.  
  
 [!code-xaml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 Die folgende Grafik zeigt die Ausgabe des Codebeispiels.  
  
 ![Rasterbeispiel](../../../../docs/framework/wpf/advanced/media/glob-grid.png "Glob_grid")  
Raster  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Verwendung eines automatischen Layouts](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)  
 [Verwenden des automatischen Layouts zum Erstellen einer Schaltfläche](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)
