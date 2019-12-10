---
title: 'Gewusst wie: Aktivieren von visuellen Stilen in einer Hybridanwendung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- visual styles [Windows Forms]
ms.assetid: 95de9b9c-d804-405c-b2d1-49a88c1e0fe1
ms.openlocfilehash: 251c53a8665d2eae7c3b5bb23b0a388009362dcc
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960111"
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a>Gewusst wie: Aktivieren von visuellen Stilen in einer Hybridanwendung
In diesem Thema wird gezeigt, wie Sie visuelle Stile für ein [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement aktivieren, das in einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]basierten Anwendung gehostet wird.  
  
 Wenn die Anwendung die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>-Methode aufruft, werden die meisten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente automatisch visuelle Stile verwenden. Weitere Informationen finden Sie unter [Rendering von Steuerelementen mit visuellen Stilen](../../winforms/controls/rendering-controls-with-visual-styles.md).  
  
 Eine umfassende Code Auflistung der in diesem Thema dargestellten Aufgaben finden Sie unter [Aktivieren von visuellen Stilen in Hybrid Anwendungen](https://go.microsoft.com/fwlink/?LinkID=159986).  
  
## <a name="enabling-windows-forms-visual-styles"></a>Aktivieren visueller Windows Forms-Stile  
  
#### <a name="to-enable-windows-forms-visual-styles"></a>Aktivieren visueller Windows Forms-Stile  
  
1. Erstellen Sie ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungsprojekt mit dem Namen `HostingWfWithVisualStyles`.  
  
2. Fügen Sie im Projektmappen-Explorer Verweise auf die folgenden Assemblys hinzu.  
  
    - WindowsFormsIntegration  
  
    - System.Windows.Forms  
  
3. Doppelklicken Sie in der Toolbox auf das <xref:System.Windows.Controls.Grid> Symbol, um ein <xref:System.Windows.Controls.Grid> Element auf der Entwurfs Oberfläche zu platzieren.  
  
4. Legen Sie im Eigenschaftenfenster die Werte der Eigenschaften <xref:System.Windows.FrameworkElement.Height%2A> und <xref:System.Windows.FrameworkElement.Width%2A> auf **Auto**fest.  
  
5. Wählen Sie in Designansicht-oder XAML-Ansicht den <xref:System.Windows.Window>aus.  
  
6. Klicken Sie im Eigenschaftenfenster auf die Registerkarte **Ereignisse** .  
  
7. Doppelklicken Sie auf das <xref:System.Windows.FrameworkElement.Loaded> Ereignis.
  
8. Fügen Sie in MainWindow. XAML. vb oder MainWindow.XAML.cs den folgenden Code ein, um das <xref:System.Windows.FrameworkElement.Loaded>-Ereignis zu behandeln.  
  
     [!code-csharp[HostingWfWithVisualStyles#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
     Das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement wird mit visuellen Stilen gezeichnet.  
  
## <a name="disabling-windows-forms-visual-styles"></a>Deaktivieren visueller Windows Forms-Stile  
 Wenn Sie visuelle Stile deaktivieren möchten, entfernen Sie einfach den aufzurufenden <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> Methode.  
  
#### <a name="to-disable-windows-forms-visual-styles"></a>So deaktivieren Sie visuelle Stile für Windows Forms  
  
1. Öffnen Sie „MainWindow.Xaml.vb“ bzw. „MainWindow.Xaml.cs“ im Code-Editor.  
  
2. Kommentieren Sie den aufzurufenden <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> Methode aus.  
  
3. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
     Das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement wird mit dem Standard Systemstil gezeichnet.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>
- <xref:System.Windows.Forms.VisualStyles>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Rendering von Steuerelementen mit visuellen Stilen](../../winforms/controls/rendering-controls-with-visual-styles.md)
- [Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
