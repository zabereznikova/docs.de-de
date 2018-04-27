---
title: 'Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
caps.latest.revision: 33
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fe706e92223d868476ac438e98b16cf07bb21259
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a>Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt eine umfangreiche Umgebung zum Erstellen von Anwendungen bereit. Wenn Sie haben jedoch eine erhebliche Investition [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Code möglich effektiver mindestens wiederverwenden Teil des Codes in Ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung statt sie von Grund auf neu zu schreiben. Das häufigste Szenario ist, wenn Sie die vorhandenen Windows Forms-Steuerelemente haben. In einigen Fällen können Sie vielleicht gar nicht mehr auf den Quellcode für diese Steuerelemente zugreifen. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Stellt ein einfaches Verfahren zum Hosten von solche Steuerelemente in einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung. Beispielsweise können Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] für den Großteil der Programmierung während des Hostens Ihre spezielle <xref:System.Windows.Forms.DataGridView> Steuerelemente.  
  
 Diese exemplarische Vorgehensweise führt Sie schrittweise durch eine Anwendung, ein zusammengesetztes Windows Forms-Steuerelements zum Durchführen der Dateneingabe im hostet, eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung. Das zusammengesetzte Steuerelement ist in eine DLL verpackt. Dieses allgemeine Verfahren kann für komplexere Anwendungen und Steuerelemente erweitert werden. Diese exemplarische Vorgehensweise dient zur Darstellung und Funktionalität auf fast identisch sind [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md). Der Hauptunterschied besteht darin, dass das Hosting-Szenario umgekehrt ist.  
  
 Diese exemplarische Vorgehensweise ist in zwei Abschnitte unterteilt. Der erste Abschnitt beschreibt kurz die Implementierung des zusammengesetzten Windows Forms-Steuerelements. Im zweite Abschnitt wird ausführlich erläutert, wie zum Hosten des zusammengesetzten Steuerelements in einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung, aus dem Steuerelement Ereignisse empfangen und Zugriff auf einige der Eigenschaften des Steuerelements.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Implementieren des zusammengesetzten Windows Forms-Steuerelements.  
  
-   Implementieren der WPF-Hostanwendung.  
  
 Vollständige Codeliste der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF-Beispiel](http://go.microsoft.com/fwlink/?LinkID=159999).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]  
  
## <a name="implementing-the-windows-forms-composite-control"></a>Implementieren des zusammengesetzten Windows Forms-Steuerelements  
 In diesem Beispiel verwendete zusammengesetzte Windows Forms-Steuerelement ist eine einfache Dateneingabe-Form. Dieses Formular erfasst den Namen und die Adresse des Benutzers und gibt diese Information unter Verwendung eines benutzerdefinierten Ereignisses an den Host zurück. Die folgende Abbildung zeigt das gerenderte Steuerelement.  
  
 ![Einfache Windows Forms-Steuerelemente](../../../../docs/framework/wpf/advanced/media/wfcontrol.gif "WFControl")  
Zusammengesetztes Windows Forms-Steuerelement  
  
### <a name="creating-the-project"></a>Erstellen des Projekts  
 Um das Projekt zu starten:  
  
1.  Starten Sie [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], und öffnen Sie die **neues Projekt** (Dialogfeld).  
  
2.  Wählen Sie in der Kategorie "Fenster" die **Windows Forms-Steuerelementbibliothek** Vorlage.  
  
3.  Geben Sie dem neuen Projekt den Namen `MyControls`.  
  
4.  Geben Sie für den Speicherort einen bequem benannten auf oberster Ebene Ordner ein, z. B. `WpfHostingWindowsFormsControl`. Sie werden die Host-Anwendung später in diesem Ordner ablegen.  
  
5.  Klicken Sie auf **OK**, um das Projekt zu erstellen. Das Standardprojekt enthält ein einzelnes Steuerelement mit dem Namen `UserControl1`.  
  
6.  Benennen Sie im Projektmappen-Explorer `UserControl1` auf `MyControl1`.  
  
 Das Projekt sollte Verweise auf die folgenden System-DLLs aufweisen. Sollten eine oder mehrere dieser DLLs nicht standardmäßig enthalten sein, fügen Sie diese manuell zum Projekt hinzu.  
  
-   System  
  
-   <legacyBold>System.Data</legacyBold>  
  
-   System.Drawing  
  
-   System.Windows.Forms  
  
-   System.Xml  
  
### <a name="adding-controls-to-the-form"></a>Hinzufügen von Steuerelementen zum Formular  
 So fügen Sie dem Formular Steuerelemente hinzu:  
  
-   Open `MyControl1` im Designer.  
  
 Fügen Sie fünf <xref:System.Windows.Forms.Label> Steuerelemente und die entsprechenden <xref:System.Windows.Forms.TextBox> Größe, und wie die vorstehende Abbildung, auf dem Formular werden Steuerelemente. Im Beispiel die <xref:System.Windows.Forms.TextBox> Steuerelemente heißen:  
  
-   `txtName`  
  
-   `txtAddress`  
  
-   `txtCity`  
  
-   `txtState`  
  
-   `txtZip`  
  
 Fügen Sie zwei <xref:System.Windows.Forms.Button> Steuerelemente, die mit der Bezeichnung **OK** und **"Abbrechen"**. Im Beispiel werden die Namen der `btnOK` und `btnCancel`zugeordnet.  
  
### <a name="implementing-the-supporting-code"></a>Implementieren des unterstützenden Codes  
 Öffnen Sie das Formular in der Codeansicht. Das Steuerelement gibt die gesammelten Daten an seinen Host zurück, indem Sie durch das Auslösen der benutzerdefinierten `OnButtonClick` Ereignis. Die Daten sind im Ereignisargumentobjekt enthalten. Der folgende Code zeigt die Deklaration von Ereignis und Delegat.  
  
 Fügen Sie der `MyControl1`-Klasse folgenden Code hinzu.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]  
  
 Die `MyControlEventArgs` -Klasse enthält die Informationen an den Host zurückgegeben werden sollen.  
  
 Fügen Sie dem Formular die folgende Klasse hinzu.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]  
  
 Klickt der Benutzer die **OK** oder **"Abbrechen"** Schaltfläche, die <xref:System.Windows.Forms.Control.Click> Ereignishandler erstellen eine `MyControlEventArgs` Objekt, das die Daten enthält und löst die `OnButtonClick` Ereignis. Der einzige Unterschied zwischen den zwei Handler ist des Ereignisarguments `IsOK` Eigenschaft. Diese Eigenschaft ermöglicht es dem Host, zu bestimmen, auf welche Schaltfläche geklickt wurde. Wird festgelegt ist, dass `true` für die **OK** Schaltfläche und `false` für die **"Abbrechen"** Schaltfläche. Der folgende Code zeigt die Handler der Schaltflächen.  
  
 Fügen Sie der `MyControl1`-Klasse folgenden Code hinzu.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]  
  
### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a>Vergeben eines starken Namens für die Assembly und Erstellen der Assembly  
 Für diese Assembly durch Verweise auf eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Anwendung einsetzen möchten, müssen sie einen starken Namen haben. Um einen starken Namen zu erstellen, erstellen Sie eine Schlüsseldatei mit Sn.exe und dem Projekt hinzugefügt.  
  
1.  Öffnen Sie eine [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]-Eingabeaufforderung. Klicken Sie hierzu auf die **starten** Menü, und wählen Sie dann **alle Programme/Microsoft Visual Studio 2010/Visual Studio Tools/Visual Studio-Eingabeaufforderung**. Dadurch wird ein Konsolenfenster mit benutzerdefinierten Umgebungsvariablen gestartet.  
  
2.  Verwenden Sie an der Eingabeaufforderung die `cd` Befehl zum Wechseln in den Projektordner.  
  
3.  Generieren Sie durch Ausführen des folgenden Befehls eine Schlüsseldatei mit dem Namen MyControls.snk.  
  
    ```  
    Sn.exe -k MyControls.snk  
    ```  
  
4.  Um die Schlüsseldatei in das Projekt einzuschließen, mit der rechten Maustaste im Projektmappen-Explorer des Projektnamen, und klicken Sie dann auf **Eigenschaften**. Klicken Sie im Projekt-Designer auf die **Signierung** Registerkarte die **zum Signieren der Assembly** Kontrollkästchen, und navigieren Sie dann zur Schlüsseldatei.  
  
5.  Erstellen Sie die Projektmappe. Der Build erzeugt eine DLL mit dem Namen MyControls.dll.  
  
## <a name="implementing-the-wpf-host-application"></a>Implementieren der WPF-Hostanwendung  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Hosten der Anwendung verwendet die <xref:System.Windows.Forms.Integration.WindowsFormsHost> zu hostende Steuerelement `MyControl1`. Die Anwendung behandelt den `OnButtonClick` Ereignis, um die Daten aus dem Steuerelement zu empfangen. Es ist auch eine Sammlung von Optionsfeldern, mit denen Sie einige der Eigenschaften des Steuerelements ändern können die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung. Die folgende Abbildung zeigt die fertige Anwendung.  
  
 ![Ein Steuerelement in eine WPF-Seite eingebettetes](../../../../docs/framework/wpf/advanced/media/avalonhost.gif "AvalonHost")  
Die vollständige Anwendung mit dem in der WPF-Anwendung eingebetteten Steuerelement  
  
### <a name="creating-the-project"></a>Erstellen des Projekts  
 Um das Projekt zu starten:  
  
1.  Open [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], und wählen Sie **neues Projekt**.  
  
2.  Wählen Sie in der Kategorie "Fenster" die **WPF-Anwendung** Vorlage.
  
3.  Geben Sie dem neuen Projekt den Namen `WpfHost`.  
  
4.  Geben Sie für den Speicherort denselben Stammordner an, der das Projekt „MyControls” enthält.  
  
5.  Klicken Sie auf **OK**, um das Projekt zu erstellen.  
  
 Sie müssen auch Verweise auf die DLL hinzufügen, enthält `MyControl1` und sonstigen Assemblys.  
  
1.  Mit der rechten Maustaste im Projektmappen-Explorer des Projektnamen, und wählen Sie **Verweis hinzufügen**.  
  
2.  Klicken Sie auf die **Durchsuchen** Registerkarte, und navigieren Sie zu dem Ordner, der MyControls.dll enthält. In dieser exemplarischen Vorgehensweise ist dies der Ordner "MyControls\bin\Debug".  
  
3.  Wählen Sie MyControls.dll aus, und klicken Sie dann auf **OK**.  
  
4.  Fügen Sie einen Verweis auf die WindowsFormsIntegration-Assembly mit die Namen WindowsFormsIntegration.dll hinzu.  
  
### <a name="implementing-the-basic-layout"></a>Implementieren des grundlegenden Layouts  
 Die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] des Hosts wird die Anwendung in der Datei "MainWindow.xaml" implementiert. Diese Datei enthält [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Markup, definiert das Layout und die Windows Forms-Steuerelement hostet. Die Anwendung ist in drei Bereiche unterteilt:  
  
-   Die **Steuerelementeigenschaften** Bereich, der eine Auflistung von Optionsfeldern, die Sie verwenden können enthält, um verschiedene Eigenschaften des gehosteten Steuerelements zu ändern.  
  
-   Die **Daten aus Steuerelement** Bereich, der mehrere enthält <xref:System.Windows.Controls.TextBlock> Elemente, die Daten anzuzeigen, die vom gehosteten Steuerelement zurückgegeben.  
  
-   Das gehostete Steuerelement selbst.  
  
 Das grundlegende Layout ist im nachfolgenden XAML-Code beschrieben. Das Markup, das erforderlich ist auf Host `MyControl1` in diesem Beispiel ausgelassen wird, jedoch wird weiter unten erläutert werden.  
  
 Ersetzen Sie den XAML-Code in der Datei MainWindow.xaml durch den folgenden Code. Wenn Sie Visual Basic verwenden, ändern Sie den Klassennamen in `x:Class="MainWindow"`.  
  
 [!code-xaml[WpfHostingWindowsFormsControl#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]  
  
 Die erste <xref:System.Windows.Controls.StackPanel> Element enthält mehrere Sätze von <xref:System.Windows.Controls.RadioButton> Steuerelemente, mit denen Sie verschiedene Standardeigenschaften des gehosteten Steuerelements ändern können. Es folgt eine <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element, welche Hosts `MyControl1`. Der endgültige <xref:System.Windows.Controls.StackPanel> -Element enthält verschiedene <xref:System.Windows.Controls.TextBlock> Elemente, die die Daten anzeigen, die vom gehosteten Steuerelement zurückgegeben wird. Die Reihenfolge der Elemente und die <xref:System.Windows.Controls.DockPanel.Dock%2A> und <xref:System.Windows.FrameworkElement.Height%2A> attributeinstellungen das gehostete Steuerelement in das Fenster ohne Lücken oder Verzerrung einzubetten.  
  
#### <a name="hosting-the-control"></a>Hosten des Steuerelements  
 Die folgende bearbeitete Version des vorherigen XAML konzentriert sich auf die Elemente, die erforderlich sind, Host `MyControl1`.  
  
 [!code-xaml[WpfHostingWindowsFormsControl#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]  
[!code-xaml[WpfHostingWindowsFormsControl#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]  
  
 Die `xmlns` Zuordnung Namespaceattribut erstellt einen Verweis auf die `MyControls` Namespace, der das gehostete Steuerelement enthält. Diese Zuordnung ermöglicht Ihnen das darstellen `MyControl1` in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] als `<mcl:MyControl1>`.  
  
 Das Hosting wird im XAML-Code von zwei Elementen behandelt:  
  
-   `WindowsFormsHost` Stellt die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element, das Sie zum Hosten eines Windows Forms-Steuerelements in ermöglicht eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung.  
  
-   `mcl:MyControl1`, steht `MyControl1`, hinzugefügt wird, um die <xref:System.Windows.Forms.Integration.WindowsFormsHost> des Elements untergeordnete Sammlung. Daher diese Windows Forms-Steuerelement gerendert wird, als Teil der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , und Sie können mit dem Steuerelement aus der Anwendung kommunizieren.  
  
### <a name="implementing-the-code-behind-file"></a>Implementieren der CodeBehind-Datei  
 Der Code-Behind-Datei "MainWindow.Xaml.vb" bzw. "MainWindow.Xaml.cs", enthält den prozeduralen Code, der die Funktionalität des implementiert die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] im vorherigen Abschnitt erläutert. Die Hauptaufgaben sind:  
  
-   Einen Ereignishandler anfügen `MyControl1`des `OnButtonClick` Ereignis.  
  
-   Ändern von verschiedenen Eigenschaften der `MyControl1`basierend auf wie die Auflistung der Optionsfelder festgelegt werden.  
  
-   Die Daten, die durch das Steuerelement gesammelt wurden, anzuzeigen.  
  
#### <a name="initializing-the-application"></a>Initialisierung der Anwendung  
 Initialisierungscode befindet sich in einem Ereignishandler für des Fensters <xref:System.Windows.FrameworkElement.Loaded> Ereignis und fügt einen Ereignishandler an des Steuerelements `OnButtonClick` Ereignis.  
  
 Fügen Sie in "MainWindow.Xaml.vb" bzw. "MainWindow.Xaml.cs" den folgenden Code, der `MainWindow` Klasse.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]  
  
 Da die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] erläutert zuvor hinzugefügten `MyControl1` auf die <xref:System.Windows.Forms.Integration.WindowsFormsHost> des Elements Auflistung untergeordneter Elemente, wandeln Sie die <xref:System.Windows.Forms.Integration.WindowsFormsHost> des Elements <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> zum Abrufen des Verweis auf `MyControl1`. Anschließend können Sie diesen Verweis fügen Sie einen Ereignishandler an `OnButtonClick`.  
  
 Geben Sie einen Verweis auf das Steuerelement selbst <xref:System.Windows.Forms.Integration.WindowsFormsHost> stellt eine Reihe von Eigenschaften des Steuerelements, das Sie aus der Anwendung bearbeiten können. Der Initialisierungscode weist diese Werte privaten globalen Variablen zu, damit sie später in der Anwendung verfügbar sind.  
  
 Damit Sie problemlos die Typen aus zugreifen, können die `MyControls` DLL, fügen Sie die folgenden `Imports` oder `using` Anweisungen am Anfang der Datei.  
  
```vb  
Imports MyControls  
```  
  
```csharp  
using MyControls;  
```  
  
#### <a name="handling-the-onbuttonclick-event"></a>Behandeln des OnButtonClick-Ereignisses  
 `MyControl1` Löst das `OnButtonClick` Ereignis aus, wenn der Benutzer auf eine der Schaltflächen des Steuerelements klickt.  
  
 Fügen Sie der `MainWindow`-Klasse folgenden Code hinzu.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]  
  
 Die Daten in die Textfelder steckt in den `MyControlEventArgs` Objekt. Wenn der Benutzer klickt auf die **OK** der Ereignishandler-Schaltfläche, die Daten extrahiert und in den Bereich darunter angezeigt `MyControl1`.  
  
#### <a name="modifying-the-controls-properties"></a>Ändern der Eigenschaften des Steuerelements  
 Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element macht mehrere Standardeigenschaften des gehosteten Steuerelements. Daher können Sie die Darstellung des Steuerelements besser dem Format Ihrer Anwendung entsprechend anpassen. Die Gruppe von Optionsschaltflächen im linken Bereich erlauben es dem Benutzer, mehrere Farb- und Schriftart-Eigenschaften zu ändern. Jeder Satz von Schaltflächen hat einen Handler für das <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignis, das der Benutzer die Schaltfläche ausgewählten erkennt und der entsprechenden Eigenschaft des Steuerelements ändert.  
  
 Fügen Sie der `MainWindow`-Klasse folgenden Code hinzu.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 Erstellen Sie die Anwendung, und führen Sie sie aus. Fügen Sie Text in der zusammengesetzten Windows Forms-Steuerelement hinzu, und klicken Sie dann auf **OK**. Der Text wird in den Beschriftungen angezeigt. Klicken Sie auf die verschiedenen Optionsfelder, um die Auswirkung auf das Steuerelement zu sehen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF-Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)  
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
