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
ms.openlocfilehash: 2d714ad020f2f7b6a6343c8f8e3901b59dfd23a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545622"
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a>Gewusst wie: Aktivieren von visuellen Stilen in einer Hybridanwendung
In diesem Thema wird gezeigt, wie aktivieren [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] visuelle Stile für eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement gehostet wird, einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]--basierten Anwendung.  
  
 Wenn die Anwendung aufruft der <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> -Methode, die meisten Ihrer [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente automatisch visuelle Stile verwenden, wenn die Anwendung ausgeführt wird, auf [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)]. Weitere Informationen finden Sie unter [Rendern von Steuerelementen mit visuellen Stilen](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md).  
  
 Vollständige Codeliste der Aufgaben in diesem Thema veranschaulicht, finden Sie unter [Aktivieren von visuellen Stilen in einer Anwendung Hybridbeispiel](http://go.microsoft.com/fwlink/?LinkID=159986).  
  
## <a name="enabling-windows-forms-visual-styles"></a>Aktivieren visueller Windows Forms-Stile  
  
#### <a name="to-enable-windows-forms-visual-styles"></a>Aktivieren visueller Windows Forms-Stile  
  
1.  Erstellen einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Anwendungsprojekt mit dem Namen `HostingWfWithVisualStyles`.  
  
2.  Fügen Sie im Projektmappen-Explorer Verweise auf die folgenden Assemblys hinzu.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  Doppelklicken Sie in der Toolbox auf die <xref:System.Windows.Controls.Grid> Symbol zum Platzieren einer <xref:System.Windows.Controls.Grid> Element auf der Entwurfsoberfläche angezeigt.  
  
4.  Legen Sie im Fenster Eigenschaften die Werte von der <xref:System.Windows.FrameworkElement.Height%2A> und <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaften **Auto**.  
  
5.  Wählen Sie in der Entwurfsansicht oder der XAML-Ansicht, die <xref:System.Windows.Window>.  
  
6.  Klicken Sie im Eigenschaftenfenster auf die **Ereignisse** Registerkarte.  
  
7.  Doppelklicken Sie auf die <xref:System.Windows.FrameworkElement.Loaded> Ereignis.
  
8.  Fügen Sie in "MainWindow.Xaml.vb" bzw. "MainWindow.Xaml.cs" den folgenden Code zum Behandeln der <xref:System.Windows.FrameworkElement.Loaded> Ereignis.  
  
     [!code-csharp[HostingWfWithVisualStyles#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
     Die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement mit visuellen Stilen gezeichnet wird.  
  
## <a name="disabling-windows-forms-visual-styles"></a>Deaktivieren visueller Windows Forms-Stile  
 Um visuelle Stile zu deaktivieren, entfernen Sie einfach den Aufruf der <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> Methode.  
  
#### <a name="to-disable-windows-forms-visual-styles"></a>So deaktivieren Sie visuelle Stile für Windows Forms  
  
1.  Öffnen Sie „MainWindow.Xaml.vb“ bzw. „MainWindow.Xaml.cs“ im Code-Editor.  
  
2.  Kommentieren Sie den Aufruf der <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> Methode.  
  
3.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
     Die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement gezeichnet wird, mit der Standardformatvorlage-System.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>  
 <xref:System.Windows.Forms.VisualStyles>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Rendering von Steuerelementen mit visuellen Stilen](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)  
 [Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)
