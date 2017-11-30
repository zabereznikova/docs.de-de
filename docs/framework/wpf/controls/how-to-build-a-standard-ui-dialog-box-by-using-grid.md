---
title: "Gewusst wie: Erstellen eines Benutzeroberflächen-Standarddialogfelds unter Verwendung des Grid-Elements"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 641e74d8c9f8db1afde19c008de08f0029b0bf90
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/controls/grid-how-to-topics.md)
