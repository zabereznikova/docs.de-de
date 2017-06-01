---
title: "Gewusst wie: Erstellen eines Stils f&#252;r einen gezogenen GridView-Spaltenheader | Microsoft Docs"
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
  - "ListView-Steuerelemente, Formatierung"
ms.assetid: 0b999645-0313-4b33-80b9-19ece08b5459
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Erstellen eines Stils f&#252;r einen gezogenen GridView-Spaltenheader
In diesem Beispiel wird erläutert, wie Sie die Darstellung eines gezogenen <xref:System.Windows.Controls.GridViewColumnHeader> ändern, wenn der Benutzer die Position einer Spalte ändert.  
  
## Beispiel  
 Wenn Sie einen Spaltenheader in einer <xref:System.Windows.Controls.ListView> im <xref:System.Windows.Controls.GridView>\-Ansichtmodus an eine neue Position ziehen, wird die Spalte an die neue Position verschoben.  Beim Ziehen des Spaltenheaders wird zusätzlich zum ursprünglichen Header eine unverankerte Kopie des Headers angezeigt.  Ein Spaltenheader in einem <xref:System.Windows.Controls.GridView> wird durch ein <xref:System.Windows.Controls.GridViewColumnHeader>\-Objekt dargestellt.  
  
 Um die Darstellung des unverankerten und des ursprünglichen Headers anzupassen, können Sie <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> zum Ändern des <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style> festlegen.  Diese <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> werden angewendet, wenn der <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A>\-Eigenschaftswert `true` und der <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A>\-Eigenschaftswert <xref:System.Windows.Controls.GridViewColumnHeaderRole> ist.  
  
 Wenn der Benutzer die Maustaste gedrückt hält, während sich der Mauszeiger über dem <xref:System.Windows.Controls.GridViewColumnHeader> befindet, wird der <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A>\-Eigenschaftswert auf `true` geändert.  Wenn der Benutzer den Ziehvorgang startet, wird die <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A>\-Eigenschaft entsprechend auf <xref:System.Windows.Controls.GridViewColumnHeaderRole> geändert.  
  
 Im folgenden Beispiel wird erläutert, wie Sie <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> so festlegen, dass die Farben für <xref:System.Windows.Controls.Control.Foreground%2A> und <xref:System.Windows.Controls.Control.Background%2A> des ursprünglichen und unverankerten Headers geändert werden, wenn der Benutzer eine Spalte an eine neue Position zieht.  
  
 [!code-xml[ListViewHeaderRoleStyle#GVCHControlTemplateStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplatestart)]  
[!code-xml[ListViewHeaderRoleStyle#ControlTemplateTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersstart)]  
[!code-xml[ListViewHeaderRoleStyle#IsPressed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#ispressed)]  
[!code-xml[ListViewHeaderRoleStyle#Floating](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#floating)]  
[!code-xml[ListViewHeaderRoleStyle#ControlTemplateTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersend)]  
[!code-xml[ListViewHeaderRoleStyle#GVCHControlTemplateEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplateend)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.GridViewColumnHeader>   
 <xref:System.Windows.Controls.GridViewColumnHeaderRole>   
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Übersicht über GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)