---
title: "Gewusst wie: Erstellen eines Stils für einen gezogenen GridView-Spaltenheader"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 0b999645-0313-4b33-80b9-19ece08b5459
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 001d0ec45ad990ef366e7fc1216a7370aade9cb7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-style-for-a-dragged-gridview-column-header"></a>Gewusst wie: Erstellen eines Stils für einen gezogenen GridView-Spaltenheader
In diesem Beispiel wird gezeigt, wie die Darstellung eines gezogenen geändert <xref:System.Windows.Controls.GridViewColumnHeader> Wenn der Benutzer die Position einer Spalte ändert.  
  
## <a name="example"></a>Beispiel  
 Wenn Sie eine Spaltenüberschrift ziehen, an einen anderen Speicherort in einer <xref:System.Windows.Controls.ListView> , verwendet <xref:System.Windows.Controls.GridView> für den Ansichtsmodus an, die für die Spalte an die neue Position verschoben wird. Während Sie den Spaltenüberschrift ziehen, wird eine unverankerte Kopie des Headers zusätzlich zu der ursprünglichen Überschrift angezeigt. Eine Spaltenüberschrift in einer <xref:System.Windows.Controls.GridView> wird dargestellt, indem Sie eine <xref:System.Windows.Controls.GridViewColumnHeader> Objekt.  
  
 Sie können zum Anpassen der Darstellung der Gleitkomma- und ursprünglichen Header festlegen <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> so ändern Sie die <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>. Diese <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> werden angewendet, wenn die <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> Eigenschaftswert ist `true` und <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> Eigenschaftswert ist <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.  
  
 Wenn der Benutzer die Maustaste drückt und gedrückt hält, während sich der Mauszeiger auf die <xref:System.Windows.Controls.GridViewColumnHeader>, <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> Eigenschaftswert geändert wird, um `true`. Ebenso, wenn der Benutzer beginnt des Ziehvorgangs wird, die <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> eigenschaftsänderungen <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.  
  
 Im folgende Beispiel wird gezeigt, wie festzulegende <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> so ändern Sie die <xref:System.Windows.Controls.Control.Foreground%2A> und <xref:System.Windows.Controls.Control.Background%2A> Farben, der die ursprünglichen "oder" floating-Header, wenn eine Spalte an eine neue Position bewegt.  
  
 [!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplatestart)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersstart)]  
[!code-xaml[ListViewHeaderRoleStyle#IsPressed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#ispressed)]  
[!code-xaml[ListViewHeaderRoleStyle#Floating](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#floating)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersend)]  
[!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplateend)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.GridViewColumnHeader>  
 <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Übersicht über GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
