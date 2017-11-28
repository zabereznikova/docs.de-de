---
title: 'Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem ElementHost-Steuerelement'
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
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dae954012d15431d2019d3d9cbe61747a8646d4b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a>Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem ElementHost-Steuerelement
Diese exemplarische Vorgehensweise veranschaulicht das Verwenden der <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> zuzuordnenden Eigenschaft [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Eigenschaften den entsprechenden Eigenschaften eines gehosteten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Element.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen des Projekts.  
  
-   Definieren einer neuen Eigenschaftenzuordnung  
  
-   Entfernen einer standardmäßigen Eigenschaftenzuordnung  
  
-   Erweitern einer standardmäßigen Eigenschaftenzuordnung  
  
 Vollständige Codeliste der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Zuordnungseigenschaften, die mithilfe der ElementHost-Steuerelement-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160018).  
  
 Wenn Sie fertig sind, können Sie zeilenfilterausdruck zuordnen [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Eigenschaften entsprechenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften in einem gehosteten Element.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
  
#### <a name="to-create-the-project"></a>So erstellen Sie das Projekt  
  
1.  Erstellen einer [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Anwendungsprojekt mit dem Namen `PropertyMappingWithElementHost`. Weitere Informationen finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Fügen Sie im Projektmappen-Explorer Verweise auf die folgenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Assemblys.  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   WindowsBase  
  
    -   WindowsFormsIntegration  
  
3.  Kopieren Sie den folgenden Code in den oberen Rand der `Form1` -Codedatei.  
  
     [!code-csharp[PropertyMappingWithElementHost#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]  
  
4.  Öffnen Sie `Form1` im Windows Forms-Designer. Doppelklicken Sie auf das Formular zum Hinzufügen eines ereignishandlers für das <xref:System.Windows.Forms.Form.Load> Ereignis.  
  
5.  Kehren Sie zum Windows Forms-Designer zurück, und fügen Sie einen Ereignishandler für des Formulars <xref:System.Windows.Forms.Control.Resize> Ereignis. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie Ereignis-Handler mithilfe des Designers](http://msdn.microsoft.com/en-us/8461e9b8-14e8-406f-936e-3726732b23d2).  
  
6.  Deklarieren Sie eine <xref:System.Windows.Forms.Integration.ElementHost> -Feld in der `Form1` Klasse.  
  
     [!code-csharp[PropertyMappingWithElementHost#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]  
  
## <a name="defining-new-property-mappings"></a>Definieren neue Eigenschaftenzuordnungen  
 Die <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement stellt mehrere eigenschaftenzuordnungen. Sie fügen Sie eine neue eigenschaftenzuordnung durch Aufrufen der <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> Methode für die <xref:System.Windows.Forms.Integration.ElementHost> des Steuerelements <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.  
  
#### <a name="to-define-new-property-mappings"></a>Um neue eigenschaftenzuordnungen zu definieren.  
  
1.  Kopieren Sie den folgenden Code in die Definition für die `Form1` Klasse.  
  
     [!code-csharp[PropertyMappingWithElementHost#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]  
  
     Die `AddMarginMapping` Methode fügt eine neue Zuordnung für die <xref:System.Windows.Forms.Control.Margin%2A> Eigenschaft.  
  
     Die `OnMarginChange` -Methode der <xref:System.Windows.Forms.Control.Margin%2A> Eigenschaft, um die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft.  
  
2.  Kopieren Sie den folgenden Code in die Definition für die `Form1` Klasse.  
  
     [!code-csharp[PropertyMappingWithElementHost#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]  
  
     Die `AddRegionMapping` Methode fügt eine neue Zuordnung für die <xref:System.Windows.Forms.Control.Region%2A> Eigenschaft.  
  
     Die `OnRegionChange` -Methode der <xref:System.Windows.Forms.Control.Region%2A> Eigenschaft, um die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> Eigenschaft.  
  
     Die `Form1_Resize` Methode behandelt des Formulars <xref:System.Windows.Forms.Control.Resize> Ereignis und die Größe des Clippingbereichs das gehostete Element passt.  
  
## <a name="removing-a-default-property-mapping"></a>Entfernen einer standardmäßigen Eigenschaftenzuordnung  
 Entfernen Sie die Zuordnung einer Standard-Eigenschaft durch Aufrufen der <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> Methode für die <xref:System.Windows.Forms.Integration.ElementHost> des Steuerelements <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.  
  
#### <a name="to-remove-a-default-property-mapping"></a>Entfernen einer standardmäßigen Eigenschaftenzuordnung  
  
-   Kopieren Sie den folgenden Code in die Definition für die `Form1` Klasse.  
  
     [!code-csharp[PropertyMappingWithElementHost#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]  
  
     Die `RemoveCursorMapping` -Methode löscht die standardzuordnung für die <xref:System.Windows.Forms.Control.Cursor%2A> Eigenschaft.  
  
## <a name="extending-a-default-property-mapping"></a>Erweitern einer standardmäßigen Eigenschaftenzuordnung  
 Sie können auch eine standardmäßige Eigenschaftenzuordnung verwenden und sie um Ihre eigenen Zuordnung erweitern.  
  
#### <a name="to-extend-a-default-property-mapping"></a>So erweitern Sie eine standardmäßigen Eigenschaftenzuordnung  
  
-   Kopieren Sie den folgenden Code in die Definition für die `Form1` Klasse.  
  
     [!code-csharp[PropertyMappingWithElementHost#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]  
  
     Die `ExtendBackColorMapping` Methode fügt eine benutzerdefinierte Eigenschaftenübersetzer zur vorhandenen <xref:System.Windows.Forms.Control.BackColor%2A> eigenschaftenzuordnung.  
  
     Die `OnBackColorChange` Methode weist ein bestimmtes Abbild des gehosteten Steuerelements <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft. Die `OnBackColorChange` Methode wird aufgerufen, nachdem die standardzuordnung für die Eigenschaft angewendet wird.  
  
## <a name="initializing-your-property-mappings"></a>Initialisieren der Eigenschaftenzuordnungen  
  
#### <a name="to-initialize-your-property-mappings"></a>So initialisieren Sie Ihre Eigenschaftenzuordnungen  
  
1.  Kopieren Sie den folgenden Code in die Definition für die `Form1` Klasse.  
  
     [!code-csharp[PropertyMappingWithElementHost#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]  
  
     Die `Form1_Load` Methode behandelt das <xref:System.Windows.Forms.Form.Load> Ereignis und führt die folgenden Initialisierung.  
  
    -   Erstellt eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> Element.  
  
    -   Sie ruft die Methoden, die Sie zuvor in der exemplarischen Vorgehensweise definiert haben, auf, um die Eigenschaftenzuordnungen einzurichten.  
  
    -   Sie weist den zugeordneten Eigenschaften Anfangswerte zu.  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Eigenschaftenzuordnung von Windows Forms und WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [WPF-Designer](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
