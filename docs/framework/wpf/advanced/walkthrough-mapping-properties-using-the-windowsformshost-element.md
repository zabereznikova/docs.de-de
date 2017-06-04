---
title: "Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem WindowsFormsHost-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Zuordnen von Eigenschaften"
  - "WindowsFormsHost-Elementeigenschaftszuordnung"
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem WindowsFormsHost-Element
In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie die <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> -Eigenschaft zum Zuordnen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften den entsprechenden Eigenschaften eines gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen des Projekts.  
  
-   Definieren des Anwendungslayouts.  
  
-   Definieren eine neue eigenschaftenzuordnung.  
  
-   Entfernen die Zuordnung einer Standard-Eigenschaft.  
  
-   Ersetzen die Zuordnung einer Standard-Eigenschaft.  
  
-   Erweitern Sie die Zuordnung einer Standard-Eigenschaft.  
  
 Vollständige Codeliste der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Zuordnen von Eigenschaften mit dem WindowsFormsHost-Element-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160019).  
  
 Wenn Sie fertig sind, werden zuordnen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften den entsprechenden Eigenschaften eines gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
  
#### <a name="to-create-and-set-up-the-project"></a>Erstellen und Einrichten des Projekts  
  
1.  Erstellen Sie ein WPF-Anwendungsprojekt mit dem Namen `PropertyMappingWithWfhSample`.  
  
2.  Fügen Sie im Projektmappen-Explorer einen Verweis auf die WindowsFormsIntegration-Assembly mit die Namen WindowsFormsIntegration.dll hinzu.  
  
3.  Fügen Sie im Projektmappen-Explorer Verweise auf die Assemblys System.Drawing und System.Windows.Forms.  
  
## <a name="defining-the-application-layout"></a>Definieren des Anwendungslayouts  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]--basierte Anwendung verwendet die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element Host ein [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.  
  
#### <a name="to-define-the-application-layout"></a>Definieren Sie das Layout der Anwendung  
  
1.  Öffnen Sie Window1.xaml in der [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
2.  Ersetzen Sie den vorhandenen Code durch den folgenden Code ein.  
  
     [!code-xml[PropertyMappingWithWfhSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]  
  
3.  Öffnen Sie Window1.xaml.cs im Code-Editor.  
  
4.  Importieren Sie am Anfang der Datei die folgenden Namespaces ein.  
  
     [!code-csharp[PropertyMappingWithWfhSample#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]  
  
## <a name="defining-a-new-property-mapping"></a>Definieren eine neue Eigenschaftenzuordnung  
 Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element stellt verschiedene eigenschaftenzuordnungen. Hinzufügen eine neuen eigenschaftenzuordnung durch den Aufruf der <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> Methode für die <xref:System.Windows.Forms.Integration.WindowsFormsHost> des Elements <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.  
  
#### <a name="to-define-a-new-property-mapping"></a>Um eine neue eigenschaftenzuordnung zu definieren.  
  
-   Kopieren Sie den folgenden Code in die Definition für die `Window1` Klasse.  
  
     [!code-csharp[PropertyMappingWithWfhSample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]  
  
     Die `AddClipMapping` -Methode fügt eine neue Zuordnung für die <xref:System.Windows.UIElement.Clip%2A> Eigenschaft.  
  
     Die `OnClipChange` Methode übersetzt die <xref:System.Windows.UIElement.Clip%2A> Eigenschaft, um die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.Region%2A> Eigenschaft.  
  
     Die `Window1_SizeChanged` Methode verarbeitet das <xref:System.Windows.FrameworkElement.SizeChanged> Ereignis und passt die Größe des Clippingbereichs an das Anwendungsfenster angepasst.  
  
## <a name="removing-a-default-property-mapping"></a>Entfernen die Zuordnung einer Standard-Eigenschaft  
 Entfernen Sie die Zuordnung einer Standard-Eigenschaft durch den Aufruf der <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> Methode für die <xref:System.Windows.Forms.Integration.WindowsFormsHost> des Elements <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.  
  
#### <a name="to-remove-a-default-property-mapping"></a>So entfernen Sie die Zuordnung einer Standard-Eigenschaft  
  
-   Kopieren Sie den folgenden Code in die Definition für die `Window1` Klasse.  
  
     [!code-csharp[PropertyMappingWithWfhSample#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]  
  
     Die `RemoveCursorMapping` -Methode löscht das Standardmapping für die <xref:System.Windows.FrameworkElement.Cursor%2A> Eigenschaft.  
  
## <a name="replacing-a-default-property-mapping"></a>Ersetzen die Zuordnung einer Standard-Eigenschaft  
 Ersetzen Sie die Zuordnung einer Standard-Eigenschaft durch Entfernen der Zuordnung und Aufrufen der <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> Methode für die <xref:System.Windows.Forms.Integration.WindowsFormsHost> des Elements <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.  
  
#### <a name="to-replace-a-default-property-mapping"></a>Ersetzen Sie die Zuordnung einer Standard-Eigenschaft  
  
-   Kopieren Sie den folgenden Code in die Definition für die `Window1` Klasse.  
  
     [!code-csharp[PropertyMappingWithWfhSample#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]  
  
     Die `ReplaceFlowDirectionMapping` Methode ersetzt das Standardmapping für die <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft.  
  
     Die `OnFlowDirectionChange` Methode übersetzt die <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft, um die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.RightToLeft%2A> Eigenschaft.  
  
     Die `cb_CheckedChanged` Methode behandelt das <xref:System.Windows.Forms.CheckBox.CheckedChanged> -Ereignis auf der <xref:System.Windows.Forms.CheckBox> Steuerelement. Weist die <xref:System.Windows.FrameworkElement.FlowDirection%2A> -Eigenschaft basierend auf dem Wert der <xref:System.Windows.Forms.CheckBox.CheckState%2A> Eigenschaft  
  
## <a name="extending-a-default-property-mapping"></a>Erweitern Sie die Zuordnung einer Standard-Eigenschaft  
 Sie können die Zuordnung einer Standard-Eigenschaft verwenden und auch mit Ihren eigenen Zuordnung zu erweitern.  
  
#### <a name="to-extend-a-default-property-mapping"></a>Erweitern Sie die Zuordnung einer Standard-Eigenschaft  
  
-   Kopieren Sie den folgenden Code in die Definition für die `Window1` Klasse.  
  
     [!code-csharp[PropertyMappingWithWfhSample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]  
  
     Die `ExtendBackgroundMapping` Methode fügt einen benutzerdefinierte Eigenschaftenübersetzer zur vorhandenen <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft zuordnen.  
  
     Die `OnBackgroundChange` Methode weist ein bestimmtes Bild des gehosteten Steuerelements <xref:System.Windows.Forms.Control.BackgroundImage%2A> Eigenschaft. Die `OnBackgroundChange` Methode wird aufgerufen, nachdem das Standardmapping für die Eigenschaft angewendet wird.  
  
## <a name="initializing-your-property-mappings"></a>Initialisieren die Eigenschaftenzuordnungen  
 Richten Sie die eigenschaftenzuordnungen durch Aufrufen der oben beschriebenen Methoden in der <xref:System.Windows.FrameworkElement.Loaded> -Ereignishandler.  
  
#### <a name="to-initialize-your-property-mappings"></a>Die eigenschaftenzuordnungen initialisiert werden.  
  
1.  Kopieren Sie den folgenden Code in die Definition für die `Window1` Klasse.  
  
     [!code-csharp[PropertyMappingWithWfhSample#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]  
  
     Die `WindowLoaded` Methode behandelt das <xref:System.Windows.FrameworkElement.Loaded> Ereignis und führt die folgende Initialisierung.  
  
    -   Erstellt eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.CheckBox> Steuerelement.  
  
    -   Ruft die Methoden, die Sie zuvor in der exemplarischen Vorgehensweise zum Einrichten der eigenschaftenzuordnungen definiert.  
  
    -   Anfangswerte weist den zugeordneten Eigenschaften.  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Klicken Sie auf das Kontrollkästchen, um die Auswirkung der der <xref:System.Windows.FrameworkElement.FlowDirection%2A> Zuordnung. Wenn Sie das Kontrollkästchen klicken, kehrt das Layout seine Ausrichtung von links nach rechts.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Windows Forms und WPF Property Mapping](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)   
 [WPF-Designer](http://msdn.microsoft.com/de-de/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)