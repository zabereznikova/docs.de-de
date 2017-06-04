---
title: "Exemplarische Vorgehensweise: Formatieren von WPF-Inhalt | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Interoperabilität [WDF]"
  - "Stile, WPF-Inhalt"
  - "WPF-Designer, Formatieren von WPF-Inhalt"
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Exemplarische Vorgehensweise: Formatieren von WPF-Inhalt
In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie eine Formatvorlage auf ein WPF\-Steuerelement \(Windows Presentation Foundation\) angewendet wird, das in einem Windows Form\-Objekt gehostet wird.  
  
 Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:  
  
-   Erstellen eines Projekts  
  
-   Erstellen des WPF\-Steuerelementtyps  
  
-   Zuweisen einer Formatvorlage zum WPF\-Steuerelement  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren**, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Vorbereitungsmaßnahmen  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)].  
  
## Erstellen des Projekts  
 Zunächst muss das Windows Forms\-Projekt erstellt werden.  
  
> [!NOTE]
>  Beim Hosten von WPF\-Inhalt werden nur C\#\- und Visual Basic\-Projekte unterstützt.  
  
#### So erstellen Sie das Projekt  
  
-   Erstellen Sie in Visual Basic oder Visual C\# ein neues Windows Forms\-Anwendungsprojekt namens `StylingWpfContent`.  
  
## Erstellen der WPF\-Steuerelementtypen  
 Nachdem Sie dem Projekt ein WPF\-Steuerelement hinzugefügt haben, können Sie dieses in einem <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement hosten.  
  
#### So erstellen Sie WPF\-Steuerelementtypen  
  
1.  Fügen Sie der Projektmappe ein neues WPF\-<xref:System.Windows.Controls.UserControl>\-Projekt hinzu.  Verwenden Sie den Standardnamen \(`UserControl1.xaml`\) für den Steuerelementtyp.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen neuen WPF\-Inhalts in Windows Forms zur Entwurfszeit](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist.  Weitere Informationen finden Sie unter [Gewusst wie: Auswählen und Verschieben von Elementen auf der Entwurfsoberfläche](http://msdn.microsoft.com/de-de/54cb70b6-b35b-46e4-a0cc-65189399c474).  
  
3.  Legen Sie im Fenster **Eigenschaften** den Wert der Eigenschaften <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> auf `200` fest.  
  
4.  Fügen Sie <xref:System.Windows.Controls.UserControl> ein <xref:System.Windows.Controls.Button?displayProperty=fullName>\-Steuerelement hinzu, und legen Sie den Wert der Eigenschaft <xref:System.Windows.Controls.ContentControl.Content%2A> auf "Cancel" fest.  
  
5.  Fügen Sie <xref:System.Windows.Controls.UserControl> ein zweites <xref:System.Windows.Controls.Button?displayProperty=fullName>\-Steuerelement hinzu, und legen Sie den Wert der Eigenschaft <xref:System.Windows.Controls.ContentControl.Content%2A> auf "OK" fest.  
  
6.  Erstellen Sie das Projekt.  
  
## Anwenden einer Formatvorlage auf ein WPF\-Steuerelement  
 Sie können verschiedene Formatvorlagen auf ein WPF\-Steuerelement anwenden, um seine Darstellung und das Verhalten zu ändern.  
  
#### So wenden Sie eine Formatvorlage auf ein WPF\-Steuerelement an  
  
1.  Öffnen Sie `Form1` im Windows Forms\-Designer.  
  
2.  Doppelklicken Sie in der **Toolbox** auf `UserControl1`, um eine Instanz von `UserControl1` im Formular zu erstellen.  
  
     Eine Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement namens `elementHost1` gehostet.  
  
3.  Klicken Sie im Smarttagbereich für `elementHost1` in der Dropdownliste auf **Gehosteten Inhalt bearbeiten**.  
  
     `UserControl1` wird im [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] geöffnet.  
  
4.  Fügen Sie den folgenden XAML\-Code in der XAML\-Ansicht hinter dem `<UserControl>`\-Starttag ein.  
  
     Dieser XAML\-Code erstellt einen Farbverlauf mit kontrastreichem Farbverlaufsrand.  Wenn das Steuerelement angeklickt wird, werden die Farbverläufe geändert, um den Eindruck einer gedrückten Schaltfläche zu generieren.  Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
```xaml  
<UserControl.Resources>  
    <LinearGradientBrush x:Key="NormalBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#FFF" Offset="0.0"/>  
        <GradientStop Color="#CCC" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="PressedBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#BBB" Offset="0.0"/>  
        <GradientStop Color="#EEE" Offset="0.1"/>  
        <GradientStop Color="#EEE" Offset="0.9"/>  
        <GradientStop Color="#FFF" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="NormalBorderBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#CCC" Offset="0.0"/>  
        <GradientStop Color="#444" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="BorderBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#CCC" Offset="0.0"/>  
        <GradientStop Color="#444" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="PressedBorderBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#444" Offset="0.0"/>  
        <GradientStop Color="#888" Offset="1.0"/>  
    </LinearGradientBrush>  
  
    <Style x:Key="SimpleButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">  
        <Setter Property="Background" Value="{StaticResource NormalBrush}"/>  
        <Setter Property="BorderBrush" Value="{StaticResource NormalBorderBrush}"/>  
        <Setter Property="Template">  
            <Setter.Value>  
                <ControlTemplate TargetType="{x:Type Button}">  
                    <Grid x:Name="Grid">  
                        <Border x:Name="Border" Background="{TemplateBinding Background}" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Padding="{TemplateBinding Padding}"/>  
                        <ContentPresenter HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" RecognizesAccessKey="True"/>  
                    </Grid>  
                    <ControlTemplate.Triggers>  
                        <Trigger Property="IsPressed" Value="true">  
                            <Setter Property="Background" Value="{StaticResource PressedBrush}" TargetName="Border"/>  
                            <Setter Property="BorderBrush" Value="{StaticResource PressedBorderBrush}" TargetName="Border"/>  
                        </Trigger>  
                    </ControlTemplate.Triggers>  
                </ControlTemplate>  
            </Setter.Value>  
        </Setter>  
    </Style>  
</UserControl.Resources>  
```  
  
1.  Wenden Sie die im vorherigen Schritt definierte `SimpleButton`\-Formatvorlage auf die "Cancel"\-Schaltfläche an, indem Sie den folgenden XAML\-Code im `<Button>`\-Tag der "Cancel"\-Schaltfläche einfügen.  
  
    ```  
    Style="{StaticResource SimpleButton}  
    ```  
  
     Ihre Schaltflächendeklaration wird dem folgenden XAML\-Code ähneln.  
  
```xaml  
<Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"  
                Style="{StaticResource SimpleButton}">Cancel</Button>  
```  
  
1.  Erstellen Sie das Projekt.  
  
2.  Öffnen Sie `Form1` im Windows Forms\-Designer.  
  
3.  Die neue Formatvorlage wird auf das Schaltflächensteuerelement angewendet.  
  
4.  Wählen Sie im Menü **Debuggen** die Option **Debugging starten** aus, um die Anwendung auszuführen.  
  
5.  Klicken Sie auf die Schaltflächen "OK" und "Cancel", und beobachten Sie die Unterschiede.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Migration und Interoperabilität](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)   
 [Verwenden von WPF\-Steuerelementen](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)   
 [WPF\-Designer](http://msdn.microsoft.com/de-de/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)