---
title: "Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen in WPF | Microsoft Docs"
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
  - "Anordnen von Steuerelementen"
  - "Hybridanwendungen [WPF-Interoperabilität]"
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
caps.latest.revision: 31
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 28
---
# Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen in WPF
In dieser exemplarischen Vorgehensweise wird gezeigt, wie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Layoutfeatures verwendet werden, um [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelemente in einer Hybridanwendung anzuordnen.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen des Projekts.  
  
-   Verwenden der Standardlayouteinstellungen  
  
-   Größenanpassung an den Inhalt  
  
-   Verwenden der absoluten Positionierung  
  
-   Explizites Angeben der Größe  
  
-   Festlegen von Layouteigenschaften  
  
-   Grundlagen der Z\-Reihenfolge\-Einschränkungen  
  
-   Andocken  
  
-   Einstellen der Sichtbarkeit  
  
-   Hosten eines Steuerelements, das nicht gestreckt wird  
  
-   Skalieren  
  
-   Drehen  
  
-   Einstellen von Textabständen und Rändern  
  
-   Verwenden von dynamischen Layoutcontainern  
  
 Eine vollständige Codeauflistung der Aufgaben, die in dieser exemplarischen Vorgehensweise veranschaulicht wurden, finden Sie unter [Beispiel für das Anordnen von Windows Forms\-Steuerelementen in WPF](http://go.microsoft.com/fwlink/?LinkID=159971).  
  
 Anschließend werden Sie die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Layoutfeatures in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-basierten Anwendungen verstehen.  
  
## Vorbereitungsmaßnahmen  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## Erstellen des Projekts  
  
#### So erstellen Sie das Projekt und richten es ein  
  
1.  Erstellen Sie ein WPF\-Anwendungsprojekt mit dem Namen `WpfLayoutHostingWf`.  
  
2.  Fügen Sie im Projektmappen\-Explorer Verweise auf die folgenden Assemblys hinzu.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
    -   System.Drawing  
  
3.  Doppelklicken Sie auf "MainWindow.xaml", um die Datei in der XAML\-Ansicht zu öffnen.  
  
4.  Fügen Sie im <xref:System.Windows.Window>\-Element die folgende [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Namespacezuordnung hinzu.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  Legen Sie im <xref:System.Windows.Controls.Grid>\-Element die <xref:System.Windows.Controls.Grid.ShowGridLines%2A>\-Eigenschaft auf `true` fest, und definieren Sie fünf Zeilen und drei Spalten.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## Verwenden der Standardlayouteinstellungen  
 Standardmäßig behandelt das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element das Layout für das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelement.  
  
#### So verwenden Sie Standardlayouteinstellungen  
  
1.  Kopieren Sie den folgenden XAML\-Code in das <xref:System.Windows.Controls.Grid>\-Element.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  Das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-<xref:System.Windows.Forms.Button?displayProperty=fullName>\-Steuerelement wird im <xref:System.Windows.Controls.Canvas> angezeigt.  Die Größe des gehosteten Steuerelements basiert auf dessen Inhalt, und die Größe des <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Elements wird an das gehostete Steuerelement angepasst.  
  
## Größenanpassung an den Inhalt  
 Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element stellt sicher, dass die Größe des gehosteten Steuerelements so angepasst wird, dass sein Inhalt ordnungsgemäß angezeigt wird.  
  
#### So passen Sie die Größe an den Inhalt an  
  
1.  Kopieren Sie den folgenden XAML\-Code in das <xref:System.Windows.Controls.Grid>\-Element.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  Die Größe der zwei neuen Schaltflächen wird so angepasst, dass die längere Textzeichenfolge und der größere Schriftgrad ordnungsgemäß angezeigt werden, und die Größe der <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Elemente wird an die gehosteten Steuerelemente angepasst.  
  
## Verwenden der absoluten Positionierung  
 Mit der absoluten Positionierung können Sie das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element beliebig in der Benutzeroberfläche einfügen.  
  
#### So verwenden Sie die absolute Positionierung  
  
1.  Kopieren Sie den folgenden XAML\-Code in das <xref:System.Windows.Controls.Grid>\-Element.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element wird 20 Pixel vom oberen Rand der Rasterzelle und 20 Pixel vom linken Rand platziert.  
  
## Explizites Angeben der Größe  
 Sie können die Größe des <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Elements mit der <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft und der <xref:System.Windows.FrameworkElement.Height%2A>\-Eigenschaft angeben.  
  
#### So geben Sie die Größe explizit an  
  
1.  Kopieren Sie den folgenden XAML\-Code in das <xref:System.Windows.Controls.Grid>\-Element.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element wird auf eine Größe von 50 x 70 Pixel \(Breite x Höhe\) festgelegt und liegt damit unter den Standardlayouteinstellungen.  Der Inhalt des [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelements wird entsprechend neu angeordnet.  
  
## Festlegen von Layouteigenschaften  
 Legen Sie layoutbezogene Eigenschaften immer für das gehostete Steuerelement fest, und verwenden Sie dabei die Eigenschaften des <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Elements.  Das Festlegen der Layouteigenschaften direkt für das gehostete Steuerelement führt zu unbeabsichtigten Ergebnissen.  
  
 Das Festlegen der layoutbezogenen Eigenschaften für das gehostete Steuerelement in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hat keine Auswirkungen.  
  
#### So zeigen Sie die Auswirkungen des Festlegens der Eigenschaften für das gehostete Steuerelement an  
  
1.  Kopieren Sie den folgenden XAML\-Code in das <xref:System.Windows.Controls.Grid>\-Element.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2.  Doppelklicken Sie im Projektmappen\-Explorer auf "MainWindow.xaml.  vb" oder "MainWindow.xaml.cs", um die Datei im Code\-Editor zu öffnen.  
  
3.  Kopieren Sie den folgenden Code in die `MainWindow`\-Klassendefinition.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]  
  
4.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
5.  Klicken Sie auf die Schaltfläche **Hier klicken**.  Der `button1_Click`\-Ereignishandler legt die <xref:System.Windows.Forms.Control.Top%2A>\-Eigenschaft und die <xref:System.Windows.Forms.Control.Left%2A>\-Eigenschaft für das gehostete Steuerelement fest.  Dadurch wird das gehostete Steuerelement innerhalb des <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Elements neu angeordnet.  Der Host behält den gleichen Bildschirmbereich bei, das gehostete Steuerelement wird jedoch abgeschnitten.  Das gehostete Steuerelement sollte jedoch immer das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element ausfüllen.  
  
## Grundlagen der Z\-Reihenfolge\-Einschränkungen  
 Standardmäßig werden sichtbare <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Elemente immer an der obersten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Elemente gezeichnet, und sie sind mit Z\-Reihenfolge nicht beeinflusst.  Um Z Reihenfolge zu aktivieren, legen Sie die <xref:System.Windows.Interop.HwndHost.IsRedirected%2A>\-Eigenschaft fest <xref:System.Windows.Forms.Integration.WindowsFormsHost> und die <xref:System.Windows.Interop.HwndHost.CompositionMode%2A>\-Eigenschaft auf <xref:System.Windows.Interop.CompositionMode.Full> oder <xref:System.Windows.Interop.CompositionMode.OutputOnly>auszurichten.  
  
#### Um das standardmäßige finden z\-Reihenfolgen\-Verhalten  
  
1.  Kopieren Sie den folgenden XAML\-Code in das <xref:System.Windows.Controls.Grid>\-Element.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element wird über das Bezeichnungselement gezeichnet.  
  
#### Um das z\-Reihenfolgen\-Verhalten finden, wenn IsRedirected auf true festgelegt ist  
  
1.  Ersetzen Sie das vorherige z\-Reihenfolgen\-Beispiel durch den folgenden XAML\-Code.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#8b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#8b)]  
  
     Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  Die Bezeichnung wird über dem Element <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element gezeichnet.  
  
## Andocken  
 Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element unterstützt das Andocken von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Legen Sie die angefügte <xref:System.Windows.Controls.DockPanel.Dock%2A>\-Eigenschaft so fest, dass das gehostete Steuerelement in einem <xref:System.Windows.Controls.DockPanel>\-Element angedockt wird.  
  
#### So docken Sie ein gehostetes Steuerelement an  
  
1.  Kopieren Sie den folgenden XAML\-Code in das <xref:System.Windows.Controls.Grid>\-Element.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element wird an der rechten Seite des <xref:System.Windows.Controls.DockPanel>\-Elements angedockt.  
  
## Einstellen der Sichtbarkeit  
 Sie können das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelement ausblenden oder reduzieren, indem Sie die <xref:System.Windows.UIElement.Visibility%2A>\-Eigenschaft für das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element festlegen.  Wenn ein Steuerelement nicht sichtbar ist, wird es nicht angezeigt, aber es belegt Platz im Layoutbereich.  Wenn ein Steuerelement reduziert ist, wird es nicht angezeigt und belegt auch keinen Platz im Layoutbereich.  
  
#### So legen Sie die Sichtbarkeit eines gehosteten Steuerelements fest  
  
1.  Kopieren Sie den folgenden XAML\-Code in das <xref:System.Windows.Controls.Grid>\-Element.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]  
  
2.  Kopieren Sie in "MainWindow.xaml.vb" oder "MainWindow.xaml.cs" den folgenden Code in die Klassendefinition.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]  
  
3.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
4.  Klicken Sie auf die Schaltfläche **Zum Ausblenden klicken**, um das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element auszublenden.  
  
5.  Klicken Sie auf die Schaltfläche **Zum Reduzieren klicken**, um das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element vollständig im Layout auszublenden.  Wenn das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelement reduziert ist, werden die umgebenden Elemente neu angeordnet, um dessen Bereich einzunehmen.  
  
## Hosten eines Steuerelements, das nicht gestreckt wird  
 Einige [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelemente haben eine feste Größe und können nicht gestreckt werden, um den verfügbaren Bereich im Layout auszufüllen.  Das <xref:System.Windows.Forms.MonthCalendar>\-Steuerelement zeigt beispielsweise einen Monat in einem festen Bereich an.  
  
#### So hosten Sie ein Steuerelement, das nicht gestreckt wird  
  
1.  Kopieren Sie den folgenden XAML\-Code in das <xref:System.Windows.Controls.Grid>\-Element.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element wird in der Rasterzeile zentriert. Es wird jedoch nicht gestreckt, um den verfügbaren Bereich auszufüllen.  Wenn das Fenster groß genug ist, werden möglicherweise zwei oder mehr Monate vom gehosteten <xref:System.Windows.Forms.MonthCalendar>\-Steuerelement angezeigt, die jedoch in der Zeile zentriert sind.  Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Layoutmodul zentriert Elemente, deren Größe nicht angepasst werden kann, um den verfügbaren Bereich auszufüllen.  
  
## Skalieren  
 Im Gegensatz zu [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Elementen sind die meisten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelemente nicht kontinuierlich skalierbar.  Standardmäßig skaliert das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element sein gehostetes Steuerelement, sofern dies möglich ist.  Um klar entwickelte Skalierung zu aktivieren, legen Sie die <xref:System.Windows.Interop.HwndHost.IsRedirected%2A>\-Eigenschaft fest <xref:System.Windows.Forms.Integration.WindowsFormsHost> und die <xref:System.Windows.Interop.HwndHost.CompositionMode%2A>\-Eigenschaft auf <xref:System.Windows.Interop.CompositionMode.Full> oder <xref:System.Windows.Interop.CompositionMode.OutputOnly>auszurichten.  
  
#### So fügen Sie ein gehostetes Steuerelement mithilfe des Standardverhaltens skalieren  
  
1.  Kopieren Sie den folgenden XAML\-Code in das <xref:System.Windows.Controls.Grid>\-Element.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  Das gehostete Steuerelement und die umgebenden Elemente werden um den Faktor 0,5 skaliert.  Die Schriftart des gehosteten Steuerelements wird jedoch nicht skaliert.  
  
#### So fügen Sie ein gehostetes Steuerelement durch Festlegen von IsRedirected skalieren True  
  
1.  Ersetzen Sie das vorherige Beispiel mit Skalierungs durch den folgenden XAML\-Code.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#12b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#12b)]  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  Das gehostete Steuerelement, dessen umgebenden Elemente und die Schriftart des gehosteten Steuerelements wird durch den Faktor 0.5 skaliert.  
  
## Drehen  
 Im Gegensatz zu [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Elementen unterstützen [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelemente keine Drehung.  Standardmäßig dreht sich das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element nicht mit anderen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Elementen, wenn eine Drehungstransformation angewendet wird.  Jeder andere Drehungswert als 180 Grad löst das <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>\-Ereignis aus.  Um das Drehen zu jedem Winkel zu aktivieren, legen Sie die <xref:System.Windows.Interop.HwndHost.IsRedirected%2A>\-Eigenschaft fest <xref:System.Windows.Forms.Integration.WindowsFormsHost> und die <xref:System.Windows.Interop.HwndHost.CompositionMode%2A>\-Eigenschaft auf <xref:System.Windows.Interop.CompositionMode.Full> oder <xref:System.Windows.Interop.CompositionMode.OutputOnly>auszurichten.  
  
#### So zeigen Sie die Auswirkung der Drehung in einer Hybridanwendung an  
  
1.  Kopieren Sie den folgenden XAML\-Code in das <xref:System.Windows.Controls.Grid>\-Element.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  Das gehostete Steuerelement wird nicht gedreht. Die umgebenden Elemente werden jedoch um 180 Grad gedreht.  Die Größe des Fensters muss möglicherweise geändert werden, damit die Elemente sichtbar sind.  
  
#### So zeigen Sie die Auswirkung der Drehung in einer Hybridanwendung ermitteln, ob IsRedirected auf true festgelegt ist  
  
1.  Ersetzen Sie das vorherige Beispiel mit Drehungs durch den folgenden XAML\-Code.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#13b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#13b)]  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  Das gehostete Steuerelement wird deaktiviert.  Beachten Sie, dass die <xref:System.Windows.Media.RotateTransform.Angle%2A>\-Eigenschaft auf einen beliebigen Wert festgelegt werden kann.  Die Größe des Fensters muss möglicherweise geändert werden, damit die Elemente sichtbar sind.  
  
## Einstellen von Textabständen und Rändern  
 Textabstände und Ränder im [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Layout sind mit den Textabständen und Rändern in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] vergleichbar.  Legen Sie einfach die <xref:System.Windows.Controls.Control.Padding%2A>\-Eigenschaft und die <xref:System.Windows.FrameworkElement.Margin%2A>\-Eigenschaft für das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element fest.  
  
#### So legen Sie Textabstände und Ränder für ein gehostetes Steuerelement fest  
  
1.  Kopieren Sie den folgenden XAML\-Code in das <xref:System.Windows.Controls.Grid>\-Element.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]  
    [!code-xml[WpfLayoutHostingWfWithXaml#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  Die Einstellungen für Textabstände und Ränder werden wie in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] auf die gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelemente angewendet.  
  
## Verwenden von dynamischen Layoutcontainern  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] stellt zwei dynamische Layoutcontainer, <xref:System.Windows.Forms.FlowLayoutPanel> und <xref:System.Windows.Forms.TableLayoutPanel>, zur Verfügung.  Sie können diese Container auch in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Layouts verwenden.  
  
#### So verwenden Sie einen dynamischen Layoutcontainer  
  
1.  Kopieren Sie den folgenden XAML\-Code in das <xref:System.Windows.Controls.Grid>\-Element.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]  
  
2.  Kopieren Sie in "MainWindow.xaml.vb" oder "MainWindow.xaml.cs" den folgenden Code in die Klassendefinition.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]  
  
3.  Fügen Sie dem Konstruktor einen Aufruf der `InitializeFlowLayoutPanel`\-Methode hinzu.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element füllt <xref:System.Windows.Controls.DockPanel> aus, und <xref:System.Windows.Forms.FlowLayoutPanel> ordnet seine untergeordneten Steuerelemente in der Standard\-<xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> an.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [WPF\-Designer](http://msdn.microsoft.com/de-de/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Überlegungen zum Layout für das WindowsFormsHost\-Element](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)   
 [Beispiel für das Anordnen von Windows Forms\-Steuerelementen in WPF](http://go.microsoft.com/fwlink/?LinkID=159971)   
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms\-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF\-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)