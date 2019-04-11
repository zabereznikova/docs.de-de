---
title: 'Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem WindowsFormsHost-Element'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
ms.openlocfilehash: edd9d6f698ba27cacb5e9a5eecab43f58d47b8e1
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59296523"
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a>Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem WindowsFormsHost-Element

In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie mit der <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> zuzuordnenden Eigenschaft [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften den entsprechenden Eigenschaften eines gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.

In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:

-   Erstellen des Projekts

-   Definieren des Anwendungslayouts

-   Definieren einer neuen Eigenschaftenzuordnung

-   Entfernen einer standardmäßigen Eigenschaftenzuordnung

-   Ersetzen einer standardmäßigen Eigenschaftenzuordnung

-   Erweitern einer standardmäßigen Eigenschaftenzuordnung

Eine vollständige codeauflistung der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Zuordnen von Eigenschaften mit dem WindowsFormsHost-Element-Beispiel](https://go.microsoft.com/fwlink/?LinkID=160019).

Wenn Sie fertig sind, Sie werden zum Zuordnen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften den entsprechenden Eigenschaften eines gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.

## <a name="prerequisites"></a>Vorraussetzungen

Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:

-   Visual Studio 2017

## <a name="create-and-set-up-the-project"></a>Erstellen und Einrichten des Projekts

1. Erstellen Sie eine **WPF-App** Projekt mit dem Namen `PropertyMappingWithWfhSample`.

2. In **Projektmappen-Explorer**, fügen Sie einen Verweis auf die Assembly "WindowsFormsIntegration", mit dem Namen WindowsFormsIntegration.dll.

3. In **Projektmappen-Explorer**, fügen Sie Verweise auf die Assemblys "System.Drawing" und "System.Windows.Forms" hinzu.

## <a name="defining-the-application-layout"></a>Definieren des Anwendungslayouts

Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]--basierte Anwendung verwendet die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element Host eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.

### <a name="to-define-the-application-layout"></a>So definieren sie das Anwendungslayout

1. Öffnen Sie Window1.xaml in der [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].

2. Ersetzen Sie den vorhandenen Code durch folgenden Code:

     [!code-xaml[PropertyMappingWithWfhSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]

3. Öffnen Sie Window1.xaml.cs im Code-Editor.

4. Importieren Sie am Anfang der Datei die folgenden Namespaces.

     [!code-csharp[PropertyMappingWithWfhSample#20](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]

## <a name="defining-a-new-property-mapping"></a>Definieren einer neuen Eigenschaftenzuordnung

Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element stellt mehrere Standard-eigenschaftenzuordnungen bereit. Hinzufügen eine neuen eigenschaftenzuordnung durch den Aufruf der <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> Methode für die <xref:System.Windows.Forms.Integration.WindowsFormsHost> des Elements <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.

### <a name="to-define-a-new-property-mapping"></a>Definieren einer neuen Eigenschaftenzuordnung

-   Kopieren Sie den folgenden Code in die Definition der `Window1` Klasse.

     [!code-csharp[PropertyMappingWithWfhSample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]

     Die `AddClipMapping` Methode fügt eine neue Zuordnung für die <xref:System.Windows.UIElement.Clip%2A> Eigenschaft.

     Die `OnClipChange` -Methode übersetzt die <xref:System.Windows.UIElement.Clip%2A> Eigenschaft, um die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.Region%2A> Eigenschaft.

     Die `Window1_SizeChanged` Methode verarbeitet das <xref:System.Windows.FrameworkElement.SizeChanged> Ereignis und passt die Größe des Clippingbereichs an das Anwendungsfenster angepasst.

## <a name="removing-a-default-property-mapping"></a>Entfernen einer standardmäßigen Eigenschaftenzuordnung

Entfernen eine standardmäßigen eigenschaftenzuordnung durch Aufrufen der <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> Methode für die <xref:System.Windows.Forms.Integration.WindowsFormsHost> des Elements <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.

### <a name="to-remove-a-default-property-mapping"></a>Entfernen einer standardmäßigen Eigenschaftenzuordnung

-   Kopieren Sie den folgenden Code in die Definition der `Window1` Klasse.

     [!code-csharp[PropertyMappingWithWfhSample#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]

     Die `RemoveCursorMapping` -Methode löscht die standardzuordnung für die <xref:System.Windows.FrameworkElement.Cursor%2A> Eigenschaft.

## <a name="replacing-a-default-property-mapping"></a>Ersetzen einer standardmäßigen Eigenschaftenzuordnung

Ersetzen eine standardmäßigen eigenschaftenzuordnung durch das Entfernen der standardzuordnung und Aufrufen der <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> Methode für die <xref:System.Windows.Forms.Integration.WindowsFormsHost> des Elements <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.

### <a name="to-replace-a-default-property-mapping"></a>So ersetzen Sie eine standardmäßige Eigenschaftenzuordnung

-   Kopieren Sie den folgenden Code in die Definition der `Window1` Klasse.

     [!code-csharp[PropertyMappingWithWfhSample#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]

     Die `ReplaceFlowDirectionMapping` Methode ersetzt die standardzuordnung für die <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft.

     Die `OnFlowDirectionChange` -Methode übersetzt die <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft, um die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.RightToLeft%2A> Eigenschaft.

     Die `cb_CheckedChanged` verarbeitet die <xref:System.Windows.Forms.CheckBox.CheckedChanged> Ereignis auf der <xref:System.Windows.Forms.CheckBox> Steuerelement. Weist die <xref:System.Windows.FrameworkElement.FlowDirection%2A> -Eigenschaft basierend auf den Wert des der <xref:System.Windows.Forms.CheckBox.CheckState%2A> Eigenschaft

## <a name="extending-a-default-property-mapping"></a>Erweitern einer standardmäßigen Eigenschaftenzuordnung

Sie können auch eine standardmäßige Eigenschaftenzuordnung verwenden und sie um Ihre eigenen Zuordnung erweitern.

### <a name="to-extend-a-default-property-mapping"></a>So erweitern Sie eine standardmäßigen Eigenschaftenzuordnung

-   Kopieren Sie den folgenden Code in die Definition der `Window1` Klasse.

     [!code-csharp[PropertyMappingWithWfhSample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]

     Die `ExtendBackgroundMapping` Methode fügt einen benutzerdefinierten Eigenschaftenübersetzer zur vorhandenen <xref:System.Windows.Controls.Control.Background%2A> eigenschaftenzuordnung.

     Die `OnBackgroundChange` Methode weist ein bestimmtes Bild des gehosteten Steuerelements <xref:System.Windows.Forms.Control.BackgroundImage%2A> Eigenschaft. Die `OnBackgroundChange` Methode wird aufgerufen, nachdem die standardzuordnung angewendet wurde.

## <a name="initializing-your-property-mappings"></a>Initialisieren der Eigenschaftenzuordnungen

Richten Ihre eigenschaftenzuordnungen durch Aufrufen der oben beschriebenen Methoden in der <xref:System.Windows.FrameworkElement.Loaded> -Ereignishandler.

### <a name="to-initialize-your-property-mappings"></a>So initialisieren Sie Ihre Eigenschaftenzuordnungen

1. Kopieren Sie den folgenden Code in die Definition der `Window1` Klasse.

     [!code-csharp[PropertyMappingWithWfhSample#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]

     Die `WindowLoaded` verarbeitet die <xref:System.Windows.FrameworkElement.Loaded> Ereignis und führt die folgende Initialisierung.

    -   Erstellt eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.CheckBox> Steuerelement.

    -   Sie ruft die Methoden, die Sie zuvor in der exemplarischen Vorgehensweise definiert haben, auf, um die Eigenschaftenzuordnungen einzurichten.

    -   Sie weist den zugeordneten Eigenschaften Anfangswerte zu.

2. Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen. Klicken Sie auf das Kontrollkästchen, um die Wirkung sehen die <xref:System.Windows.FrameworkElement.FlowDirection%2A> Zuordnung. Wenn Sie das Kontrollkästchen klicken, kehrt das Layout seine Links-Rechts-Ausrichtung um.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Eigenschaftenzuordnung von Windows Forms und WPF](windows-forms-and-wpf-property-mapping.md)
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)