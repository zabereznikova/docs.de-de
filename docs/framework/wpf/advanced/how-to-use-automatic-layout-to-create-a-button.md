---
title: "Gewusst wie: Verwenden des automatischen Layouts zum Erstellen einer Schaltfläche"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Button controls [WPF], creating with automatic layout
- automatic layout [WPF], creating buttons
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c642e6491722e9bfe35337d066e3870f5a70f38c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-automatic-layout-to-create-a-button"></a>Gewusst wie: Verwenden des automatischen Layouts zum Erstellen einer Schaltfläche
Dieses Beispiel beschreibt, wie der automatische Layoutansatz zum Erstellen einer Schaltfläche in einer lokalisierbaren Anwendung verwendet wird.  
  
 Lokalisierung von einem [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] kann zeitaufwändig sein. Oft müssen Lokalisierungsexperten die Größe von Elementen ändern und sie neu positionieren, um Text zu übersetzen. In der Vergangenheit jede Sprache, die eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für erforderliche Anpassung angepasst wurde. Jetzt mit den Funktionen von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] können Sie Elemente, die die Notwendigkeit einer Anpassung reduzieren entwerfen. Der Ansatz zum Schreiben von Anwendungen, die leichter dessen Größe geändert wurde und neu positioniert werden können heißt `automatic layout`.  
  
 Die folgenden beiden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beispiele für Anwendungen erstellen, die eine Schaltfläche, eine mit englischem Text und eine spanische Text zu instanziieren. Beachten Sie, dass der Code mit Ausnahme des Texts der gleiche ist; die Schaltfläche wird an den Text angepasst.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 [!code-xaml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 Die folgende Grafik zeigt die Ausgabe der Codebeispiele.  
  
 ![Die gleiche Schaltfläche mit Text in unterschiedlichen Sprachen](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")  
Schaltfläche zur automatischen Größenanpassung  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Verwendung eines automatischen Layouts](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)  
 [Verwenden eines Rasters für automatisches Layout](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)
