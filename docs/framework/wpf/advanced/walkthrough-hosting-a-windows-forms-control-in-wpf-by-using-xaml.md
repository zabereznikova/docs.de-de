---
title: Hosten eines Windows Forms-Steuer Elements in WPF mithilfe von XAML
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 99c077801a26043e17e0d51ecc0a97b9608784c0
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095059"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a>Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF mithilfe von XAML
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt viele Steuerelemente mit einem großen Funktionsumfang bereit. Es kann jedoch vorkommen, dass Sie Windows Forms-Steuerelemente auf Ihren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Seiten verwenden möchten. Beispielsweise haben Sie möglicherweise beträchtliche Investitionen in vorhandene Windows Forms-Steuerelemente, oder Sie verfügen über ein Windows Forms-Steuerelement, das eindeutige Funktionen bereitstellt.  
  
 In dieser exemplarischen Vorgehensweise wird gezeigt, wie Sie mithilfe [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]ein Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType>-Steuerelement auf einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Seite hosten.  
  
 Eine vollständige Code Auflistung der in dieser exemplarischen Vorgehensweise gezeigten Aufgaben finden [Sie unter Hosting a Windows Forms Control in WPF using XAML Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).
  
## <a name="prerequisites"></a>Voraussetzungen  

Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.  
  
## <a name="hosting-the-windows-forms-control"></a>Hosten des Windows Forms-Steuerelements  
  
#### <a name="to-host-the-maskedtextbox-control"></a>So hosten Sie das MaskedTextBox-Steuerelement  
  
1. Erstellen Sie ein WPF-Anwendungsprojekt mit dem Namen `HostingWfInWpfWithXaml`.  
  
2. Fügen Sie Verweise auf die folgenden Assemblys hinzu.  
  
    - WindowsFormsIntegration  
  
    - System.Windows.Forms  
  
3. Öffnen Sie die Datei "MainWindow. XAML" im WPF-Designer.  
  
4. Fügen Sie im <xref:System.Windows.Window>-Element die folgende Namespace Zuordnung hinzu. Die `wf`-Namespace Zuordnung legt einen Verweis auf die Assembly fest, die das Windows Forms Steuerelement enthält.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. Fügen Sie im <xref:System.Windows.Controls.Grid>-Element den folgenden XAML-Code hinzu.  
  
     Das <xref:System.Windows.Forms.MaskedTextBox> Steuerelement wird als untergeordnetes Element des <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuer Elements erstellt.  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Windows Forms-Steuerelemente und entsprechende WPF-Steuerelemente](windows-forms-controls-and-equivalent-wpf-controls.md)
- [Hosting eines Windows Forms-Steuer Elements in WPF mithilfe von XAML-Beispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml)
