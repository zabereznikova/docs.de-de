---
title: Eigenschaftenzuordnung von Windows Forms und WPF
ms.date: 03/30/2017
helpviewer_keywords:
- property mapping [WPF interoperability]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 999d8298-9c04-467d-a453-86e41002057d
ms.openlocfilehash: a7d78837a141ed322da42629501cee6dcc9143e1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053131"
---
# <a name="windows-forms-and-wpf-property-mapping"></a>Eigenschaftenzuordnung von Windows Forms und WPF
Die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Technologien verfügen über zwei ähnliche, aber unterschiedliche Eigenschaft Modelle. *Eigenschaftenzuordnung* unterstützt die Interoperation zwischen beiden Architekturen und bietet die folgenden Funktionen:  
  
- Erleichtert die relevante eigenschaftsänderungen in der hostumgebung das gehostete Steuerelement oder Element zuzuordnen.  
  
- Stellt Klassenbehandlung für das Zuordnen der am häufigsten standardmäßig Eigenschaften verwendet.  
  
- Ermöglicht einfaches entfernen, überschreiben oder Erweitern von Eigenschaften an.  
  
- Stellt sicher, dass der Eigenschaftswert ändert auf dem Host automatisch erkannt und in das gehostete Steuerelement oder Element übersetzt.  
  
> [!NOTE]
>  Eigenschaftenänderungsereignisse werden die hosting-Steuerelement oder die Hierarchie der Elemente nicht weitergegeben. Eigenschaft Übersetzung wird nicht ausgeführt werden, wenn Sie der lokale Wert einer Eigenschaft nicht ändert, aufgrund der direkten Einstellung, Stile, Vererbung, die Datenbindung oder andere Mechanismen, die den Wert der Eigenschaft zu ändern.  
  
 Verwenden der <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> Eigenschaft für die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element und die <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> Eigenschaft <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement eigenschaftenzuordnung auf.  
  
## <a name="property-mapping-with-the-windowsformshost-element"></a>Zuordnung der Eigenschaft mit dem WindowsFormsHost-Element  
 Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element übersetzt Standard [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften, die ihre [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Entsprechungen mithilfe der folgenden Übersetzungstabelle.  
  
|Hosten von Windows Presentation Foundation|Windows Forms|Interoperations-Verhalten|  
|---------------------------------------------|-------------------|-----------------------------|  
|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elementgruppen die <xref:System.Windows.Forms.Control.BackColor%2A> -Eigenschaft des gehosteten Steuerelements und dem <xref:System.Windows.Forms.Control.BackgroundImage%2A> -Eigenschaft des gehosteten Steuerelements. Zuordnung erfolgt über die folgenden Regeln:<br /><br /> -If <xref:System.Windows.Controls.Control.Background%2A> ist eine Volltonfarbe, er konvertiert und zum Festlegen der <xref:System.Windows.Forms.Control.BackColor%2A> -Eigenschaft des gehosteten Steuerelements. Die <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft ist nicht für das gehostete Steuerelement festgelegt, da das gehostete Steuerelement den Wert der erben kann die <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft. **Hinweis**:  Das gehostete Steuerelement unterstützt keine Transparenz. Farbe zugewiesen <xref:System.Windows.Forms.Control.BackColor%2A> muss vollständig deckend ist, mit einem Alphawert von 0xFF sein. <br /><br /> -If <xref:System.Windows.Controls.Control.Background%2A> ist keine Volltonfarbe, die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement erstellt eine Bitmap aus der <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft. Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Steuerelement ordnet diese Bitmap, die <xref:System.Windows.Forms.Control.BackgroundImage%2A> -Eigenschaft des gehosteten Steuerelements. Dies bietet einen Effekt aus der Transparenz ähnelt. **Hinweis**:  Sie können dieses Verhalten überschreiben, oder Sie entfernen die <xref:System.Windows.Controls.Control.Background%2A> eigenschaftenzuordnung.|  
|<xref:System.Windows.FrameworkElement.Cursor%2A>|<xref:System.Windows.Forms.Control.Cursor%2A>|Wenn die standardzuordnung nicht zugewiesen wurde, <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement seiner übergeordneten Hierarchie durchsucht, bis er einen Vorgänger mit findet die <xref:System.Windows.FrameworkElement.Cursor%2A> Eigenschaftensatz. Dieser Wert wird in der nächsten entsprechenden übersetzt [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Cursor.<br /><br /> Wenn die standardzuordnung für die <xref:System.Windows.FrameworkElement.ForceCursor%2A> Eigenschaft wurde nicht neu zugewiesen wurde, der Traversierung beendet wird, auf den ersten Vorgänger mit <xref:System.Windows.FrameworkElement.ForceCursor%2A> festgelegt `true`.|  
|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FlowDirection.LeftToRight> Ordnet <xref:System.Windows.Forms.RightToLeft.No>.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft> Ordnet <xref:System.Windows.Forms.RightToLeft.Yes>.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Inherit> ist nicht zugeordnet.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> Ordnet <xref:System.Windows.Forms.RightToLeft.Yes?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.Control.FontStyle%2A>|<xref:System.Drawing.Font.Style%2A> für des gehosteten Steuerelements <xref:System.Drawing.Font?displayProperty=nameWithType>|Der Satz von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften in eine entsprechende übersetzt <xref:System.Drawing.Font>. Wenn eine dieser Eigenschaften geändert wird, ein neues <xref:System.Drawing.Font> erstellt wird. Für <xref:System.Windows.FontStyles.Normal%2A>: <xref:System.Drawing.FontStyle.Italic> ist deaktiviert. Für <xref:System.Windows.FontStyles.Italic%2A> oder <xref:System.Windows.FontStyles.Oblique%2A>: <xref:System.Drawing.FontStyle.Italic> aktiviert ist.|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Drawing.Font.Style%2A> für des gehosteten Steuerelements <xref:System.Drawing.Font?displayProperty=nameWithType>|Der Satz von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften in eine entsprechende übersetzt <xref:System.Drawing.Font>. Wenn eine dieser Eigenschaften geändert wird, ein neues <xref:System.Drawing.Font> erstellt wird. Für <xref:System.Windows.FontWeights.Black%2A>, <xref:System.Windows.FontWeights.Bold%2A>, <xref:System.Windows.FontWeights.DemiBold%2A>, <xref:System.Windows.FontWeights.ExtraBold%2A>, <xref:System.Windows.FontWeights.Heavy%2A>, <xref:System.Windows.FontWeights.Medium%2A>, <xref:System.Windows.FontWeights.SemiBold%2A>, oder <xref:System.Windows.FontWeights.UltraBold%2A>: <xref:System.Drawing.FontStyle.Bold> aktiviert ist. Für <xref:System.Windows.FontWeights.ExtraLight%2A>, <xref:System.Windows.FontWeights.Light%2A>, <xref:System.Windows.FontWeights.Normal%2A>, <xref:System.Windows.FontWeights.Regular%2A>, <xref:System.Windows.FontWeights.Thin%2A>, oder <xref:System.Windows.FontWeights.UltraLight%2A>: <xref:System.Drawing.FontStyle.Bold> ist deaktiviert.|  
|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|Der Satz von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften in eine entsprechende übersetzt <xref:System.Drawing.Font>. Wenn eine dieser Eigenschaften geändert wird, ein neues <xref:System.Drawing.Font> erstellt wird. Das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Steuerelements geändert wird, die basierend auf der Größe der Schriftart.<br /><br /> Schriftgrad in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wird als eine 90-sechsten Zoll und in ausgedrückt [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] als eine 70-Sekunde Zoll. Die entsprechende Konvertierung ist:<br /><br /> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Schriftgrad = [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Schriftgrad * 72,0 / 96,0.|  
|<xref:System.Windows.Controls.Control.Foreground%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.ForeColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|Die <xref:System.Windows.Controls.Control.Foreground%2A> eigenschaftenzuordnung erfolgt über die folgenden Regeln:<br /><br /> -If <xref:System.Windows.Controls.Control.Foreground%2A> ist eine <xref:System.Windows.Media.SolidColorBrush>, verwenden Sie <xref:System.Windows.Media.SolidColorBrush.Color%2A> für <xref:System.Windows.Forms.Control.ForeColor%2A>.<br />-If <xref:System.Windows.Controls.Control.Foreground%2A> ist eine <xref:System.Windows.Media.GradientBrush>, verwenden Sie die Farbe von der <xref:System.Windows.Media.GradientStop> mit dem niedrigsten Offsetwert für <xref:System.Windows.Forms.Control.ForeColor%2A>.<br />– Für alle anderen <xref:System.Windows.Media.Brush> eingeben, lassen Sie <xref:System.Windows.Forms.Control.ForeColor%2A> unverändert. Dies bedeutet, dass der Standardwert verwendet wird.|  
|<xref:System.Windows.UIElement.IsEnabled%2A>|<xref:System.Windows.Forms.Control.Enabled%2A>|Wenn <xref:System.Windows.UIElement.IsEnabled%2A> festgelegt ist, <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elementgruppen die <xref:System.Windows.Forms.Control.Enabled%2A> Eigenschaft für das gehostete Steuerelement.|  
|<xref:System.Windows.Controls.Control.Padding%2A>|<xref:System.Windows.Forms.Control.Padding%2A>|Alle vier Werte von der <xref:System.Windows.Forms.Control.Padding%2A> -Eigenschaft für das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Kontrollnummer auf den gleichen <xref:System.Windows.Thickness> Wert.<br /><br /> -Werte größer als <xref:System.Int32.MaxValue> festgelegt <xref:System.Int32.MaxValue>.<br />-Werte kleiner als <xref:System.Int32.MinValue> festgelegt <xref:System.Int32.MinValue>.|  
|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Control.Visible%2A>|-   <xref:System.Windows.Visibility.Visible> Ordnet <xref:System.Windows.Forms.Control.Visible%2A>  =  `true`. Das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Steuerelement sichtbar ist. Explizites Festlegen der <xref:System.Windows.Forms.Control.Visible%2A> Eigenschaft für das gehostete Steuerelement `false` wird nicht empfohlen.<br />-   <xref:System.Windows.Visibility.Collapsed> Ordnet <xref:System.Windows.Forms.Control.Visible%2A>  =  `true` oder `false`. Das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Steuerelement wird nicht gezeichnet, und der Bereich wird reduziert.<br />-   <xref:System.Windows.Visibility.Hidden> : Das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement Platz im Layout belegt, jedoch nicht sichtbar ist. In diesem Fall die <xref:System.Windows.Forms.Control.Visible%2A> -Eigenschaftensatz auf `true`. Explizites Festlegen der <xref:System.Windows.Forms.Control.Visible%2A> Eigenschaft für das gehostete Steuerelement `false` wird nicht empfohlen.|  
  
 Angefügte Eigenschaften auf Container-Elemente werden vollständig unterstützt, indem die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element.  
  
 Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem WindowsFormsHost-Element](walkthrough-mapping-properties-using-the-windowsformshost-element.md).  
  
## <a name="updates-to-parent-properties"></a>Updates für die Eigenschaften für übergeordnetes Element  
 Die meisten Eigenschaften der übergeordneten Änderungen bewirken, dass Benachrichtigungen an das gehostete untergeordnete Steuerelement. Die folgende Liste beschreibt die Eigenschaften, die keine Benachrichtigungen verursachen, wenn sich ihre Werte ändern.  
  
- <xref:System.Windows.Controls.Control.Background%2A>  
  
- <xref:System.Windows.FrameworkElement.Cursor%2A>  
  
- <xref:System.Windows.FrameworkElement.ForceCursor%2A>  
  
- <xref:System.Windows.UIElement.Visibility%2A>  
  
 Angenommen, Sie ändern, dass den Wert des der <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft der <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element, das <xref:System.Windows.Forms.Control.BackColor%2A> -Eigenschaft des gehosteten Steuerelements nicht geändert.  
  
## <a name="property-mapping-with-the-elementhost-control"></a>Zuordnung der Eigenschaft mit dem ElementHost-Steuerelement  
 Die folgenden Eigenschaften bieten integrierte änderungsbenachrichtigungen. Rufen Sie nicht die <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> Methode, wenn Sie diese Eigenschaften zuordnen:  
  
- AutoSize  
  
- BackColor  
  
- BackgroundImage  
  
- BackgroundImageLayout  
  
- BindingContext  
  
- CausesValidation  
  
- ContextMenu  
  
- ContextMenuStrip  
  
- Cursor  
  
- Andocken  
  
- Aktiviert  
  
- Schriftart  
  
- ForeColor  
  
- Speicherort  
  
- Rand  
  
- Abstand  
  
- Übergeordnetes Element  
  
- Region  
  
- RightToLeft  
  
- Größe  
  
- TabIndex  
  
- TabStop  
  
- Text  
  
- Sichtbar  
  
 Die <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement übersetzt Standard [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Eigenschaften, die ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Entsprechungen mithilfe der folgenden Übersetzungstabelle.  
  
 Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem ElementHost-Steuerelement](walkthrough-mapping-properties-using-the-elementhost-control.md).  
  
|Hosten von Windows Forms|Windows Presentation Foundation|Interoperations-Verhalten|  
|---------------------------|-------------------------------------|-----------------------------|  
|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) für das gehostete Element|Durch Festlegen dieser Eigenschaft erzwingt das Neuzeichnen mit einer <xref:System.Windows.Media.ImageBrush>. Wenn die <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> -Eigenschaftensatz auf `false` (der Standardwert), dies <xref:System.Windows.Media.ImageBrush> basiert darauf, dass die Darstellung von der <xref:System.Windows.Forms.Integration.ElementHost> zu steuern, einschließlich der <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> Eigenschaften und alle angefügten Paint Handler.<br /><br /> Wenn die <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> -Eigenschaftensatz auf `true`, <xref:System.Windows.Media.ImageBrush> basiert darauf, dass die Darstellung von der <xref:System.Windows.Forms.Integration.ElementHost> übergeordnete Element des Steuerelements, einschließlich des übergeordneten Elements <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> Eigenschaften und alle angefügten Paint Handler.|  
|<xref:System.Windows.Forms.Control.BackgroundImage%2A><br /><br /> (<xref:System.Drawing.Image?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) für das gehostete Element|Durch Festlegen dieser Eigenschaft führt dazu, dass das gleiche Verhalten beschrieben, für die <xref:System.Windows.Forms.Control.BackColor%2A> Zuordnung.|  
|<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) für das gehostete Element|Durch Festlegen dieser Eigenschaft führt dazu, dass das gleiche Verhalten beschrieben, für die <xref:System.Windows.Forms.Control.BackColor%2A> Zuordnung.|  
|<xref:System.Windows.Forms.Control.Cursor%2A><br /><br /> (<xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.Cursor%2A><br /><br /> (<xref:System.Windows.Input.Cursor?displayProperty=nameWithType>)|Die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] standard Cursor wird in der entsprechenden übersetzt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] standard Cursor. Wenn die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Standardcursor ist, ist die Standardpriorität zugewiesen ist.|  
|<xref:System.Windows.Forms.Control.Enabled%2A>|<xref:System.Windows.UIElement.IsEnabled%2A>|Wenn <xref:System.Windows.Forms.Control.Enabled%2A> festgelegt ist, wird die <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement legt die <xref:System.Windows.UIElement.IsEnabled%2A> Eigenschaft für das gehostete Element.|  
|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|Die <xref:System.Windows.Forms.Control.Font%2A> Wert wird in einen entsprechenden Satz von übersetzt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Schriftarteigenschaften.|  
|<xref:System.Drawing.Font.Bold%2A>|<xref:System.Windows.Controls.Control.FontWeight%2A> für das gehostete element|Wenn<xref:System.Drawing.Font.Bold%2A>`true` ist, wird <xref:System.Windows.Controls.Control.FontWeight%2A> auf <xref:System.Windows.FontWeights.Bold%2A> festgelegt.<br /><br /> Wenn<xref:System.Drawing.Font.Bold%2A>`false` ist, wird <xref:System.Windows.Controls.Control.FontWeight%2A> auf <xref:System.Windows.FontWeights.Normal%2A> festgelegt.|  
|<xref:System.Drawing.Font.Italic%2A>|<xref:System.Windows.Controls.Control.FontStyle%2A> für das gehostete element|Wenn<xref:System.Drawing.Font.Italic%2A>`true` ist, wird <xref:System.Windows.Controls.Control.FontStyle%2A> auf <xref:System.Windows.FontStyles.Italic%2A> festgelegt.<br /><br /> Wenn<xref:System.Drawing.Font.Italic%2A>`false` ist, wird <xref:System.Windows.Controls.Control.FontStyle%2A> auf <xref:System.Windows.FontStyles.Normal%2A> festgelegt.|  
|<xref:System.Drawing.Font.Strikeout%2A>|<xref:System.Windows.TextDecorations> für das gehostete element|Gilt nur beim Hosten einer <xref:System.Windows.Controls.TextBlock> Steuerelement.|  
|<xref:System.Drawing.Font.Underline%2A>|<xref:System.Windows.TextDecorations> für das gehostete element|Gilt nur beim Hosten einer <xref:System.Windows.Controls.TextBlock> Steuerelement.|  
|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection>)|<xref:System.Windows.Forms.RightToLeft.No> Ordnet <xref:System.Windows.FlowDirection.LeftToRight>.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Yes> Ordnet <xref:System.Windows.FlowDirection.RightToLeft>.|  
|<xref:System.Windows.Forms.Control.Visible%2A>|<xref:System.Windows.UIElement.Visibility%2A>|Die <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement legt die <xref:System.Windows.UIElement.Visibility%2A> Eigenschaft für das gehostete Element mithilfe der folgenden Regeln:<br /><br /> -   <xref:System.Windows.Forms.Control.Visible%2A> = `true` Ordnet <xref:System.Windows.Visibility.Visible>.<br />-   <xref:System.Windows.Forms.Control.Visible%2A> = `false` Ordnet <xref:System.Windows.Visibility.Hidden>.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Interaktion zwischen WPF und Win32](wpf-and-win32-interoperation.md)
- [Interaktion zwischen WPF und Windows Forms](wpf-and-windows-forms-interoperation.md)
- [Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem WindowsFormsHost-Element](walkthrough-mapping-properties-using-the-windowsformshost-element.md)
- [Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem ElementHost-Steuerelement](walkthrough-mapping-properties-using-the-elementhost-control.md)
