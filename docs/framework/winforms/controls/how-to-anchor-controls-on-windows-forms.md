---
title: "Gewusst wie: Verankern von Steuerelementen in Windows&#160;Forms | Microsoft Docs"
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
  - "Anchor-Eigenschaft, Aktivieren von Formularen mit veränderbarer Größe"
  - "Steuerelemente [Windows Forms], Verankern"
  - "Steuerelemente [Windows Forms], Positionieren"
  - "Formulare, Größenänderung"
  - "Größenänderung von Formularen"
  - "Bildschirmauflösung und Steuerelementanzeige"
  - "Windows Forms-Steuerelemente, Bildschirmauflösungen"
  - "Windows Forms-Steuerelemente, Größe"
  - "Windows Forms, Größenänderung"
ms.assetid: 59ea914f-fbd3-427a-80fe-decd02f7ae6d
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Verankern von Steuerelementen in Windows&#160;Forms
Wenn Sie ein Formular entwerfen, dessen Größe vom Benutzer zur Laufzeit geändert werden kann, sollten sich auch Größe und Position der im Formular enthaltenen Steuerelemente problemlos anpassen.  Damit sich die Größe von Steuerelementen dynamisch mit dem Formular ändert, verwenden Sie die <xref:System.Windows.Forms.Control.Anchor%2A>\-Eigenschaft der Steuerelemente für Windows Forms.  Die <xref:System.Windows.Forms.Control.Anchor%2A>\-Eigenschaft definiert eine Anchorposition für das Steuerelement.  Wenn ein Steuerelement in einem Formular verankert ist und die Größe des Formulars geändert wird, behält das Steuerelement den Abstand zwischen dem Element und den Anchorpositionen bei.  Angenommen, Sie verwenden ein <xref:System.Windows.Forms.TextBox>\-Steuerelement, das am linken, rechten und unteren Formularrand verankert ist. Ändert sich die Größe des Formulars, wird das <xref:System.Windows.Forms.TextBox>\-Steuerelement horizontal gestreckt, wobei der ursprüngliche Abstand vom rechten und linken Formularrand erhalten bleibt.  Darüber hinaus wird das Steuerelement vertikal positioniert, sodass seine Position stets denselben Abstand vom unteren Formularrand hat.  Wird ein Formular mit einem nicht verankerten Steuerelement vergrößert oder verkleinert, ändert sich die Position des Steuerelements im Verhältnis zu den Formularrändern.  
  
 Die <xref:System.Windows.Forms.Control.Anchor%2A>\-Eigenschaft interagiert mit der <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft.  Weitere Informationen finden Sie unter [Übersicht über die AutoSize\-Eigenschaft](../../../../docs/framework/winforms/controls/autosize-property-overview.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So verankern Sie ein Steuerelement in einem Formular  
  
1.  Markieren Sie das zu verankernde Steuerelement.  
  
    > [!NOTE]
    >  Sie können mehrere Steuerelemente gleichzeitig verankern, indem Sie die STRG\-TASTE drücken und auf die gewünschten Steuerelemente klicken, um sie auszuwählen. Führen Sie anschließend die restlichen Schritte dieser Prozedur aus.  
  
2.  Klicken Sie im **Eigenschaftenfenster** auf den Pfeil rechts neben der <xref:System.Windows.Forms.Control.Anchor%2A>\-Eigenschaft.  
  
     Es wird ein Editor mit einem Kreuz angezeigt.  
  
3.  Um einen Anchor zu setzen, klicken Sie in den oberen, linken, rechten oder unteren Bereich des Kreuzes.  
  
     Steuerelemente werden standardmäßig am oberen und linken Rand verankert.  
  
4.  Um ein verankertes Steuerelement an einer Seite zu lösen, klicken Sie auf den jeweiligen Balken des Kreuzes.  
  
5.  Um den <xref:System.Windows.Forms.Control.Anchor%2A>\-Eigenschaften\-Editor zu schließen, klicken Sie erneut auf den Namen der <xref:System.Windows.Forms.Control.Anchor%2A>\-Eigenschaft.  
  
 Wenn das Formular zur Laufzeit angezeigt wird, behält das Steuerelement bei einer Größenänderung denselben Abstand zum Formularrand bei.  Der Abstand zum verankerten Rand ist immer identisch mit dem Abstand, der beim Positionieren des Steuerelements im Windows Forms\-Designer definiert wurde.  
  
> [!NOTE]
>  Einige Steuerelemente, z. B. das <xref:System.Windows.Forms.ComboBox>\-Steuerelement, verfügen über eine Höhenbegrenzung.  Diese Höhenbegrenzung kann auch nicht überschrieben werden, indem das Steuerelement am unteren Rand eines Formulars oder Containers verankert wird.  
  
 Für geerbte Steuerelemente muss `Protected` angegeben sein, damit sie verankert werden können.  Um die Zugriffsebene eines Steuerelements zu ändern, legen Sie seine `Modifiers`\-Eigenschaft im **Eigenschaftenfenster** fest.  
  
## Siehe auch  
 [Windows Forms\-Steuerelemente](../../../../docs/framework/winforms/controls/index.md)   
 [Anordnen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [Übersicht über die AutoSize\-Eigenschaft](../../../../docs/framework/winforms/controls/autosize-property-overview.md)   
 [Gewusst wie: Andocken von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)   
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)   
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)   
 [Exemplarische Vorgehensweise: Anordnen von Windows Forms\-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize\-Eigenschaft](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)