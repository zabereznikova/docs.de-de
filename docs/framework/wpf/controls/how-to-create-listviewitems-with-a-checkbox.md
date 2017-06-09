---
title: "Gewusst wie: Erstellen von ListViewItems mit einem Kontrollk&#228;stchen | Microsoft Docs"
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
  - "ListView-Steuerelemente"
  - "CheckBox-Steuerelemente"
  - "ListView-Steuerelemente, steuert das Kontrollkästchen"
  - "CheckBox-Steuerelement ListView-Steuerelement"
ms.assetid: f6d66c7f-906c-4f65-a55a-0ede9d00e26a
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Erstellen von ListViewItems mit einem Kontrollk&#228;stchen
In diesem Beispiel wird veranschaulicht, wie eine Spalte der <xref:System.Windows.Controls.CheckBox> Steuerelemente in eine <xref:System.Windows.Controls.ListView> -Steuerelement, verwendet eine <xref:System.Windows.Controls.GridView>.  
  
## <a name="example"></a>Beispiel  
 Um eine Spalte zu erstellen, enthält <xref:System.Windows.Controls.CheckBox> Steuerelemente in einer <xref:System.Windows.Controls.ListView>, erstellen eine <xref:System.Windows.DataTemplate> , enthält eine <xref:System.Windows.Controls.CheckBox>. Legen Sie dann die <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> von einer <xref:System.Windows.Controls.GridViewColumn> an der <xref:System.Windows.DataTemplate>.  
  
 Das folgende Beispiel zeigt eine <xref:System.Windows.DataTemplate> , enthält eine <xref:System.Windows.Controls.CheckBox>. Im Beispiel wird die <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> Eigenschaft der <xref:System.Windows.Controls.CheckBox> auf der <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> Eigenschaftswert der <xref:System.Windows.Controls.ListViewItem> , die Sie enthält. Daher bei der <xref:System.Windows.Controls.ListViewItem> , enthält die <xref:System.Windows.Controls.CheckBox> ausgewählt ist, die <xref:System.Windows.Controls.CheckBox> aktiviert ist.  
  
 [!code-xml[ListViewChkBox#CheckBoxDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#checkboxdatatemplate)]  
  
 Im folgenden Beispiel wird veranschaulicht, wie eine Spalte von <xref:System.Windows.Controls.CheckBox> Steuerelemente. Zu der Spalte im Beispiel wird die <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> Eigenschaft der <xref:System.Windows.Controls.GridViewColumn> an der <xref:System.Windows.DataTemplate>.  
  
 [!code-xml[ListViewChkBox#GridViewColumnCheckBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#gridviewcolumncheckbox)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Control>   
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Gewusst-wie-Themen](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [Übersicht über GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)