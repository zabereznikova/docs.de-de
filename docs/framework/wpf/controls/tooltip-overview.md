---
title: Übersicht über die QuickInfo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], about ToolTip control
- controls [WPF], ToolTip
ms.assetid: f06c1603-e9cb-4809-8a62-234607fc52f7
ms.openlocfilehash: 5378744ea43b72bafb77c9d58c1a8d848c3a8fc9
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2019
ms.locfileid: "56745514"
---
# <a name="tooltip-overview"></a>Übersicht über die QuickInfo
Eine QuickInfo ist ein kleines Popupfenster, das angezeigt wird, wenn ein Benutzer den Mauszeiger auf ein Element, beispielsweise über hält eine <xref:System.Windows.Controls.Button>. In diesem Thema wird die QuickInfo vorgestellt und das Erstellen und Anpassen von QuickInfo-Inhalten erläutert.  
  
 
  
<a name="what_is_a_tooltip"></a>   
## <a name="what-is-a-tooltip"></a>Was ist eine QuickInfo?  
 Wenn ein Benutzer den Mauszeiger über ein Element mit einer QuickInfo bewegt, wird für einen festgelegten Zeitraum ein Fenster mit dem Inhalt dieser QuickInfo angezeigt. Dabei kann es sich z.B. um Text handeln, der die Funktion eines Steuerelements beschreibt. Wenn der Benutzer den Mauszeiger vom Steuerelement wegbewegt, wird das Fenster nicht mehr angezeigt, da der Inhalt der QuickInfo keinen Fokus erhalten kann.  
  
 Der Inhalt einer QuickInfo kann eine oder mehrere Zeilen Text, Bilder, Formen oder andere visuelle Inhalte enthalten. Um eine QuickInfo für ein Steuerelement zu definieren, legen Sie für deren Inhalt eine der folgenden Eigenschaften fest.  
  
-   <xref:System.Windows.FrameworkContentElement.ToolTip%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType>  
  
 Die Eigenschaft, die Sie verwenden, hängt davon ab, ob das Steuerelement, das die QuickInfo definiert, erbt die <xref:System.Windows.FrameworkContentElement> oder <xref:System.Windows.FrameworkElement> Klasse.  
  
<a name="create_tooltip"></a>   
## <a name="creating-a-tooltip"></a>Erstellen einer QuickInfo  
 Das folgende Beispiel zeigt, wie Sie eine einfache QuickInfo erstellen, durch Festlegen der <xref:System.Windows.FrameworkElement.ToolTip%2A> -Eigenschaft für eine <xref:System.Windows.Controls.Button> Steuerelement auf eine Zeichenfolge.  
  
 [!code-xaml[GroupBoxSnippet#ToolTipString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipstring)]  
  
 Sie können auch eine QuickInfo als definieren eine <xref:System.Windows.Controls.ToolTip> Objekt. Im folgenden Beispiel wird [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] an eine <xref:System.Windows.Controls.ToolTip> Objekt als QuickInfo für ein <xref:System.Windows.Controls.TextBox> Element. Beachten Sie, die im Beispiel wird die <xref:System.Windows.Controls.ToolTip> durch Festlegen der <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType> Eigenschaft.  
  
 [!code-xaml[ToolTipSimple#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#tooltip)]  
  
 Im folgenden Beispiel wird der Code zum Generieren einer <xref:System.Windows.Controls.ToolTip> Objekt. Das Beispiel erstellt eine <xref:System.Windows.Controls.ToolTip> (`tt`) und ordnet ihn einem <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ToolTipSimple#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ToolTipSimple#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipSimple/VisualBasic/Window1.xaml.vb#2)]  
  
 Sie können auch QuickInfo-Inhalte, die als nicht definiert ist erstellen eine <xref:System.Windows.Controls.ToolTip> Objekt schließen Sie den QuickInfo-Inhalt in ein Layoutelement, z. B. eine <xref:System.Windows.Controls.DockPanel>. Das folgende Beispiel zeigt, wie Sie festlegen der <xref:System.Windows.FrameworkElement.ToolTip%2A> Eigenschaft eine <xref:System.Windows.Controls.TextBox> zu Inhalt, der in eingeschlossen ist eine <xref:System.Windows.Controls.DockPanel> Steuerelement.  
  
 [!code-xaml[GroupBoxSnippet#ToolTipDockPanel](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipdockpanel)]  
  
<a name="Using_the_ToolTip_and_ToolTipService_Properties"></a>   
## <a name="using-the-properties-of-the-tooltip-and-tooltipservice-classes"></a>Verwenden der Eigenschaften der Klassen ToolTip und ToolTipService  
 Sie können den Inhalt einer QuickInfo anpassen, indem Sie Eigenschaften für das Erscheinungsbild festlegen und Stile anwenden. Wenn Sie den QuickInfo-Inhalt als definieren eine <xref:System.Windows.Controls.ToolTip> Objekt ist, können Sie die visuellen Eigenschaften des Festlegen der <xref:System.Windows.Controls.ToolTip> Objekt. Andernfalls müssen Sie entsprechende angefügte Eigenschaften festlegen, auf die <xref:System.Windows.Controls.ToolTipService> Klasse.  
  
 Ein Beispiel zum Festlegen von Eigenschaften, um die Position der QuickInfo-Inhalte mithilfe von angeben der <xref:System.Windows.Controls.ToolTip> und <xref:System.Windows.Controls.ToolTipService> Eigenschaften finden Sie [Positionieren einer QuickInfo](../../../../docs/framework/wpf/controls/how-to-position-a-tooltip.md).  
  
<a name="StylingToolTip"></a>   
## <a name="styling-a-tooltip"></a>Formatieren einer QuickInfo  
 Sie können Formatieren einer <xref:System.Windows.Controls.ToolTip> durch Definieren eines benutzerdefinierten <xref:System.Windows.Style>. Das folgende Beispiel definiert eine <xref:System.Windows.Style> namens `Simple` , die zeigt, wie die Platzierung der offset der <xref:System.Windows.Controls.ToolTip> , und ändern Sie seine Darstellung durch Festlegen der <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, und <xref:System.Windows.Controls.Control.FontWeight%2A>.  
  
 [!code-xaml[ToolTipSimple#Style](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#style)]  
  
<a name="UsingtheToolTipServiceTimeIntervalProperties"></a>   
## <a name="using-the-time-interval-properties-of-tooltipservice"></a>Verwenden der Eigenschaften von ToolTipService für Zeitintervalle  
 Die <xref:System.Windows.Controls.ToolTipService> -Klasse bietet die folgenden Eigenschaften für die Sie festlegen, QuickInfo anzeigen: <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>, <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>, und <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A>.  
  
 Verwenden der <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> und <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A> Eigenschaften an eine Verzögerung in der Regel eine kurze, vor einer <xref:System.Windows.Controls.ToolTip> angezeigt wird und auch angeben, wie lange eine <xref:System.Windows.Controls.ToolTip> sichtbar bleibt. Weitere Informationen finden Sie unter [Vorgehensweise: Verzögern der Anzeige einer QuickInfo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms747264(v=vs.90)).  
  
 Die <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> Eigenschaft bestimmt, ob QuickInfos für andere Steuerelemente ohne Verzögerung angezeigt werden, wenn Sie den Mauszeiger Maus schnell zwischen diesen bewegen. Weitere Informationen zu den <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> -Eigenschaft finden Sie unter [verwenden der BetweenShowDelay-Eigenschaft](../../../../docs/framework/wpf/controls/how-to-use-the-betweenshowdelay-property.md).  
  
 Das nachstehende Beispiel zeigt, wie Sie diese Eigenschaften für eine QuickInfo festlegen.  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.ToolTipService>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipEventArgs>
- <xref:System.Windows.Controls.ToolTipEventHandler>
- [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)
