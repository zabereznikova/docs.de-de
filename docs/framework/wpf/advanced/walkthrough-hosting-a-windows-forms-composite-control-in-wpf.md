---
title: 'Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
ms.openlocfilehash: e4c1de17b131ee68c6e6fce0035b703eb5b489a0
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991883"
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a>Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt eine umfangreiche Umgebung zum Erstellen von Anwendungen bereit. Wenn Sie jedoch eine beträchtliche Investition in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] den Code haben, kann es effektiver sein, zumindest einen Teil dieses Codes in Ihrer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung wiederzuverwenden, anstatt ihn von Grund auf neu zu schreiben. Das häufigste Szenario ist, wenn Sie über vorhandene Windows Forms Steuerelemente verfügen. In einigen Fällen können Sie vielleicht gar nicht mehr auf den Quellcode für diese Steuerelemente zugreifen. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]bietet ein einfaches Verfahren zum Hosting solcher Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] einer-Anwendung. Beispielsweise können Sie für den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] größten Teil der Programmierung verwenden, während Sie Ihre <xref:System.Windows.Forms.DataGridView> spezialisierten Steuerelemente als Host verwenden.  
  
 Diese exemplarische Vorgehensweise führt Sie durch eine Anwendung, die ein Windows Forms zusammengesetztes Steuerelement hostet, um Dateneingaben in einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Anwendung auszuführen Das zusammengesetzte Steuerelement ist in eine DLL verpackt. Dieses allgemeine Verfahren kann für komplexere Anwendungen und Steuerelemente erweitert werden. Diese exemplarische Vorgehensweise ist so konzipiert, dass Sie in Darstellung und [Funktionalität nahezu identisch ist mit exemplarischen Vorgehensweisen: Hosting eines zusammengesetzten WPF-Steuer](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)Elements in Windows Forms. Der Hauptunterschied besteht darin, dass das Hosting-Szenario umgekehrt ist.  
  
 Diese exemplarische Vorgehensweise ist in zwei Abschnitte unterteilt. Im ersten Abschnitt wird die Implementierung des Windows Forms zusammengesetzten Steuer Elements kurz beschrieben. Im zweiten Abschnitt wird ausführlich erläutert, wie Sie das zusammengesetzte Steuerelement [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in einer-Anwendung hosten, Ereignisse vom Steuerelement empfangen und auf einige der Eigenschaften des Steuer Elements zugreifen können.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
- Implementieren des zusammengesetzten Windows Forms-Steuerelements.  
  
- Implementieren der WPF-Hostanwendung.  
  
 Eine komplette Code Auflistung der Aufgaben in dieser exemplarischen Vorgehensweise finden Sie unter [Hosting a Windows Forms Composite Control in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159999).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  

Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.
  
## <a name="implementing-the-windows-forms-composite-control"></a>Implementieren des zusammengesetzten Windows Forms-Steuerelements  
 Das in diesem Beispiel verwendete zusammengesetzte Steuerelement Windows Forms ist ein einfaches Dateneingabe Formular. Dieses Formular erfasst den Namen und die Adresse des Benutzers und gibt diese Information unter Verwendung eines benutzerdefinierten Ereignisses an den Host zurück. Die folgende Abbildung zeigt das gerenderte Steuerelement.  

 Die folgende Abbildung zeigt ein Windows Forms zusammengesetztes Steuerelement:  

 ![Screenshot, der ein einfaches Windows Forms Steuerelement anzeigt.](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-forms-control.gif)  
  
### <a name="creating-the-project"></a>Erstellen des Projekts  
 Um das Projekt zu starten:  
  
1. Starten [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]Sie, und öffnen Sie das Dialogfeld **Neues Projekt** .  
  
2. Wählen Sie in der Kategorie Fenster die Vorlage **Windows Forms Steuerelement Bibliothek** aus.  
  
3. Geben Sie dem neuen Projekt den Namen `MyControls`.  
  
4. Geben Sie für den Speicherort einen komfortabel benannten Ordner der obersten Ebene an, `WpfHostingWindowsFormsControl`z. b. Sie werden die Host-Anwendung später in diesem Ordner ablegen.  
  
5. Klicken Sie auf **OK**, um das Projekt zu erstellen. Das Standard Projekt enthält ein einzelnes Steuerelement `UserControl1`mit dem Namen.  
  
6. Benennen `UserControl1` Sie in Projektmappen-Explorer in `MyControl1`um.  
  
 Das Projekt sollte Verweise auf die folgenden System-DLLs aufweisen. Sollten eine oder mehrere dieser DLLs nicht standardmäßig enthalten sein, fügen Sie diese manuell zum Projekt hinzu.  
  
- System  
  
- <legacyBold>System.Data</legacyBold>  
  
- System.Drawing  
  
- System.Windows.Forms  
  
- System.Xml  
  
### <a name="adding-controls-to-the-form"></a>Hinzufügen von Steuerelementen zum Formular  
 So fügen Sie dem Formular Steuerelemente hinzu:  
  
- Öffnen `MyControl1` Sie im Designer.  
  
 Fügen Sie <xref:System.Windows.Forms.Label> im Formular fünf Steuer <xref:System.Windows.Forms.TextBox> Elemente und ihre entsprechenden Steuerelemente, die in der vorangehenden Abbildung angeordnet sind, in der Abbildung dargestellt. Im Beispiel lauten die <xref:System.Windows.Forms.TextBox> Steuerelemente wie folgt:  
  
- `txtName`  
  
- `txtAddress`  
  
- `txtCity`  
  
- `txtState`  
  
- `txtZip`  
  
 Fügen Sie <xref:System.Windows.Forms.Button> die beiden Steuerelemente **OK** und **Abbrechen**hinzu. Im Beispiel lauten die Schaltflächen Namen `btnOK` `btnCancel`bzw.  
  
### <a name="implementing-the-supporting-code"></a>Implementieren des unterstützenden Codes  
 Öffnen Sie das Formular in der Codeansicht. Das-Steuerelement gibt die gesammelten Daten an den Host zurück, `OnButtonClick` indem das benutzerdefinierte-Ereignis erhöht wird. Die Daten sind im Ereignisargumentobjekt enthalten. Der folgende Code zeigt die Deklaration von Ereignis und Delegat.  
  
 Fügen Sie der `MyControl1` -Klasse folgenden Code hinzu.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]

 Die `MyControlEventArgs` -Klasse enthält die Informationen, die an den Host zurückgegeben werden sollen.

 Fügen Sie dem Formular die folgende Klasse hinzu.

 [!code-csharp[WpfHostingWindowsFormsControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]

 Wenn der Benutzer auf die Schaltfläche **OK** oder **Abbrechen** klickt <xref:System.Windows.Forms.Control.Click> , erstellen die Ereignishandler `MyControlEventArgs` ein-Objekt, das die Daten enthält `OnButtonClick` , und löst das-Ereignis aus. Der einzige Unterschied zwischen den beiden Handlern ist die- `IsOK` Eigenschaft des Ereignis Arguments. Diese Eigenschaft ermöglicht es dem Host, zu bestimmen, auf welche Schaltfläche geklickt wurde. Es ist für die `true` Schaltfläche " **OK** " und `false` für die Schaltfläche " **Abbrechen** " auf festgelegt. Der folgende Code zeigt die Handler der Schaltflächen.

 Fügen Sie der `MyControl1` -Klasse folgenden Code hinzu.

 [!code-csharp[WpfHostingWindowsFormsControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]

### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a>Vergeben eines starken Namens für die Assembly und Erstellen der Assembly
 Damit diese Assembly von einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Anwendung referenziert werden kann, muss Sie einen starken Namen haben. Um einen starken Namen zu erstellen, erstellen Sie eine Schlüsseldatei mit Sn. exe, und fügen Sie Sie dem Projekt hinzu.

1. Öffnen Sie eine [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]-Eingabeaufforderung. Klicken Sie hierzu **auf das** Startmenü, und wählen Sie dann **Alle Programme/Microsoft Visual Studio 2010/Visual Studio-Tools/Visual Studio-Eingabeaufforderung**aus. Dadurch wird ein Konsolenfenster mit benutzerdefinierten Umgebungsvariablen gestartet.

2. Verwenden Sie an der Eingabeaufforderung den `cd` Befehl, um zu Ihrem Projektordner zu wechseln.

3. Generieren Sie durch Ausführen des folgenden Befehls eine Schlüsseldatei mit dem Namen MyControls.snk.

    ```console
    Sn.exe -k MyControls.snk
    ```

4. Um die Schlüsseldatei in das Projekt einzuschließen, klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf den Projektnamen, und klicken Sie dann auf **Eigenschaften**. Klicken Sie im Projekt-Designer auf die Registerkarte **Signierung** , aktivieren Sie das Kontrollkästchen **Assembly signieren** , und navigieren Sie dann zu ihrer Schlüsseldatei.

5. Erstellen Sie die Projektmappe. Der Build erzeugt eine DLL mit dem Namen MyControls.dll.

## <a name="implementing-the-wpf-host-application"></a>Implementieren der WPF-Hostanwendung
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Host Anwendung verwendet das <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Steuerelement `MyControl1`, um zu hosten. Die Anwendung behandelt das `OnButtonClick` -Ereignis, um die Daten vom-Steuerelement zu empfangen. Es enthält auch eine Auflistung von Options Schaltflächen, mit denen Sie einige der Eigenschaften des Steuer Elements in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] der Anwendung ändern können. Die folgende Abbildung zeigt die fertige Anwendung.

Die folgende Abbildung zeigt die gesamte Anwendung, einschließlich des in die WPF-Anwendung eingebetteten-Steuer Elements:

 ![Screenshot, der ein in einer WPF-Seite eingebettetes Steuerelement anzeigt.](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-presentation-foundation-page-control.gif)

### <a name="creating-the-project"></a>Erstellen des Projekts
 Um das Projekt zu starten:

1. Öffnen [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]Sie, und wählen Sie **Neues Projekt**aus.

2. Wählen Sie in der Kategorie Fenster die Vorlage **WPF-Anwendung** aus.

3. Geben Sie dem neuen Projekt den Namen `WpfHost`.

4. Geben Sie für den Speicherort denselben Stammordner an, der das Projekt „MyControls” enthält.

5. Klicken Sie auf **OK**, um das Projekt zu erstellen.

 Außerdem müssen Sie Verweise auf die dll hinzufügen, die `MyControl1` und andere Assemblys enthält.

1. Klicken Sie mit der rechten Maustaste auf den Projektnamen in Projektmappen-Explorer und wählen Sie **Verweis hinzufügen**.

2. Klicken Sie auf die Registerkarte **Durchsuchen** , und navigieren Sie zu dem Ordner, der MyControls. dll enthält. In dieser exemplarischen Vorgehensweise ist dies der Ordner "MyControls\bin\Debug".

3. Wählen Sie MyControls. dll aus, und klicken Sie dann auf **OK**.

4. Fügen Sie einen Verweis auf die WindowsFormsIntegration-Assembly mit dem Namen "WindowsFormsIntegration. dll" hinzu.

### <a name="implementing-the-basic-layout"></a>Implementieren des grundlegenden Layouts
 Der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] der Host Anwendung wird in "MainWindow. XAML" implementiert. Diese Datei enthält [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Markup, das das Layout definiert und das Windows Forms Steuerelement hostet. Die Anwendung ist in drei Bereiche unterteilt:

- Das **Eigenschaften** Panel des-Steuer Elements, das eine Auflistung von Options Schaltflächen enthält, mit denen Sie verschiedene Eigenschaften des gehosteten Steuer Elements ändern können.

- Die **Daten aus der Systemsteuerung** , die mehrere <xref:System.Windows.Controls.TextBlock> Elemente enthält, die die vom gehosteten Steuerelement zurückgegebenen Daten anzeigen.

- Das gehostete Steuerelement selbst.

 Das grundlegende Layout ist im nachfolgenden XAML-Code beschrieben. Das Markup, das zum Hosten `MyControl1` von benötigt wird, wird in diesem Beispiel weggelassen, wird aber später erläutert.

 Ersetzen Sie den XAML-Code in der Datei MainWindow.xaml durch den folgenden Code. Wenn Sie Visual Basic verwenden, ändern Sie die-Klasse `x:Class="MainWindow"`in.

 [!code-xaml[WpfHostingWindowsFormsControl#100](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]

 Das erste <xref:System.Windows.Controls.StackPanel> -Element enthält mehrere Sätze <xref:System.Windows.Controls.RadioButton> von Steuerelementen, mit denen Sie verschiedene Standardeigenschaften des gehosteten Steuer Elements ändern können. Danach folgt ein <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element, das hostet `MyControl1`. Das letzte <xref:System.Windows.Controls.StackPanel> -Element enthält <xref:System.Windows.Controls.TextBlock> mehrere-Elemente, die die vom gehosteten Steuerelement zurückgegebenen Daten anzeigen. Die Reihenfolge der-Elemente und <xref:System.Windows.Controls.DockPanel.Dock%2A> der <xref:System.Windows.FrameworkElement.Height%2A> -und-Attribut Einstellungen Betten das gehostete Steuerelement ohne Lücken oder Verzerrung in das Fenster ein.

#### <a name="hosting-the-control"></a>Hosten des Steuerelements
 In der folgenden bearbeiteten Version der vorherigen XAML liegt der Schwerpunkt auf den Elementen, die `MyControl1`zum Hosten von benötigt werden.

 [!code-xaml[WpfHostingWindowsFormsControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]
[!code-xaml[WpfHostingWindowsFormsControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]

 Das `xmlns` Namespace Mapping-Attribut erstellt einen Verweis auf `MyControls` den Namespace, der das gehostete Steuerelement enthält. Mit dieser Zuordnung können Sie in `MyControl1` [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] als `<mcl:MyControl1>`darstellen.

 Das Hosting wird im XAML-Code von zwei Elementen behandelt:

- `WindowsFormsHost`stellt das <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element dar, mit dem Sie ein Windows Forms-Steuer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Element in einer-Anwendung hosten können.

- `mcl:MyControl1`, das darstellt `MyControl1`, wird der untergeordneten <xref:System.Windows.Forms.Integration.WindowsFormsHost> Auflistung des-Elements hinzugefügt. Folglich wird dieses Windows Forms Steuerelement als Teil des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Fensters gerendert, und Sie können über die Anwendung mit dem Steuerelement kommunizieren.

### <a name="implementing-the-code-behind-file"></a>Implementieren der CodeBehind-Datei
 Die Code-Behind-Datei MainWindow. XAML. vb oder MainWindow.XAML.cs enthält den prozeduralen Code, der die Funktionalität von [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] implementiert, die im vorherigen Abschnitt erläutert wurde. Die Hauptaufgaben sind:

- Anfügen eines Ereignis Handlers `OnButtonClick` an `MyControl1`das-Ereignis.

- Ändern verschiedener Eigenschaften von `MyControl1`, basierend darauf, wie die Auflistung von Options Schaltflächen festgelegt wird.

- Die Daten, die durch das Steuerelement gesammelt wurden, anzuzeigen.

#### <a name="initializing-the-application"></a>Initialisierung der Anwendung
 Der Initialisierungs Code ist in einem Ereignishandler für das- <xref:System.Windows.FrameworkElement.Loaded> Ereignis des Fensters enthalten und fügt einen Ereignishandler an das-Ereignis des- `OnButtonClick` Steuer Elements an.

 Fügen Sie in MainWindow. XAML. vb oder MainWindow.XAML.cs der- `MainWindow` Klasse den folgenden Code hinzu.

 [!code-csharp[WpfHostingWindowsFormsControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]

 Da der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , der zuvor `MyControl1` erläutert wurde <xref:System.Windows.Forms.Integration.WindowsFormsHost> , der untergeordneten Element Auflistung des-Elements hinzu <xref:System.Windows.Forms.Integration.WindowsFormsHost> gefügt wurde <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> , können Sie den des `MyControl1`Elements umwandeln, um den Verweis auf zu erhalten. Sie können diesen Verweis dann verwenden, um einen Ereignishandler an `OnButtonClick`anzufügen.

 Zusätzlich zur Bereitstellung eines Verweises auf das Steuerelement <xref:System.Windows.Forms.Integration.WindowsFormsHost> selbst wird von eine Reihe von Eigenschaften des-Steuer Elements bereitgestellt, die Sie in der Anwendung bearbeiten können. Der Initialisierungscode weist diese Werte privaten globalen Variablen zu, damit sie später in der Anwendung verfügbar sind.

 Damit Sie problemlos auf die Typen in der `MyControls` dll zugreifen können, fügen Sie die folgende `using` `Imports` -oder-Anweisung am Anfang der Datei hinzu.

```vb
Imports MyControls
```

```csharp
using MyControls;
```

#### <a name="handling-the-onbuttonclick-event"></a>Behandeln des OnButtonClick-Ereignisses
 `MyControl1`Löst das `OnButtonClick` -Ereignis aus, wenn der Benutzer auf eine der Schaltflächen des Steuer Elements klickt.

 Fügen Sie der `MainWindow` -Klasse folgenden Code hinzu.

 [!code-csharp[WpfHostingWindowsFormsControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]

 Die Daten in den Textfeldern werden in das `MyControlEventArgs` -Objekt gepackt. Wenn der Benutzer auf die Schaltfläche **OK** klickt, extrahiert der Ereignishandler die Daten und zeigt Sie im folgenden `MyControl1`Bereich an.

#### <a name="modifying-the-controls-properties"></a>Ändern der Eigenschaften des Steuerelements
 Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element macht mehrere der Standardeigenschaften des gehosteten Steuer Elements verfügbar. Daher können Sie die Darstellung des Steuerelements besser dem Format Ihrer Anwendung entsprechend anpassen. Die Gruppe von Optionsschaltflächen im linken Bereich erlauben es dem Benutzer, mehrere Farb- und Schriftart-Eigenschaften zu ändern. Jeder Satz von Schaltflächen verfügt über einen Handler <xref:System.Windows.Controls.Primitives.ButtonBase.Click> für das-Ereignis, das die Auswahl Schaltfläche des Benutzers erkennt und die entsprechende-Eigenschaft des Steuer Elements ändert.

 Fügen Sie der `MainWindow` -Klasse folgenden Code hinzu.

 [!code-csharp[WpfHostingWindowsFormsControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 Erstellen Sie die Anwendung, und führen Sie sie aus. Fügen Sie im Windows Forms zusammengesetzten Steuer Elements Text hinzu, und klicken Sie dann auf **OK**. Der Text wird in den Beschriftungen angezeigt. Klicken Sie auf die verschiedenen Optionsfelder, um die Auswirkung auf das Steuerelement zu sehen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Exemplarische Vorgehensweise: Hosting eines Windows Forms-Steuer Elements in WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Exemplarische Vorgehensweise: Hosting eines zusammengesetzten WPF-Steuer Elements in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
