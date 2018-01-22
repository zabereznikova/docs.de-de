---
title: 'Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem WindowsFormsHost-Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eaab6b7724a1e6145dfce3998ccf75904df01802
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a>Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem WindowsFormsHost-Element
Diese exemplarische Vorgehensweise veranschaulicht das Verwenden der <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> zuzuordnenden Eigenschaft [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften den entsprechenden Eigenschaften eines gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen des Projekts  
  
-   Definieren des Anwendungslayouts  
  
-   Definieren einer neuen Eigenschaftenzuordnung  
  
-   Entfernen einer standardmäßigen Eigenschaftenzuordnung  
  
-   Ersetzen einer standardmäßigen Eigenschaftenzuordnung  
  
-   Erweitern einer standardmäßigen Eigenschaftenzuordnung  
  
 Vollständige Codeliste der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Zuordnen von Eigenschaften mit dem WindowsFormsHost-Element-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160019).  
  
 Wenn Sie fertig sind, können Sie zeilenfilterausdruck zuordnen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften den entsprechenden Eigenschaften eines gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
  
#### <a name="to-create-and-set-up-the-project"></a>So erstellen und richten Sie das Projekt ein  
  
1.  Erstellen Sie ein WPF-Anwendungsprojekt mit dem Namen `PropertyMappingWithWfhSample`.  
  
2.  Fügen Sie im Projektmappen-Explorer einen Verweis auf die Assembly mit die Namen WindowsFormsIntegration.dll WindowsFormsIntegration.  
  
3.  Fügen Sie im Projektmappen-Explorer Verweise auf die Assemblys "System.Drawing" und "System.Windows.Forms".  
  
## <a name="defining-the-application-layout"></a>Definieren des Anwendungslayouts  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]--basierte Anwendung verwendet die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element Host ein [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.  
  
#### <a name="to-define-the-application-layout"></a>So definieren sie das Anwendungslayout  
  
1.  Öffnen Sie Window1.xaml in der [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
2.  Ersetzen Sie den vorhandenen Code durch folgenden Code:  
  
     [!code-xaml[PropertyMappingWithWfhSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]  
  
3.  Öffnen Sie Window1.xaml.cs im Code-Editor.  
  
4.  Importieren Sie am Anfang der Datei die folgenden Namespaces.  
  
     [!code-csharp[PropertyMappingWithWfhSample#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]  
  
## <a name="defining-a-new-property-mapping"></a>Definieren einer neuen Eigenschaftenzuordnung  
 Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element stellt mehrere eigenschaftenzuordnungen bereit. Sie fügen Sie eine neue eigenschaftenzuordnung durch Aufrufen der <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> Methode für die <xref:System.Windows.Forms.Integration.WindowsFormsHost> des Elements <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.  
  
#### <a name="to-define-a-new-property-mapping"></a>Definieren einer neuen Eigenschaftenzuordnung  
  
-   Kopieren Sie den folgenden Code in die Definition für die `Window1` Klasse.  
  
     [!code-csharp[PropertyMappingWithWfhSample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]  
  
     Die `AddClipMapping` Methode fügt eine neue Zuordnung für die <xref:System.Windows.UIElement.Clip%2A> Eigenschaft.  
  
     Die `OnClipChange` -Methode der <xref:System.Windows.UIElement.Clip%2A> Eigenschaft, um die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.Region%2A> Eigenschaft.  
  
     Die `Window1_SizeChanged` Methode behandelt des Fensters <xref:System.Windows.FrameworkElement.SizeChanged> Ereignis und die Größe des Clippingbereichs entsprechend im Anwendungsfenster angezeigt.  
  
## <a name="removing-a-default-property-mapping"></a>Entfernen einer standardmäßigen Eigenschaftenzuordnung  
 Entfernen Sie die Zuordnung einer Standard-Eigenschaft durch Aufrufen der <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> Methode für die <xref:System.Windows.Forms.Integration.WindowsFormsHost> des Elements <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.  
  
#### <a name="to-remove-a-default-property-mapping"></a>Entfernen einer standardmäßigen Eigenschaftenzuordnung  
  
-   Kopieren Sie den folgenden Code in die Definition für die `Window1` Klasse.  
  
     [!code-csharp[PropertyMappingWithWfhSample#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]  
  
     Die `RemoveCursorMapping` -Methode löscht die standardzuordnung für die <xref:System.Windows.FrameworkElement.Cursor%2A> Eigenschaft.  
  
## <a name="replacing-a-default-property-mapping"></a>Ersetzen einer standardmäßigen Eigenschaftenzuordnung  
 Ersetzen Sie die Zuordnung einer Standard-Eigenschaft entfernen, indem die standardzuordnung und Aufrufen der <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> Methode für die <xref:System.Windows.Forms.Integration.WindowsFormsHost> des Elements <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.  
  
#### <a name="to-replace-a-default-property-mapping"></a>So ersetzen Sie eine standardmäßige Eigenschaftenzuordnung  
  
-   Kopieren Sie den folgenden Code in die Definition für die `Window1` Klasse.  
  
     [!code-csharp[PropertyMappingWithWfhSample#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]  
  
     Die `ReplaceFlowDirectionMapping` Methode ersetzt die standardzuordnung für die <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft.  
  
     Die `OnFlowDirectionChange` -Methode der <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft, um die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.RightToLeft%2A> Eigenschaft.  
  
     Die `cb_CheckedChanged` Methode behandelt das <xref:System.Windows.Forms.CheckBox.CheckedChanged> Ereignis auf der <xref:System.Windows.Forms.CheckBox> Steuerelement. Weist die <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft basierend auf den Wert der <xref:System.Windows.Forms.CheckBox.CheckState%2A> Eigenschaft  
  
## <a name="extending-a-default-property-mapping"></a>Erweitern einer standardmäßigen Eigenschaftenzuordnung  
 Sie können auch eine standardmäßige Eigenschaftenzuordnung verwenden und sie um Ihre eigenen Zuordnung erweitern.  
  
#### <a name="to-extend-a-default-property-mapping"></a>So erweitern Sie eine standardmäßigen Eigenschaftenzuordnung  
  
-   Kopieren Sie den folgenden Code in die Definition für die `Window1` Klasse.  
  
     [!code-csharp[PropertyMappingWithWfhSample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]  
  
     Die `ExtendBackgroundMapping` Methode fügt eine benutzerdefinierte Eigenschaftenübersetzer zur vorhandenen <xref:System.Windows.Controls.Control.Background%2A> eigenschaftenzuordnung.  
  
     Die `OnBackgroundChange` Methode weist ein bestimmtes Abbild des gehosteten Steuerelements <xref:System.Windows.Forms.Control.BackgroundImage%2A> Eigenschaft. Die `OnBackgroundChange` Methode wird aufgerufen, nachdem die standardzuordnung für die Eigenschaft angewendet wird.  
  
## <a name="initializing-your-property-mappings"></a>Initialisieren der Eigenschaftenzuordnungen  
 Einrichten von gehen die eigenschaftenzuordnungen durch Aufrufen der zuvor beschriebenen Methoden der <xref:System.Windows.FrameworkElement.Loaded> -Ereignishandler.  
  
#### <a name="to-initialize-your-property-mappings"></a>So initialisieren Sie Ihre Eigenschaftenzuordnungen  
  
1.  Kopieren Sie den folgenden Code in die Definition für die `Window1` Klasse.  
  
     [!code-csharp[PropertyMappingWithWfhSample#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]  
  
     Die `WindowLoaded` Methode behandelt das <xref:System.Windows.FrameworkElement.Loaded> Ereignis und führt die folgenden Initialisierung.  
  
    -   Erstellt eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.CheckBox> Steuerelement.  
  
    -   Sie ruft die Methoden, die Sie zuvor in der exemplarischen Vorgehensweise definiert haben, auf, um die Eigenschaftenzuordnungen einzurichten.  
  
    -   Sie weist den zugeordneten Eigenschaften Anfangswerte zu.  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Klicken Sie auf dieses Kontrollkästchen, damit die Auswirkungen der finden Sie unter der <xref:System.Windows.FrameworkElement.FlowDirection%2A> Zuordnung. Wenn Sie das Kontrollkästchen klicken, kehrt das Layout seine Links-Rechts-Ausrichtung um.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Eigenschaftenzuordnung von Windows Forms und WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [WPF-Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)
