---
title: 'Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem ElementHost-Steuerelement'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
ms.openlocfilehash: 29356f171506ece0fe35418f682681b19830d71c
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2019
ms.locfileid: "56746337"
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a>Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem ElementHost-Steuerelement

In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie mit der <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> zuzuordnenden Eigenschaft [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Eigenschaften den entsprechenden Eigenschaften eines gehosteten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Element.

In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:

-   Erstellen des Projekts.

-   Definieren einer neuen Eigenschaftenzuordnung

-   Entfernen einer standardmäßigen Eigenschaftenzuordnung

-   Erweitern einer standardmäßigen Eigenschaftenzuordnung

Eine vollständige codeauflistung der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Zuordnen von Eigenschaften mit dem ElementHost-Steuerelement-Beispiel](https://go.microsoft.com/fwlink/?LinkID=160018).

Wenn Sie fertig sind, Sie werden zum Zuordnen [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Eigenschaften entsprechenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften eines gehosteten Elements.

## <a name="prerequisites"></a>Vorraussetzungen

Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:

-   Visual Studio 2017

## <a name="creating-the-project"></a>Erstellen des Projekts

### <a name="to-create-the-project"></a>So erstellen Sie das Projekt

1.  Erstellen Sie eine **Windows Forms-App** Projekt mit dem Namen `PropertyMappingWithElementHost`.

2.  In **Projektmappen-Explorer**, fügen Sie Verweise auf die folgenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Assemblys.

    -   PresentationCore

    -   PresentationFramework

    -   WindowsBase

    -   WindowsFormsIntegration

3.  Kopieren Sie den folgenden Code oben in der `Form1` Codedatei.

     [!code-csharp[PropertyMappingWithElementHost#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]

4.  Öffnen Sie `Form1` im Windows Forms-Designer. Doppelklicken Sie auf das Formular, um das Hinzufügen eines ereignishandlers für das <xref:System.Windows.Forms.Form.Load> Ereignis.

5.  Zurück zu den Windows Forms-Designer, und fügen Sie einen Ereignishandler für des Formulars des <xref:System.Windows.Forms.Control.Resize> Ereignis. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Ereignishandlern mithilfe des Designers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).

6.  Deklarieren Sie eine <xref:System.Windows.Forms.Integration.ElementHost> -Feld in der `Form1` Klasse.

     [!code-csharp[PropertyMappingWithElementHost#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]

## <a name="defining-new-property-mappings"></a>Definieren neue Eigenschaftenzuordnungen

Die <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement bietet mehrere Standard-eigenschaftenzuordnungen. Hinzufügen eine neuen eigenschaftenzuordnung durch den Aufruf der <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> Methode für die <xref:System.Windows.Forms.Integration.ElementHost> des Steuerelements <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.

### <a name="to-define-new-property-mappings"></a>Definieren Sie neue eigenschaftenzuordnungen

1.  Kopieren Sie den folgenden Code in die Definition der `Form1` Klasse.

     [!code-csharp[PropertyMappingWithElementHost#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]

     Die `AddMarginMapping` Methode fügt eine neue Zuordnung für die <xref:System.Windows.Forms.Control.Margin%2A> Eigenschaft.

     Die `OnMarginChange` -Methode übersetzt die <xref:System.Windows.Forms.Control.Margin%2A> Eigenschaft, um die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft.

2.  Kopieren Sie den folgenden Code in die Definition der `Form1` Klasse.

     [!code-csharp[PropertyMappingWithElementHost#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]

     Die `AddRegionMapping` Methode fügt eine neue Zuordnung für die <xref:System.Windows.Forms.Control.Region%2A> Eigenschaft.

     Die `OnRegionChange` -Methode übersetzt die <xref:System.Windows.Forms.Control.Region%2A> Eigenschaft, um die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> Eigenschaft.

     Die `Form1_Resize` Methode verarbeitet des Formulars <xref:System.Windows.Forms.Control.Resize> Ereignis und passt die Größe des Clippingbereichs an das gehostete Element passt.

## <a name="removing-a-default-property-mapping"></a>Entfernen einer standardmäßigen Eigenschaftenzuordnung

Entfernen eine standardmäßigen eigenschaftenzuordnung durch Aufrufen der <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> Methode für die <xref:System.Windows.Forms.Integration.ElementHost> des Steuerelements <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.

### <a name="to-remove-a-default-property-mapping"></a>Entfernen einer standardmäßigen Eigenschaftenzuordnung

-   Kopieren Sie den folgenden Code in die Definition der `Form1` Klasse.

     [!code-csharp[PropertyMappingWithElementHost#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]

     Die `RemoveCursorMapping` -Methode löscht die standardzuordnung für die <xref:System.Windows.Forms.Control.Cursor%2A> Eigenschaft.

## <a name="extending-a-default-property-mapping"></a>Erweitern einer standardmäßigen Eigenschaftenzuordnung

Sie können auch eine standardmäßige Eigenschaftenzuordnung verwenden und sie um Ihre eigenen Zuordnung erweitern.

### <a name="to-extend-a-default-property-mapping"></a>So erweitern Sie eine standardmäßigen Eigenschaftenzuordnung

-   Kopieren Sie den folgenden Code in die Definition der `Form1` Klasse.

     [!code-csharp[PropertyMappingWithElementHost#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]

     Die `ExtendBackColorMapping` Methode fügt einen benutzerdefinierten Eigenschaftenübersetzer zur vorhandenen <xref:System.Windows.Forms.Control.BackColor%2A> eigenschaftenzuordnung.

     Die `OnBackColorChange` Methode weist ein bestimmtes Bild des gehosteten Steuerelements <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft. Die `OnBackColorChange` Methode wird aufgerufen, nachdem die standardzuordnung angewendet wurde.

## <a name="initialize-your-property-mappings"></a>Initialisieren Sie Ihre eigenschaftenzuordnungen

1.  Kopieren Sie den folgenden Code in die Definition der `Form1` Klasse.

     [!code-csharp[PropertyMappingWithElementHost#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]

     Die `Form1_Load` verarbeitet die <xref:System.Windows.Forms.Form.Load> Ereignis und führt die folgende Initialisierung.

    -   Erstellt eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> Element.

    -   Sie ruft die Methoden, die Sie zuvor in der exemplarischen Vorgehensweise definiert haben, auf, um die Eigenschaftenzuordnungen einzurichten.

    -   Sie weist den zugeordneten Eigenschaften Anfangswerte zu.

2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Eigenschaftenzuordnung von Windows Forms und WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)