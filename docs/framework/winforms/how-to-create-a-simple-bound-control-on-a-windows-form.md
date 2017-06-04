---
title: "Gewusst wie: Erstellen eines einfach gebundenen Steuerelements in einem Windows&#160;Form | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Datenbindung, Einfache Datenbindung"
  - "Windows Forms-Steuerelemente, Datenbindung"
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Erstellen eines einfach gebundenen Steuerelements in einem Windows&#160;Form
Durch die *einfache Bindung* können Sie ein einzelnes Datenelement – z. B. einen Spaltenwert aus einer DataSet\-Tabelle – in einem Steuerelement anzeigen.  Alle Eigenschaften von Steuerelementen können einfach an einen Datenwert gebunden werden.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So binden Sie Steuerelemente einfach  
  
1.  Bauen Sie eine Verbindung zu einer Datenquelle auf.  Weitere Informationen finden Sie unter [Aufbauen der Verbindung zu einer Datenquelle](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).  
  
2.  Markieren Sie das Steuerelement auf dem Formular, und rufen Sie das **Eigenschaftenfenster** auf.  
  
3.  Erweitern Sie die Eigenschaft **\(DataBindings\)**.  
  
     Die am häufigsten gebundenen Eigenschaften werden unterhalb der Eigenschaft **\(DataBindings\)** angezeigt.  So ist in den meisten Steuerelementen beispielsweise die **Text**\-Eigenschaft am häufigsten gebunden.  
  
4.  Wenn die zu bindende Eigenschaft nicht zu den häufig gebundenen Eigenschaften gehört, klicken Sie im Dialogfeld **\(Erweitert\)** auf die Schaltfläche **Auslassungspunkte** \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\), um das Dialogfeld **Formatierung und erweiterte Bindung** mit einer vollständigen Liste der Eigenschaften für dieses Steuerelement anzuzeigen.  
  
5.  Wählen Sie die zu bindende Eigenschaft aus, und klicken Sie unter **Bindung** auf den Dropdownpfeil.  
  
     Eine Liste der verfügbaren Datenquellen wird angezeigt.  
  
6.  Erweitern Sie die Datenquelle, die Sie binden möchten, bis Sie das gewünschte Datenelement gefunden haben.  Wenn Sie beispielsweise an den Spaltenwert einer DataSet\-Tabelle binden, erweitern Sie zuerst den Namen des DataSets und dann den Tabellennamen, um die Spaltennamen anzuzeigen.  
  
7.  Klicken Sie auf den Namen des Elements, an das gebunden werden soll.  
  
8.  Wenn Sie das Dialogfeld **Formatierung und erweiterte Bindung** verwendet haben, klicken Sie auf **OK**, um zum Fenster **Eigenschaften** zurückzukehren.  
  
9. Wenn Sie weitere Eigenschaften des Steuerelements binden möchten, wiederholen Sie die Schritte 3 bis 7.  
  
    > [!NOTE]
    >  Da einfach gebundene Steuerelemente nur ein Datenelement anzeigen, wird in Windows Forms mit einfach gebundenen Steuerelementen normalerweise Navigationslogik verwendet.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Binding>   
 [Datenbindung in Web Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Datenbindung und Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)