---
title: Eigenschaftenzuordnung von Windows Forms und WPF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- property mapping [WPF interoperability]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 999d8298-9c04-467d-a453-86e41002057d
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 615d46b949a70c337204552b7bcf8b2934054b77
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="windows-forms-and-wpf-property-mapping"></a>Eigenschaftenzuordnung von Windows Forms und WPF
Die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Technologien können zwei ähnliche, aber nicht identische Eigenschaft Modelle. *Eigenschaftenzuordnung* Interoperation zwischen den beiden Architekturen unterstützt, und bietet die folgenden Funktionen:  
  
-   Vereinfacht die relevante eigenschaftenänderungen in der hostumgebung das gehostete Steuerelement oder Element zuzuordnen.  
  
-   Bietet Standardbehandlung für das Zuordnen der am häufigsten Eigenschaften verwendet.  
  
-   Ermöglicht einfaches entfernen, überschreiben oder Erweitern von Standardeigenschaften.  
  
-   Stellt sicher, dass der Eigenschaftswert ändert auf dem Host automatisch erkannt und in das gehostete Steuerelement oder Element übersetzt.  
  
> [!NOTE]
>  Eigenschaftenänderungsereignisse werden nicht die hosting-Steuerelement oder Elementhierarchie weitergegeben. Eigenschaft Übersetzung wird nicht ausgeführt, wenn Sie der lokale Wert einer Eigenschaft nicht geändert wird, aufgrund der direkten Einstellung, Stile, Vererbung, Binden von Daten oder anderen Mechanismen, die den Wert der Eigenschaft zu ändern.  
  
 Verwenden der <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> Eigenschaft auf die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element und die <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> Eigenschaft auf <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement eigenschaftenzuordnung zugreifen.  
  
## <a name="property-mapping-with-the-windowsformshost-element"></a>Eigenschaftenzuordnung durch das WindowsFormsHost-Element  
 Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element übersetzt Standard [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften auf ihre [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Entsprechungen anhand der folgenden Übersetzungstabelle.  
  
|Hosten von Windows Presentation Foundation|Windows Forms|Verhalten bei der Interoperation|  
|---------------------------------------------|-------------------|-----------------------------|  
|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element legt die <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft des gehosteten Steuerelements und der <xref:System.Windows.Forms.Control.BackgroundImage%2A> Eigenschaft des gehosteten Steuerelements. Zuordnung erfolgt über die folgenden Regeln:<br /><br /> -If <xref:System.Windows.Controls.Control.Background%2A> ist eine Volltonfarbe er konvertiert und zum Festlegen der <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft des gehosteten Steuerelements. Die <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft ist nicht für das gehostete Steuerelement festgelegt, da das gehostete Steuerelement den Wert der erben kann die <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft. **Hinweis:** Transparenz das gehostete Steuerelement nicht unterstützt. Alle zugewiesenen Farben <xref:System.Windows.Forms.Control.BackColor%2A> muss vollständig deckend ist, mit der Alphawert 0xFF sein. <br /><br /> -If <xref:System.Windows.Controls.Control.Background%2A> ist keine Volltonfarbe aus der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement erstellt eine Bitmap aus der <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft. Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Steuerelement ordnet diese Bitmap der <xref:System.Windows.Forms.Control.BackgroundImage%2A> Eigenschaft des gehosteten Steuerelements. Dies bietet einen Effekt der Transparenz ähnelt. **Hinweis:** können Sie dieses Verhalten überschreiben, oder entfernen Sie die <xref:System.Windows.Controls.Control.Background%2A> eigenschaftenzuordnung.|  
|<xref:System.Windows.FrameworkElement.Cursor%2A>|<xref:System.Windows.Forms.Control.Cursor%2A>|Wenn die standardzuordnung nicht zugewiesen wurde, <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement seine Vorgänger Hierarchie durchläuft, bis er einen Vorgänger mit findet die <xref:System.Windows.FrameworkElement.Cursor%2A> Eigenschaftensatz. Dieser Wert wird in der nächsten entsprechenden übersetzt [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Cursor.<br /><br /> Wenn die standardzuordnung für die <xref:System.Windows.FrameworkElement.ForceCursor%2A> Eigenschaft wurde nicht zugewiesen wurden, Durchlauf beendet wird, auf den ersten Vorgänger mit <xref:System.Windows.FrameworkElement.ForceCursor%2A> festgelegt `true`.|  
|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FlowDirection.LeftToRight> wird <xref:System.Windows.Forms.RightToLeft.No> zugeordnet.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft> wird <xref:System.Windows.Forms.RightToLeft.Yes> zugeordnet.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Inherit>ist nicht zugeordnet.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> wird <xref:System.Windows.Forms.RightToLeft.Yes?displayProperty=nameWithType> zugeordnet.|  
|<xref:System.Windows.Controls.Control.FontStyle%2A>|<xref:System.Drawing.Font.Style%2A>im gehosteten Steuerelement<xref:System.Drawing.Font?displayProperty=nameWithType>|Der Satz von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften übersetzt in ein entsprechendes <xref:System.Drawing.Font>. Wenn eine dieser Eigenschaften geändert wird, ein neues <xref:System.Drawing.Font> wird erstellt. Für <xref:System.Windows.FontStyles.Normal%2A>: <xref:System.Drawing.FontStyle.Italic> ist deaktiviert. Für <xref:System.Windows.FontStyles.Italic%2A> oder <xref:System.Windows.FontStyles.Oblique%2A>: <xref:System.Drawing.FontStyle.Italic> aktiviert ist.|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Drawing.Font.Style%2A>im gehosteten Steuerelement<xref:System.Drawing.Font?displayProperty=nameWithType>|Der Satz von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften übersetzt in ein entsprechendes <xref:System.Drawing.Font>. Wenn eine dieser Eigenschaften geändert wird, ein neues <xref:System.Drawing.Font> wird erstellt. Für <xref:System.Windows.FontWeights.Black%2A>, <xref:System.Windows.FontWeights.Bold%2A>, <xref:System.Windows.FontWeights.DemiBold%2A>, <xref:System.Windows.FontWeights.ExtraBold%2A>, <xref:System.Windows.FontWeights.Heavy%2A>, <xref:System.Windows.FontWeights.Medium%2A>, <xref:System.Windows.FontWeights.SemiBold%2A>, oder <xref:System.Windows.FontWeights.UltraBold%2A>: <xref:System.Drawing.FontStyle.Bold> aktiviert ist. Für <xref:System.Windows.FontWeights.ExtraLight%2A>, <xref:System.Windows.FontWeights.Light%2A>, <xref:System.Windows.FontWeights.Normal%2A>, <xref:System.Windows.FontWeights.Regular%2A>, <xref:System.Windows.FontWeights.Thin%2A>, oder <xref:System.Windows.FontWeights.UltraLight%2A>: <xref:System.Drawing.FontStyle.Bold> ist deaktiviert.|  
|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|Der Satz von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften übersetzt in ein entsprechendes <xref:System.Drawing.Font>. Wenn eine dieser Eigenschaften geändert wird, ein neues <xref:System.Drawing.Font> wird erstellt. Das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ändert die Größe basierend auf der Größe der Schriftart zu steuern.<br /><br /> Schriftgrad in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wird als eine 90-sechsten Zoll und in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] als ein zweiundsiebzigstel Zoll. Die entsprechende Konvertierung ist:<br /><br /> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]Schriftgrad = [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Schriftgrad * 72,0 / 96,0.|  
|<xref:System.Windows.Controls.Control.Foreground%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.ForeColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|Die <xref:System.Windows.Controls.Control.Foreground%2A> eigenschaftenzuordnung erfolgt über die folgenden Regeln:<br /><br /> -If <xref:System.Windows.Controls.Control.Foreground%2A> ist ein <xref:System.Windows.Media.SolidColorBrush>, verwenden Sie <xref:System.Windows.Media.SolidColorBrush.Color%2A> für <xref:System.Windows.Forms.Control.ForeColor%2A>.<br />-If <xref:System.Windows.Controls.Control.Foreground%2A> ist ein <xref:System.Windows.Media.GradientBrush>, verwenden Sie die Farbe von der <xref:System.Windows.Media.GradientStop> mit den niedrigsten Offsetwert für <xref:System.Windows.Forms.Control.ForeColor%2A>.<br />– Für alle anderen <xref:System.Windows.Media.Brush> eingeben, lassen Sie <xref:System.Windows.Forms.Control.ForeColor%2A> unverändert. Dies bedeutet, dass der Standardwert verwendet wird.|  
|<xref:System.Windows.UIElement.IsEnabled%2A>|<xref:System.Windows.Forms.Control.Enabled%2A>|Wenn <xref:System.Windows.UIElement.IsEnabled%2A> festgelegt ist, <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element legt die <xref:System.Windows.Forms.Control.Enabled%2A> Eigenschaft des gehosteten Steuerelements.|  
|<xref:System.Windows.Controls.Control.Padding%2A>|<xref:System.Windows.Forms.Control.Padding%2A>|Alle vier Werte von der <xref:System.Windows.Forms.Control.Padding%2A> -Eigenschaft für das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement werden festgelegt, auf den gleichen <xref:System.Windows.Thickness> Wert.<br /><br /> -Werte größer als <xref:System.Int32.MaxValue> festgelegt <xref:System.Int32.MaxValue>.<br />-Werte kleiner als <xref:System.Int32.MinValue> festgelegt <xref:System.Int32.MinValue>.|  
|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Control.Visible%2A>|-   <xref:System.Windows.Visibility.Visible>Ordnet <xref:System.Windows.Forms.Control.Visible%2A>  =  `true`. Das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement sichtbar ist. Das explizite Festlegen der <xref:System.Windows.Forms.Control.Visible%2A> -Eigenschaft für das gehostete Steuerelement `false` wird nicht empfohlen.<br />-   <xref:System.Windows.Visibility.Collapsed>Ordnet <xref:System.Windows.Forms.Control.Visible%2A>  =  `true` oder `false`. Das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement nicht gezeichnet wird, und der Bereich wird reduziert.<br />-   <xref:System.Windows.Visibility.Hidden>: Vom gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement belegt Speicherplatz im Layout, jedoch nicht sichtbar ist. In diesem Fall die <xref:System.Windows.Forms.Control.Visible%2A> -Eigenschaftensatz auf `true`. Das explizite Festlegen der <xref:System.Windows.Forms.Control.Visible%2A> -Eigenschaft für das gehostete Steuerelement `false` wird nicht empfohlen.|  
  
 Angefügte Eigenschaften auf Containerelemente werden vollständig unterstützt, indem Sie die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element.  
  
 Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem WindowsFormsHost-Element](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-windowsformshost-element.md).  
  
## <a name="updates-to-parent-properties"></a>Updates für die Eigenschaften des übergeordneten  
 Die meisten Eigenschaften des übergeordneten Änderungen bewirken, dass Benachrichtigungen an das gehostete untergeordnete Steuerelement. Die folgende Liste beschreibt die Eigenschaften, die keine Benachrichtigungen verursachen, wenn deren Werte zu ändern.  
  
-   <xref:System.Windows.Controls.Control.Background%2A>  
  
-   <xref:System.Windows.FrameworkElement.Cursor%2A>  
  
-   <xref:System.Windows.FrameworkElement.ForceCursor%2A>  
  
-   <xref:System.Windows.UIElement.Visibility%2A>  
  
 Z. B., wenn Sie den Wert ändern die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element, das <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft des gehosteten Steuerelements ändert sich nicht.  
  
## <a name="property-mapping-with-the-elementhost-control"></a>Eigenschaftenzuordnung mit dem ElementHost-Steuerelement  
 Die folgenden Eigenschaften stellen integrierte änderungsbenachrichtigung bereit. Rufen Sie nicht die <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> Methode, wenn Sie diese Eigenschaften zuordnen:  
  
-   AutoSize  
  
-   Hintergrundfarbe  
  
-   BackgroundImage  
  
-   BackgroundImageLayout  
  
-   BindingContext  
  
-   CausesValidation  
  
-   ContextMenu  
  
-   ContextMenuStrip  
  
-   Cursor  
  
-   Andocken  
  
-   Aktiviert  
  
-   Schriftart  
  
-   Vordergrundfarbe  
  
-   Speicherort  
  
-   Margin  
  
-   Textabstand  
  
-   Übergeordnetes Element  
  
-   Region  
  
-   RightToLeft  
  
-   Größe  
  
-   TabIndex  
  
-   TabStop  
  
-   Text  
  
-   Visible  
  
 Die <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement übersetzt Standard [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Eigenschaften auf ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Entsprechungen mithilfe der folgenden Übersetzungstabelle.  
  
 Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mithilfe der ElementHost-Steuerelement](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-elementhost-control.md).  
  
|Hosten von Windows Forms|Windows Presentation Foundation|Verhalten bei der Interoperation|  
|---------------------------|-------------------------------------|-----------------------------|  
|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) für das gehostete Element|Durch Festlegen dieser Eigenschaft erzwingt das Neuzeichnen mit einem <xref:System.Windows.Media.ImageBrush>. Wenn der <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> -Eigenschaftensatz auf `false` (Standardwert), dies <xref:System.Windows.Media.ImageBrush> basiert auf die Darstellung der der <xref:System.Windows.Forms.Integration.ElementHost> zu steuern, einschließlich seiner <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> Eigenschaften und alle angefügten Paint Handler.<br /><br /> Wenn die <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> -Eigenschaftensatz auf `true`, die <xref:System.Windows.Media.ImageBrush> basiert auf das Aussehen von der <xref:System.Windows.Forms.Integration.ElementHost> übergeordnete Element des Steuerelements, einschließlich der übergeordneten <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> Eigenschaften und alle angefügten Paint Handler.|  
|<xref:System.Windows.Forms.Control.BackgroundImage%2A><br /><br /> (<xref:System.Drawing.Image?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) für das gehostete Element|Durch Festlegen dieser Eigenschaft führt dazu, dass das gleiche Verhalten beschrieben, für die <xref:System.Windows.Forms.Control.BackColor%2A> Zuordnung.|  
|<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) für das gehostete Element|Durch Festlegen dieser Eigenschaft führt dazu, dass das gleiche Verhalten beschrieben, für die <xref:System.Windows.Forms.Control.BackColor%2A> Zuordnung.|  
|<xref:System.Windows.Forms.Control.Cursor%2A><br /><br /> (<xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.Cursor%2A><br /><br /> (<xref:System.Windows.Input.Cursor?displayProperty=nameWithType>)|Die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] standard Cursor wird in den entsprechenden übersetzt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] standard Cursor. Wenn die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] handelt es sich nicht um ein standard Cursor die Standardpriorität zugewiesen ist.|  
|<xref:System.Windows.Forms.Control.Enabled%2A>|<xref:System.Windows.UIElement.IsEnabled%2A>|Wenn <xref:System.Windows.Forms.Control.Enabled%2A> festgelegt ist, die <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement legt die <xref:System.Windows.UIElement.IsEnabled%2A> Eigenschaft für das gehostete Element.|  
|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|Die <xref:System.Windows.Forms.Control.Font%2A> Wert wird in einer entsprechenden Reihe von übersetzt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Schriftarteigenschaften.|  
|<xref:System.Drawing.Font.Bold%2A>|<xref:System.Windows.Controls.Control.FontWeight%2A>für das gehostete element|Wenn<xref:System.Drawing.Font.Bold%2A> `true` ist, wird <xref:System.Windows.Controls.Control.FontWeight%2A> auf <xref:System.Windows.FontWeights.Bold%2A> festgelegt.<br /><br /> Wenn<xref:System.Drawing.Font.Bold%2A> `false` ist, wird <xref:System.Windows.Controls.Control.FontWeight%2A> auf <xref:System.Windows.FontWeights.Normal%2A> festgelegt.|  
|<xref:System.Drawing.Font.Italic%2A>|<xref:System.Windows.Controls.Control.FontStyle%2A>für das gehostete element|Wenn<xref:System.Drawing.Font.Italic%2A> `true` ist, wird <xref:System.Windows.Controls.Control.FontStyle%2A> auf <xref:System.Windows.FontStyles.Italic%2A> festgelegt.<br /><br /> Wenn<xref:System.Drawing.Font.Italic%2A> `false` ist, wird <xref:System.Windows.Controls.Control.FontStyle%2A> auf <xref:System.Windows.FontStyles.Normal%2A> festgelegt.|  
|<xref:System.Drawing.Font.Strikeout%2A>|<xref:System.Windows.TextDecorations>für das gehostete element|Gilt nur beim Hosten einer <xref:System.Windows.Controls.TextBlock> Steuerelement.|  
|<xref:System.Drawing.Font.Underline%2A>|<xref:System.Windows.TextDecorations>für das gehostete element|Gilt nur beim Hosten einer <xref:System.Windows.Controls.TextBlock> Steuerelement.|  
|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection>)|<xref:System.Windows.Forms.RightToLeft.No> wird <xref:System.Windows.FlowDirection.LeftToRight> zugeordnet.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Yes> wird <xref:System.Windows.FlowDirection.RightToLeft> zugeordnet.|  
|<xref:System.Windows.Forms.Control.Visible%2A>|<xref:System.Windows.UIElement.Visibility%2A>|Die <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement legt die <xref:System.Windows.UIElement.Visibility%2A> Eigenschaft für das gehostete Element mithilfe der folgenden Regeln:<br /><br /> -   <xref:System.Windows.Forms.Control.Visible%2A> = `true`Ordnet <xref:System.Windows.Visibility.Visible>.<br />-   <xref:System.Windows.Forms.Control.Visible%2A> = `false`Ordnet <xref:System.Windows.Visibility.Hidden>.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Interaktion zwischen WPF und Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [Interaktion zwischen WPF und Windows Forms](../../../../docs/framework/wpf/advanced/wpf-and-windows-forms-interoperation.md)  
 [Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem WindowsFormsHost-Element](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-windowsformshost-element.md)  
 [Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem ElementHost-Steuerelement](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-elementhost-control.md)
