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
ms.openlocfilehash: 0fec31b28a21c2e17986210c852b3d630087842d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181950"
---
# <a name="tooltip-overview"></a>Übersicht über die QuickInfo
Eine QuickInfo ist ein kleines Popupfenster, das angezeigt wird, wenn ein Benutzer <xref:System.Windows.Controls.Button>den Mauszeiger über ein Element anhält, z. B. über einem . In diesem Thema wird die QuickInfo vorgestellt und das Erstellen und Anpassen von QuickInfo-Inhalten erläutert.  

<a name="what_is_a_tooltip"></a>
## <a name="what-is-a-tooltip"></a>Was ist eine QuickInfo?  
 Wenn ein Benutzer den Mauszeiger über ein Element mit einer QuickInfo bewegt, wird für einen festgelegten Zeitraum ein Fenster mit dem Inhalt dieser QuickInfo angezeigt. Dabei kann es sich z.B. um Text handeln, der die Funktion eines Steuerelements beschreibt. Wenn der Benutzer den Mauszeiger vom Steuerelement wegbewegt, wird das Fenster nicht mehr angezeigt, da der Inhalt der QuickInfo keinen Fokus erhalten kann.  
  
 Der Inhalt einer QuickInfo kann eine oder mehrere Zeilen Text, Bilder, Formen oder andere visuelle Inhalte enthalten. Um eine QuickInfo für ein Steuerelement zu definieren, legen Sie für deren Inhalt eine der folgenden Eigenschaften fest.  
  
- <xref:System.Windows.FrameworkContentElement.ToolTip%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType>  
  
 Welche Eigenschaft Sie verwenden, hängt davon ab, ob das <xref:System.Windows.FrameworkContentElement> Steuerelement, das die QuickInfo definiert, von der oder-Klasse <xref:System.Windows.FrameworkElement> erbt.  
  
<a name="create_tooltip"></a>
## <a name="creating-a-tooltip"></a>Erstellen einer QuickInfo  
 Das folgende Beispiel zeigt, wie Sie eine <xref:System.Windows.FrameworkElement.ToolTip%2A> einfache <xref:System.Windows.Controls.Button> QuickInfo erstellen, indem Sie die Eigenschaft für ein Steuerelement auf eine Textzeichenfolge festlegen.  
  
 [!code-xaml[GroupBoxSnippet#ToolTipString](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipstring)]  
  
 Sie können auch eine QuickInfo als <xref:System.Windows.Controls.ToolTip> Objekt definieren. Im folgenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Beispiel wird <xref:System.Windows.Controls.ToolTip> ein Objekt als <xref:System.Windows.Controls.TextBox> QuickInfo eines Elements angegeben. Beachten Sie, dass <xref:System.Windows.Controls.ToolTip> das Beispiel <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType> die durch Festlegen der Eigenschaft angibt.  
  
 [!code-xaml[ToolTipSimple#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#tooltip)]  
  
 Im folgenden Beispiel wird <xref:System.Windows.Controls.ToolTip> Code zum Generieren eines Objekts verwendet. Das Beispiel <xref:System.Windows.Controls.ToolTip> erstellt`tt`eine ( ) <xref:System.Windows.Controls.Button>und ordnet sie einer zu.  
  
 [!code-csharp[ToolTipSimple#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ToolTipSimple#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipSimple/VisualBasic/Window1.xaml.vb#2)]  
  
 Sie können auch QuickInfo-Inhalte erstellen, <xref:System.Windows.Controls.ToolTip> die nicht als Objekt definiert sind, indem <xref:System.Windows.Controls.DockPanel>Sie den QuickInfo-Inhalt in ein Layoutelement einschließen, z. B. eine . Das folgende Beispiel zeigt, <xref:System.Windows.FrameworkElement.ToolTip%2A> wie <xref:System.Windows.Controls.TextBox> die Eigenschaft von a <xref:System.Windows.Controls.DockPanel> auf Inhalt festgelegt wird, der in einem Steuerelement eingeschlossen ist.  
  
 [!code-xaml[GroupBoxSnippet#ToolTipDockPanel](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipdockpanel)]  
  
<a name="Using_the_ToolTip_and_ToolTipService_Properties"></a>
## <a name="using-the-properties-of-the-tooltip-and-tooltipservice-classes"></a>Verwenden der Eigenschaften der Klassen ToolTip und ToolTipService  
 Sie können den Inhalt einer QuickInfo anpassen, indem Sie Eigenschaften für das Erscheinungsbild festlegen und Stile anwenden. Wenn Sie den QuickInfo-Inhalt als <xref:System.Windows.Controls.ToolTip> Objekt definieren, können <xref:System.Windows.Controls.ToolTip> Sie die visuellen Eigenschaften des Objekts festlegen. Andernfalls müssen Sie entsprechende angefügte <xref:System.Windows.Controls.ToolTipService> Eigenschaften für die Klasse festlegen.  
  
 Ein Beispiel für das Festlegen von Eigenschaften zum Angeben der Position <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ToolTipService> des QuickInfo-Inhalts mithilfe der und-Eigenschaften finden Sie unter [Positionieren eines ToolTip](how-to-position-a-tooltip.md).  
  
<a name="StylingToolTip"></a>
## <a name="styling-a-tooltip"></a>Formatieren einer QuickInfo  
 Sie können <xref:System.Windows.Controls.ToolTip> eine formatieren, indem Sie eine benutzerdefinierte <xref:System.Windows.Style>. Im folgenden Beispiel <xref:System.Windows.Style> wird `Simple` ein Aufruf definiert, der <xref:System.Windows.Controls.ToolTip> zeigt, wie die <xref:System.Windows.Controls.Control.Background%2A> <xref:System.Windows.Controls.Control.Foreground%2A>Platzierung <xref:System.Windows.Controls.Control.FontSize%2A>der <xref:System.Windows.Controls.Control.FontWeight%2A>versetzt und ihre Darstellung durch Festlegen der , , und .  
  
 [!code-xaml[ToolTipSimple#Style](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#style)]  
  
<a name="UsingtheToolTipServiceTimeIntervalProperties"></a>
## <a name="using-the-time-interval-properties-of-tooltipservice"></a>Verwenden der Eigenschaften von ToolTipService für Zeitintervalle  
 Die <xref:System.Windows.Controls.ToolTipService> Klasse stellt die folgenden Eigenschaften bereit, <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>mit <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>denen <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A>Sie die Anzeigezeiten für QuickInfos festlegen können: , und .  
  
 Verwenden <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> Sie <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A> die und Eigenschaften, um eine <xref:System.Windows.Controls.ToolTip> Verzögerung anzugeben, die <xref:System.Windows.Controls.ToolTip> in der Regel kurz ist, bevor ein angezeigt wird, und auch, um anzugeben, wie lange ein sichtbar bleibt. Weitere Informationen finden Sie unter [Vorgehensweise: Verzögern der Anzeige einer QuickInfo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms747264(v=vs.90)).  
  
 Die <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> Eigenschaft bestimmt, ob QuickInfos für verschiedene Steuerelemente ohne anfängliche Verzögerung angezeigt werden, wenn Sie den Mauszeiger schnell zwischen ihnen bewegen. Weitere Informationen zur <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> Eigenschaft finden Sie unter [Verwenden der BetweenShowDelay-Eigenschaft](how-to-use-the-betweenshowdelay-property.md).  
  
 Das nachstehende Beispiel zeigt, wie Sie diese Eigenschaften für eine QuickInfo festlegen.  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Controls.ToolTipService>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipEventArgs>
- <xref:System.Windows.Controls.ToolTipEventHandler>
- [How-to-Themen](tooltip-how-to-topics.md)
