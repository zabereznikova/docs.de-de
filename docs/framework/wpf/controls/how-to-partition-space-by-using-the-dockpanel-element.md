---
title: 'Vorgehensweise: Aufteilen von Bereichen mithilfe des DockPanel-Elements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], partitioning space
- partitioning space [WPF]
ms.assetid: a219b9e5-b205-4438-89b5-0a137ac463ab
ms.openlocfilehash: ab51270644bf370944ebc933c765b40c528681c5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052182"
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a>Vorgehensweise: Aufteilen von Bereichen mithilfe des DockPanel-Elements
Das folgende Beispiel erstellt eine einfache [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Framework mit einer <xref:System.Windows.Controls.DockPanel> Element. Die <xref:System.Windows.Controls.DockPanel> teilt den verfügbaren Platz für seine untergeordneten Elemente.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die <xref:System.Windows.Controls.DockPanel.Dock%2A> -Eigenschaft, die eine angefügte Eigenschaft, um zwei identische anzudocken <xref:System.Windows.Controls.Border> Elemente an die <xref:System.Windows.Controls.Dock.Top> des aufgeteilten Bereichs. Eine dritte <xref:System.Windows.Controls.Border> Elements angedockt ist die <xref:System.Windows.Controls.Dock.Left>, dessen Breite auf 200 Pixel festgelegt. Eine vierte <xref:System.Windows.Controls.Border> angedockt ist die <xref:System.Windows.Controls.Dock.Bottom> des Bildschirms. Die letzte <xref:System.Windows.Controls.Border> Elements den verbleibenden Platz ausfüllt.  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
>  Standardmäßig ist das letzte untergeordnete Element von einem <xref:System.Windows.Controls.DockPanel> Element füllt die verbleibenden verfügbaren Speicherplatz. Wenn Sie dieses Verhalten nicht wünschen, legen Sie `LastChildFill="False"` fest.  
  
 Die kompilierte Anwendung gibt eine neue Benutzeroberfläche aus, die folgendermaßen aussieht.  
  
 ![Ein typisches DockPanel-Szenario.](./media/panel-intro-dockpanel.PNG "Panel_intro_dockpanel")  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.DockPanel>
- [Übersicht über Panel-Elemente](panels-overview.md)
