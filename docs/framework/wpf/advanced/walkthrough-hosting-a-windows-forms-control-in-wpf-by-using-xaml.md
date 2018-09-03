---
title: 'Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF mithilfe von XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 2f13689a15e91ee0f80c0d7b6bc71c5f973b8333
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43487129"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a>Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF mithilfe von XAML
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt viele Steuerelemente mit einem großen Funktionsumfang bereit. Allerdings unter Umständen möchten Sie verwenden [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] steuert, die auf Ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Seiten. Angenommen, Sie müssen möglicherweise eine erhebliche Investition in vorhandenen [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente, oder Sie haben möglicherweise eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Steuerelement, das einzigartige Funktionen bereitstellt.  
  
 In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie ein Windows Forms hosten <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control für eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Seite mithilfe von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Eine vollständige codeauflistung der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Hosten eines Windows Forms-Steuerelements in WPF mithilfe von XAML-Beispiel](https://go.microsoft.com/fwlink/?LinkID=160000).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]  
  
## <a name="hosting-the-windows-forms-control"></a>Hosten des Windows Forms-Steuerelements  
  
#### <a name="to-host-the-maskedtextbox-control"></a>So hosten Sie das MaskedTextBox-Steuerelement  
  
1.  Erstellen einer WPF-Anwendungsprojekt mit dem Namen `HostingWfInWpfWithXaml`.  
  
2.  Fügen Sie Verweise auf die folgenden Assemblys hinzu.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  Öffnen Sie "MainWindow.xaml" in der [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
4.  In der <xref:System.Windows.Window> -Element, fügen Sie die folgende Namespacezuordnung hinzu. Die `wf` Namespace-Zuordnung erstellt einen Verweis auf die Assembly, die das Windows Forms-Steuerelement enthält.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  In der <xref:System.Windows.Controls.Grid> Element fügen Sie das folgende XAML hinzu.  
  
     Die <xref:System.Windows.Forms.MaskedTextBox> Steuerelement wird erstellt, als untergeordnetes Element der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement.  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Entwerfen von XAML-Code in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)  
 [Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)  
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [Windows Forms-Steuerelemente und entsprechende WPF-Steuerelemente](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)  
 [Hosten eines Windows Forms-Steuerelements in WPF mit XAML-Beispiel](https://go.microsoft.com/fwlink/?LinkID=160000)
