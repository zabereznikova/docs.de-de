---
title: "Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF | Microsoft Docs"
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
  - "Zusammengesetzte Steuerelemente, Hosting in WPF"
  - "Hosten eines Windows Forms-Steuerelements in WPF"
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
caps.latest.revision: 33
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 30
---
# Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt eine umfangreiche Umgebung zum Erstellen von Anwendungen bereit.  Wenn Sie allerdings bereits erheblichen Aufwand für [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Code betrieben haben, kann es effektiver sein, zumindest einen Teil dieses Codes in Ihrer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung wieder zu verwenden, anstatt ihn von Grund auf neu zu schreiben.  Das häufigste Szenario ist, dass Sie über vorhandene [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]\-Steuerelemente verfügen.  In einigen Fällen haben Sie möglicherweise noch nicht einmal Zugriff auf den Quellcode für diese Steuerelemente.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt ein einfaches Verfahren bereit, um diese Steuerelemente in einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung zu hosten.  Zum Beispiel können Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] für den Großteil der Programmierung verwenden, während sie die spezialisierten <xref:System.Windows.Forms.DataGridView>\-Steuerelemente hosten.  
  
 In dieser exemplarischen Vorgehensweise wird eine Anwendung vorgestellt, die ein zusammengesetztes [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]\-Steuerelement hostet, um die Dateneingabe in einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung auszuführen.  Das zusammengesetzte Steuerelement ist in einer DLL gepackt.  Diese allgemeine Prozedur kann auf komplexere Anwendungen und Steuerelemente erweitert werden.  Diese exemplarische Vorgehensweise ist hinsichtlich Darstellung und Funktionalität nahezu identisch mit [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF\-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md).  Der Hauptunterschied liegt in einer Umkehrung des Hostingszenarios.  
  
 Die exemplarische Vorgehensweise ist in zwei Abschnitte unterteilt.  Im ersten Abschnitt wird kurz die Implementierung des zusammengesetzten [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]\-Steuerelements beschrieben.  Im zweiten Abschnitt wird detailliert erläutert, wie das zusammengesetzte Steuerelement in einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung gehostet wird, Ereignisse vom Steuerelement empfangen werden und auf einige Eigenschaften des Steuerelements zugegriffen wird.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Implementieren des zusammengesetzten Windows Forms\-Steuerelements  
  
-   Implementieren der WPF\-Hostanwendung  
  
 Eine vollständige Codeauflistung der Aufgaben, die in dieser exemplarischen Vorgehensweise veranschaulicht wurden, finden Sie unter [Beispiel für das Hosten eines zusammengesetzten Windows Forms\-Steuerelements in Windows Presentation Foundation](http://go.microsoft.com/fwlink/?LinkID=159999).  
  
## Vorbereitungsmaßnahmen  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## Implementieren des zusammengesetzten Windows Forms\-Steuerelements  
 Das in diesem Beispiel verwendete zusammengesetzte [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]\-Steuerelement ist ein einfaches Dateneingabeformular.  Dieses Formular nimmt den Namen und die Adresse des Benutzers auf und verwendet dann ein benutzerdefiniertes Ereignis, um diese Informationen an den Host zurückzugeben.  Die folgende Abbildung zeigt das gerenderte Steuerelement.  
  
 ![Einfaches Windows Forms&#45;Steuerelement](../../../../docs/framework/wpf/advanced/media/wfcontrol.png "WFControl")  
Zusammengesetztes Windows Forms\-Steuerelement  
  
### Erstellen des Projekts  
 So starten Sie das Projekt  
  
1.  Starten Sie [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], und öffnen Sie das Dialogfeld **Neues Projekt**.  
  
2.  Wählen Sie in der Kategorie "Fenster" die Vorlage **Windows Forms\-Steuerelementbibliothek** aus.  
  
3.  Geben Sie für das neue Projekt den Namen `MyControls` ein.  
  
4.  Geben Sie für den Speicherort einen passend benannten Ordner der obersten Ebene an, z. B. `WpfHostingWindowsFormsControl`.  Später legen Sie die Hostanwendung in diesem Ordner ab.  
  
5.  Klicken Sie auf **OK**, um das Projekt zu erstellen.  Das Standardprojekt enthält ein einzelnes Steuerelement mit dem Namen `UserControl1`.  
  
6.  Benennen Sie im Projektmappen\-Explorer `UserControl1` in `MyControl1` um.  
  
 Das Projekt sollte Verweise auf die folgenden System\-DLLs aufweisen.  Wenn diese DLLs nicht standardmäßig eingeschlossen sind, fügen Sie sie dem Projekt hinzu.  
  
-   System  
  
-   System.Data  
  
-   System.Drawing  
  
-   System.Windows.Forms  
  
-   System.Xml  
  
### Hinzufügen von Steuerelementen zum Formular  
 So fügen Sie dem Formular Steuerelemente hinzu  
  
-   Öffnen Sie `MyControl1` im Designer.  
  
 Fügen Sie fünf <xref:System.Windows.Forms.Label>\-Steuerelemente und die entsprechenden <xref:System.Windows.Forms.TextBox>\-Steuerelemente im Formular hinzu, und passen Sie ihre Größe und Anordnung wie in der vorhergehenden Abbildung an.  Im Beispiel werden die <xref:System.Windows.Forms.TextBox>\-Steuerelemente folgendermaßen benannt:  
  
-   `txtName`  
  
-   `txtAddress`  
  
-   `txtCity`  
  
-   `txtState`  
  
-   `txtZip`  
  
 Fügen Sie zwei <xref:System.Windows.Forms.Button>\-Steuerelemente mit den Bezeichnungen **OK** und **Cancel** hinzu.  Im Beispiel lauten die Schaltflächennamen `btnOK` bzw. `btnCancel`.  
  
### Implementieren des unterstützenden Codes  
 Öffnen Sie das Formular in der Codeansicht.  Das Steuerelement gibt die gesammelten Daten an seinen Host zurück, indem es das benutzerdefinierte `OnButtonClick`\-Ereignis auslöst.  Die Daten sind im Ereignisargumentobjekt enthalten.  Der folgende Code zeigt die Ereignis\- und Delegatdeklaration.  
  
 Fügen Sie der `MyControl1`\-Klasse den folgenden Code hinzu.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]  
  
 Die `MyControlEventArgs`\-Klasse enthält die Informationen, die an den Host zurückgegeben werden sollen.  
  
 Fügen Sie dem Formular die folgende Klasse hinzu.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]  
  
 Wenn der Benutzer auf die Schaltfläche **OK** oder **Cancel** klickt, erstellen die <xref:System.Windows.Forms.Control.Click>\-Ereignishandler ein `MyControlEventArgs`\-Objekt, das die Daten enthält und das `OnButtonClick`\-Ereignis auslöst.  Der einzige Unterschied zwischen den zwei Handlern ist die `IsOK`\-Eigenschaft des Ereignisarguments.  Diese Eigenschaft ermöglicht es dem Host, zu bestimmen, auf welche Schaltfläche geklickt wurde.  Sie ist für die Schaltfläche **OK** auf `true` und für die Schaltfläche **Cancel** auf `false` festgelegt.  Der folgende Code zeigt die beiden Schaltflächenhandler.  
  
 Fügen Sie der `MyControl1`\-Klasse den folgenden Code hinzu.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]  
  
### Vergeben eines starken Namens für die Assembly und Erstellen der Assembly  
 Damit von einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung auf diese Assembly verwiesen wird, muss sie einen starken Namen haben.  Um einen starken Namen zu erstellen, erstellen Sie mit "Sn.exe" eine Schlüsseldatei, und fügen Sie sie dem Projekt hinzu.  
  
1.  Öffnen Sie eine [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]\-Eingabeaufforderung.  Klicken Sie dazu auf das Menü **Start**, und wählen Sie dann **Alle Programme\/Microsoft Visual Studio 2010\/Visual Studio Tools\/Visual Studio\-Eingabeaufforderung** aus.  Dies startet ein Konsolenfenster mit benutzerdefinierten Umgebungsvariablen.  
  
2.  Verwenden Sie an der Eingabeaufforderung den `cd`\-Befehl, um zum Projektordner zu wechseln.  
  
3.  Generieren Sie eine Schlüsseldatei mit dem Namen MyControls.snk, indem Sie den folgenden Befehl ausführen.  
  
    ```  
    Sn.exe -k MyControls.snk  
    ```  
  
4.  Um die Schlüsseldatei dem Projekt hinzuzufügen, klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf den Projektnamen, und klicken Sie dann auf **Eigenschaften**.  Klicken Sie im Projekt\-Designer auf die Registerkarte **Signierung**, aktivieren Sie das Kontrollkästchen **Assembly signieren**, und navigieren Sie dann zur Schlüsseldatei.  
  
5.  Erstellen Sie die Projektmappe.  Der Build erzeugt eine DLL mit dem Namen MyControls.dll.  
  
## Implementieren der WPF\-Hostanwendung  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Hostanwendung verwendet das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Steuerelement, um `MyControl1` zu hosten.  Die Anwendung behandelt das `OnButtonClick`\-Ereignis, um die Daten vom Steuerelement zu empfangen.  Sie enthält außerdem eine Auflistung von Optionsschaltflächen, mit denen Sie einige der Eigenschaften des Steuerelements in der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung ändern können.  Die folgende Abbildung zeigt die fertige Anwendung.  
  
 ![Ein in einer WPF&#45;Seite eingebettetes Steuerelement](../../../../docs/framework/wpf/advanced/media/avalonhost.png "AvalonHost")  
Vollständige Anwendung mit in der WPF\-Anwendung eingebettetem Steuerelement  
  
### Erstellen des Projekts  
 So starten Sie das Projekt  
  
1.  Öffnen Sie [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], und wählen Sie **Neues Projekt** aus.  
  
2.  Wählen Sie in der Kategorie "Fenster" die Vorlage **WPF\-Anwendung** aus.  
  
3.  Geben Sie für das neue Projekt den Namen `WpfHost` ein.  
  
4.  Geben Sie für den Speicherort den Ordner der obersten Ebene an, der auch das Projekt "MyControls" enthält.  
  
5.  Klicken Sie auf **OK**, um das Projekt zu erstellen.  
  
 Außerdem müssen Sie Verweise auf die DLL hinzufügen, die `MyControl1` und andere Assemblys enthält.  
  
1.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf den Projektnamen, und klicken Sie dann auf **Verweis hinzufügen**.  
  
2.  Klicken Sie auf die Registerkarte **Durchsuchen**, und navigieren Sie zu dem Ordner, der "MyControls.dll" enthält.  In dieser exemplarischen Vorgehensweise ist dies der Ordner "MyControls\\bin\\Debug".  
  
3.  Wählen Sie "MyControls.dll" aus, und klicken Sie dann auf **OK**.  
  
4.  Fügen Sie einen Verweis auf die WindowsFormsIntegration\-Assembly, die WindowsFormsIntegration.dll genannt wird, hinzu.  
  
### Implementieren des grundlegenden Layouts  
 Die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] der Hostanwendung wird in "MainWindow.xaml" implementiert.  Diese Datei enthält [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Markup, das das Layout definiert, und hostet das [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]\-Steuerelement.  Die Anwendung ist in drei Bereiche unterteilt:  
  
-   Bereich **Steuerelementeigenschaften**, der eine Auflistung von Optionsschaltflächen enthält, mit denen Sie verschiedene Eigenschaften des gehosteten Steuerelements ändern können.  
  
-   Bereich **Steuerelementdaten**, der verschiedene <xref:System.Windows.Controls.TextBlock>\-Elemente enthält, die die vom gehosteten Steuerelement zurückgegebenen Daten anzeigen.  
  
-   Das gehostete Steuerelement selbst.  
  
 Der folgende XAML\-Code zeigt das grundlegende Layout.  Das zum Hosten von `MyControl1` erforderliche Markup ist in diesem Beispiel nicht enthalten, wird aber später erläutert.  
  
 Ersetzen Sie den XAML\-Code in "MainWindow.xaml" durch den folgenden Code:  Wenn Sie Visual Basic verwenden, ändern Sie die Klasse in `x:Class="MainWindow"`.  
  
 [!code-xml[WpfHostingWindowsFormsControl#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]  
  
 Das erste <xref:System.Windows.Controls.StackPanel>\-Element enthält verschieden Gruppen von <xref:System.Windows.Controls.RadioButton>\-Steuerelementen, mit denen Sie verschiedene Standardeigenschaften des gehosteten Steuerelements ändern können.  Dem folgt ein <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element, das `MyControl1` hostet.  Das letzte <xref:System.Windows.Controls.StackPanel>\-Element enthält verschiedene <xref:System.Windows.Controls.TextBlock>\-Elemente, die die vom gehosteten Steuerelement zurückgegebenen Daten anzeigen.  Durch die Reihenfolge der Elemente und die Attributeinstellungen <xref:System.Windows.Controls.DockPanel.Dock%2A> und <xref:System.Windows.FrameworkElement.Height%2A> wird das gehostete Steuerelement ohne Lücken oder Verzerrungen in das Fenster eingebettet.  
  
#### Hosten des Steuerelements  
 Der Schwerpunkt der folgenden bearbeiteten Version des vorherigen XAML\-Codes liegt auf den Elementen, die zum Hosten von `MyControl1` benötigt werden.  
  
 [!code-xml[WpfHostingWindowsFormsControl#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]  
[!code-xml[WpfHostingWindowsFormsControl#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]  
  
 Das `xmlns`\-Namespace\-Zuordnungsattribut erstellt einen Verweis auf den `MyControls`\-Namespace, der das gehostete Steuerelement enthält.  Diese Zuordnung ermöglicht es Ihnen, `MyControl1` als `<mcl:MyControl1>` in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] darzustellen.  
  
 Zwei Elemente im XAML\-Code behandeln das Hosting:  
  
-   `WindowsFormsHost` stellt das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element dar, das das Hosten eines [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]\-Steuerelements in einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung ermöglicht.  
  
-   `mcl:MyControl1`, das `MyControl1` darstellt, wird der untergeordneten Auflistung des <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Elements hinzugefügt.  Dadurch wird dieses [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]\-Steuerelement als Teil des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Fensters gerendert, und Sie können über die Anwendung Daten mit dem Steuerelement austauschen.  
  
### Implementieren der Code\-Behind\-Datei  
 Die CodeBehind\-Datei \("MainWindow.xaml.vb" oder "MainWindow.xaml.cs"\) enthält den prozeduralen Code, der die im vorherigen Abschnitt erläuterten Funktionen der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] implementiert.  Die Hauptaufgaben sind:  
  
-   Anfügen eines Ereignishandlers an das `OnButtonClick`\-Ereignis von `MyControl1`.  
  
-   Ändern verschiedener Eigenschaften von `MyControl1` auf Grundlage der Auflistung von Optionsschaltflächen.  
  
-   Anzeigen der vom Steuerelement gesammelten Daten.  
  
#### Initialisieren der Anwendung  
 Der Code für die Initialisierung ist in einem Ereignishandler für das <xref:System.Windows.FrameworkElement.Loaded>\-Ereignis des Fensters enthalten und fügt einen Ereignishandler an das `OnButtonClick`\-Ereignis des Steuerelements an.  
  
 Fügen Sie in "MainWindow.xaml.vb" bzw. "MainWindow.xaml.cs" der `MainWindow`\-Klasse den folgenden Code hinzu.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]  
  
 Da `MyControl1` im zuvor erläuterten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Code zur Auflistung untergeordneter Elemente des <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Elements hinzugefügt wurde, können Sie das <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> des <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Elements umwandeln, um den Verweis auf `MyControl1` abzurufen.  Sie können dann diesen Verweis verwenden, um einen Ereignishandler an `OnButtonClick` anzufügen.  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> stellt nicht nur einen Verweis auf das Steuerelement selbst bereit, sondern macht eine Reihe von Eigenschaften des Steuerelements verfügbar, die Sie in der Anwendung ändern können.  Im Initialisierungscode werden diese Werte privaten globalen Variablen zur späteren Verwendung in der Anwendung zugewiesen.  
  
 Damit Sie mühelos auf die Typen in der `MyControls`\-DLL zugreifen können, fügen Sie am Anfang der Datei die folgende `Imports`\- oder `using`\-Anweisung hinzu.  
  
```vb  
Imports MyControls  
```  
  
```csharp  
using MyControls;  
```  
  
#### Behandeln des OnButtonClick\-Ereignisses  
 `MyControl1` löst das `OnButtonClick`\-Ereignis aus, wenn der Benutzer auf eine der Schaltflächen des Steuerelements klickt.  
  
 Fügen Sie der `MainWindow`\-Klasse den folgenden Code hinzu.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]  
  
 Die Daten in den Textfeldern werden in das `MyControlEventArgs`\-Objekt gepackt.  Wenn der Benutzer auf die Schaltfläche **OK** klickt, extrahiert der Ereignishandler die Daten und zeigt sie im Bereich unter `MyControl1` an.  
  
#### Ändern der Eigenschaften des Steuerelements  
 Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element macht mehrere Standardeigenschaften des gehosteten Steuerelements verfügbar.  Daher können Sie die Darstellung des Steuerelements entsprechend dem Stil Ihrer Anwendung ändern.  Die Gruppen von Optionsschaltflächen im linken Bereich ermöglichen die Änderung mehrerer Farb\- und Schrifteigenschaften.  Jede Schaltflächengruppe besitzt einen Handler für das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignis, der die vom Benutzer ausgewählten Optionsschaltflächen ermittelt und die entsprechende Eigenschaft für das Steuerelement ändert.  
  
 Fügen Sie der `MainWindow`\-Klasse den folgenden Code hinzu.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 Erstellen Sie die Anwendung, und führen Sie sie aus.  Fügen Sie im zusammengesetzten Windows Forms\-Steuerelement Text hinzu, und klicken Sie dann auf **OK**.  Der Text wird in den Beschriftungen angezeigt.  Klicken Sie auf die verschiedenen Optionsfelder, um die Auswirkung auf das Steuerelement zu überprüfen.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [WPF\-Designer](http://msdn.microsoft.com/de-de/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Exemplarische Vorgehensweise: Hosten eines Windows Forms\-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)   
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF\-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)