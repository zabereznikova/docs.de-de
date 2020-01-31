---
title: Zusammengesetztes 3D-WPF-Steuerelement in Windows Forms
titleSuffix: ''
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: aaa726ac90fd75a12054c18be6ec08a1372c1128
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794210"
---
# <a name="walkthrough-host-a-3d-wpf-composite-control-in-windows-forms"></a>Exemplarische Vorgehensweise: Hosten eines zusammengesetzten 3D WPF-Steuer Elements in Windows Forms

In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zusammengesetztes Steuerelement erstellen und es mithilfe des <xref:System.Windows.Forms.Integration.ElementHost>-Steuer Elements in Windows Forms Steuerelementen und Formularen hosten

In dieser exemplarischen Vorgehensweise implementieren Sie einen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>, der zwei untergeordnete Steuerelemente enthält. Die <xref:System.Windows.Controls.UserControl> zeigt einen dreidimensionalen (3D-) Kegel an. Das Rendern von 3D-Objekten ist mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wesentlich einfacher als mit Windows Forms. Daher ist es sinnvoll, eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> Klasse zu hosten, um 3D-Grafiken in Windows Forms zu erstellen.

In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:

- Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>wird erstellt.

- Das Windows Forms Host Projekt wird erstellt.

- Hosting des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.

## <a name="prerequisites"></a>Erforderliche Komponenten

Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:

- Visual Studio 2017

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a>Erstellen des UserControl-Steuer Elements

1. Erstellen Sie ein **WPF-Benutzer Steuer** Element-Bibliotheksprojekt namens `HostingWpfUserControlInWf`.

2. Öffnen Sie UserControl1. XAML im WPF-Designer.

3. Ersetzen Sie den generierten Code durch den folgenden Code:

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     Dieser Code definiert eine <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>, die zwei untergeordnete Steuerelemente enthält. Das erste untergeordnete Steuerelement ist ein <xref:System.Windows.Controls.Label?displayProperty=nameWithType> Steuerelement; die zweite ist ein <xref:System.Windows.Controls.Viewport3D> Steuerelement, das einen 3D-Kegel anzeigt.

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a>Erstellen des Host Projekts

1. Fügen Sie der Projekt Mappe ein **Windows Forms App-Projekt (.NET Framework)** mit dem Namen `WpfUserControlHost` hinzu.

2. Fügen Sie in **Projektmappen-Explorer**einen Verweis auf die WindowsFormsIntegration-Assembly mit dem Namen "WindowsFormsIntegration. dll" hinzu.

3. Fügen Sie Verweise auf die folgenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Assemblys hinzu:

    - PresentationCore

    - PresentationFramework

    - WindowsBase

4. Fügen einen Verweis auf das `HostingWpfUserControlInWf`-Projekt hinzu.

5. Legen Sie in Projektmappen-Explorer das `WpfUserControlHost` Projekt als Startprojekt fest.

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a>Hosten von UserControl

1. Öffnen Sie in der Windows Forms-Designer Form1.

2. Klicken Sie im Eigenschaftenfenster auf **Ereignisse**, und doppelklicken Sie dann auf das <xref:System.Windows.Forms.Form.Load>-Ereignis, um einen Ereignishandler zu erstellen.

     Der Code-Editor wird mit dem neu generierten `Form1_Load` Ereignishandler geöffnet.

3. Ersetzen Sie den Code in Form1.cs durch den folgenden Code.

     Der `Form1_Load`-Ereignishandler erstellt eine Instanz von `UserControl1` und fügt die Auflistung von untergeordneten Steuerelementen des <xref:System.Windows.Forms.Integration.ElementHost>-Steuer Elements hinzu. Das <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement wird der Auflistung von untergeordneten Steuerelementen des Formulars hinzugefügt.

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Hosting eines zusammengesetzten WPF-Steuer Elements in Windows Forms Beispiel](https://go.microsoft.com/fwlink/?LinkID=160001)
