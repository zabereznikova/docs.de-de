---
title: "&#220;bersicht &#252;ber die QuickInfo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Steuerelemente, QuickInfo"
  - "ToolStrip-Steuerelement, Informationen über das ToolTip-Steuerelement"
ms.assetid: f06c1603-e9cb-4809-8a62-234607fc52f7
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# &#220;bersicht &#252;ber die QuickInfo
Eine QuickInfo ist ein kleines Popupfenster, das angezeigt wird, wenn ein Benutzer den Mauszeiger über ein Element hält, z. B. über eine <xref:System.Windows.Controls.Button>.  In diesem Thema wird die QuickInfo vorgestellt und erläutert, wie Sie QuickInfo\-Inhalte erstellen und anpassen.  
  
   
  
<a name="what_is_a_tooltip"></a>   
## Was ist eine QuickInfo?  
 Wenn ein Benutzer den Mauszeiger über ein Element bewegt, das über eine QuickInfo verfügt, wird für eine bestimmte Zeitspanne ein Fenster mit dem QuickInfo\-Inhalt angezeigt \(z. B. Text, der die Funktion eines Steuerelements beschreibt\).  Wenn der Benutzer den Mauszeiger vom Steuerelement weg bewegt, wird das Fenster nicht mehr angezeigt, da der QuickInfo\-Inhalt den Fokus nicht erhalten kann.  
  
 Eine QuickInfo kann eine oder mehrere Textzeilen, Bilder, Formen oder andere visuelle Inhalte enthalten.  Sie definieren eine QuickInfo für ein Steuerelement, indem Sie eine der folgenden Eigenschaften auf den QuickInfo\-Inhalt festlegen.  
  
-   <xref:System.Windows.FrameworkContentElement.ToolTip%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=fullName>  
  
 Welche Eigenschaft Sie verwenden, ist davon abhängig, ob das Steuerelement, das die QuickInfo definiert, von der <xref:System.Windows.FrameworkContentElement>\-Klasse oder der <xref:System.Windows.FrameworkElement>\-Klasse erbt.  
  
<a name="create_tooltip"></a>   
## Erstellen einer QuickInfo  
 Im folgenden Beispiel wird veranschaulicht, wie Sie eine einfache QuickInfo erstellen, indem Sie die <xref:System.Windows.FrameworkElement.ToolTip%2A>\-Eigenschaft für ein <xref:System.Windows.Controls.Button>\-Steuerelement auf eine Textzeichenfolge festlegen.  
  
 [!code-xml[GroupBoxSnippet#ToolTipString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipstring)]  
  
 Sie können eine QuickInfo ebenfalls als ein <xref:System.Windows.Controls.ToolTip>\-Objekt definieren.  Im folgenden Beispiel wird [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] verwendet, um ein <xref:System.Windows.Controls.ToolTip>\-Objekt als QuickInfo eines <xref:System.Windows.Controls.TextBox>\-Elements anzugeben.  Beachten Sie, dass die <xref:System.Windows.Controls.ToolTip> im Beispiel durch Festlegen der <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=fullName>\-Eigenschaft angegeben wird.  
  
 [!code-xml[ToolTipSimple#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#tooltip)]  
  
 Im folgenden Beispiel wird Code verwendet, um ein <xref:System.Windows.Controls.ToolTip>\-Objekt zu generieren.  Im Beispiel wird eine <xref:System.Windows.Controls.ToolTip> \(`tt`\) erstellt und einem <xref:System.Windows.Controls.Button> zugeordnet.  
  
 [!code-csharp[ToolTipSimple#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ToolTipSimple#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipSimple/VisualBasic/Window1.xaml.vb#2)]  
  
 Sie können auch QuickInfo\-Inhalte erstellen, die nicht als ein <xref:System.Windows.Controls.ToolTip>\-Objekt definiert sind, indem Sie diese in ein Layoutelement \(z. B. ein <xref:System.Windows.Controls.DockPanel>\) einschließen.  Im folgenden Beispiel wird veranschaulicht, wie die <xref:System.Windows.FrameworkElement.ToolTip%2A>\-Eigenschaft einer <xref:System.Windows.Controls.TextBox> auf Inhalte festgelegt wird, die in einem <xref:System.Windows.Controls.DockPanel>\-Steuerelement eingeschlossen sind.  
  
 [!code-xml[GroupBoxSnippet#ToolTipDockPanel](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipdockpanel)]  
  
<a name="Using_the_ToolTip_and_ToolTipService_Properties"></a>   
## Verwenden der Eigenschaften der QuickInfo\-Klasse und der ToolTipService\-Klasse  
 Sie können QuickInfo\-Inhalte anpassen, indem Sie visuelle Eigenschaften festlegen und Stile anwenden.  Wenn Sie den QuickInfo\-Inhalt als ein <xref:System.Windows.Controls.ToolTip>\-Objekt definieren, können Sie die visuellen Eigenschaften des <xref:System.Windows.Controls.ToolTip>\-Objekts festlegen.  Andernfalls müssen Sie für die <xref:System.Windows.Controls.ToolTipService>\-Klasse entsprechende [angefügte Eigenschaften](GTMT) festlegen.  
  
 Ein Beispiel zum Festlegen von Eigenschaften, um die Position der QuickInfo\-Inhalte mithilfe der <xref:System.Windows.Controls.ToolTip>\-Eigenschaft und der <xref:System.Windows.Controls.ToolTipService>\-Eigenschaft anzugeben, finden Sie unter [Positionieren einer QuickInfo](../../../../docs/framework/wpf/controls/how-to-position-a-tooltip.md).  
  
<a name="StylingToolTip"></a>   
## Formatieren einer QuickInfo  
 Sie können eine <xref:System.Windows.Controls.ToolTip> formatieren, indem Sie einen benutzerdefinierten <xref:System.Windows.Style> definieren.  Im folgenden Beispiel wird ein <xref:System.Windows.Style> mit dem Namen `Simple` definiert, mit dem gezeigt wird, wie Sie den Offset für die Platzierung der <xref:System.Windows.Controls.ToolTip> angeben und die Darstellung ändern, indem Sie <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, <xref:System.Windows.Controls.Control.FontSize%2A> und <xref:System.Windows.Controls.Control.FontWeight%2A> festlegen.  
  
 [!code-xml[ToolTipSimple#Style](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#style)]  
  
<a name="UsingtheToolTipServiceTimeIntervalProperties"></a>   
## Verwenden der Zeitintervalleigenschaften von ToolTipService  
 Die <xref:System.Windows.Controls.ToolTipService>\-Klasse stellt Ihnen die folgenden Eigenschaften zur Verfügung, mit denen Sie festlegen können, wie lange eine QuickInfo angezeigt wird: <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>, <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> und <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A>.  
  
 Geben Sie mit der <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>\-Eigenschaft und der <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A>\-Eigenschaft eine \(normalerweise kurze\) Verzögerung vor dem Anzeigen der <xref:System.Windows.Controls.ToolTip> und die Zeitspanne an, die die <xref:System.Windows.Controls.ToolTip> sichtbar bleibt.  Weitere Informationen finden Sie unter [How to: Delay the Display of a ToolTip](http://msdn.microsoft.com/de-de/618e05ef-f2bf-4a53-a0f4-aacb49918bd7).  
  
 Die <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>\-Eigenschaft legt fest, ob QuickInfos für verschiedene Steuerelemente ohne eine Verzögerung angezeigt werden, wenn Sie den Mauszeiger schnell von einem zum anderen Steuerelement bewegen.  Weitere Informationen zur <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>\-Eigenschaft finden Sie unter [Verwenden der BetweenShowDelay\-Eigenschaft](../../../../docs/framework/wpf/controls/how-to-use-the-betweenshowdelay-property.md).  
  
 Das folgende Beispiel zeigt, wie diese Eigenschaften für eine QuickInfo festgelegt werden.  
  
 [!code-xml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.ToolTipService>   
 <xref:System.Windows.Controls.ToolTip>   
 <xref:System.Windows.Controls.ToolTipEventArgs>   
 <xref:System.Windows.Controls.ToolTipEventHandler>   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)