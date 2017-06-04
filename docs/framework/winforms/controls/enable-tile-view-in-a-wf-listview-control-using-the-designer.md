---
title: "Gewusst wie: Aktivieren der Tile-Ansicht in einem ListView-Steuerelement in Windows Forms mithilfe des Designers | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ListView-Steuerelement [Windows Forms], Tile-Ansicht"
  - "Tile-Ansicht (Feature)"
  - "Nebeneinander/Untereinander, Windows Forms, Steuerelemente"
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Aktivieren der Tile-Ansicht in einem ListView-Steuerelement in Windows Forms mithilfe des Designers
Mit dem Feature für die Tile\-Ansicht des <xref:System.Windows.Forms.ListView>\-Steuerelements können Sie ein optisches Gleichgewicht zwischen Grafik\- und Textinformationen herstellen.  Die für ein Element in der Tile\-Ansicht angezeigten Textinformationen sind mit den für die Detailansicht definierten Spalteninformationen identisch.  Die Tile\-Ansicht wird mit dem Gruppierungs\- oder Einfügemarkenfeature im <xref:System.Windows.Forms.ListView>\-Steuerelement verwendet.  
  
 Die Tile\-Ansicht verwendet ein Symbol im Format 32 x 32 und mehrere Textzeilen, wie in der folgenden Abbildung dargestellt.  
  
 ![Ansicht "Nebeneinander" in einem ListView&#45;Steuerelement](../../../../docs/framework/winforms/controls/media/listviewtile.gif "ListViewTile")  
  
 Mit den Eigenschaften und Methoden der Tile\-Ansicht können Sie angeben, welche Spaltenfelder für die einzelnen Elemente angezeigt werden sollen. Außerdem können Sie die Größe und die Darstellung aller Elemente in einem Fenster in der Tile\-Ansicht auf einmal festlegen.  Zur Verdeutlichung: Die erste Textzeile in einem Ausschnitt enthält immer den Elementnamen und kann nicht geändert werden.  
  
 Für das folgende Verfahren wird ein Projekt vom Typ **Windows\-Anwendung** mit einem Formular benötigt, das ein <xref:System.Windows.Forms.ListView>\-Steuerelement enthält.  Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Die Tile\-Ansicht ist für [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] nur verfügbar, wenn die Anwendung die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName>\-Methode aufruft.  Auf früheren Betriebssystemen ist Code in Zusammenhang mit der Tile\-Ansicht unwirksam, und das <xref:System.Windows.Forms.ListView>\-Steuerelement wird in der Ansicht mit großen Symbolen angezeigt.  Weitere Informationen finden Sie unter <xref:System.Windows.Forms.ListView.View%2A?displayProperty=fullName>.  
>   
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So legen Sie die Tile\-Ansicht im Designer fest  
  
1.  Wählen Sie im Formular das <xref:System.Windows.Forms.ListView>\-Steuerelement aus.  
  
2.  Wählen Sie im **Eigenschaftenfenster** die <xref:System.Windows.Forms.ListView.View%2A>\-Eigenschaft aus, und aktivieren Sie die Option **Nebeneinander**.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ListView.TileSize%2A>   
 [Windows XP Features and Windows Forms Controls](http://msdn.microsoft.com/de-de/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)   
 [Übersicht über das ListView\-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)