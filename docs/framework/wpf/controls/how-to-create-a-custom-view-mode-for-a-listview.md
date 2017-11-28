---
title: "Gewusst wie: Erstellen eines benutzerdefinierten Ansichtsmodus für eine ListView"
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
helpviewer_keywords: ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c62bcb14f444490991b36dc21eb7676a67007906
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a>Gewusst wie: Erstellen eines benutzerdefinierten Ansichtsmodus für eine ListView
In diesem Beispiel wird gezeigt, wie eine benutzerdefinierte <xref:System.Windows.Controls.ListView.View%2A> Modus für eine <xref:System.Windows.Controls.ListView> Steuerelement.  
  
## <a name="example"></a>Beispiel  
 Verwenden Sie die <xref:System.Windows.Controls.ViewBase> Klasse bei der Erstellung einer benutzerdefinierten Ansicht für die <xref:System.Windows.Controls.ListView> Steuerelement. Das folgende Beispiel zeigt einen Ansichtsmodus, die aufgerufen wird `PlainView`, abgeleitet aus dem <xref:System.Windows.Controls.ViewBase> Klasse.  
  
 [!code-csharp[ListViewCustomView#PlainView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 Um einen Stil für die benutzerdefinierte Ansicht anzuwenden, verwenden die <xref:System.Windows.Style> Klasse. Das folgende Beispiel definiert eine <xref:System.Windows.Style> für die `PlainView` sichtmodus befinden. Im vorherigen Beispiel dieses Format festgelegt ist, als Wert für die <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> für definierte Eigenschaft `PlainView`.  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 Um das Layout der Daten in einen benutzerdefinierten Ansichtsmodus definieren, definieren eine <xref:System.Windows.DataTemplate> Objekt. Das folgende Beispiel definiert eine <xref:System.Windows.DataTemplate> , die verwendet werden kann, zum Anzeigen von Daten in die `PlainView` sichtmodus befinden.  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.ResourceKey> für die `PlainView` Anzeigemodus, verwendet die <xref:System.Windows.DataTemplate> , die im vorherigen Beispiel definiert ist.  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 Ein <xref:System.Windows.Controls.ListView> Steuerelement kann eine benutzerdefinierte Ansicht verwenden, wenn Sie festlegen, die <xref:System.Windows.Controls.ListView.View%2A> Eigenschaft auf den Ressourcenschlüssel. Im folgende Beispiel wird gezeigt, wie an `PlainView` wie der Anzeigemodus für eine <xref:System.Windows.Controls.ListView>.  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 Das vollständige Beispiel finden Sie unter [ListView mit mehreren Ansichten Beispiel](http://go.microsoft.com/fwlink/?LinkID=160013).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Übersicht über GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
