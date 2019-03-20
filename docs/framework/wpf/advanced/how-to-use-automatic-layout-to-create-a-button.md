---
title: 'Vorgehensweise: Verwenden des automatischen Layouts zum Erstellen einer Schaltfläche'
ms.date: 03/30/2017
helpviewer_keywords:
- Button controls [WPF], creating with automatic layout
- automatic layout [WPF], creating buttons
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
ms.openlocfilehash: 185bf71d4105d10a2bb85e6a0abd9da63c7d26f0
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185453"
---
# <a name="how-to-use-automatic-layout-to-create-a-button"></a>Vorgehensweise: Verwenden des automatischen Layouts zum Erstellen einer Schaltfläche
Dieses Beispiel beschreibt, wie der automatische Layoutansatz zum Erstellen einer Schaltfläche in einer lokalisierbaren Anwendung verwendet wird.  
  
 Lokalisierung von einer [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] kann ein zeitaufwändiger Prozess sein. Oft müssen Lokalisierungsexperten die Größe von Elementen ändern und sie neu positionieren, um Text zu übersetzen. In der Vergangenheit jede Sprache, die eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für musste angepasst wurde. Jetzt mit den Funktionen von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] können Sie Elemente, die die Notwendigkeit der Anpassung reduzieren entwerfen. Der Ansatz zum Schreiben von Anwendungen, die einfacher geändert und neu positioniert werden können, heißt `automatic layout`.  
  
## <a name="example"></a>Beispiel  

Die folgenden beiden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Beispiele erstellen Anwendungen, die eine Schaltfläche, eine mit englischem Text und eine mit spanischem Text zu instanziieren. Beachten Sie, dass der Code mit Ausnahme des Texts der gleiche ist; die Schaltfläche wird an den Text angepasst.

[!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
[!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 Die folgende Grafik zeigt die Ausgabe der Codebeispiele.  
  
 ![Die gleiche Schaltfläche mit Text in unterschiedlichen Sprachen](./media/globalizationbutton.png "GlobalizationButton")  
Schaltfläche zur automatischen Größenanpassung  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Verwendung eines automatischen Layouts](use-automatic-layout-overview.md)
- [Verwenden eines Rasters für automatisches Layout](how-to-use-a-grid-for-automatic-layout.md)
