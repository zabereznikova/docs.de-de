---
title: Bidirektionale Unterstützung
ms.date: 09/30/2017
helpviewer_keywords:
- globalization [Windows Forms], bi-directional support in Windows
- Windows Forms, international
- localization [Windows Forms], bi-directional support in Windows
- bi-directional language support [Windows Forms], Windows applications
- Windows Forms, bi-directional support
ms.openlocfilehash: 8b2e842fc08be78b74cede85927352fafca7bc8f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742078"
---
# <a name="bi-directional-support-for-windows-forms-applications"></a>Bidirektionale Unterstützung für Windows Forms-Anwendungen
Mithilfe von Visual Studio können Sie Windows-basierte Anwendungen erstellen, die bidirektionale (von rechts nach links geschriebene) Sprachen wie Arabisch und Hebräisch unterstützen. Dies beinhaltet Standardformulare, Dialogfelder, MDI-Formulare und alle Steuerelemente, die Sie in diesen Formularen verwenden können, also alle Objekte im <xref:System.Windows.Forms.Control>-Namespace.

## <a name="culture-support"></a>Kulturspezifische Unterstützung
 Durch Einstellungen der Kultur und Benutzeroberflächenkultur wird festgelegt, wie Datums- und Zeitangaben, Währungen und andere Informationen in Anwendungen gehandhabt werden. Kultur und Benutzeroberflächenkultur werden für bidirektionale Sprachen genauso wie für andere Sprachen unterstützt. Weitere Informationen finden Sie unter [kulturspezifische Klassen für globale Windows Forms und Web Forms](/visualstudio/ide/globalizing-and-localizing-applications).

## <a name="righttoleft-and-righttoleftlayout-properties"></a>RightToLeft-Eigenschaft und RightToLeftLayout-Eigenschaft
 Die <xref:System.Windows.Forms.Control>-Basisklasse, von der Formulare abgeleitet werden, enthält auch eine <xref:System.Windows.Forms.Control.RightToLeft%2A>-Eigenschaft, die Sie zum Ändern der Leserichtung eines Formulars und seiner Steuerelemente verwenden können. Wenn Sie die <xref:System.Windows.Forms.Control.RightToLeft%2A>-Eigenschaft eines Formulars festlegen, erben standardmäßig alle Steuerelemente des Formulars diese Einstellung. Bei den meisten Steuerelementen können Sie die <xref:System.Windows.Forms.Control.RightToLeft%2A>-Eigenschaft aber auch individuell festlegen. Siehe auch [Vorgehensweise: Anzeigen von Text mit der Schreibrichtung von rechts nach links in Windows Forms für die Globalisierung](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7d3337xw(v=vs.100)).

 Die Auswirkung der <xref:System.Windows.Forms.Control.RightToLeft%2A>-Eigenschaft kann sich von Steuerelement zu Steuerelement unterscheiden. Bei einigen Steuerelementen, wie den Steuerelementen <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.TreeView> und <xref:System.Windows.Forms.ToolTip>, legt die Eigenschaft nur die Leserichtung fest. Bei anderen Steuerelementen wird durch die <xref:System.Windows.Forms.Control.RightToLeft%2A>-Eigenschaft sowohl die Leserichtung als auch das Layout geändert. Dazu gehören Steuerelemente des Typs <xref:System.Windows.Forms.RadioButton>, <xref:System.Windows.Forms.ComboBox> und <xref:System.Windows.Forms.CheckBox>. Andere Steuerelemente erfordern, dass die <xref:System.Windows.Forms.Form.RightToLeftLayout%2A>-Eigenschaft angewendet wird, um das Layout von rechts nach links zu spiegeln. In der folgenden Tabelle ist angegeben, wie sich die <xref:System.Windows.Forms.Control.RightToLeft%2A>-Eigenschaft und die <xref:System.Windows.Forms.Form.RightToLeftLayout%2A>-Eigenschaft auf die einzelnen Windows Forms-Steuerelemente auswirken.

|Steuerelement/Komponente|Auswirkung der RightToLeft-Eigenschaft|Auswirkung der RightToLeftLayout-Eigenschaft|Spiegeln erforderlich?|
|------------------------|------------------------------------|------------------------------------------|-------------------------|
|<xref:System.Windows.Forms.Button>|Stellt die Rechts-nach-Links-Lesefolge ein. Kehrt <xref:System.Windows.Forms.ButtonBase.TextAlign%2A>, <xref:System.Windows.Forms.ButtonBase.ImageAlign%2A> und <xref:System.Windows.Forms.ButtonBase.TextImageRelation%2A> um.|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.CheckBox>|Das Kontrollkästchen wird rechts vom Text angezeigt.|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.CheckedListBox>|Alle Kontrollkästchen werden rechts vom Text angezeigt.|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.ColorDialog>|Keine Auswirkung. Hängt von der Sprache des Betriebssystems ab.|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.ComboBox>|Elemente im Kombinationsfeld sind rechtsbündig.|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.ContextMenu>|Wird rechtsbündig mit Rechts-nach-Links-Lesefolge angezeigt.|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.DataGrid>|Wird rechtsbündig mit Rechts-nach-Links-Lesefolge angezeigt.|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.DataGridView>|Wirkt sich sowohl auf die Rechts-nach-Links-Lesefolge als auch auf das Steuerelementlayout aus.|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.DateTimePicker>|Keine Auswirkung. Hängt von der Sprache des Betriebssystems ab.|Spiegelt das Steuerelement|Ja|
|<xref:System.Windows.Forms.DomainUpDown>|Richtet die Schaltflächen "Nach oben" und "Nach unten" linksbündig aus.|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.ErrorProvider>|Nicht unterstützt|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.FontDialog>|Hängt von der Sprache des Betriebssystems ab.|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.Form>|Stellt die Rechts-nach-Links-Lesefolge ein und kehrt Schiebeleisten um.|Spiegelt das Formular|Ja|
|<xref:System.Windows.Forms.GroupBox>|Die Beschriftung wird rechtsbündig angezeigt. Untergeordnete Steuerelemente können diese Eigenschaft erben.|Verwenden Sie <xref:System.Windows.Forms.TableLayoutPanel> im Steuerelement für die Unterstützung der Spiegelung von rechts nach links.|Nein|
|<xref:System.Windows.Forms.HScrollBar>|Startet mit einem rechtsbündigen Bildlauffeld (Ziehpunkt).|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.ImageList>|Nicht erforderlich|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.Label>|Wird rechtsbündig angezeigt. Kehrt <xref:System.Windows.Forms.Label.TextAlign%2A> und <xref:System.Windows.Forms.Label.ImageAlign%2A> um.|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.LinkLabel>|Wird rechtsbündig angezeigt. Kehrt <xref:System.Windows.Forms.Label.TextAlign%2A> und <xref:System.Windows.Forms.Label.ImageAlign%2A> um.|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.ListBox>|Elemente werden rechtsbündig angezeigt.|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.ListView>|Setzt die Lesefolge auf Rechts-nach-Links. Elemente bleiben linksbündig.|Spiegelt das Steuerelement|Ja|
|<xref:System.Windows.Forms.MainMenu>|Wird zur Laufzeit (nicht zur Entwurfszeit) rechtsbündig mit Rechts-nach-Links-Lesefolge angezeigt.|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.MaskedTextBox>|Zeigt Text von rechts nach links an.|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.MonthCalendar>|Keine Auswirkung. Hängt von der Sprache des Betriebssystems ab.|Spiegelt das Steuerelement|Ja|
|<xref:System.Windows.Forms.NotifyIcon>|Nicht unterstützt|Nicht unterstützt|Nein|
|<xref:System.Windows.Forms.NumericUpDown>|Die Schaltflächen "Nach oben" und "Nach unten" sind linksbündig.|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.OpenFileDialog>|Bei Betriebssystemen mit der Größe von rechts nach links legen Sie die <xref:System.Windows.Forms.Control.RightToLeft>-Eigenschaft des enthaltenden Formulars auf fest, um <xref:System.Windows.Forms.RightToLeft.Yes?displayProperty=nameWithType> das Dialogfeld zu lokalisieren |Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.PageSetupDialog>|Keine Auswirkung. Hängt von der Sprache des Betriebssystems ab.|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.Panel>|Untergeordnete Steuerelemente können diese Eigenschaft erben.|Verwenden Sie <xref:System.Windows.Forms.TableLayoutPanel> im Steuerelement für die Rechts-nach-Links-Unterstützung.|Ja|
|<xref:System.Windows.Forms.PictureBox>|Nicht unterstützt|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.PrintDialog>|Keine Auswirkung. Hängt von der Sprache des Betriebssystems ab.|Keine Auswirkungen|Nein|
|<xref:System.Drawing.Printing.PrintDocument>|Die vertikale Schiebeleiste wird linksbündig angezeigt, und die horizontale Schiebeleiste beginnt links.|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.PrintPreviewDialog>|Nicht unterstützt|Nicht unterstützt|Nein|
|<xref:System.Windows.Forms.ProgressBar>|Diese Eigenschaft hat keine Auswirkung.|Spiegelt das Steuerelement|Ja|
|<xref:System.Windows.Forms.RadioButton>|Das Optionsfeld wird rechts vom Text angezeigt.|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.RichTextBox>|Steuerelemente, die Text enthalten, werden von rechts nach links mit Rechts-nach-Links-Lesefolge angezeigt.|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.SaveFileDialog>|Keine Auswirkung. Hängt von der Sprache des Betriebssystems ab.|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.SplitContainer>|Das Bereichslayout wird umgekehrt. Die vertikale Scrollleiste wird auf der linken Seite angezeigt, die horizontale Scrollleiste beginnt rechts.|Verwenden Sie <xref:System.Windows.Forms.TableLayoutPanel>, um die Reihenfolge der untergeordneten Steuerelemente zu spiegeln.|Nein|
|<xref:System.Windows.Forms.Splitter>|Nicht unterstützt|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.StatusBar>|Nicht unterstützt. Verwenden Sie stattdessen <xref:System.Windows.Forms.StatusStrip>.|Keine Auswirkung. Verwenden Sie stattdessen <xref:System.Windows.Forms.StatusStrip>.|Nein|
|<xref:System.Windows.Forms.TabControl>|Diese Eigenschaft hat keine Auswirkung.|Spiegelt das Steuerelement|Ja|
|<xref:System.Windows.Forms.TextBox>|Text wird rechtsbündig mit Rechts-nach-Links-Lesefolge angezeigt.|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.Timer>|Nicht erforderlich|Nicht erforderlich|Nein|
|<xref:System.Windows.Forms.ToolBar>|Diese Eigenschaft hat keine Auswirkung. Verwenden Sie stattdessen <xref:System.Windows.Forms.ToolStrip>.|Keine Auswirkung. Verwenden Sie stattdessen <xref:System.Windows.Forms.ToolStrip>.|Ja|
|<xref:System.Windows.Forms.ToolTip>|Stellt die Rechts-nach-Links-Lesefolge ein.|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.TrackBar>|Bildlauf oder Position beginnt auf der rechten Seite. Wenn <xref:System.Windows.Forms.TrackBar.Orientation%2A> als vertikal angegeben ist, werden Teilstriche rechts angezeigt.|Keine Auswirkungen|Nein|
|<xref:System.Windows.Forms.TreeView>|Stellt nur die Rechts-nach-Links-Lesefolge ein.|Spiegelt das Steuerelement|Ja|
|<xref:System.Windows.Forms.UserControl>|Vertikale Scrollleiste wird auf der linken Seite angezeigt. Der Ziehpunkt der horizontalen Scrollleiste befindet sich auf der rechten Seite.|Keine direkte Unterstützung. Verwenden Sie <xref:System.Windows.Forms.TableLayoutPanel>.|Nein|
|<xref:System.Windows.Forms.VScrollBar>|Wird statt auf der rechten auf der linken Seite von bildlauffähigen Steuerelementen angezeigt.|Keine Auswirkungen|Nein|

## <a name="encoding"></a>Codieren
 Windows Forms unterstützen Unicode, sodass Sie beim Erstellen von bidirektionalen Anwendungen alle Zeichensätze verwenden können. Allerdings wird Unicode nicht auf allen Plattformen von allen Windows Forms-Steuerelementen unterstützt.

## <a name="gdi"></a>GDI+
 Sie können GDI+ zum Zeichnen von Text mit der Lesefolge von rechts nach Links verwenden. Die <xref:System.Drawing.Graphics.DrawString%2A>-Methode, die zum Zeichnen von Text verwendet wird, unterstützt einen `StringFormat`-Parameter, den Sie auf den <xref:System.Drawing.StringFormatFlags.DirectionRightToLeft>-Member der <xref:System.Drawing.StringFormatFlags>-Enumeration festlegen können, um den Ausgangspunkt des Texts umzukehren.

## <a name="common-dialog-boxes"></a>Häufig verwendete Dialogfelder
 Systemtools wie das Dialogfeld "Datei öffnen" werden durch Windows gesteuert. Sie erben Sprachelemente vom Betriebssystem. Wenn Sie eine Windows-Version mit den richtigen Spracheinstellungen verwenden, funktionieren diese Dialogfelder auch mit bidirektionalen Sprachen.

 Ebenso werden Meldungsfelder durch das Betriebssystem gesteuert und unterstützen bidirektionalen Text. Die Beschriftungen auf den Schaltflächen der Meldungsfelder hängen von der aktuellen Spracheinstellung ab. Standardmäßig verwenden Meldungsfelder keine Rechts-nach-Links-Lesefolge. Sie können jedoch einen Parameter angeben, damit die Lesefolge bei Anzeige der Meldungsfelder geändert wird.

## <a name="righttoleft-scrollbars-and-scrollablecontrol"></a>RightToLeft, Schiebeleisten und ScrollableControl
 In Windows Forms besteht derzeit eine Einschränkung, die die ordnungsgemäße Funktion aller von <xref:System.Windows.Forms.ScrollableControl> abgeleiteten Klassen verhindert, wenn sowohl <xref:System.Windows.Forms.Control.RightToLeft%2A> aktiviert als auch <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> auf <xref:System.Windows.Forms.RightToLeft.Yes> festgelegt ist. Angenommen, Sie platzieren z. B. das <xref:System.Windows.Forms.Panel>-Steuerelement oder eine von <xref:System.Windows.Forms.Panel> abgeleitete Containerklasse (z. B. <xref:System.Windows.Forms.FlowLayoutPanel> oder <xref:System.Windows.Forms.TableLayoutPanel>) in einem Formular. Wenn Sie <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> im Container auf <xref:System.Windows.Forms.RightToLeft.Yes> und dann die <xref:System.Windows.Forms.Control.Anchor%2A>-Eigenschaft für mindestens ein Steuerelement im Container auf <xref:System.Windows.Forms.AnchorStyles.Right> festlegen, wird grundsätzlich keine Schiebeleiste angezeigt. Die von <xref:System.Windows.Forms.ScrollableControl> abgeleitete Klasse verhält sich so, als ob <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> auf <xref:System.Windows.Forms.RightToLeft.No> festgelegt wäre.

 Die einzige Problemumgehung besteht derzeit darin, <xref:System.Windows.Forms.ScrollableControl> in einem anderen <xref:System.Windows.Forms.ScrollableControl> zu schachteln. Wenn Sie beispielsweise in dieser Situation die Funktion von <xref:System.Windows.Forms.TableLayoutPanel> benötigen, können Sie es in einem <xref:System.Windows.Forms.Panel>-Steuerelement platzieren und <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> in <xref:System.Windows.Forms.Panel> auf <xref:System.Windows.Forms.RightToLeft.Yes> festlegen.

## <a name="mirroring"></a>Spiegelung
 *Spiegeln* bezeichnet die Umkehrung des Layouts von Elementen der Benutzeroberfläche, sodass diese von rechts nach links fließen. Bei einem gespiegelten Windows Form werden z. B. die Schaltflächen "Minimieren", "Maximieren" und "Schließen" nicht am rechten, sondern am linken Rand der Titelleiste angezeigt.

 Wenn die <xref:System.Windows.Forms.Control.RightToLeft%2A>-Eigenschaft eines Formulars oder eines Steuerelements auf `true` gesetzt ist, wird die Leserichtung der Elemente eines Formulars umgekehrt. Das Layout wird durch diese Einstellung jedoch nicht auf Rechts-nach-Links umgeschaltet, es findet also keine Spiegelung statt. Beispielsweise werden durch das Festlegen dieser Eigenschaft die Schaltflächen **Minimieren**, **Maximieren** und **Schließen** in der Titelleiste des Formulars nicht auf die linke Seite des Formulars verschoben. Ebenso ist Spiegeln für einige Steuerelemente, z. B. das <xref:System.Windows.Forms.TreeView>-Steuerelement, erforderlich, damit sie für Arabisch oder Hebräisch korrekt angezeigt werden. Sie können diese Steuerelemente spiegeln, indem Sie die <xref:System.Windows.Forms.Form.RightToLeftLayout%2A>-Eigenschaft festlegen.

 Von den folgenden Steuerelementen können Sie gespiegelte Versionen erzeugen:

- <xref:System.Windows.Forms.ColumnHeader.ListView%2A>

- <xref:System.Windows.Forms.Panel>

- <xref:System.Windows.Forms.StatusBar>

- <xref:System.Windows.Forms.TabControl>

- <xref:System.Windows.Forms.TabPage>

- <xref:System.Windows.Forms.ToolBar>

- <xref:System.Windows.Forms.TreeView>

 Einige Steuerelemente sind versiegelt. Es ist deshalb nicht möglich, neue Steuerelemente von ihnen abzuleiten. Dazu gehören das <xref:System.Windows.Forms.ImageList>-Steuerelement und das <xref:System.Windows.Forms.ProgressBar>-Steuerelement.

## <a name="see-also"></a>Weitere Informationen

- [Bidirektionale Unterstützung für ASP.NET-Webanwendungen](https://docs.microsoft.com/previous-versions/aspnet/6eedwbtt(v=vs.100))
