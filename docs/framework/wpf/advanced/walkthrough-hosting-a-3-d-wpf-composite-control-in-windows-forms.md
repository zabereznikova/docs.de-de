---
title: 'Exemplarische Vorgehensweise: Hosten eines zusammengesetzten 3D-WPF-Steuerelements in Windows Forms'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: 74f82f9be734cb7dc5225dc4226e14c2cee317df
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64605522"
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a>Exemplarische Vorgehensweise: Hosten eines zusammengesetzten 3D-WPF-Steuerelements in Windows Forms

In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie kann eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zusammengesetzten steuern und hosten Sie es in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Steuerelementen und-Formularen mithilfe der <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement.

In dieser exemplarischen Vorgehensweise implementieren Sie eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> , das zwei untergeordnete Steuerelemente enthält. Die <xref:System.Windows.Controls.UserControl> zeigt einen Kegel der dreidimensionalen (3D). 3D-Objekte zu rendern ist viel einfacher, mit der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] als mit [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Aus diesem Grund ist es sinnvoll, auf Host eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> -Klasse zur Erstellung von 3D-Grafiken in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].

In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:

- Erstellen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.

- Erstellen die Windows Forms-Hostprojekts.

- Hosten der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.

## <a name="prerequisites"></a>Vorraussetzungen

Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:

- Visual Studio 2017

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a>Erstellen Sie das UserControl-Steuerelement

1. Erstellen Sie eine **WPF-Benutzersteuerelementbibliothek** Projekt mit dem Namen `HostingWpfUserControlInWf`.

2. Öffnen Sie die Datei UserControl1.xaml im der [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].

3. Ersetzen Sie den generierten Code durch den folgenden Code:

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     Dieser Code definiert eine <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> , das zwei untergeordnete Steuerelemente enthält. Das erste untergeordnete Steuerelement ist ein <xref:System.Windows.Controls.Label?displayProperty=nameWithType> Steuerelement, das zweite ist ein <xref:System.Windows.Controls.Viewport3D> Steuerelement, das einen 3D-Kegel anzeigt.

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a>Erstellen des Hostprojekts

1. Hinzufügen einer **WPF-App ((.NET Framework)** Projekt mit dem Namen `WpfUserControlHost` der Projektmappe. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md).

2. In **Projektmappen-Explorer**, fügen Sie einen Verweis auf die Assembly "WindowsFormsIntegration", mit dem Namen WindowsFormsIntegration.dll.

3. Fügen Sie Verweise auf die folgenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Assemblys:

    - PresentationCore

    - PresentationFramework

    - WindowsBase

4. Fügen einen Verweis auf das `HostingWpfUserControlInWf`-Projekt hinzu.

5. Legen Sie im Projektmappen-Explorer die `WpfUserControlHost` Projekt das Startprojekt sein.

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a>Hosten Sie das UserControl-Steuerelement

1. Öffnen Sie Form1 im Windows Forms-Designer.

2. Klicken Sie im Fenster Eigenschaften auf **Ereignisse**, und doppelklicken Sie dann auf die <xref:System.Windows.Forms.Form.Load> Ereignis, um einen Ereignishandler erstellen.

     Der Code-Editor wird geöffnet, mit dem neu generierten `Form1_Load` -Ereignishandler.

3. Ersetzen Sie den Code in "Form1.cs" durch den folgenden Code ein.

     Die `Form1_Load` -Ereignishandler erstellt eine Instanz des `UserControl1` und fügt hinzu, auf die <xref:System.Windows.Forms.Integration.ElementHost> des Steuerelements Auflistung von untergeordneten Steuerelementen. Die <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement des Formulars die Auflistung der untergeordneten Steuerelemente hinzugefügt.

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms-Beispiel](https://go.microsoft.com/fwlink/?LinkID=160001)