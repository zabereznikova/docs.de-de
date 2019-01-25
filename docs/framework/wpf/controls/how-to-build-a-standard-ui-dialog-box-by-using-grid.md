---
title: 'Vorgehensweise: Erstellen eines Benutzeroberflächen-Standarddialogfelds unter Verwendung des Grid-Elements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: 893b3f7fda3314b158f7c67392a0913e30a92c09
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650521"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a>Vorgehensweise: Erstellen eines Benutzeroberflächen-Standarddialogfelds unter Verwendung des Grid-Elements
In diesem Beispiel wird gezeigt, wie eine Standard- [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Dialogfeld mithilfe der <xref:System.Windows.Controls.Grid> Element.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt ein Dialogfeld wie das **ausführen** im Dialogfeld die [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Betriebssystem.  
  
 Das Beispiel erstellt eine <xref:System.Windows.Controls.Grid> und verwendet die <xref:System.Windows.Controls.ColumnDefinition> und <xref:System.Windows.Controls.RowDefinition> Klassen zum Definieren von fünf Spalten und vier Zeilen.  
  
 Anschließend fügt hinzu und platziert eine <xref:System.Windows.Controls.Image>, `RunIcon.png`, zum Darstellen des Bilds, die Sie im Dialogfeld befindet. Das Bild wird in der ersten Spalte und Zeile platziert die <xref:System.Windows.Controls.Grid> (linke obere Ecke).  
  
 Als Nächstes das Beispiel fügt eine <xref:System.Windows.Controls.TextBlock> Element der ersten Spalte, die die verbleibenden Spalten der ersten Zeile erstreckt. Fügt einen anderen <xref:System.Windows.Controls.TextBlock> Element der zweiten Zeile in der ersten Spalte zur Darstellung der **öffnen** Textfeld. Ein <xref:System.Windows.Controls.TextBlock> folgt, das den Dateneingabebereich darstellt.  
  
 Zum Schluss das Beispiel fügt drei <xref:System.Windows.Controls.Button> Elemente der letzten Zeile, die darstellen der **OK**, **Abbrechen**, und **Durchsuchen** Ereignisse.  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.GridUnitType>
- [Übersicht über Panel-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)
- [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/grid-how-to-topics.md)
