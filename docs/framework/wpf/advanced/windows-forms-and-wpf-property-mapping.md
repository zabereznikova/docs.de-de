---
title: Eigenschaftenzuordnung von Windows Forms und WPF
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- property mapping [WPF interoperability]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 999d8298-9c04-467d-a453-86e41002057d
ms.openlocfilehash: 07e58f87d886212426e25be83f988037549ab642
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735238"
---
# <a name="windows-forms-and-wpf-property-mapping"></a>Eigenschaftenzuordnung von Windows Forms und WPF
Die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Technologien haben zwei ähnliche, aber unterschiedliche Eigenschaften Modelle. Die *Eigenschaften Zuordnung* unterstützt die Interoperation zwischen den beiden Architekturen und bietet die folgenden Funktionen:  
  
- Macht es einfach, relevante Eigenschaften Änderungen in der Host Umgebung dem gehosteten Steuerelement oder Element zuzuordnen.  
  
- Stellt die Standardbehandlung für die Zuordnung der am häufigsten verwendeten Eigenschaften bereit.  
  
- Ermöglicht das einfache entfernen, überschreiben oder Erweitern von Standardeigenschaften.  
  
- Stellt sicher, dass Eigenschafts Wertänderungen auf dem Host automatisch erkannt und in das gehostete Steuerelement oder Element übersetzt werden.  
  
> [!NOTE]
> Eigenschaften Änderungs Ereignisse werden nicht im Hostingsteuerelement oder in der Element Hierarchie nach oben weitergegeben. Die Eigenschaften Übersetzung wird nicht ausgeführt, wenn sich der lokale Wert einer Eigenschaft aufgrund direkter Einstellung, Stile, Vererbung, Datenbindung oder anderer Mechanismen, die den Wert der Eigenschaft ändern, nicht ändert.  
  
 Verwenden Sie die <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>-Eigenschaft für das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element und die <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>-Eigenschaft in <xref:System.Windows.Forms.Integration.ElementHost> Steuerung, um auf die Eigenschaften Zuordnung zuzugreifen.  
  
## <a name="property-mapping-with-the-windowsformshost-element"></a>Eigenschaften Zuordnung mit dem WindowsFormsHost-Element  
 Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element übersetzt Standard [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften mithilfe der folgenden Übersetzungstabelle in Ihre [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Entsprechungen.  
  
|Windows Presentation Foundation Hosting|Windows Forms|Interoperation-Verhalten|  
|---------------------------------------------|-------------------|-----------------------------|  
|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element legt die <xref:System.Windows.Forms.Control.BackColor%2A>-Eigenschaft des gehosteten Steuer Elements und die <xref:System.Windows.Forms.Control.BackgroundImage%2A>-Eigenschaft des gehosteten Steuer Elements fest. Die Zuordnung erfolgt mithilfe der folgenden Regeln:<br /><br /> Wenn <xref:System.Windows.Controls.Control.Background%2A> eine voll Tonfarbe ist, wird Sie konvertiert und zum Festlegen der <xref:System.Windows.Forms.Control.BackColor%2A>-Eigenschaft des gehosteten Steuer Elements verwendet. Die <xref:System.Windows.Forms.Control.BackColor%2A>-Eigenschaft ist für das gehostete Steuerelement nicht festgelegt, da das gehostete Steuerelement den Wert der <xref:System.Windows.Forms.Control.BackColor%2A>-Eigenschaft erben kann. **Hinweis:**  Das gehostete Steuerelement unterstützt keine Transparenz. Jede Farbe, die <xref:System.Windows.Forms.Control.BackColor%2A> zugewiesen ist, muss vollständig deckend sein, mit einem Alphawert von 0xFF. <br /><br /> Wenn <xref:System.Windows.Controls.Control.Background%2A> keine voll Tonfarbe ist, erstellt das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Steuerelement eine Bitmap aus der <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft. Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Steuerelement weist diese Bitmap der <xref:System.Windows.Forms.Control.BackgroundImage%2A>-Eigenschaft des gehosteten Steuer Elements zu. Dies bietet eine ähnliche Wirkung wie Transparenz. **Hinweis:**  Sie können dieses Verhalten außer Kraft setzen, oder Sie können die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaften Zuordnung entfernen.|  
|<xref:System.Windows.FrameworkElement.Cursor%2A>|<xref:System.Windows.Forms.Control.Cursor%2A>|Wenn die Standard Zuordnung nicht neu zugewiesen wurde, <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Steuerelement die Vorgänger Hierarchie durchlaufen, bis ein Vorgänger gefunden wird, dessen <xref:System.Windows.FrameworkElement.Cursor%2A>-Eigenschaft festgelegt ist. Dieser Wert wird in den nächstgelegenen entsprechenden [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Cursor übersetzt.<br /><br /> Wenn die Standard Zuordnung für die <xref:System.Windows.FrameworkElement.ForceCursor%2A>-Eigenschaft nicht neu zugewiesen wurde, wird der Durchlauf auf dem ersten Vorgänger beendet, wobei <xref:System.Windows.FrameworkElement.ForceCursor%2A> auf `true`festgelegt ist.|  
|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FlowDirection.LeftToRight> wird <xref:System.Windows.Forms.RightToLeft.No> zugeordnet.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft> wird <xref:System.Windows.Forms.RightToLeft.Yes> zugeordnet.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Inherit> ist nicht zugeordnet.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> wird <xref:System.Windows.Forms.RightToLeft.Yes?displayProperty=nameWithType> zugeordnet.|  
|<xref:System.Windows.Controls.Control.FontStyle%2A>|<xref:System.Drawing.Font.Style%2A> auf dem <xref:System.Drawing.Font?displayProperty=nameWithType> des gehosteten Steuer Elements|Der Satz von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften wird in eine entsprechende <xref:System.Drawing.Font>übersetzt. Wenn eine dieser Eigenschaften geändert wird, wird ein neuer <xref:System.Drawing.Font> erstellt. Für <xref:System.Windows.FontStyles.Normal%2A>: <xref:System.Drawing.FontStyle.Italic> ist deaktiviert. Für <xref:System.Windows.FontStyles.Italic%2A> oder <xref:System.Windows.FontStyles.Oblique%2A>: <xref:System.Drawing.FontStyle.Italic> aktiviert ist.|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Drawing.Font.Style%2A> auf dem <xref:System.Drawing.Font?displayProperty=nameWithType> des gehosteten Steuer Elements|Der Satz von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften wird in eine entsprechende <xref:System.Drawing.Font>übersetzt. Wenn eine dieser Eigenschaften geändert wird, wird ein neuer <xref:System.Drawing.Font> erstellt. Für <xref:System.Windows.FontWeights.Black%2A>, <xref:System.Windows.FontWeights.Bold%2A>, <xref:System.Windows.FontWeights.DemiBold%2A>, <xref:System.Windows.FontWeights.ExtraBold%2A>, <xref:System.Windows.FontWeights.Heavy%2A>, <xref:System.Windows.FontWeights.Medium%2A>, <xref:System.Windows.FontWeights.SemiBold%2A>oder <xref:System.Windows.FontWeights.UltraBold%2A>: <xref:System.Drawing.FontStyle.Bold> aktiviert ist. Für <xref:System.Windows.FontWeights.ExtraLight%2A>, <xref:System.Windows.FontWeights.Light%2A>, <xref:System.Windows.FontWeights.Normal%2A>, <xref:System.Windows.FontWeights.Regular%2A>, <xref:System.Windows.FontWeights.Thin%2A>oder <xref:System.Windows.FontWeights.UltraLight%2A>: <xref:System.Drawing.FontStyle.Bold> ist deaktiviert.|  
|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|Der Satz von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften wird in eine entsprechende <xref:System.Drawing.Font>übersetzt. Wenn eine dieser Eigenschaften geändert wird, wird ein neuer <xref:System.Drawing.Font> erstellt. Die Größe des gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuer Elements wird basierend auf dem Schrift Grad angepasst.<br /><br /> Der Schrift Grad in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wird als ein neunstel eines Zoll ausgedrückt und in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] als eine siebte Sekunde Zoll. Die entsprechende Konvertierung lautet wie folgt:<br /><br /> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Schriftart Größe = [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Schriftart Größe * 72,0/96,0.|  
|<xref:System.Windows.Controls.Control.Foreground%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.ForeColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|Die <xref:System.Windows.Controls.Control.Foreground%2A> Eigenschaften Zuordnung wird mithilfe der folgenden Regeln durchgeführt:<br /><br /> -Wenn <xref:System.Windows.Controls.Control.Foreground%2A> ein <xref:System.Windows.Media.SolidColorBrush>ist, verwenden Sie <xref:System.Windows.Media.SolidColorBrush.Color%2A> für <xref:System.Windows.Forms.Control.ForeColor%2A>.<br />-Wenn <xref:System.Windows.Controls.Control.Foreground%2A> ein <xref:System.Windows.Media.GradientBrush>ist, verwenden Sie die Farbe des <xref:System.Windows.Media.GradientStop> mit dem niedrigsten Offset Wert für <xref:System.Windows.Forms.Control.ForeColor%2A>.<br />-Für alle anderen <xref:System.Windows.Media.Brush> Typen lassen Sie <xref:System.Windows.Forms.Control.ForeColor%2A> unverändert. Dies bedeutet, dass der Standardwert verwendet wird.|  
|<xref:System.Windows.UIElement.IsEnabled%2A>|<xref:System.Windows.Forms.Control.Enabled%2A>|Wenn <xref:System.Windows.UIElement.IsEnabled%2A> festgelegt ist, legt <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element die <xref:System.Windows.Forms.Control.Enabled%2A>-Eigenschaft für das gehostete Steuerelement fest.|  
|<xref:System.Windows.Controls.Control.Padding%2A>|<xref:System.Windows.Forms.Control.Padding%2A>|Alle vier Werte der <xref:System.Windows.Forms.Control.Padding%2A>-Eigenschaft für das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelement werden auf denselben <xref:System.Windows.Thickness> Wert festgelegt.<br /><br /> -Werte, die größer als <xref:System.Int32.MaxValue> sind, werden auf <xref:System.Int32.MaxValue>festgelegt.<br />-Werte, die kleiner als <xref:System.Int32.MinValue> sind, werden <xref:System.Int32.MinValue>festgelegt.|  
|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Control.Visible%2A>|-   <xref:System.Windows.Visibility.Visible> wird <xref:System.Windows.Forms.Control.Visible%2A> = `true`zugeordnet. Das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement ist sichtbar. Das explizite Festlegen der <xref:System.Windows.Forms.Control.Visible%2A>-Eigenschaft für das gehostete Steuerelement auf `false` ist nicht empfehlenswert.<br />-   <xref:System.Windows.Visibility.Collapsed> wird <xref:System.Windows.Forms.Control.Visible%2A> = `true` oder `false`zugeordnet. Das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement wird nicht gezeichnet, und sein Bereich ist reduziert.<br />-   <xref:System.Windows.Visibility.Hidden>: das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelement belegt Platz im Layout, ist aber nicht sichtbar. In diesem Fall wird die <xref:System.Windows.Forms.Control.Visible%2A>-Eigenschaft auf `true`festgelegt. Das explizite Festlegen der <xref:System.Windows.Forms.Control.Visible%2A>-Eigenschaft für das gehostete Steuerelement auf `false` ist nicht empfehlenswert.|  
  
 Angefügte Eigenschaften für Container Elemente werden vom <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element vollständig unterstützt.  
  
 Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Mapping von Eigenschaften mit dem WindowsFormsHost-Element](walkthrough-mapping-properties-using-the-windowsformshost-element.md).  
  
## <a name="updates-to-parent-properties"></a>Aktualisierungen von übergeordneten Eigenschaften  
 Änderungen an den meisten übergeordneten Eigenschaften verursachen Benachrichtigungen an das gehostete untergeordnete Steuerelement. In der folgenden Liste werden Eigenschaften beschrieben, die keine Benachrichtigungen verursachen, wenn sich die Werte ändern.  
  
- <xref:System.Windows.Controls.Control.Background%2A>  
  
- <xref:System.Windows.FrameworkElement.Cursor%2A>  
  
- <xref:System.Windows.FrameworkElement.ForceCursor%2A>  
  
- <xref:System.Windows.UIElement.Visibility%2A>  
  
 Wenn Sie z. b. den Wert der <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft des <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Elements ändern, wird die <xref:System.Windows.Forms.Control.BackColor%2A>-Eigenschaft des gehosteten Steuer Elements nicht geändert.  
  
## <a name="property-mapping-with-the-elementhost-control"></a>Eigenschaften Zuordnung mit dem Element Host-Steuerelement  
 Die folgenden Eigenschaften stellen eine integrierte Änderungs Benachrichtigung bereit. Wenn Sie diese Eigenschaften Mapping, dürfen Sie die <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A>-Methode nicht aufzurufen:  
  
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
  
- Verzeichnis  
  
- Rand  
  
- Abstand  
  
- Übergeordnet  
  
- Region  
  
- RightToLeft  
  
- -Größe  
  
- TabIndex  
  
- TabStop  
  
- Text  
  
- Sichtbar  
  
 Das <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement übersetzt die Standard [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Eigenschaften mithilfe der folgenden Übersetzungstabelle in Ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Entsprechungen.  
  
 Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Mapping von Eigenschaften mit dem Element Host-Steuerelement](walkthrough-mapping-properties-using-the-elementhost-control.md).  
  
|Windows Forms Hosting|Windows Presentation Foundation|Interoperation-Verhalten|  
|---------------------------|-------------------------------------|-----------------------------|  
|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) für das gehostete Element|Wenn diese Eigenschaft festgelegt wird, wird ein Repaint mit einem <xref:System.Windows.Media.ImageBrush>erzwungen. Wenn die <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A>-Eigenschaft auf `false` (Standardwert) festgelegt ist, basiert dieser <xref:System.Windows.Media.ImageBrush> auf der Darstellung des <xref:System.Windows.Forms.Integration.ElementHost> Steuer Elements, einschließlich seiner <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> Eigenschaften und angehängten Zeichnungs Handlern.<br /><br /> Wenn die <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A>-Eigenschaft auf `true`festgelegt ist, basiert die <xref:System.Windows.Media.ImageBrush> auf der Darstellung des übergeordneten Elements des <xref:System.Windows.Forms.Integration.ElementHost> Steuer Elements, einschließlich der <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> Eigenschaften und angehängten Zeichnungs Handler.|  
|<xref:System.Windows.Forms.Control.BackgroundImage%2A><br /><br /> (<xref:System.Drawing.Image?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) für das gehostete Element|Das Festlegen dieser Eigenschaft bewirkt das gleiche Verhalten, das für die <xref:System.Windows.Forms.Control.BackColor%2A> Zuordnung beschrieben wird.|  
|<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) für das gehostete Element|Das Festlegen dieser Eigenschaft bewirkt das gleiche Verhalten, das für die <xref:System.Windows.Forms.Control.BackColor%2A> Zuordnung beschrieben wird.|  
|<xref:System.Windows.Forms.Control.Cursor%2A><br /><br /> (<xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.Cursor%2A><br /><br /> (<xref:System.Windows.Input.Cursor?displayProperty=nameWithType>)|Der [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Standard Cursor wird in den entsprechenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Standard-Cursor übersetzt. Wenn das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] kein Standard Cursor ist, wird der Standardwert zugewiesen.|  
|<xref:System.Windows.Forms.Control.Enabled%2A>|<xref:System.Windows.UIElement.IsEnabled%2A>|Wenn <xref:System.Windows.Forms.Control.Enabled%2A> festgelegt ist, legt das <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement die <xref:System.Windows.UIElement.IsEnabled%2A>-Eigenschaft für das gehostete Element fest.|  
|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|Der <xref:System.Windows.Forms.Control.Font%2A> Wert wird in einen entsprechenden Satz von Eigenschaften für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Schriftart übersetzt.|  
|<xref:System.Drawing.Font.Bold%2A>|<xref:System.Windows.Controls.Control.FontWeight%2A> auf gehostetes Element|Wenn<xref:System.Drawing.Font.Bold%2A>`true` ist, wird <xref:System.Windows.Controls.Control.FontWeight%2A> auf <xref:System.Windows.FontWeights.Bold%2A> festgelegt.<br /><br /> Wenn<xref:System.Drawing.Font.Bold%2A>`false` ist, wird <xref:System.Windows.Controls.Control.FontWeight%2A> auf <xref:System.Windows.FontWeights.Normal%2A> festgelegt.|  
|<xref:System.Drawing.Font.Italic%2A>|<xref:System.Windows.Controls.Control.FontStyle%2A> auf gehostetes Element|Wenn<xref:System.Drawing.Font.Italic%2A>`true` ist, wird <xref:System.Windows.Controls.Control.FontStyle%2A> auf <xref:System.Windows.FontStyles.Italic%2A> festgelegt.<br /><br /> Wenn<xref:System.Drawing.Font.Italic%2A>`false` ist, wird <xref:System.Windows.Controls.Control.FontStyle%2A> auf <xref:System.Windows.FontStyles.Normal%2A> festgelegt.|  
|<xref:System.Drawing.Font.Strikeout%2A>|<xref:System.Windows.TextDecorations> auf gehostetes Element|Gilt nur, wenn ein <xref:System.Windows.Controls.TextBlock>-Steuerelement gehostet wird.|  
|<xref:System.Drawing.Font.Underline%2A>|<xref:System.Windows.TextDecorations> auf gehostetes Element|Gilt nur, wenn ein <xref:System.Windows.Controls.TextBlock>-Steuerelement gehostet wird.|  
|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection>)|<xref:System.Windows.Forms.RightToLeft.No> wird <xref:System.Windows.FlowDirection.LeftToRight> zugeordnet.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Yes> wird <xref:System.Windows.FlowDirection.RightToLeft> zugeordnet.|  
|<xref:System.Windows.Forms.Control.Visible%2A>|<xref:System.Windows.UIElement.Visibility%2A>|Das <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement legt die <xref:System.Windows.UIElement.Visibility%2A>-Eigenschaft für das gehostete Element fest, indem die folgenden Regeln verwendet werden:<br /><br /> -   <xref:System.Windows.Forms.Control.Visible%2A> = `true` wird <xref:System.Windows.Visibility.Visible>zugeordnet.<br />-   <xref:System.Windows.Forms.Control.Visible%2A> = `false` wird <xref:System.Windows.Visibility.Hidden>zugeordnet.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Interaktion zwischen WPF und Win32](wpf-and-win32-interoperation.md)
- [Interaktion zwischen WPF und Windows Forms](wpf-and-windows-forms-interoperation.md)
- [Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem WindowsFormsHost-Element](walkthrough-mapping-properties-using-the-windowsformshost-element.md)
- [Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem ElementHost-Steuerelement](walkthrough-mapping-properties-using-the-elementhost-control.md)
