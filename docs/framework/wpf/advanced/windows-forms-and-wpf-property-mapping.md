---
title: "Eigenschaftenzuordnung von Windows Forms und WPF | Microsoft Docs"
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
  - "Interoperabilität [WPF], Windows Forms"
  - "Eigenschaftenzuordnung [WPF-Interoperabilität]"
  - "Windows Forms [WPF], Interoperabilität mit"
  - "Windows Forms, WPF-Interoperation"
  - "WindowsFormsHost-Elementeigenschaftszuordnung"
ms.assetid: 999d8298-9c04-467d-a453-86e41002057d
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Eigenschaftenzuordnung von Windows Forms und WPF
Die Technologien von [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] besitzen zwei zwar ähnliche, aber dennoch unterschiedliche Eigenschaftenmodelle.  Die *Eigenschaftenzuordnung* unterstützt die Interoperation zwischen den zwei Architekturen und stellt die folgenden Funktionen bereit:  
  
-   Einfaches Zuordnen wichtiger Eigenschaftenänderungen in der Hostumgebung zum gehosteten Steuerelement oder Element.  
  
-   Bereitstellen einer Standardbehandlung zum Zuordnen der am häufigsten verwendeten Eigenschaften.  
  
-   Einfaches Entfernen, Überschreiben oder Erweitern von Standardeigenschaften.  
  
-   Sicherstellen, dass Änderungen der Eigenschaftswerte auf dem Host automatisch erkannt und für das gehostete Steuerelement oder Element übersetzt werden.  
  
> [!NOTE]
>  Eigenschaftenänderungsereignisse werden nicht in der Hierarchie des Hostingsteuerelements oder des Elements weitergeleitet.  Die Eigenschaftenübersetzung wird nicht ausgeführt, wenn der lokale Wert einer Eigenschaft sich nicht aufgrund von direkter Festlegung, Stilen, Vererbung, Datenbindung oder anderen Verfahren, die den Wert der Eigenschaft ändern, ändert.  
  
 Verwenden Sie die <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>\-Eigenschaft für das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element und die <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>\-Eigenschaft für das <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement, um auf die Eigenschaftenzuordnung zuzugreifen.  
  
## Eigenschaftenzuordnung mit dem WindowsFormsHost\-Element  
 Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element übersetzt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Standardeigenschaften mit der folgenden Übersetzungstabelle in ihre [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Entsprechungen.  
  
|In Windows Presentation Foundation gehostete Elemente|Windows Forms|Interoperationsverhalten|  
|-----------------------------------------------------------|-------------------|------------------------------|  
|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> \(<xref:System.Windows.Media.Brush?displayProperty=fullName>\)|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> \(<xref:System.Drawing.Color?displayProperty=fullName>\)|Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element legt die <xref:System.Windows.Forms.Control.BackColor%2A>\-Eigenschaft des gehosteten Steuerelements und die <xref:System.Windows.Forms.Control.BackgroundImage%2A>\-Eigenschaft des gehosteten Steuerelements fest.  Die Zuordnung wird unter Anwendung der folgenden Regeln ausgeführt:<br /><br /> -   Wenn <xref:System.Windows.Controls.Control.Background%2A> eine Volltonfarbe ist, wird sie konvertiert und zum Festlegen der <xref:System.Windows.Forms.Control.BackColor%2A>\-Eigenschaft des gehosteten Steuerelements verwendet.  Die <xref:System.Windows.Forms.Control.BackColor%2A>\-Eigenschaft wird nicht für das gehostete Steuerelement festgelegt, da das gehostete Steuerelement den Wert von der <xref:System.Windows.Forms.Control.BackColor%2A>\-Eigenschaft erben kann. **Note:**  Das gehostete Steuerelement unterstützt keine Transparenz.  Jede <xref:System.Windows.Forms.Control.BackColor%2A> zugewiesene Farbe muss vollständig deckend sein, mit einem Alphawert von 0xFF. <br /><br /> -   Wenn <xref:System.Windows.Controls.Control.Background%2A> keine Volltonfarbe ist, erstellt das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Steuerelement eine Bitmap aus der <xref:System.Windows.Controls.Control.Background%2A>\-Eigenschaft.  Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Steuerelement ordnet diese Bitmap der <xref:System.Windows.Forms.Control.BackgroundImage%2A>\-Eigenschaft des gehosteten Steuerelements zu.  Dadurch kommt ein Effekt zustande, der der Transparenz ähnelt. **Note:**  Sie können dieses Verhalten überschreiben, oder Sie können die <xref:System.Windows.Controls.Control.Background%2A>\-Eigenschaftenzuordnung entfernen.|  
|<xref:System.Windows.FrameworkElement.Cursor%2A>|<xref:System.Windows.Forms.Control.Cursor%2A>|Wenn die Standardzuordnung nicht erneut zugewiesen wurde, durchläuft das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Steuerelement die Vorgängerhierarchie, bis es einen Vorgänger mit festgelegter <xref:System.Windows.FrameworkElement.Cursor%2A>\-Eigenschaft findet.  Dieser Wert wird in den [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Cursor mit der größten Entsprechung übersetzt.<br /><br /> Wenn die Standardzuordnung für die <xref:System.Windows.FrameworkElement.ForceCursor%2A>\-Eigenschaft nicht erneut zugewiesen wurde, wird das Durchlaufen beim ersten Vorgänger beendet, dessen <xref:System.Windows.FrameworkElement.ForceCursor%2A>\-Eigenschaft auf `true` festgelegt ist.|  
|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> \(<xref:System.Windows.FlowDirection?displayProperty=fullName>\)|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> \(<xref:System.Windows.Forms.RightToLeft?displayProperty=fullName>\)|<xref:System.Windows.FlowDirection> wird <xref:System.Windows.Forms.RightToLeft> zugeordnet.<br /><br /> <xref:System.Windows.FlowDirection> wird <xref:System.Windows.Forms.RightToLeft> zugeordnet.<br /><br /> <xref:System.Windows.Forms.RightToLeft> wird nicht zugeordnet.<br /><br /> <xref:System.Windows.FlowDirection?displayProperty=fullName> wird <xref:System.Windows.Forms.RightToLeft?displayProperty=fullName> zugeordnet.|  
|<xref:System.Windows.Controls.Control.FontStyle%2A>|<xref:System.Drawing.Font.Style%2A> für <xref:System.Drawing.Font?displayProperty=fullName> des gehosteten Steuerelements.|Der Satz von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Eigenschaften wird in eine entsprechende <xref:System.Drawing.Font> übersetzt.  Wenn sich eine dieser Eigenschaften ändert, wird eine neue <xref:System.Drawing.Font> erstellt.  Für <xref:System.Windows.FontStyles.Normal%2A>: <xref:System.Drawing.FontStyle> wird deaktiviert.  Für <xref:System.Windows.FontStyles.Italic%2A> oder <xref:System.Windows.FontStyles.Oblique%2A>: <xref:System.Drawing.FontStyle> wird aktiviert.|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Drawing.Font.Style%2A> für <xref:System.Drawing.Font?displayProperty=fullName> des gehosteten Steuerelements.|Der Satz von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Eigenschaften wird in eine entsprechende <xref:System.Drawing.Font> übersetzt.  Wenn sich eine dieser Eigenschaften ändert, wird eine neue <xref:System.Drawing.Font> erstellt.  Für <xref:System.Windows.FontWeights.Black%2A>, <xref:System.Windows.FontWeights.Bold%2A>, <xref:System.Windows.FontWeights.DemiBold%2A>, <xref:System.Windows.FontWeights.ExtraBold%2A>, <xref:System.Windows.FontWeights.Heavy%2A>, <xref:System.Windows.FontWeights.Medium%2A>, <xref:System.Windows.FontWeights.SemiBold%2A> oder <xref:System.Windows.FontWeights.UltraBold%2A>: <xref:System.Drawing.FontStyle> wird aktiviert.  Für <xref:System.Windows.FontWeights.ExtraLight%2A>, <xref:System.Windows.FontWeights.Light%2A>, <xref:System.Windows.FontWeights.Normal%2A>, <xref:System.Windows.FontWeights.Regular%2A>, <xref:System.Windows.FontWeights.Thin%2A> oder <xref:System.Windows.FontWeights.UltraLight%2A>: <xref:System.Drawing.FontStyle> wird deaktiviert.|  
|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> \(<xref:System.Drawing.Font?displayProperty=fullName>\)|Der Satz von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Eigenschaften wird in eine entsprechende <xref:System.Drawing.Font> übersetzt.  Wenn sich eine dieser Eigenschaften ändert, wird eine neue <xref:System.Drawing.Font> erstellt.  Die Größe des gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelements wird entsprechend dem Schriftgrad angepasst.<br /><br /> In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wird der Schriftgrad als ein sechsundneunzigstel Zoll ausgedrückt, in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] als ein zweiundsiebzigstel Zoll.  Die entsprechende Umrechnungsformel lautet:<br /><br /> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Schriftgrad \= [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Schriftgrad \* 72,0 \/ 96,0.|  
|<xref:System.Windows.Controls.Control.Foreground%2A><br /><br /> \(<xref:System.Windows.Media.Brush?displayProperty=fullName>\)|<xref:System.Windows.Forms.Control.ForeColor%2A><br /><br /> \(<xref:System.Drawing.Color?displayProperty=fullName>\)|Die <xref:System.Windows.Controls.Control.Foreground%2A>\-Eigenschaftenzuordnung wird unter Anwendung der folgenden Regeln ausgeführt:<br /><br /> -   Wenn <xref:System.Windows.Controls.Control.Foreground%2A> ein <xref:System.Windows.Media.SolidColorBrush> ist, verwenden Sie für <xref:System.Windows.Forms.Control.ForeColor%2A> <xref:System.Windows.Media.SolidColorBrush.Color%2A>.<br />-   Wenn <xref:System.Windows.Controls.Control.Foreground%2A> ein <xref:System.Windows.Media.GradientBrush> ist, verwenden Sie für <xref:System.Windows.Forms.Control.ForeColor%2A> die Farbe von <xref:System.Windows.Media.GradientStop> mit dem kleinsten Offsetwert.<br />-   Lassen Sie für alle anderen <xref:System.Windows.Media.Brush>\-Typen <xref:System.Windows.Forms.Control.ForeColor%2A> unverändert.  Dadurch wird die Standardeinstellung verwendet.|  
|<xref:System.Windows.UIElement.IsEnabled%2A>|<xref:System.Windows.Forms.Control.Enabled%2A>|Wenn <xref:System.Windows.UIElement.IsEnabled%2A> festgelegt ist, legt das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element die <xref:System.Windows.Forms.Control.Enabled%2A>\-Eigenschaft für das gehostete Steuerelement fest.|  
|<xref:System.Windows.Controls.Control.Padding%2A>|<xref:System.Windows.Forms.Control.Padding%2A>|Alle vier Werte der <xref:System.Windows.Forms.Control.Padding%2A>\-Eigenschaft für das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelement werden auf denselben <xref:System.Windows.Thickness>\-Wert festgelegt.<br /><br /> -   Werte, die größer sind als <xref:System.Int32.MaxValue>, werden auf <xref:System.Int32.MaxValue> festgelegt.<br />-   Werte, die kleiner sind als <xref:System.Int32.MinValue>, werden auf <xref:System.Int32.MinValue> festgelegt.|  
|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Control.Visible%2A>|-   <xref:System.Windows.Visibility> wird <xref:System.Windows.Forms.Control.Visible%2A> \= `true` zugeordnet.  Das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelement ist sichtbar.  Es wird nicht empfohlen, die <xref:System.Windows.Forms.Control.Visible%2A>\-Eigenschaft für das gehostete Steuerelement explizit auf `false` festzulegen.<br />-   <xref:System.Windows.Visibility> wird <xref:System.Windows.Forms.Control.Visible%2A> \= `true` oder `false` zugeordnet.  Das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelement wird nicht gezeichnet, und der zugehörige Bereich wird reduziert.<br />-   <xref:System.Windows.Visibility>: Das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelement nimmt Platz im Layout ein, ist aber nicht sichtbar.  In diesem Fall wird die <xref:System.Windows.Forms.Control.Visible%2A>\-Eigenschaft auf `true` festgelegt.  Es wird nicht empfohlen, die <xref:System.Windows.Forms.Control.Visible%2A>\-Eigenschaft für das gehostete Steuerelement explizit auf `false` festzulegen.|  
  
 Angefügte Eigenschaften für Containerelemente werden vom <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element vollständig unterstützt.  
  
 Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem WindowsFormsHost\-Element](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-windowsformshost-element.md).  
  
## Aktualisierungen für übergeordnete Eigenschaften  
 Bei Änderungen an den meisten übergeordneten Eigenschaften werden Benachrichtigungen an das gehostete untergeordnete Steuerelement ausgegeben.  In der folgenden Liste werden Eigenschaften beschrieben, für die keine Benachrichtigungen ausgegeben werden, wenn sich ihre Werte ändern.  
  
-   <xref:System.Windows.Controls.Control.Background%2A>  
  
-   <xref:System.Windows.FrameworkElement.Cursor%2A>  
  
-   <xref:System.Windows.FrameworkElement.ForceCursor%2A>  
  
-   <xref:System.Windows.UIElement.Visibility%2A>  
  
 Wenn Sie z. B. den Wert der <xref:System.Windows.Controls.Control.Background%2A>\-Eigenschaft des <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Elements ändern, ändert sich die <xref:System.Windows.Forms.Control.BackColor%2A>\-Eigenschaft des gehosteten Steuerelements nicht.  
  
## Eigenschaftenzuordnung mit dem ElementHost\-Steuerelement  
 Die folgenden Eigenschaften bieten eine integrierte Änderungsbenachrichtigung.  Rufen Sie nicht die <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A>\-Methode auf, wenn Sie diese Eigenschaften zuordnen:  
  
-   AutoSize  
  
-   BackColor  
  
-   BackgroundImage  
  
-   BackgroundImageLayout  
  
-   BindingContext  
  
-   CausesValidation  
  
-   ContextMenu  
  
-   ContextMenuStrip  
  
-   Cursor  
  
-   Dock  
  
-   Aktiviert  
  
-   Schriftart  
  
-   ForeColor  
  
-   Speicherort  
  
-   Margin  
  
-   Padding  
  
-   Parent \(Übergeordnet\)  
  
-   Region  
  
-   RightToLeft  
  
-   Größe  
  
-   TabIndex  
  
-   TabStop  
  
-   Text  
  
-   Visible  
  
 Das <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement übersetzt [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Standardeigenschaften mit der folgenden Übersetzungstabelle in die zugehörigen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Entsprechungen.  
  
 Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem ElementHost\-Steuerelement](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-elementhost-control.md).  
  
|In Windows Forms gehostete Elemente|Windows Presentation Foundation|Interoperationsverhalten|  
|-----------------------------------------|-------------------------------------|------------------------------|  
|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> \(<xref:System.Drawing.Color?displayProperty=fullName>\)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> \(<xref:System.Windows.Media.Brush?displayProperty=fullName>\) für das gehostete Element|Das Festlegen dieser Eigenschaft erzwingt das Neuzeichnen mit einem <xref:System.Windows.Media.ImageBrush>.  Wenn die <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A>\-Eigenschaft auf `false` \(den Standardwert\) festgelegt wird, basiert dieser <xref:System.Windows.Media.ImageBrush> auf der Darstellung des <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelements, einschließlich der zugehörigen <xref:System.Windows.Forms.Control.BackColor%2A>\-Eigenschaft, der <xref:System.Windows.Forms.Control.BackgroundImage%2A>\-Eigenschaft, der <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>\-Eigenschaft und aller angefügten Paint\-Handler.<br /><br /> Wenn die <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A>\-Eigenschaft auf `true` festgelegt wird, basiert der <xref:System.Windows.Media.ImageBrush> auf der Darstellung des übergeordneten Elements des <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelements, einschließlich der <xref:System.Windows.Forms.Control.BackColor%2A>\-Eigenschaft, der <xref:System.Windows.Forms.Control.BackgroundImage%2A>\-Eigenschaft und der <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>\-Eigenschaft des übergeordneten Elements sowie aller angefügten Paint\-Handler.|  
|<xref:System.Windows.Forms.Control.BackgroundImage%2A><br /><br /> \(<xref:System.Drawing.Image?displayProperty=fullName>\)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> \(<xref:System.Windows.Media.Brush?displayProperty=fullName>\) für das gehostete Element|Das Festlegen dieser Eigenschaft bewirkt dasselbe Verhalten, das für die <xref:System.Windows.Forms.Control.BackColor%2A>\-Zuordnung beschrieben wurde.|  
|<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> \(<xref:System.Windows.Media.Brush?displayProperty=fullName>\) für das gehostete Element|Das Festlegen dieser Eigenschaft bewirkt dasselbe Verhalten, das für die <xref:System.Windows.Forms.Control.BackColor%2A>\-Zuordnung beschrieben wurde.|  
|<xref:System.Windows.Forms.Control.Cursor%2A><br /><br /> \(<xref:System.Windows.Forms.Cursor?displayProperty=fullName>\)|<xref:System.Windows.FrameworkElement.Cursor%2A><br /><br /> \(<xref:System.Windows.Input.Cursor?displayProperty=fullName>\)|Der [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Standardcursor wird in den entsprechenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Standardcursor übersetzt.  Wenn der Cursor von [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] nicht der Standardcursor ist, wird der Standard zugewiesen.|  
|<xref:System.Windows.Forms.Control.Enabled%2A>|<xref:System.Windows.UIElement.IsEnabled%2A>|Wenn <xref:System.Windows.Forms.Control.Enabled%2A> festgelegt ist, legt das <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement die <xref:System.Windows.UIElement.IsEnabled%2A>\-Eigenschaft für das gehostete Element fest.|  
|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> \(<xref:System.Drawing.Font?displayProperty=fullName>\)|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|Der <xref:System.Windows.Forms.Control.Font%2A>\-Wert wird in einen entsprechenden Satz von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Schriftarteigenschaften übersetzt.|  
|<xref:System.Drawing.Font.Bold%2A>|<xref:System.Windows.Controls.Control.FontWeight%2A> für das gehostete Element|Wenn <xref:System.Drawing.Font.Bold%2A> `true` ist, wird <xref:System.Windows.Controls.Control.FontWeight%2A> auf <xref:System.Windows.FontWeights.Bold%2A> festgelegt.<br /><br /> Wenn <xref:System.Drawing.Font.Bold%2A> `false` ist, wird <xref:System.Windows.Controls.Control.FontWeight%2A> auf <xref:System.Windows.FontWeights.Normal%2A> festgelegt.|  
|<xref:System.Drawing.Font.Italic%2A>|<xref:System.Windows.Controls.Control.FontStyle%2A> für das gehostete Element|Wenn <xref:System.Drawing.Font.Italic%2A> `true` ist, wird <xref:System.Windows.Controls.Control.FontStyle%2A> auf <xref:System.Windows.FontStyles.Italic%2A> festgelegt.<br /><br /> Wenn <xref:System.Drawing.Font.Italic%2A> `false` ist, wird <xref:System.Windows.Controls.Control.FontStyle%2A> auf <xref:System.Windows.FontStyles.Normal%2A> festgelegt.|  
|<xref:System.Drawing.Font.Strikeout%2A>|<xref:System.Windows.TextDecorations> für das gehostete Element|Gilt nur, wenn ein <xref:System.Windows.Controls.TextBlock>\-Steuerelement gehostet wird.|  
|<xref:System.Drawing.Font.Underline%2A>|<xref:System.Windows.TextDecorations> für das gehostete Element|Gilt nur, wenn ein <xref:System.Windows.Controls.TextBlock>\-Steuerelement gehostet wird.|  
|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> \(<xref:System.Windows.Forms.RightToLeft?displayProperty=fullName>\)|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> \(<xref:System.Windows.FlowDirection>\)|<xref:System.Windows.Forms.RightToLeft> wird <xref:System.Windows.FlowDirection> zugeordnet.<br /><br /> <xref:System.Windows.Forms.RightToLeft> wird <xref:System.Windows.FlowDirection> zugeordnet.|  
|<xref:System.Windows.Forms.Control.Visible%2A>|<xref:System.Windows.UIElement.Visibility%2A>|Das <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement legt die <xref:System.Windows.UIElement.Visibility%2A>\-Eigenschaft für das gehostete Element unter Anwendung der folgenden Regeln fest:<br /><br /> -   <xref:System.Windows.Forms.Control.Visible%2A> \= `true` wird <xref:System.Windows.Visibility> zugeordnet.<br />-   <xref:System.Windows.Forms.Control.Visible%2A> \= `false` wird <xref:System.Windows.Visibility> zugeordnet.|  
  
## Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Interaktion zwischen WPF und Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)   
 [Interaktion zwischen WPF und Windows Forms](../../../../docs/framework/wpf/advanced/wpf-and-windows-forms-interoperation.md)   
 [Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem WindowsFormsHost\-Element](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-windowsformshost-element.md)   
 [Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem ElementHost\-Steuerelement](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-elementhost-control.md)