---
title: Hosten eines ActiveX-Steuer Elements in WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ActiveX controls [WPF interoperability]
- hosting ActiveX controls [WPF]
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
ms.openlocfilehash: f2d9345eaaba7b85a217e6b230ae202f27ad3af8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742621"
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a>Exemplarische Vorgehensweise: Hosten eines ActiveX-Steuerelements in WPF
Um eine verbesserte Interaktion mit Browsern zu ermöglichen, können Sie Microsoft-ActiveX-Steuerelemente in ihrer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]basierten Anwendung verwenden. In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie die Microsoft Windows-Media Player als Steuerelement auf einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Seite hosten können.

 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:

- Erstellen des Projekts

- Das ActiveX-Steuerelement wird erstellt.

- Hosting des ActiveX-Steuer Elements auf einer WPF-Seite.

 Wenn Sie diese exemplarische Vorgehensweise abgeschlossen haben, erfahren Sie, wie Sie Microsoft-ActiveX-Steuerelemente in ihrer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]basierten Anwendung verwenden.

## <a name="prerequisites"></a>Erforderliche Komponenten
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:

- Microsoft Windows Media Player auf dem Computer installiert, auf dem Visual Studio installiert ist.

- Visual Studio 2010.

## <a name="creating-the-project"></a>Erstellen des Projekts

### <a name="to-create-and-set-up-the-project"></a>So erstellen und richten Sie das Projekt ein

1. Erstellen Sie ein WPF-Anwendungsprojekt mit dem Namen `HostingAxInWpf`.

2. Fügen Sie ein Windows Forms-Steuerelement Bibliothek-Projekt zur Projekt Mappe hinzu, und benennen Sie das Projekt `WmpAxLib`.

3. Fügen Sie im wmpxlib-Projekt einen Verweis auf die Windows Media Player-Assembly mit dem Namen "WMP. dll" hinzu.

4. Öffnen Sie die **Toolbox**.

5. Klicken Sie mit der rechten Maustaste in die **Toolbox**, und klicken Sie dann auf **Elemente auswählen**.

6. Klicken Sie auf die Registerkarte **com-Komponenten** , wählen Sie das **Fenster Windows Media Player** aus, und klicken Sie dann auf **OK**

     Das Windows Media Player-Steuerelement wird der **Toolbox**hinzugefügt.

7. Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf die Datei **UserControl1** , und klicken Sie dann auf **Umbenennen**.

8. Ändern Sie den Namen abhängig von der Sprache in `WmpAxControl.vb` oder `WmpAxControl.cs`.

9. Wenn Sie aufgefordert werden, alle Verweise umzubenennen, klicken Sie auf **Ja**.

## <a name="creating-the-activex-control"></a>Erstellen des ActiveX-Steuer Elements
Visual Studio generiert automatisch eine <xref:System.Windows.Forms.AxHost> Wrapper Klasse für ein Microsoft ActiveX-Steuerelement, wenn das Steuerelement einer Entwurfs Oberfläche hinzugefügt wird. Mit der folgenden Prozedur wird eine verwaltete Assembly mit dem Namen "AxInterop. WMPLib. dll" erstellt.

### <a name="to-create-the-activex-control"></a>So erstellen Sie das ActiveX-Steuerelement

1. Öffnen Sie wmpxcontrol. vb oder WmpAxControl.cs im Windows Forms-Designer.

2. Fügen Sie der Entwurfs Oberfläche aus der **Toolbox**das Windows Media Player-Steuerelement hinzu.

3. Legen Sie in der Eigenschaftenfenster den Wert der Eigenschaft <xref:System.Windows.Forms.Control.Dock%2A> des Windows Media Player-Steuer Elements auf <xref:System.Windows.Forms.DockStyle.Fill>fest.

4. Erstellen Sie das wmpxlib-Steuerelement Bibliothek-Projekt.

## <a name="hosting-the-activex-control-on-a-wpf-page"></a>Hosting des ActiveX-Steuer Elements auf einer WPF-Seite

### <a name="to-host-the-activex-control"></a>Zum Hosten des ActiveX-Steuer Elements

1. Fügen Sie im Projekt "hustingaxinwpf" einen Verweis auf die generierte ActiveX-Interoperabilitäts-Assembly hinzu.

     Diese Assembly heißt "AxInterop. WMPLib. dll" und wurde beim Importieren des Windows Media Player-Steuer Elements zum Ordner "Debug" des Projekts "wmpxlib" hinzugefügt.

2. Fügen Sie einen Verweis auf die WindowsFormsIntegration-Assembly mit dem Namen "WindowsFormsIntegration. dll" hinzu.

3. Fügen Sie einen Verweis auf die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Assembly mit dem Namen "System. Windows. Forms. dll" hinzu.

4. Öffnen Sie die Datei "MainWindow. XAML" im WPF-Designer.

5. Benennen Sie das <xref:System.Windows.Controls.Grid> Element `grid1`.

     [!code-xaml[HostingAxInWpf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]

6. Wählen Sie in Designansicht-oder XAML-Ansicht das <xref:System.Windows.Window> Element aus.

7. Klicken Sie im Eigenschaftenfenster auf die Registerkarte **Ereignisse** .

8. Doppelklicken Sie auf das <xref:System.Windows.FrameworkElement.Loaded> Ereignis.

9. Fügen Sie den folgenden Code ein, um das <xref:System.Windows.FrameworkElement.Loaded>-Ereignis zu behandeln.

     Mit diesem Code wird eine Instanz des <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Steuer Elements erstellt und eine Instanz des `AxWindowsMediaPlayer` Steuer Elements als untergeordnetes Element hinzugefügt.

     [!code-csharp[HostingAxInWpf#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
