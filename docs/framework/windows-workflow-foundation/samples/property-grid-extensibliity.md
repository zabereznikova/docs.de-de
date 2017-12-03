---
title: Erweiterbarkeit von Eigenschaftenrastern
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3530c3a3-756d-4712-9f10-fb2897414d3a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6e27a16519acf567903579fafe90da3cd0a8bbf3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="property-grid-extensibliity"></a>Erweiterbarkeit von Eigenschaftenrastern
Entwickler können das Eigenschaftenraster anpassen, das bei Auswahl einer Aktivität im Designer angezeigt wird. Auf diese Weise lassen sich die Bearbeitungsmöglichkeiten optimieren. Dieses Beispiel veranschaulicht die Vorgehensweise.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 Erweiterbarkeit des Eigenschaftenrasters im Workflow-Designer.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`  
  
## <a name="discussion"></a>Diskussion  
 Zur Erweiterung des Eigenschaftenrasters stehen Entwicklern Optionen zur Verfügung, mit denen sie die Darstellung des Eigenschaftenraster-Editors anpassen oder ein Dialogfeld bereitstellen können, das für eine erweiterte Entwurfsoberfläche angezeigt wird. In diesem Beispiel werden zwei verschiedene Editoren veranschaulicht, ein Inline-Editor und ein Dialog-Editor.  
  
## <a name="inline-editor"></a>Inline-Editor  
 Das Beispiel zum Inline-Editor veranschaulicht Folgendes:  
  
-   Ein von <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor> abgeleiteter Typ wird erstellt.  
  
-   Im Konstruktor wird der <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A>-Wert mit einer [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)]-Datenvorlage festgelegt. Diese kann an eine XAML-Vorlage gebunden werden, in diesem Beispiel wird jedoch Code zur Initialisierung der Datenbindung verwendet.  
  
-   Die Datenvorlage weist einen Datenkontext für den <xref:System.Activities.Presentation.PropertyEditing.PropertyValue>-Wert des im Eigenschaftenraster gerenderten Elements auf. Beachten Sie beim folgenden Code (aus der Datei "CustomInlineEditor.cs"), dass dieser Kontext dann an die `Value`-Eigenschaft gebunden wird.  
  
    ```csharp  
    FrameworkElementFactory stack = new FrameworkElementFactory(typeof(StackPanel));  
    FrameworkElementFactory slider = new FrameworkElementFactory(typeof(Slider));  
    Binding sliderBinding = new Binding("Value");  
    sliderBinding.Mode = BindingMode.TwoWay;  
    slider.SetValue(Slider.MinimumProperty, 0.0);  
    slider.SetValue(Slider.MaximumProperty, 100.0);  
    slider.SetValue(Slider.ValueProperty, sliderBinding);  
    stack.AppendChild(slider);  
    ```  
  
-   Da die Aktivität und der Designer sich in derselben Assembly befinden, erfolgt die Registrierung der Aktivitätsdesignerattribute im statischen Konstruktor der Aktivität, wie im folgenden Beispiel aus der Datei "SimpleCodeActivity.cs" gezeigt.  
  
    ```  
    static SimpleCodeActivity()  
    {  
        AttributeTableBuilder builder = new AttributeTableBuilder();  
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));  
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));  
        MetadataStore.AddAttributeTable(builder.CreateTable());  
    }  
    ```  
  
## <a name="dialog-editor"></a>Dialog-Editor  
 Das Beispiel zum Dialog-Editor veranschaulicht Folgendes:  
  
1.  Ein von <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor> abgeleiteter Typ wird erstellt.  
  
2.  Der <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A>-Wert im Konstruktor wird mit einer [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]-Datenvorlage festgelegt. Diese kann in XAML erstellt werden, in diesem Beispiel wird jedoch Code verwendet.  
  
3.  Die Datenvorlage weist einen Datenkontext für den <xref:System.Activities.Presentation.PropertyEditing.PropertyValue>-Wert des im Eigenschaftenraster gerenderten Elements auf. Im folgenden Code wird dieser dann an die `Value`-Eigenschaft gebunden. Es muss auch ein <xref:System.Activities.Presentation.PropertyEditing.EditModeSwitchButton>-Element eingebunden werden, um die Schaltfläche bereitzustellen, mit der das Dialogfeld in "FilePickerEditor.cs" ausgelöst wird.  
  
    ```  
    this.InlineEditorTemplate = new DataTemplate();  
  
    FrameworkElementFactory stack = new FrameworkElementFactory(typeof(StackPanel));  
    stack.SetValue(StackPanel.OrientationProperty, Orientation.Horizontal);  
    FrameworkElementFactory label = new FrameworkElementFactory(typeof(Label));  
    Binding labelBinding = new Binding("Value");  
    label.SetValue(Label.ContentProperty, labelBinding);  
    label.SetValue(Label.MaxWidthProperty, 90.0);  
  
    stack.AppendChild(label);  
  
    FrameworkElementFactory editModeSwitch = new FrameworkElementFactory(typeof(EditModeSwitchButton));  
  
    editModeSwitch.SetValue(EditModeSwitchButton.TargetEditModeProperty, PropertyContainerEditMode.Dialog);  
  
    stack.AppendChild(editModeSwitch);  
  
    this.InlineEditorTemplate.VisualTree = stack;  
    ```  
  
4.  Überschreibt die <!--zz <xref:Microsoft.Windows.Design.PropertyEditing.ShowDialog%2A>--> `Microsoft.Windows.Design.PropertyEditing.ShowDialog` -Methode im Designertyp zur Behandlung die Anzeige des Dialogfelds zu behandeln. In diesem Beispiel wird ein einfaches <xref:System.Windows.Forms.FileDialog> gezeigt.  
  
    ```  
    public override void ShowDialog(PropertyValue propertyValue, IInputElement commandSource)  
    {  
        Microsoft.Win32.OpenFileDialog ofd = new Microsoft.Win32.OpenFileDialog();  
        if (ofd.ShowDialog() == true)  
        {  
            propertyValue.Value = ofd.FileName;  
        }  
    }  
    ```  
  
5.  Da die Aktivität und der Designer sich in derselben Assembly befinden, erfolgt die Registrierung der Aktivitätsdesignerattribute im statischen Konstruktor der Aktivität, wie im folgenden Beispiel aus der Datei "SimpleCodeActivity.cs" gezeigt.  
  
    ```  
    static SimpleCodeActivity()  
    {  
        AttributeTableBuilder builder = new AttributeTableBuilder();  
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));  
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));  
        MetadataStore.AddAttributeTable(builder.CreateTable());  
    }  
    ```  
  
## <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Erstellen Sie die Projektmappe, und öffnen Sie dann "Workflow1.xaml".  
  
2.  Ziehen Sie eine **SimpleCodeActivity** aus der Toolbox auf den designerzeichnungsbereich.  
  
3.  Klicken Sie auf die **SimpleCodeActivity** und öffnen Sie dann das Eigenschaftenraster, das ein Schieberegler-Steuerelement und ein Dateiauswahl-Steuerelement.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`
