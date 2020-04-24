---
title: 'Exemplarische Vorgehensweise: Formatieren von WPF-Inhalten'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 07241d41e3fbf270a76bd241765bfa369ee265d5
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646327"
---
# <a name="walkthrough-style-wpf-content"></a>Exemplarische Vorgehensweise: Formatieren von WPF-Inhalten

In diesem Artikel erfahren Sie, wie Sie das Styling auf ein Windows Presentation Foundation (WPF)-Steuerelement anwenden, das in einem Windows-Formular gehostet wird.

## <a name="prerequisites"></a>Voraussetzungen

Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.

## <a name="create-the-project"></a>Erstellen des Projekts

Öffnen Sie Visual Studio, und erstellen Sie ein neues `StylingWpfContent`Windows Forms Application-Projekt in Visual Basic oder Visual C. mit dem Namen .

> [!NOTE]
> Beim Hosten von WPF-Inhalt werden nur C#- und Visual Basic-Projekte unterstützt.

## <a name="create-the-wpf-control-types"></a>Erstellen der WPF-Steuerelementtypen

Nachdem Sie dem Projekt ein WPF-Steuerelement hinzugefügt haben, können Sie dieses in einem <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement hosten.

1. Fügen Sie der Projektmappe ein neues WPF-<xref:System.Windows.Controls.UserControl>-Projekt hinzu. Verwenden Sie den Standardnamen, `UserControl1.xaml`, für den Steuerelementtyp. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen neuer WPF-Inhalte in Windows Forms zur Entwurfszeit](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).

2. Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist.

3. Legen Sie im **Fenster Eigenschaften** <xref:System.Windows.FrameworkElement.Width%2A> den <xref:System.Windows.FrameworkElement.Height%2A> Wert der und-Eigenschaften auf **200**fest.

4. Fügen <xref:System.Windows.Controls.Button?displayProperty=nameWithType> Sie dem <xref:System.Windows.Controls.UserControl> ein Steuerelement hinzu, und legen Sie den Wert der <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft auf **Abbrechen**fest.

5. Fügen Sie <xref:System.Windows.Controls.Button?displayProperty=nameWithType> ein <xref:System.Windows.Controls.UserControl> zweites Steuerelement zum <xref:System.Windows.Controls.ContentControl.Content%2A> hinzu, und legen Sie den Wert der Eigenschaft auf **OK**fest.

6. Erstellen Sie das Projekt.

## <a name="apply-a-style-to-a-wpf-control"></a>Anwenden eines Stils auf ein WPF-Steuerelement

Sie können verschiedene Formatvorlagen auf ein WPF-Steuerelement anwenden, um seine Darstellung und das Verhalten zu ändern.

1. Öffnen Sie `Form1` im Windows Forms-Designer.

1. Doppelklicken Sie `UserControl1` in der **Toolbox,** `UserControl1` um eine Instanz im Formular zu erstellen.

   Eine Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost1` gehostet.

1. Klicken Sie im `elementHost1`Smarttag-Bedienfeld für in der Dropdown-Liste auf **Gehostete Inhalte bearbeiten.**

   `UserControl1`wird im WPF-Designer geöffnet.

1. Fügen Sie den folgenden XAML-Code in der XAML-Ansicht hinter dem `<UserControl>`-Starttag ein. Dieser XAML-Code erstellt einen Farbverlauf mit kontrastreichem Farbverlaufsrand. Wenn das Steuerelement angeklickt wird, werden die Farbverläufe geändert, um den Eindruck einer gedrückten Schaltfläche zu generieren. Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md).

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

1. Wenden `SimpleButton` Sie den im vorherigen Schritt definierten Stil auf die Schaltfläche `<Button>` Abbrechen an, indem Sie das folgende XAML in das Tag der Schaltfläche **Abbrechen** einfügen.

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   Ihre Schaltflächendeklaration ähnelt der folgenden XAML:

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

1. Erstellen Sie das Projekt.

1. Öffnen Sie `Form1` im Windows Forms-Designer.

1. Die neue Formatvorlage wird auf das Schaltflächensteuerelement angewendet.

1. Wählen Sie im **Menü Debuggen** die Option **Debuggen starten** aus, um die Anwendung auszuführen.

1. Klicken Sie auf die Schaltflächen **OK** und **Abbrechen,** und zeigen Sie die Unterschiede an.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migration und Interoperabilität](../../wpf/advanced/migration-and-interoperability.md)
- [Verwenden von WPF-Steuerelementen](using-wpf-controls.md)
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
