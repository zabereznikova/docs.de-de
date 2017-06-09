---
title: "Gewusst wie: Steuern, wann der TextBox-Text die Quelle aktualisiert | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Datenbindung, Zeitsteuerung von Quellenaktualisierungen"
  - "Quellenaktualisierungen, Zeitsteuerung von"
  - "Zeitsteuerung von Quellenaktualisierungen"
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Steuern, wann der TextBox-Text die Quelle aktualisiert
In diesem Thema wird beschrieben, wie die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>\-Eigenschaft verwendet wird, um Aktualisierungen von [Bindungsquellen](GTMT) zeitlich zu steuern.  In diesem Thema wird das <xref:System.Windows.Controls.TextBox>\-Steuerelement als Beispiel verwendet.  
  
## Beispiel  
 Der <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>\-Standardwert der <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A>\-Eigenschaft ist <xref:System.Windows.Data.UpdateSourceTrigger>.  Wenn eine Anwendung also ein <xref:System.Windows.Controls.TextBox>\-Element mit einer datengebundenen <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A>\-Eigenschaft besitzt, wird beim Eingeben von Text in das <xref:System.Windows.Controls.TextBox>\-Element die Quelle erst dann mit diesem Text aktualisiert, wenn das <xref:System.Windows.Controls.TextBox>\-Element den Fokus verliert \(wenn Sie beispielsweise außerhalb des <xref:System.Windows.Controls.TextBox>\-Elements klicken\).  
  
 Wenn Sie möchten, dass die Quelle aktualisiert wird, während Sie den Text eingeben, legen Sie den <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> der Bindung auf <xref:System.Windows.Data.UpdateSourceTrigger> fest.  Im folgenden Beispiel werden die `Text`\-Eigenschaften des <xref:System.Windows.Controls.TextBox>\-Elements und des <xref:System.Windows.Controls.TextBlock>\-Elements an die gleiche Quelleneigenschaft gebunden.  Die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>\-Eigenschaft der <xref:System.Windows.Controls.TextBox>\-Bindung ist auf <xref:System.Windows.Data.UpdateSourceTrigger> festgelegt.  
  
 [!code-xml[SimpleBinding#USTHowTo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml#usthowto)]  
  
 Dadurch zeigt das <xref:System.Windows.Controls.TextBlock>\-Element \(aufgrund der Änderungen in der Quelle\) den gleichen Text an, den der Benutzer in das <xref:System.Windows.Controls.TextBox>\-Element eingibt. Dies wird durch die folgende Bildschirmabbildung des Beispiels veranschaulicht:  
  
 ![Bildschirmabbildung für ein einfaches Datenbindungsbeispiel](../../../../docs/framework/wpf/data/media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")  
  
 Wenn Sie mit einem Dialogfeld oder einem vom Benutzer bearbeitbaren Formular arbeiten und Sie die Aktualisierungen der Quelle auf den Zeitpunkt verschieben möchten, zu dem der Benutzer die Bearbeitung der Felder abgeschlossen und auf "OK" geklickt hat, können Sie den <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>\-Wert Ihrer Bindungen auf <xref:System.Windows.Data.UpdateSourceTrigger> festlegen, wie in dem folgenden Beispiel gezeigt:  
  
 [!code-xml[UpdateSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]  
  
 Wenn Sie den <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>\-Wert auf <xref:System.Windows.Data.UpdateSourceTrigger> festlegen, ändert sich der Quellwert nur dann, wenn die Anwendung die <xref:System.Windows.Data.BindingExpression.UpdateSource%2A>\-Methode aufruft.  Im folgenden Beispiel wird veranschaulicht, wie <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> für `itemNameTextBox` aufgerufen wird:  
  
 [!code-csharp[UpdateSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]  
  
> [!NOTE]
>  Sie können das gleiche Verfahren für Eigenschaften anderer Steuerelemente verwenden. Denken Sie jedoch daran, dass die meisten anderen Eigenschaften einen <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>\-Standardwert von <xref:System.Windows.Data.UpdateSourceTrigger> haben.  Weitere Informationen finden Sie auf der Eigenschaftenseite für <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
> [!NOTE]
>  Die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>\-Eigenschaft behandelt Quellupdates und ist deshalb nur für die <xref:System.Windows.Data.BindingMode>\-Bindung oder die <xref:System.Windows.Data.BindingMode>\-Bindung relevant.  Damit die <xref:System.Windows.Data.BindingMode>\-Bindung und die <xref:System.Windows.Data.BindingMode>\-Bindung funktionieren, muss das Quellobjekt Benachrichtigungen für Eigenschaftenänderungen bereitstellen.  Weitere Informationen finden Sie in den Beispielen in diesem Thema.  Zusätzliche Informationen können Sie auch dem Dokument [Implementieren von Benachrichtigungen bei Eigenschaftenänderungen](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md) entnehmen.  
  
## Siehe auch  
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)