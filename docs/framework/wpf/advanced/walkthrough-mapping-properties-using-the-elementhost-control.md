---
title: "Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem ElementHost-Steuerelement | Microsoft Docs"
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
  - "ElementHost-Steuerelement, Zuordnen von Eigenschaften"
  - "Zuordnen von Eigenschaften"
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem ElementHost-Steuerelement
In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie mithilfe der <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>\-Eigenschaft die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Eigenschaften den entsprechenden Eigenschaften eines gehosteten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Elements zuordnen.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen des Projekts.  
  
-   Definieren einer neuen Eigenschaftenzuordnung.  
  
-   Entfernen der Standardzuordnung einer Eigenschaft.  
  
-   Erweitern der Standardzuordnung einer Eigenschaft.  
  
 Eine vollständige Codeauflistung der in dieser exemplarischen Vorgehensweise veranschaulichten Aufgaben finden Sie unter [Beispiel für das Zuordnen von Eigenschaften mit dem ElementHost\-Steuerelement](http://go.microsoft.com/fwlink/?LinkID=160018).  
  
 Nach Abschluss können Sie [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Eigenschaften den entsprechenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Eigenschaften eines gehosteten Elements zuordnen.  
  
## Vorbereitungsmaßnahmen  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## Erstellen des Projekts  
  
#### So erstellen Sie das Projekt  
  
1.  Erstellen Sie ein [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Anwendungsprojekt mit dem Namen `PropertyMappingWithElementHost`.  Weitere Informationen finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Fügen Sie im Projektmappen\-Explorer Verweise zu den folgenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Assemblys hinzu.  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   WindowsBase  
  
    -   WindowsFormsIntegration  
  
3.  Kopieren Sie den folgenden Code in den Anfang der Codedatei `Form1`.  
  
     [!code-csharp[PropertyMappingWithElementHost#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]  
  
4.  Öffnen Sie `Form1` im Windows Forms\-Designer.  Doppelklicken Sie auf das Formular, um einen Ereignishandler für das <xref:System.Windows.Forms.Form.Load>\-Ereignis hinzuzufügen.  
  
5.  Kehren Sie zum Windows Forms\-Designer zurück, und fügen Sie einen Ereignishandler für das <xref:System.Windows.Forms.Control.Resize>\-Ereignis des Formulars hinzu.  Weitere Informationen finden Sie unter [How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/de-de/8461e9b8-14e8-406f-936e-3726732b23d2).  
  
6.  Deklarieren Sie ein <xref:System.Windows.Forms.Integration.ElementHost>\-Feld in der `Form1`\-Klasse.  
  
     [!code-csharp[PropertyMappingWithElementHost#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]  
  
## Definieren neuer Eigenschaftenzuordnungen  
 Das <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement stellt mehrere Standardzuordnungen von Eigenschaften bereit.  Sie fügen eine neue Eigenschaftenzuordnung hinzu, indem Sie die <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A>\-Methode in der <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> des <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelements aufrufen.  
  
#### So definieren Sie neue Eigenschaftenzuordnungen  
  
1.  Kopieren Sie den folgenden Code in die `Form1`\-Klassendefinition.  
  
     [!code-csharp[PropertyMappingWithElementHost#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]  
  
     Die `AddMarginMapping`\-Methode fügt eine neue Zuordnung für die <xref:System.Windows.Forms.Control.Margin%2A>\-Eigenschaft hinzu.  
  
     Die `OnMarginChange`\-Methode übersetzt die <xref:System.Windows.Forms.Control.Margin%2A>\-Eigenschaft in die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-<xref:System.Windows.FrameworkElement.Margin%2A>\-Eigenschaft.  
  
2.  Kopieren Sie den folgenden Code in die `Form1`\-Klassendefinition.  
  
     [!code-csharp[PropertyMappingWithElementHost#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]  
  
     Die `AddRegionMapping`\-Methode fügt eine neue Zuordnung für die <xref:System.Windows.Forms.Control.Region%2A>\-Eigenschaft hinzu.  
  
     Die `OnRegionChange`\-Methode übersetzt die <xref:System.Windows.Forms.Control.Region%2A>\-Eigenschaft in die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-<xref:System.Windows.UIElement.Clip%2A>\-Eigenschaft.  
  
     Die `Form1_Resize`\-Methode behandelt das <xref:System.Windows.Forms.Control.Resize>\-Ereignis des Formulars und passt die Größe des Clippingbereichs an das gehostete Element an.  
  
## Entfernen der Standardzuordnung einer Eigenschaft  
 Sie entfernen die Standardzuordnung einer Eigenschaft, indem Sie die <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A>\-Methode für die <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> des <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelements aufrufen.  
  
#### So entfernen Sie die Standardzuordnung einer Eigenschaft  
  
-   Kopieren Sie den folgenden Code in die `Form1`\-Klassendefinition.  
  
     [!code-csharp[PropertyMappingWithElementHost#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]  
  
     Die `RemoveCursorMapping`\-Methode löscht die Standardzuordnung für die <xref:System.Windows.Forms.Control.Cursor%2A>\-Eigenschaft.  
  
## Erweitern der Standardzuordnung einer Eigenschaft  
 Sie können die Standardzuordnung einer Eigenschaft verwenden und sie zudem mit Ihrer eigenen Zuordnung erweitern.  
  
#### So erweitern Sie die Standardzuordnung einer Eigenschaft  
  
-   Kopieren Sie den folgenden Code in die `Form1`\-Klassendefinition.  
  
     [!code-csharp[PropertyMappingWithElementHost#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]  
  
     Die `ExtendBackColorMapping`\-Methode fügt der vorhandenen <xref:System.Windows.Forms.Control.BackColor%2A>\-Eigenschaftenzuordnung einen benutzerdefinierten Eigenschaftenübersetzer hinzu.  
  
     Die `OnBackColorChange`\-Methode weist der <xref:System.Windows.Controls.Control.Background%2A>\-Eigenschaft des gehosteten Steuerelements ein bestimmtes Bild zu.  Die `OnBackColorChange`\-Methode wird aufgerufen, nachdem die Standardzuordnung der Eigenschaft angewendet wurde.  
  
## Initialisieren der Eigenschaftenzuordnungen  
  
#### So initialisieren Sie die Eigenschaftenzuordnungen  
  
1.  Kopieren Sie den folgenden Code in die `Form1`\-Klassendefinition.  
  
     [!code-csharp[PropertyMappingWithElementHost#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]  
  
     Die `Form1_Load`\-Methode behandelt das <xref:System.Windows.Forms.Form.Load>\-Ereignis und führt die folgende Initialisierung aus.  
  
    -   Erstellt ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-<xref:System.Windows.Controls.Button>\-Element.  
  
    -   Ruft die Methoden auf, die Sie bereits in der exemplarischen Vorgehensweise zum Festlegen der Eigenschaftenzuordnungen definiert haben.  
  
    -   Weist den zugeordneten Eigenschaften Anfangswerte zu.  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Eigenschaftenzuordnung von Windows Forms und WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)   
 [WPF\-Designer](http://msdn.microsoft.com/de-de/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF\-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)