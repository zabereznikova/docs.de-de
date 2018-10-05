---
title: 'Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
ms.openlocfilehash: cd5a416c4eafa5b6260b49873fe2d4c2ed3a6af8
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48266798"
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a>Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt eine umfangreiche Umgebung zum Erstellen von Anwendungen bereit. Wann haben Sie jedoch eine erhebliche Investition [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Code möglich effektiver mindestens wiederverwenden Teil dieses Codes in Ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung anstatt sie von Grund auf neu zu schreiben. Das häufigste Szenario ist, wenn Sie vorhandenen Windows Forms-Steuerelemente haben. In einigen Fällen können Sie vielleicht gar nicht mehr auf den Quellcode für diese Steuerelemente zugreifen. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet ein einfaches Verfahren zum Hosten solcher Steuerelemente in einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung. Beispielsweise können Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] für den Großteil der Programmierung beim Hosten Ihrer speziellen <xref:System.Windows.Forms.DataGridView> Steuerelemente.  
  
 Diese exemplarische Vorgehensweise führt Sie durch eine Anwendung, ein zusammengesetztes Windows Forms-Steuerelements zum Durchführen der Dateneingabe im hostet, eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung. Das zusammengesetzte Steuerelement ist in eine DLL verpackt. Dieses allgemeine Verfahren kann für komplexere Anwendungen und Steuerelemente erweitert werden. In dieser exemplarischen Vorgehensweise in Darstellung und Funktionalität nahezu identisch sein soll [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md). Der Hauptunterschied besteht darin, dass das Hosting-Szenario umgekehrt ist.  
  
 Diese exemplarische Vorgehensweise ist in zwei Abschnitte unterteilt. Der erste Abschnitt beschreibt kurz die Implementierung des zusammengesetzten Windows Forms-Steuerelements. Der zweite Abschnitt wird detailliert erläutert, wie Sie hosten das zusammengesetzte Steuerelement in einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung Ereignisse vom Steuerelement empfangen und Zugriff auf einige der Eigenschaften des Steuerelements.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Implementieren des zusammengesetzten Windows Forms-Steuerelements.  
  
-   Implementieren der WPF-Hostanwendung.  
  
 Eine vollständige codeauflistung der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF-Beispiel](https://go.microsoft.com/fwlink/?LinkID=159999).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  

Sie benötigen Visual Studio zum Durchführen dieser exemplarischen Vorgehensweise.
  
## <a name="implementing-the-windows-forms-composite-control"></a>Implementieren des zusammengesetzten Windows Forms-Steuerelements  
 In diesem Beispiel verwendeten zusammengesetzte Windows Forms-Steuerelement ist ein einfaches Dateneingabeformular. Dieses Formular erfasst den Namen und die Adresse des Benutzers und gibt diese Information unter Verwendung eines benutzerdefinierten Ereignisses an den Host zurück. Die folgende Abbildung zeigt das gerenderte Steuerelement.  
  
 ![Einfaches Windows Forms-Steuerelement](../../../../docs/framework/wpf/advanced/media/wfcontrol.gif "WFControl")  
Zusammengesetztes Windows Forms-Steuerelement  
  
### <a name="creating-the-project"></a>Erstellen des Projekts  
 Um das Projekt zu starten:  
  
1.  Starten Sie [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], und öffnen Sie die **neues Projekt** Dialogfeld.  
  
2.  Wählen Sie in der Kategorie der **Windows Forms-Steuerelementbibliothek** Vorlage.  
  
3.  Geben Sie dem neuen Projekt den Namen `MyControls`.  
  
4.  Geben Sie für den Speicherort einen bequem benannten Ordner an der obersten Ebene, z. B. `WpfHostingWindowsFormsControl`. Sie werden die Host-Anwendung später in diesem Ordner ablegen.  
  
5.  Klicken Sie auf **OK**, um das Projekt zu erstellen. Das Standardprojekt enthält ein einzelnes Steuerelement mit dem Namen `UserControl1`.  
  
6.  Benennen Sie im Projektmappen-Explorer `UserControl1` zu `MyControl1`.  
  
 Das Projekt sollte Verweise auf die folgenden System-DLLs aufweisen. Sollten eine oder mehrere dieser DLLs nicht standardmäßig enthalten sein, fügen Sie diese manuell zum Projekt hinzu.  
  
-   System  
  
-   <legacyBold>System.Data</legacyBold>  
  
-   System.Drawing  
  
-   System.Windows.Forms  
  
-   System.Xml  
  
### <a name="adding-controls-to-the-form"></a>Hinzufügen von Steuerelementen zum Formular  
 So fügen Sie dem Formular Steuerelemente hinzu:  
  
-   Open `MyControl1` im Designer.  
  
 Fügen Sie fünf <xref:System.Windows.Forms.Label> Steuerelemente und die entsprechenden <xref:System.Windows.Forms.TextBox> Steuerelemente, Größe und Anordnung, wie in der vorherigen Abbildung auf dem Formular. Im Beispiel die <xref:System.Windows.Forms.TextBox> -Steuerelemente folgendermaßen benannt werden:  
  
-   `txtName`  
  
-   `txtAddress`  
  
-   `txtCity`  
  
-   `txtState`  
  
-   `txtZip`  
  
 Hinzufügen von zwei <xref:System.Windows.Forms.Button> Steuerelemente, die mit der Bezeichnung **OK** und **Abbrechen**. Im Beispiel werden die Namen der `btnOK` und `btnCancel`bzw.  
  
### <a name="implementing-the-supporting-code"></a>Implementieren des unterstützenden Codes  
 Öffnen Sie das Formular in der Codeansicht. Das Steuerelement und gibt Sie die gesammelten Daten auf den Host durch Auslösen der benutzerdefiniertes `OnButtonClick` Ereignis. Die Daten sind im Ereignisargumentobjekt enthalten. Der folgende Code zeigt die Deklaration von Ereignis und Delegat.  
  
 Fügen Sie der `MyControl1`-Klasse folgenden Code hinzu.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]

 Die `MyControlEventArgs` Klasse enthält die Informationen, die an den Host zurückgegeben werden.

 Fügen Sie dem Formular die folgende Klasse hinzu.

 [!code-csharp[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]

 Klickt der Benutzer die **OK** oder **Abbrechen** Schaltfläche der <xref:System.Windows.Forms.Control.Click> -Ereignishandler zu erstellen einen `MyControlEventArgs` -Objekt, das die Daten enthält und löst die `OnButtonClick` Ereignis. Der einzige Unterschied zwischen den zwei Handler ist des Ereignisarguments `IsOK` Eigenschaft. Diese Eigenschaft ermöglicht es dem Host, zu bestimmen, auf welche Schaltfläche geklickt wurde. Wird festgelegt `true` für die **OK** Schaltfläche und `false` für die **Abbrechen** Schaltfläche. Der folgende Code zeigt die Handler der Schaltflächen.

 Fügen Sie der `MyControl1`-Klasse folgenden Code hinzu.

 [!code-csharp[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]

### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a>Vergeben eines starken Namens für die Assembly und Erstellen der Assembly
 Für diese Assembly durch Verweise auf eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung, sie müssen einen starken Namen haben. Um einen starken Namen zu erstellen, erstellen Sie mit Sn.exe eine Schlüsseldatei, und fügen sie dem Projekt hinzu.

1.  Öffnen Sie eine [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]-Eingabeaufforderung. Zu diesem Zweck klicken Sie auf die **starten** Menü, und wählen Sie dann **alle Programme/Microsoft Visual Studio 2010/Visual Studio Tools/Visual Studio-Eingabeaufforderung**. Dadurch wird ein Konsolenfenster mit benutzerdefinierten Umgebungsvariablen gestartet.

2.  Verwenden Sie an der Eingabeaufforderung die `cd` Befehl aus, um Sie zu Ihrem Projektordner zu wechseln.

3.  Generieren Sie durch Ausführen des folgenden Befehls eine Schlüsseldatei mit dem Namen MyControls.snk.

    ```
    Sn.exe -k MyControls.snk
    ```

4.  Um die Schlüsseldatei in Ihr Projekt einzuschließen, mit der rechten Maustaste des Projektnamen im Projektmappen-Explorer, und klicken Sie dann auf **Eigenschaften**. Klicken Sie im Projekt-Designer auf die **Signierung** Registerkarte die **Assembly signieren** Kontrollkästchen aus, und navigieren Sie dann zur Schlüsseldatei.

5.  Erstellen Sie die Projektmappe. Der Build erzeugt eine DLL mit dem Namen MyControls.dll.

## <a name="implementing-the-wpf-host-application"></a>Implementieren der WPF-Hostanwendung
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Hosten der Anwendung verwendet die <xref:System.Windows.Forms.Integration.WindowsFormsHost> zu hostende Steuerelement `MyControl1`. Die Anwendung behandelt den `OnButtonClick` Ereignis, um die Daten aus dem Steuerelement zu empfangen. Es verfügt auch über eine Auflistung von Optionsschaltflächen, mit denen Sie einige der Eigenschaften des Steuerelements ändern, aktivieren Sie die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung. Die folgende Abbildung zeigt die fertige Anwendung.

 ![Ein in einer WPF-Seite eingebettetes Steuerelement](../../../../docs/framework/wpf/advanced/media/avalonhost.gif "AvalonHost") die vollständige Anwendung, das Anzeigen des Steuerelements in WPF-Anwendung eingebettet

### <a name="creating-the-project"></a>Erstellen des Projekts
 Um das Projekt zu starten:

1.  Open [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], und wählen Sie **neues Projekt**.

2.  Wählen Sie in der Kategorie der **WPF-Anwendung** Vorlage.

3.  Geben Sie dem neuen Projekt den Namen `WpfHost`.

4.  Geben Sie für den Speicherort denselben Stammordner an, der das Projekt „MyControls” enthält.

5.  Klicken Sie auf **OK**, um das Projekt zu erstellen.

 Sie müssen auch Verweise auf die DLL hinzufügen, enthält `MyControl1` und andere Assemblys.

1.  Mit der rechten Maustaste des Projektnamen im Projektmappen-Explorer, und wählen Sie **Verweis hinzufügen**.

2.  Klicken Sie auf die **Durchsuchen** Registerkarte, und navigieren Sie zu dem Ordner, der MyControls.dll enthält. In dieser exemplarischen Vorgehensweise ist dies der Ordner "MyControls\bin\Debug".

3.  Wählen Sie MyControls.dll aus, und klicken Sie dann auf **OK**.

4.  Fügen Sie einen Verweis auf die Assembly "WindowsFormsIntegration", mit die Namen WindowsFormsIntegration.dll hinzu.

### <a name="implementing-the-basic-layout"></a>Implementieren des grundlegenden Layouts
 Die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] des Hosts wird die Anwendung in "MainWindow.xaml" implementiert. Diese Datei enthält [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Markup, das Layout definiert, und das Windows Forms-Steuerelement hostet. Die Anwendung ist in drei Bereiche unterteilt:

-   Die **Steuerelementeigenschaften** aus, der eine Auflistung von Optionsschaltflächen enthält, mit denen Sie verschiedene Eigenschaften des gehosteten Steuerelements ändern.

-   Die **Data from Control** aus, der mehrere enthält <xref:System.Windows.Controls.TextBlock> Elemente, die Daten anzuzeigen, die vom gehosteten Steuerelement zurückgegeben.

-   Das gehostete Steuerelement selbst.

 Das grundlegende Layout ist im nachfolgenden XAML-Code beschrieben. Das Markup, das erforderlich ist auf Host `MyControl1` in diesem Beispiel ausgelassen wird, aber später erläutert.

 Ersetzen Sie den XAML-Code in der Datei MainWindow.xaml durch den folgenden Code. Wenn Sie Visual Basic verwenden, ändern Sie die Klasse `x:Class="MainWindow"`.

 [!code-xaml[WpfHostingWindowsFormsControl#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]

 Die erste <xref:System.Windows.Controls.StackPanel> Element enthält eine Reihe von <xref:System.Windows.Controls.RadioButton> Steuerelemente, mit denen Sie verschiedene Standardeigenschaften des gehosteten Steuerelements ändern können. Es folgt eine <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element, welche Hosts `MyControl1`. Die endgültige <xref:System.Windows.Controls.StackPanel> -Element enthält verschiedene <xref:System.Windows.Controls.TextBlock> Elemente, die die Daten anzeigen, die vom gehosteten Steuerelement zurückgegeben wird. Die Reihenfolge der Elemente und die <xref:System.Windows.Controls.DockPanel.Dock%2A> und <xref:System.Windows.FrameworkElement.Height%2A> attributeinstellungen betten Sie das gehostete Steuerelement ohne Lücken oder Verzerrung in das Fenster.

#### <a name="hosting-the-control"></a>Hosten des Steuerelements
 Die nachfolgende angepasste Version von der vorherigen XAML konzentriert sich auf die Elemente, die erforderlich sind, auf Host `MyControl1`.

 [!code-xaml[WpfHostingWindowsFormsControl#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]
[!code-xaml[WpfHostingWindowsFormsControl#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]

 Die `xmlns` Namespace-Zuordnungsattribut erstellt einen Verweis auf die `MyControls` Namespace, der das gehostete Steuerelement enthält. Diese Zuordnung ermöglicht Ihnen das Darstellen von `MyControl1` in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] als `<mcl:MyControl1>`.

 Das Hosting wird im XAML-Code von zwei Elementen behandelt:

-   `WindowsFormsHost` Stellt die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element, das Ihnen ermöglicht, das Hosten eines Windows Forms-Steuerelements in einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung.

-   `mcl:MyControl1`, die darstellt, `MyControl1`, wurde die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Auflistung der untergeordneten Elemente. Daher diese Windows Forms-Steuerelement gerendert wird, als Teil der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , und Sie können mit dem Steuerelement aus der Anwendung kommunizieren.

### <a name="implementing-the-code-behind-file"></a>Implementieren der CodeBehind-Datei
 Der Code-Behind-Datei "MainWindow.Xaml.vb" bzw. "MainWindow.Xaml.cs" enthält den prozeduralen Code, der die Funktionalität des implementiert die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] im vorherigen Abschnitt erläutert. Die Hauptaufgaben sind:

-   Anhängen eines ereignishandlers zu `MyControl1`des `OnButtonClick` Ereignis.

-   Ändern die verschiedenen Eigenschaften der `MyControl1`basierend auf wie die Auflistung von Optionsschaltflächen festgelegt werden.

-   Die Daten, die durch das Steuerelement gesammelt wurden, anzuzeigen.

#### <a name="initializing-the-application"></a>Initialisierung der Anwendung
 Der Initialisierungscode befindet sich in einem Ereignishandler für des Fensters des <xref:System.Windows.FrameworkElement.Loaded> Ereignis und fügt einen Ereignishandler des Steuerelements `OnButtonClick` Ereignis.

 Fügen Sie den folgenden Code in "MainWindow.Xaml.vb" bzw. "MainWindow.Xaml.cs", die `MainWindow` Klasse.

 [!code-csharp[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]

 Da die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] erläutert zuvor hinzugefügten `MyControl1` auf die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element der Auflistung untergeordneter Elemente, wandeln Sie die <xref:System.Windows.Forms.Integration.WindowsFormsHost> des Elements <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> zum Abrufen des Verweis auf `MyControl1`. Anschließend können Sie diesen Verweis einen Ereignishandler angefügt `OnButtonClick`.

 Zusätzlich zur Bereitstellung von eines Verweis auf das Steuerelement selbst <xref:System.Windows.Forms.Integration.WindowsFormsHost> bietet eine Reihe von Eigenschaften des Steuerelements, das Sie aus der Anwendung bearbeiten können. Der Initialisierungscode weist diese Werte privaten globalen Variablen zu, damit sie später in der Anwendung verfügbar sind.

 Damit Sie problemlos die Typen aus zugreifen, können die `MyControls` DLL, fügen Sie die folgenden `Imports` oder `using` Anweisung am Anfang der Datei.

```vb
Imports MyControls
```

```csharp
using MyControls;
```

#### <a name="handling-the-onbuttonclick-event"></a>Behandeln des OnButtonClick-Ereignisses
 `MyControl1` löst die `OnButtonClick` Ereignis aus, wenn der Benutzer auf eine der Schaltflächen des Steuerelements klickt.

 Fügen Sie der `MainWindow`-Klasse folgenden Code hinzu.

 [!code-csharp[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]

 Die Daten in die Textfelder steckt in den `MyControlEventArgs` Objekt. Wenn der Benutzer klickt auf die **OK** Schaltfläche der Ereignishandler die Daten extrahiert und zeigt sie im Bereich darunter `MyControl1`.

#### <a name="modifying-the-controls-properties"></a>Ändern der Eigenschaften des Steuerelements
 Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element macht mehrere Standardeigenschaften des gehosteten Steuerelements verfügbar. Daher können Sie die Darstellung des Steuerelements besser dem Format Ihrer Anwendung entsprechend anpassen. Die Gruppe von Optionsschaltflächen im linken Bereich erlauben es dem Benutzer, mehrere Farb- und Schriftart-Eigenschaften zu ändern. Jede Schaltflächengruppe besitzt einen Handler für die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis, das der Benutzer die Auswahl an Optionsschaltflächen ermittelt und die entsprechende Eigenschaft des Steuerelements ändert.

 Fügen Sie der `MainWindow`-Klasse folgenden Code hinzu.

 [!code-csharp[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 Erstellen Sie die Anwendung, und führen Sie sie aus. Fügen Sie dem zusammengesetzten Windows Forms-Steuerelement etwas Text hinzu, und klicken Sie dann auf **OK**. Der Text wird in den Beschriftungen angezeigt. Klicken Sie auf die verschiedenen Optionsfelder, um die Auswirkung auf das Steuerelement zu sehen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Entwerfen von XAML-Code in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)  
 [Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)  
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
