---
title: 'Gewusst wie: Erstellen eines Benutzeroberflächen-Standarddialogfelds unter Verwendung des Grid-Elements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: d0b24e320c2a341b069e1c9c3e8b6d5e93076733
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a>Gewusst wie: Erstellen eines Benutzeroberflächen-Standarddialogfelds unter Verwendung des Grid-Elements
In diesem Beispiel wird gezeigt, wie eine Standard- [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Dialogfeld mithilfe der <xref:System.Windows.Controls.Grid> Element.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt ein Dialogfeld an, wie die **ausführen** im Dialogfeld die [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Betriebssystem.  
  
 Das Beispiel erstellt eine <xref:System.Windows.Controls.Grid> und verwendet die <xref:System.Windows.Controls.ColumnDefinition> und <xref:System.Windows.Controls.RowDefinition> Klassen zum Definieren von fünf Spalten und vier Zeilen.  
  
 Anschließend fügt hinzu und platziert eine <xref:System.Windows.Controls.Image>, `RunIcon.png`, zum Darstellen des Bilds, das Sie im Dialogfeld gefunden wird. Das Bild wird in der ersten Spalte und Zeile platziert die <xref:System.Windows.Controls.Grid> (der oberen linken Ecke).  
  
 Als Nächstes das Beispiel fügt eine <xref:System.Windows.Controls.TextBlock> Element der ersten Spalte, der die übrigen Spalten der ersten Zeile erstreckt. Fügt eine andere <xref:System.Windows.Controls.TextBlock> Element der zweiten Zeile in der ersten Spalte zur Darstellung der **öffnen** Textfeld. Ein <xref:System.Windows.Controls.TextBlock> folgt, das den Dateneingabebereich darstellt.  
  
 Schließlich im Beispiel fügt drei <xref:System.Windows.Controls.Button> Elemente, die auf die letzte Zeile darstellen der **OK**, **"Abbrechen"**, und **Durchsuchen** Ereignisse.  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.GridUnitType>  
 [Übersicht über Panel-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/grid-how-to-topics.md)
