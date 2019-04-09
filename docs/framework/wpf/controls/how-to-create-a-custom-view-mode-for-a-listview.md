---
title: 'Vorgehensweise: Erstellen eines benutzerdefinierten Ansichtsmodus für ein ListView-Objekt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: de11250a2e7529fba3b262e42b6714262738fa90
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092889"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a>Vorgehensweise: Erstellen eines benutzerdefinierten Ansichtsmodus für ein ListView-Objekt
In diesem Beispiel wird gezeigt, wie eine benutzerdefinierte <xref:System.Windows.Controls.ListView.View%2A> Modus für eine <xref:System.Windows.Controls.ListView> Steuerelement.  
  
## <a name="example"></a>Beispiel  
 Verwenden Sie die <xref:System.Windows.Controls.ViewBase> Klasse bei der Erstellung einer benutzerdefinierten Ansicht für die <xref:System.Windows.Controls.ListView> Steuerelement. Das folgende Beispiel zeigt einen Anzeigemodus aus, die aufgerufen wird `PlainView`, ergibt sich aus der <xref:System.Windows.Controls.ViewBase> Klasse.  
  
 [!code-csharp[ListViewCustomView#PlainView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 Verwenden Sie zum Anwenden eines Stils für die benutzerdefinierte Ansicht der <xref:System.Windows.Style> Klasse. Das folgende Beispiel definiert eine <xref:System.Windows.Style> für die `PlainView` sichtmodus befinden. Im vorherigen Beispiel dieses Format festgelegt ist, als Wert für die <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> für definierte Eigenschaft `PlainView`.  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 Um das Layout der Daten in einen benutzerdefinierten Ansichtsmodus zu definieren, definieren eine <xref:System.Windows.DataTemplate> Objekt. Das folgende Beispiel definiert eine <xref:System.Windows.DataTemplate> , die verwendet werden kann, zum Anzeigen von Daten in die `PlainView` sichtmodus befinden.  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.ResourceKey> für die `PlainView` Anzeigemodus, verwendet der <xref:System.Windows.DataTemplate> , die im vorherigen Beispiel definiert ist.  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 Ein <xref:System.Windows.Controls.ListView> -Steuerelement kann eine benutzerdefinierte Ansicht verwenden, setzen Sie die <xref:System.Windows.Controls.ListView.View%2A> Eigenschaft, um den Ressourcenschlüssel. Das folgende Beispiel zeigt, wie angegeben `PlainView` als den Anzeigemodus für eine <xref:System.Windows.Controls.ListView>.  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 Das vollständige Beispiel finden Sie unter [ListView mit mehreren Ansichten (C#)](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) oder [ListView mit mehreren Views(Visual Basic)](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Gewusst wie-Themen](listview-how-to-topics.md)
- [Übersicht über ListView](listview-overview.md)
- [Übersicht über GridView](gridview-overview.md)
