---
title: "&#220;bersicht &#252;ber Expander-Steuerelemente | Microsoft Docs"
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
  - "Steuerelemente, Expander"
  - "Expander-Steuerelement, Informationen über das Expander-Steuerelement"
ms.assetid: 877bf425-0e54-49ec-8fd2-13a211377abb
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# &#220;bersicht &#252;ber Expander-Steuerelemente
Mit einem <xref:System.Windows.Controls.Expander>\-Steuerelement können Sie Inhalte in einem erweiterbaren Bereich bereitstellen, der einem Fenster ähnelt und einen Header enthält.  
  
   
  
<a name="CreatinganExpanderinXAML"></a>   
## Erstellen eines einfachen Expander\-Steuerelements  
 Im folgenden Beispiel wird das Erstellen eines einfachen <xref:System.Windows.Controls.Expander>\-Steuerelements veranschaulicht.  In diesem Beispiel wird ein <xref:System.Windows.Controls.Expander>\-Steuerelement erstellt, das der vorherigen Abbildung entspricht.  
  
 [!code-xml[ExpanderExample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderExample/CSharp/Page1.xaml#2)]  
  
 <xref:System.Windows.Controls.ContentControl.Content%2A> und <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> eines <xref:System.Windows.Controls.Expander>\-Steuerelements können auch komplexen Inhalt wie <xref:System.Windows.Controls.RadioButton>\-Objekte und <xref:System.Windows.Controls.Image>\-Objekte enthalten.  
  
<a name="SettingtheDirectionoftheExpandingWindow"></a>   
## Festlegen der Erweiterungsrichtung des Inhaltsbereichs  
 Sie können als Erweiterungsrichtung für den Inhaltsbereich eines <xref:System.Windows.Controls.Expander>\-Steuerelements eine von vier Richtungen festlegen \(<xref:System.Windows.Controls.ExpandDirection>, <xref:System.Windows.Controls.ExpandDirection>, <xref:System.Windows.Controls.ExpandDirection> oder <xref:System.Windows.Controls.ExpandDirection>\). Verwenden Sie dazu die <xref:System.Windows.Controls.ExpandDirection>\-Eigenschaft.  Wenn der Inhaltsbereich reduziert ist, werden nur <xref:System.Windows.Controls.Expander><xref:System.Windows.Controls.HeaderedContentControl.Header%2A> und die entsprechende Umschaltfläche angezeigt.  Als Umschaltfläche zum Erweitern bzw. Reduzieren des Inhaltsbereichs wird ein <xref:System.Windows.Controls.Button>\-Steuerelement verwendet, in dem ein Richtungspfeil anzeigt wird.  Wenn das <xref:System.Windows.Controls.Expander>\-Steuerelement erweitert wird, versucht es, den Inhalt in einem fensterähnlichen Bereich anzuzeigen.  
  
<a name="SettingSizeDimensionsonanExpanderinaPanel"></a>   
## Festlegen der Größe eines Expander\-Steuerelements in einem Bereich  
 Wenn sich ein <xref:System.Windows.Controls.Expander>\-Steuerelement innerhalb eines Layoutsteuerelements befindet, das von <xref:System.Windows.Controls.Panel> wie z. B. <xref:System.Windows.Controls.StackPanel> erbt, legen Sie nicht <xref:System.Windows.FrameworkElement.Height%2A> für das <xref:System.Windows.Controls.Expander>Steuerelement fest, falls die <xref:System.Windows.Controls.Expander.ExpandDirection%2A>\-Eigenschaft auf <xref:System.Windows.Controls.ExpandDirection> oder <xref:System.Windows.Controls.ExpandDirection> festgelegt ist.  Legen Sie entsprechend nicht <xref:System.Windows.FrameworkElement.Width%2A> für das <xref:System.Windows.Controls.Expander>\-Steuerelement fest, wenn die <xref:System.Windows.Controls.Expander.ExpandDirection%2A>\-Eigenschaft auf <xref:System.Windows.Controls.ExpandDirection> oder <xref:System.Windows.Controls.ExpandDirection> festgelegt ist.  
  
 Wenn Sie für ein <xref:System.Windows.Controls.Expander>\-Steuerelement eine Größendimension in der Richtung festlegen, in der der erweiterte Inhalt angezeigt wird, übernimmt das <xref:System.Windows.Controls.Expander>\-Steuerelement die Steuerung des Inhaltsbereichs und zeigt einen Rahmen um den Inhalt an.  Der Rahmen wird auch angezeigt, wenn der Inhalt reduziert ist.  Zum Festlegen der Größe des erweiterten Inhaltsbereichs legen Sie Größendimensionen für den Inhalt des <xref:System.Windows.Controls.Expander>\-Steuerelements fest. Wenn Bildlauffunktionen zur Verfügung gestellt werden sollen, legen Sie Größendimensionen für das <xref:System.Windows.Controls.ScrollViewer>\-Steuerelement fest, das den Inhalt einschließt.  
  
 Wenn ein <xref:System.Windows.Controls.Expander>\-Steuerelement das letzte Element in <xref:System.Windows.Controls.DockPanel> ist, legt [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] die <xref:System.Windows.Controls.Expander>\-Dimensionen automatisch so fest, dass sie dem verbleibenden Bereich von <xref:System.Windows.Controls.DockPanel> entsprechen.  Wenn dieses Standardverhalten nicht verwendet werden soll, legen Sie die <xref:System.Windows.Controls.DockPanel.LastChildFill%2A>\-Eigenschaft des <xref:System.Windows.Controls.DockPanel>\-Objekts auf `false` fest, oder stellen Sie sicher, dass <xref:System.Windows.Controls.Expander> nicht das letzte Element in <xref:System.Windows.Controls.DockPanel> ist.  
  
<a name="CreatingScrollableContent"></a>   
## Erstellen von bildlauffähigem Inhalt  
 Wenn der Inhalt die Größe des Inhaltsbereichs überschreitet, können Sie den Inhalt eines <xref:System.Windows.Controls.Expander>\-Steuerelements mit einem <xref:System.Windows.Controls.ScrollViewer>\-Steuerelement umschließen, um bildlauffähigen Inhalt bereitzustellen.  Das <xref:System.Windows.Controls.Expander>\-Steuerelement stellt die Bildlauffunktion nicht automatisch bereit.  In der folgenden Abbildung wird ein <xref:System.Windows.Controls.Expander>\-Steuerelement dargestellt, das ein <xref:System.Windows.Controls.ScrollViewer>\-Steuerelement enthält.  
  
 **Expander\-Steuerelement in einem ScrollViewer\-Steuerelement**  
  
 ![Expander mit ScrollBar](../../../../docs/framework/wpf/controls/media/expanderwithscrollbar.JPG "ExpanderWithScrollBar")  
  
 Wenn Sie ein <xref:System.Windows.Controls.Expander>\-Steuerelement in ein <xref:System.Windows.Controls.ScrollViewer>\-Steuerelement einfügen, legen Sie die Größe der <xref:System.Windows.Controls.ScrollViewer>\-Dimensionseigenschaft für die Richtung, in die der <xref:System.Windows.Controls.Expander>\-Inhalt erweitert wird, auf die Größe des <xref:System.Windows.Controls.Expander>\-Inhaltsbereichs fest.  Wenn Sie z. B. die <xref:System.Windows.Controls.Expander.ExpandDirection%2A>\-Eigenschaft des <xref:System.Windows.Controls.Expander>\-Steuerelements auf <xref:System.Windows.Controls.ExpandDirection> festlegen \(der Inhaltsbereich wird nach unten erweitert\), legen Sie die <xref:System.Windows.FrameworkElement.Height%2A>\-Eigenschaft des <xref:System.Windows.Controls.ScrollViewer>\-Steuerelements auf die für den Inhaltsbereich erforderliche Höhe fest.  Wenn Sie stattdessen die Höhendimension auf den Inhalt festlegen, wird diese Einstellung vom <xref:System.Windows.Controls.ScrollViewer>\-Steuerelement nicht erkannt. Es steht daher kein bildlauffähiger Inhalt zur Verfügung.  
  
 Im folgenden Beispiel wird das Erstellen eines <xref:System.Windows.Controls.Expander>\-Steuerelements veranschaulicht, das komplexen Inhalt und ein <xref:System.Windows.Controls.ScrollViewer>\-Steuerelement enthält.  In diesem Beispiel wird ein <xref:System.Windows.Controls.Expander>\-Steuerelement erstellt, das der Abbildung am Anfang dieses Abschnitts entspricht.  
  
 [!code-csharp[ExpanderRichContent#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ExpanderRichContent#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpanderRichContent/VisualBasic/Window1.xaml.vb#1)]
 [!code-xml[ExpanderRichContent#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#1)]  
  
<a name="UsingtheAlignmentProperties"></a>   
## Verwenden der Alignment\-Eigenschaften  
 Sie können Inhalt ausrichten, indem Sie die <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>\-Eigenschaft und die <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A>\-Eigenschaft des <xref:System.Windows.Controls.Expander>\-Steuerelements festlegen.  Wenn Sie diese Eigenschaften festlegen, wird die Ausrichtung auf den Header sowie auf den erweiterten Inhalt angewendet.  
  
## Siehe auch  
 <xref:System.Windows.Controls.Expander>   
 <xref:System.Windows.Controls.ExpandDirection>   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)