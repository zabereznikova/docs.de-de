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
ms.openlocfilehash: ae4a97bc96a4f9e93942b4995f488c427fda3134
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917503"
---
# <a name="windows-forms-and-wpf-property-mapping"></a>Eigenschaftenzuordnung von Windows Forms und WPF
Die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] - [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und-Technologien verfügen über zwei ähnliche, aber unterschiedliche Eigenschaften Modelle. Die *Eigenschaften Zuordnung* unterstützt die Interoperation zwischen den beiden Architekturen und bietet die folgenden Funktionen:  
  
- Macht es einfach, relevante Eigenschaften Änderungen in der Host Umgebung dem gehosteten Steuerelement oder Element zuzuordnen.  
  
- Stellt die Standardbehandlung für die Zuordnung der am häufigsten verwendeten Eigenschaften bereit.  
  
- Ermöglicht das einfache entfernen, überschreiben oder Erweitern von Standardeigenschaften.  
  
- Stellt sicher, dass Eigenschafts Wertänderungen auf dem Host automatisch erkannt und in das gehostete Steuerelement oder Element übersetzt werden.  
  
> [!NOTE]
> Eigenschaften Änderungs Ereignisse werden nicht im Hostingsteuerelement oder in der Element Hierarchie nach oben weitergegeben. Die Eigenschaften Übersetzung wird nicht ausgeführt, wenn sich der lokale Wert einer Eigenschaft aufgrund direkter Einstellung, Stile, Vererbung, Datenbindung oder anderer Mechanismen, die den Wert der Eigenschaft ändern, nicht ändert.  
  
 Verwenden Sie <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> die-Eigenschaft <xref:System.Windows.Forms.Integration.WindowsFormsHost> des- <xref:System.Windows.Forms.Integration.ElementHost> Elements <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> und die-Eigenschaft des-Steuer Elements, um auf die Eigenschaften Zuordnung zuzugreifen  
  
## <a name="property-mapping-with-the-windowsformshost-element"></a>Eigenschaften Zuordnung mit dem WindowsFormsHost-Element  
 Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element übersetzt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Standardeigenschaften mithilfe [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] der folgenden Übersetzungstabelle in ihre Entsprechungen.  
  
|Windows Presentation Foundation Hosting|Windows Forms|Interoperation-Verhalten|  
|---------------------------------------------|-------------------|-----------------------------|  
|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element legt <xref:System.Windows.Forms.Control.BackColor%2A> die-Eigenschaft des gehosteten- <xref:System.Windows.Forms.Control.BackgroundImage%2A> Steuer Elements und die-Eigenschaft des gehosteten Steuer Elements fest. Die Zuordnung erfolgt mithilfe der folgenden Regeln:<br /><br /> Wenn <xref:System.Windows.Controls.Control.Background%2A> eine voll Tonfarbe ist, wird Sie konvertiert und zum Festlegen der <xref:System.Windows.Forms.Control.BackColor%2A> -Eigenschaft des gehosteten Steuer Elements verwendet. Die <xref:System.Windows.Forms.Control.BackColor%2A> -Eigenschaft ist für das gehostete Steuerelement nicht festgelegt, da das gehostete Steuerelement <xref:System.Windows.Forms.Control.BackColor%2A> den Wert der-Eigenschaft erben kann. **Hinweis**:  Das gehostete Steuerelement unterstützt keine Transparenz. Jede Farbe, die <xref:System.Windows.Forms.Control.BackColor%2A> zugewiesen ist, muss vollständig deckend sein, mit einem Alpha-Wert von 0xFF. <br /><br /> Wenn <xref:System.Windows.Controls.Control.Background%2A> keine voll Tonfarbe ist, erstellt das <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Steuerelement eine Bitmap aus <xref:System.Windows.Controls.Control.Background%2A> der-Eigenschaft. Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Steuerelement weist diese Bitmap <xref:System.Windows.Forms.Control.BackgroundImage%2A> der-Eigenschaft des gehosteten Steuer Elements zu. Dies bietet eine ähnliche Wirkung wie Transparenz. **Hinweis**:  Sie können dieses Verhalten außer Kraft setzen, oder Sie <xref:System.Windows.Controls.Control.Background%2A> können die Eigenschaften Zuordnung entfernen.|  
|<xref:System.Windows.FrameworkElement.Cursor%2A>|<xref:System.Windows.Forms.Control.Cursor%2A>|Wenn die Standard Zuordnung nicht neu zugewiesen wurde, wird <xref:System.Windows.Forms.Integration.WindowsFormsHost> die übergeordnete Hierarchie durch das Steuerelement durchlaufen, bis <xref:System.Windows.FrameworkElement.Cursor%2A> ein Vorgänger gefunden wird, dessen-Eigenschaft festgelegt ist. Dieser Wert wird in den nächstgelegenen entsprechenden [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Cursor übersetzt.<br /><br /> Wenn die Standard Zuordnung für die <xref:System.Windows.FrameworkElement.ForceCursor%2A> Eigenschaft nicht neu zugewiesen wurde, wird der Durchlauf auf dem ersten Vorgänger beendet, wobei <xref:System.Windows.FrameworkElement.ForceCursor%2A> auf `true`festgelegt ist.|  
|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FlowDirection.LeftToRight>wird zugeordnet <xref:System.Windows.Forms.RightToLeft.No>.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft>wird zugeordnet <xref:System.Windows.Forms.RightToLeft.Yes>.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Inherit>ist nicht zugeordnet.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType>wird zugeordnet <xref:System.Windows.Forms.RightToLeft.Yes?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.Control.FontStyle%2A>|<xref:System.Drawing.Font.Style%2A>auf dem<xref:System.Drawing.Font?displayProperty=nameWithType>|Der Satz von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften wird in ein entsprechendes <xref:System.Drawing.Font>übersetzt. Wenn eine dieser Eigenschaften geändert wird, wird ein <xref:System.Drawing.Font> neuer erstellt. Für <xref:System.Windows.FontStyles.Normal%2A> :<xref:System.Drawing.FontStyle.Italic> ist deaktiviert. Für <xref:System.Windows.FontStyles.Italic%2A> oder <xref:System.Windows.FontStyles.Oblique%2A> :<xref:System.Drawing.FontStyle.Italic> ist aktiviert.|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Drawing.Font.Style%2A>auf dem<xref:System.Drawing.Font?displayProperty=nameWithType>|Der Satz von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften wird in ein entsprechendes <xref:System.Drawing.Font>übersetzt. Wenn eine dieser Eigenschaften geändert wird, wird ein <xref:System.Drawing.Font> neuer erstellt. For <xref:System.Windows.FontWeights.Black%2A>, <xref:System.Windows.FontWeights.Bold%2A>, ,<xref:System.Windows.FontWeights.DemiBold%2A> ,<xref:System.Windows.FontWeights.Heavy%2A>, ,<xref:System.Windows.FontWeights.SemiBold%2A>oder: istaktiviert<xref:System.Drawing.FontStyle.Bold> . <xref:System.Windows.FontWeights.ExtraBold%2A> <xref:System.Windows.FontWeights.Medium%2A> <xref:System.Windows.FontWeights.UltraBold%2A> For <xref:System.Windows.FontWeights.ExtraLight%2A>, <xref:System.Windows.FontWeights.Light%2A>, ,<xref:System.Windows.FontWeights.Normal%2A> ,oder<xref:System.Windows.FontWeights.Thin%2A>: ist<xref:System.Drawing.FontStyle.Bold> deaktiviert. <xref:System.Windows.FontWeights.Regular%2A> <xref:System.Windows.FontWeights.UltraLight%2A>|  
|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|Der Satz von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften wird in ein entsprechendes <xref:System.Drawing.Font>übersetzt. Wenn eine dieser Eigenschaften geändert wird, wird ein <xref:System.Drawing.Font> neuer erstellt. Die Größe [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] des gehosteten Steuer Elements wird basierend auf dem Schrift Grad angepasst.<br /><br /> Der Schrift Grad [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in wird als ein neunstel eines Zoll und in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] als eine siebte Sekunde Zoll ausgedrückt. Die entsprechende Konvertierung lautet wie folgt:<br /><br /> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]Font size = [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Font Size * 72,0/96,0.|  
|<xref:System.Windows.Controls.Control.Foreground%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.ForeColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|Die <xref:System.Windows.Controls.Control.Foreground%2A> Eigenschaften Zuordnung wird mithilfe der folgenden Regeln durchgeführt:<br /><br /> -Wenn <xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Media.SolidColorBrush>ein ist, verwenden <xref:System.Windows.Media.SolidColorBrush.Color%2A> Sie <xref:System.Windows.Forms.Control.ForeColor%2A>für.<br />Wenn <xref:System.Windows.Controls.Control.Foreground%2A> ein <xref:System.Windows.Media.GradientBrush>ist, <xref:System.Windows.Forms.Control.ForeColor%2A>verwenden Sie die Farbe des mitdemniedrigstenOffsetWertfür.<xref:System.Windows.Media.GradientStop><br />-Lassen <xref:System.Windows.Media.Brush> <xref:System.Windows.Forms.Control.ForeColor%2A> Sie für jeden anderen Typ unverändert. Dies bedeutet, dass der Standardwert verwendet wird.|  
|<xref:System.Windows.UIElement.IsEnabled%2A>|<xref:System.Windows.Forms.Control.Enabled%2A>|Wenn <xref:System.Windows.UIElement.IsEnabled%2A> festgelegt ist <xref:System.Windows.Forms.Integration.WindowsFormsHost> , legt das <xref:System.Windows.Forms.Control.Enabled%2A> -Element die-Eigenschaft des gehosteten Steuer Elements fest.|  
|<xref:System.Windows.Controls.Control.Padding%2A>|<xref:System.Windows.Forms.Control.Padding%2A>|Alle vier Werte der <xref:System.Windows.Forms.Control.Padding%2A> -Eigenschaft für das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement werden auf denselben <xref:System.Windows.Thickness> Wert festgelegt.<br /><br /> -Werte größer als <xref:System.Int32.MaxValue> werden auf <xref:System.Int32.MaxValue>festgelegt.<br />-Werte kleiner als <xref:System.Int32.MinValue> werden auf <xref:System.Int32.MinValue>festgelegt.|  
|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Control.Visible%2A>|-   <xref:System.Windows.Visibility.Visible>wird zugeordnet <xref:System.Windows.Forms.Control.Visible%2A>.  =  `true` Das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement ist sichtbar. Das explizite Festlegen <xref:System.Windows.Forms.Control.Visible%2A> der-Eigenschaft für das gehostete Steuerelement auf `false` ist nicht empfehlenswert.<br />-   <xref:System.Windows.Visibility.Collapsed>wird oder <xref:System.Windows.Forms.Control.Visible%2A> zugeordnet`false`.  =  `true` Das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement wird nicht gezeichnet, und sein Bereich ist reduziert.<br />-   <xref:System.Windows.Visibility.Hidden> : Das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement belegt Platz im Layout, ist aber nicht sichtbar. In diesem Fall wird die <xref:System.Windows.Forms.Control.Visible%2A> -Eigenschaft auf `true`festgelegt. Das explizite Festlegen <xref:System.Windows.Forms.Control.Visible%2A> der-Eigenschaft für das gehostete Steuerelement auf `false` ist nicht empfehlenswert.|  
  
 Angefügte Eigenschaften für Container Elemente werden vom <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element vollständig unterstützt.  
  
 Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Mapping von Eigenschaften mit dem WindowsFormsHost](walkthrough-mapping-properties-using-the-windowsformshost-element.md)-Element.  
  
## <a name="updates-to-parent-properties"></a>Aktualisierungen von übergeordneten Eigenschaften  
 Änderungen an den meisten übergeordneten Eigenschaften verursachen Benachrichtigungen an das gehostete untergeordnete Steuerelement. In der folgenden Liste werden Eigenschaften beschrieben, die keine Benachrichtigungen verursachen, wenn sich die Werte ändern.  
  
- <xref:System.Windows.Controls.Control.Background%2A>  
  
- <xref:System.Windows.FrameworkElement.Cursor%2A>  
  
- <xref:System.Windows.FrameworkElement.ForceCursor%2A>  
  
- <xref:System.Windows.UIElement.Visibility%2A>  
  
 Wenn Sie z. b. den Wert der <xref:System.Windows.Controls.Control.Background%2A> -Eigenschaft <xref:System.Windows.Forms.Integration.WindowsFormsHost> des-Elements ändern, <xref:System.Windows.Forms.Control.BackColor%2A> wird die-Eigenschaft des gehosteten Steuer Elements nicht geändert.  
  
## <a name="property-mapping-with-the-elementhost-control"></a>Eigenschaften Zuordnung mit dem Element Host-Steuerelement  
 Die folgenden Eigenschaften stellen eine integrierte Änderungs Benachrichtigung bereit. Wenn Sie diese Eigenschaften <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> Mapping, dürfen Sie die-Methode nicht aufzurufen:  
  
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
  
- Enabled  
  
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
  
 Das <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] übersetzt Standardeigenschaften [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mithilfe der folgenden Übersetzungstabelle in ihre Entsprechungen.  
  
 Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Mapping von Eigenschaften mit dem Element Host-Steuer](walkthrough-mapping-properties-using-the-elementhost-control.md)Element.  
  
|Windows Forms Hosting|Windows Presentation Foundation|Interoperation-Verhalten|  
|---------------------------|-------------------------------------|-----------------------------|  
|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) für das gehostete Element|Wenn diese Eigenschaft festgelegt wird, wird ein <xref:System.Windows.Media.ImageBrush>Repaint mit einem erzwungen. Wenn die <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> -Eigenschaft auf `false` festgelegt ist (der Standardwert) <xref:System.Windows.Media.ImageBrush> , basiert dies auf <xref:System.Windows.Forms.Control.BackColor%2A>der Darstellung des <xref:System.Windows.Forms.Integration.ElementHost> Steuer Elements, einschließlich der <xref:System.Windows.Forms.Control.BackgroundImage%2A>Eigenschaften <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> ,, und angefügter Farben. Handler.<br /><br /> Wenn die <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> -Eigenschaft auf `true`festgelegt ist <xref:System.Windows.Media.ImageBrush> , basiert auf der Darstellung des über <xref:System.Windows.Forms.Integration.ElementHost> geordneten Elements des Steuer Elements, einschließlich der <xref:System.Windows.Forms.Control.BackColor%2A>Eigenschaften <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> ,, und angefügter Farben. Handler.|  
|<xref:System.Windows.Forms.Control.BackgroundImage%2A><br /><br /> (<xref:System.Drawing.Image?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) für das gehostete Element|Das Festlegen dieser Eigenschaft bewirkt das gleiche Verhalten, das <xref:System.Windows.Forms.Control.BackColor%2A> für die Zuordnung beschrieben wird.|  
|<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) für das gehostete Element|Das Festlegen dieser Eigenschaft bewirkt das gleiche Verhalten, das <xref:System.Windows.Forms.Control.BackColor%2A> für die Zuordnung beschrieben wird.|  
|<xref:System.Windows.Forms.Control.Cursor%2A><br /><br /> (<xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.Cursor%2A><br /><br /> (<xref:System.Windows.Input.Cursor?displayProperty=nameWithType>)|Der [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Standard Cursor wird in den entsprechenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Standard Cursor übersetzt. Wenn kein Standard Cursor ist,wirdderStandardwertzugewiesen.[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]|  
|<xref:System.Windows.Forms.Control.Enabled%2A>|<xref:System.Windows.UIElement.IsEnabled%2A>|Wenn <xref:System.Windows.Forms.Control.Enabled%2A> festgelegt ist, <xref:System.Windows.Forms.Integration.ElementHost> legt das- <xref:System.Windows.UIElement.IsEnabled%2A> Steuerelement die-Eigenschaft für das gehostete Element fest.|  
|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|Der <xref:System.Windows.Forms.Control.Font%2A> Wert wird in einen entsprechenden Satz von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Schriftart Eigenschaften übersetzt.|  
|<xref:System.Drawing.Font.Bold%2A>|<xref:System.Windows.Controls.Control.FontWeight%2A>on Hosted-Element|Wenn<xref:System.Drawing.Font.Bold%2A>`true` ist, wird <xref:System.Windows.Controls.Control.FontWeight%2A> auf <xref:System.Windows.FontWeights.Bold%2A> festgelegt.<br /><br /> Wenn<xref:System.Drawing.Font.Bold%2A>`false` ist, wird <xref:System.Windows.Controls.Control.FontWeight%2A> auf <xref:System.Windows.FontWeights.Normal%2A> festgelegt.|  
|<xref:System.Drawing.Font.Italic%2A>|<xref:System.Windows.Controls.Control.FontStyle%2A>on Hosted-Element|Wenn<xref:System.Drawing.Font.Italic%2A>`true` ist, wird <xref:System.Windows.Controls.Control.FontStyle%2A> auf <xref:System.Windows.FontStyles.Italic%2A> festgelegt.<br /><br /> Wenn<xref:System.Drawing.Font.Italic%2A>`false` ist, wird <xref:System.Windows.Controls.Control.FontStyle%2A> auf <xref:System.Windows.FontStyles.Normal%2A> festgelegt.|  
|<xref:System.Drawing.Font.Strikeout%2A>|<xref:System.Windows.TextDecorations>on Hosted-Element|Gilt nur, wenn ein <xref:System.Windows.Controls.TextBlock> -Steuerelement gehostet wird.|  
|<xref:System.Drawing.Font.Underline%2A>|<xref:System.Windows.TextDecorations>on Hosted-Element|Gilt nur, wenn ein <xref:System.Windows.Controls.TextBlock> -Steuerelement gehostet wird.|  
|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection>)|<xref:System.Windows.Forms.RightToLeft.No>wird zugeordnet <xref:System.Windows.FlowDirection.LeftToRight>.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Yes>wird zugeordnet <xref:System.Windows.FlowDirection.RightToLeft>.|  
|<xref:System.Windows.Forms.Control.Visible%2A>|<xref:System.Windows.UIElement.Visibility%2A>|Das <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement <xref:System.Windows.UIElement.Visibility%2A> legt die-Eigenschaft für das gehostete Element fest, indem die folgenden Regeln verwendet werden:<br /><br /> -   <xref:System.Windows.Forms.Control.Visible%2A> = `true`wird zugeordnet <xref:System.Windows.Visibility.Visible>.<br />-   <xref:System.Windows.Forms.Control.Visible%2A> = `false`wird zugeordnet <xref:System.Windows.Visibility.Hidden>.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Interaktion zwischen WPF und Win32](wpf-and-win32-interoperation.md)
- [Interaktion zwischen WPF und Windows Forms](wpf-and-windows-forms-interoperation.md)
- [Exemplarische Vorgehensweise: Mapping von Eigenschaften mit dem WindowsFormsHost-Element](walkthrough-mapping-properties-using-the-windowsformshost-element.md)
- [Exemplarische Vorgehensweise: Mapping von Eigenschaften mit dem Element Host-Steuerelement](walkthrough-mapping-properties-using-the-elementhost-control.md)
