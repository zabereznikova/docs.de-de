---
title: 'Exemplarische Vorgehensweise: Hosten eines ActiveX-Steuerelements in WPF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ActiveX controls [WPF interoperability]
- hosting ActiveX controls [WPF]
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
ms.openlocfilehash: 25019444e107af2ad681e9f51adebbf01c444438
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668315"
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a>Exemplarische Vorgehensweise: Hosten eines ActiveX-Steuerelements in WPF
Um verbesserte Interaktion mit Browsern zu aktivieren, können Sie [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] -Steuerelemente in Ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-basierten Anwendung. In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie hosten können die [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] als ein Steuerelement auf einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Seite.

 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:

-   Erstellen des Projekts.

-   Erstellen das ActiveX-Steuerelement.

-   Hosten das ActiveX-Steuerelement auf einer WPF-Seite.

 Wenn Sie diese exemplarische Vorgehensweise abgeschlossen haben, wissen Sie, wie mit [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] -Steuerelemente in Ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-basierenden Anwendung.

## <a name="prerequisites"></a>Vorraussetzungen
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:

-   [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] installiert auf dem Computer, auf dem Visual Studio installiert ist.

-   Visual Studio 2010.

## <a name="creating-the-project"></a>Erstellen des Projekts

#### <a name="to-create-and-set-up-the-project"></a>So erstellen und richten Sie das Projekt ein

1.  Erstellen einer WPF-Anwendungsprojekt mit dem Namen `HostingAxInWpf`.

2.  Hinzufügen ein Windows Forms-Steuerelementbibliothek-Projekts zur Projektmappe, und nennen Sie das Projekt `WmpAxLib`.

3.  Fügen Sie einen Verweis auf die Windows Media Player-Assembly, mit die Namen wmp.dll WmpAxLib im Projekt hinzu.

4.  Öffnen der **Toolbox**.

5.  Mit der rechten Maustaste den **Toolbox**, und klicken Sie dann auf **Elemente auswählen**.

6.  Klicken Sie auf die **COM-Komponenten** Registerkarte die **Windows Media Player** steuern, und klicken Sie dann auf **OK**.

     Das Windows Media Player-Steuerelement wird hinzugefügt, um die **Toolbox**.

7.  Klicken Sie im Projektmappen-Explorer mit der Maustaste der **"UserControl1"** Datei, und klicken Sie dann auf **umbenennen**.

8.  Ändern Sie den Namen in `WmpAxControl.vb` oder `WmpAxControl.cs`, je nach Sprache.

9. Wenn Sie aufgefordert werden, alle Verweise umzubenennen, klicken Sie auf **Ja**.

## <a name="creating-the-activex-control"></a>Erstellen das ActiveX-Steuerelement
 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] generiert automatisch ein <xref:System.Windows.Forms.AxHost> Wrapperklasse für ein [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] steuern, wenn das Steuerelement, einer Entwurfsoberfläche hinzugefügt wird. Die folgende Prozedur erstellt eine verwaltete Assembly mit dem Namen AxInterop.WMPLib.dll.

#### <a name="to-create-the-activex-control"></a>Beim Erstellen des ActiveX-Steuerelements

1.  Öffnen Sie WmpAxControl.vb oder WmpAxControl.cs im Windows Forms-Designer an.

2.  Von der **Toolbox**, fügen Sie das Windows Media Player-Steuerelement, auf die Entwurfsoberfläche.

3.  Legen Sie im Eigenschaftenfenster den Wert des Windows Media Player-Steuerelements <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Fill>.

4.  Erstellen Sie das WmpAxLib Steuerelementbibliothek-Projekt.

## <a name="hosting-the-activex-control-on-a-wpf-page"></a>Hosten das ActiveX-Steuerelement auf einer WPF-Seite

#### <a name="to-host-the-activex-control"></a>Zum Hosten des ActiveX-Steuerelements

1.  Fügen Sie in HostingAxInWpf-Projekt einen Verweis auf die generierte [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] Interop-Assembly.

     Diese Assembly ist mit dem Namen AxInterop.WMPLib.dll und wurde dem Debugordner des Projekts WmpAxLib hinzugefügt, wenn Sie das Windows Media Player-Steuerelement importiert.

2.  Fügen Sie einen Verweis auf die Assembly "WindowsFormsIntegration", mit die Namen WindowsFormsIntegration.dll hinzu.

3.  Hinzufügen eines Verweises auf die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Assembly, die mit dem Namen "System.Windows.Forms.dll".

4.  Öffnen Sie "MainWindow.xaml" im WPF-Designer.

5.  Name der <xref:System.Windows.Controls.Grid> Element `grid1`.

     [!code-xaml[HostingAxInWpf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]

6.  Wählen Sie in der Entwurfsansicht oder XAML-Ansicht der <xref:System.Windows.Window> Element.

7.  Klicken Sie im Eigenschaftenfenster auf die **Ereignisse** Registerkarte.

8.  Doppelklicken Sie auf die <xref:System.Windows.FrameworkElement.Loaded> Ereignis.

9. Fügen Sie den folgenden Code zum Behandeln der <xref:System.Windows.FrameworkElement.Loaded> Ereignis.

     Dieser Code erstellt eine Instanz der <xref:System.Windows.Forms.Integration.WindowsFormsHost> steuern und fügt eine Instanz des der `AxWindowsMediaPlayer` Steuerelement als untergeordnetes Element.

     [!code-csharp[HostingAxInWpf#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
