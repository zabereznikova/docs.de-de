---
title: 'Exemplarische Vorgehensweise: Erstellen einer Schaltfläche mit XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: a8cc227703e81e5de9dea7e44e10dfecca2cd05c
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646470"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a>Exemplarische Vorgehensweise: Erstellen einer Schaltfläche mit XAML

Das Ziel dieser exemplarischen Vorgehensweise besteht darin, zu erfahren, wie Sie eine animierte Schaltfläche für die Verwendung in einer Windows Presentation Foundation (WPF)-Anwendung erstellen. In dieser exemplarischen Vorgehensweise werden Stile und eine Vorlage verwendet, um eine benutzerdefinierte Schaltflächenressource zu erstellen, die die Wiederverwendung von Code und die Trennung der Schaltflächenlogik von der Schaltflächendeklaration ermöglicht. Diese exemplarische Vorgehensweise [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ist vollständig in geschrieben.

> [!IMPORTANT]
> In dieser exemplarischen Vorgehensweise führen Sie durch die Schritte zum [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Erstellen der Anwendung durch Eingabe oder Kopieren und Einfügen in Visual Studio. Wenn Sie möchten, wie Sie einen Designer zum Erstellen derselben Anwendung verwenden möchten, finden Sie weitere Informationen unter [Erstellen einer Schaltfläche mithilfe von Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).

Die folgende Abbildung zeigt die fertigen Schaltflächen.

![Benutzerdefinierte Schaltflächen, die mit XAML erstellt wurden](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")

## <a name="create-basic-buttons"></a>Erstellen von Basisschaltflächen

Beginnen wir mit dem Erstellen eines neuen Projekts und dem Hinzufügen einiger Schaltflächen zum Fenster.

### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a>So erstellen Sie ein neues WPF-Projekt und fügen dem Fenster Schaltflächen hinzu

1. Starten Sie Visual Studio.

2. **Erstellen Sie ein neues WPF-Projekt:** Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**. Suchen Sie die **Windows-Anwendungsvorlage (WPF),** und benennen Sie das Projekt "AnimatedButton". Dadurch wird das Skelett für die Anwendung erstellt.

3. **Hinzufügen grundlegender Standardschaltflächen:** Alle Dateien, die Sie für diese exemplarische Vorgehensweise benötigen, werden von der Vorlage bereitgestellt. Öffnen Sie die Datei Window1.xaml, indem Sie im Projektmappen-Explorer darauf doppelklicken. Standardmäßig gibt es <xref:System.Windows.Controls.Grid> ein Element in Window1.xaml. Entfernen <xref:System.Windows.Controls.Grid> Sie das Element, und [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] fügen Sie der Seite einige Schaltflächen hinzu, indem Sie den folgenden hervorgehobenen Code in Window1.xaml eingeben oder kopieren und einfügen:

    ```xaml
    <Window x:Class="AnimatedButton.Window1"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      Title="AnimatedButton" Height="300" Width="300"
      Background="Black">
      <!-- Buttons arranged vertically inside a StackPanel. -->
      <StackPanel HorizontalAlignment="Left">
          <Button>Button 1</Button>
          <Button>Button 2</Button>
          <Button>Button 3</Button>
      </StackPanel>
    </Window>
    ```

     Drücken Sie F5, um die Anwendung auszuführen; Sie sollten eine Reihe von Schaltflächen sehen, die wie die folgende Abbildung aussieht.

     ![Drei grundlegende Schaltflächen](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")

     Nachdem Sie die grundlegenden Schaltflächen erstellt haben, sind Sie mit der Arbeit in der Datei Window1.xaml fertig. Der Rest der exemplarischen Vorgehensweise konzentriert sich auf die Datei app.xaml, die Stile und eine Vorlage für die Schaltflächen definiert.

## <a name="set-basic-properties"></a>Festlegen grundlegender Eigenschaften

Als Nächstes legen wir einige Eigenschaften auf diesen Schaltflächen fest, um die Schaltflächendarstellung und das Layout zu steuern. Anstatt Eigenschaften für die Schaltflächen einzeln festzulegen, verwenden Sie Ressourcen, um Schaltflächeneigenschaften für die gesamte Anwendung zu definieren. Anwendungsressourcen ähneln konzeptionell externen Cascading Style Sheets (CSS) für Webseiten. Ressourcen sind jedoch viel leistungsfähiger als Cascading Style Sheets (CSS), wie Sie am Ende dieser exemplarischen Vorgehensweise sehen werden. Weitere Informationen zu Ressourcen finden Sie unter [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a>So verwenden Sie Stile, um grundlegende Eigenschaften für die Schaltflächen festzulegen

1. **Definieren eines Application.Resources-Blocks:** Öffnen Sie app.xaml und fügen Sie das folgende hervorgehobene Markup hinzu, wenn es noch nicht vorhanden ist:

    ```xaml
    <Application x:Class="AnimatedButton.App"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      StartupUri="Window1.xaml"
      >
      <Application.Resources>
        <!-- Resources for the entire application can be defined here. -->
      </Application.Resources>
    </Application>
    ```

     Der Ressourcenbereich wird dadurch bestimmt, wo Sie die Ressource definieren. Durch das `Application.Resources` Definieren von Ressourcen in der Datei app.xaml kann die Ressource von überall in der Anwendung verwendet werden. Weitere Informationen zum Definieren des Ressourcenbereichs finden Sie unter [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

2. **Erstellen Sie einen Stil, und definieren Sie damit grundlegende Eigenschaftswerte:** Fügen Sie dem `Application.Resources` Block das folgende Markup hinzu. Dieses Markup <xref:System.Windows.Style> erstellt eine, die für alle <xref:System.Windows.FrameworkElement.Width%2A> Schaltflächen in der Anwendung <xref:System.Windows.FrameworkElement.Margin%2A> gilt, und legt die Schaltflächen auf 90 und die auf 10 fest:

    ```xaml
    <Application.Resources>
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     Die <xref:System.Windows.Style.TargetType%2A> Eigenschaft gibt an, dass der <xref:System.Windows.Controls.Button>Stil für alle Objekte vom Typ gilt. Jeder <xref:System.Windows.Setter> legt einen anderen <xref:System.Windows.Style>Eigenschaftswert für die fest. Daher hat an dieser Stelle jede Taste in der Anwendung eine Breite von 90 und einen Rand von 10.  Wenn Sie F5 drücken, um die Anwendung auszuführen, wird das folgende Fenster angezeigt.

     ![Schaltflächen mit einer Breite von 90 und einem Rand von 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")

     Es gibt viel mehr, was Sie mit Stilen tun können, einschließlich einer Vielzahl von Möglichkeiten, um die Ziele von Objekten zu optimieren, komplexe Eigenschaftswerte anzugeben und sogar Stile als Eingabe für andere Stile zu verwenden. Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md).

3. **Legen Sie einen Stileigenschaftswert für eine Ressource fest:** Ressourcen ermöglichen eine einfache Möglichkeit, häufig definierte Objekte und Werte wiederzuverwenden. Es ist besonders nützlich, komplexe Werte mithilfe von Ressourcen zu definieren, um den Code modularer zu gestalten. Fügen Sie das folgende hervorgehobene Markup zu app.xaml hinzu.

    ```xaml
    <Application.Resources>
      <LinearGradientBrush x:Key="GrayBlueGradientBrush" StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>
      <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />
        <Setter Property="Width" Value="80" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     Direkt unter `Application.Resources` dem Block haben Sie eine Ressource mit dem Namen "GrayBlueGradientBrush" erstellt. Diese Ressource definiert einen horizontalen Farbverlauf. Diese Ressource kann als Eigenschaftswert von überall in der Anwendung verwendet <xref:System.Windows.Controls.Control.Background%2A> werden, einschließlich innerhalb des Schaltflächenstil-Setters für die Eigenschaft. Jetzt haben alle Schaltflächen einen <xref:System.Windows.Controls.Control.Background%2A> Eigenschaftswert dieses Farbverlaufs.

     Drücken Sie die Taste F5, um die Anwendung auszuführen. Es sollte wie folgt aussehen.

     ![Schaltflächen mit einem Farbverlaufshintergrund](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")

## <a name="create-a-template-that-defines-the-look-of-the-button"></a>Erstellen einer Vorlage, die das Aussehen der Schaltfläche definiert

In diesem Abschnitt erstellen Sie eine Vorlage, die die Darstellung (Präsentation) der Schaltfläche anpasst. Die Schaltflächenpräsentation besteht aus mehreren Objekten, einschließlich Rechtecken und anderen Komponenten, um der Schaltfläche ein einzigartiges Aussehen zu verleihen.

Bisher beschränkte sich die Steuerung, wie Schaltflächen in der Anwendung aussehen, auf die Änderung der Eigenschaften der Schaltfläche. Was ist, wenn Sie radikalere Änderungen am Erscheinungsbild der Schaltfläche vornehmen möchten? Vorlagen ermöglichen eine leistungsstarke Steuerung der Darstellung eines Objekts. Da Vorlagen innerhalb von Stilen verwendet werden können, können Sie eine Vorlage auf alle Objekte anwenden, auf die der Stil angewendet wird (in dieser exemplarischen Vorgehensweise die Schaltfläche).

### <a name="to-use-the-template-to-define-the-look-of-the-button"></a>So verwenden Sie die Vorlage, um das Aussehen der Schaltfläche zu definieren

1. **Richten Sie die Vorlage ein:** Da <xref:System.Windows.Controls.Button> Steuerelemente <xref:System.Windows.Controls.Control.Template%2A> wie eine Eigenschaft vorhanden sind, können Sie den Wert der <xref:System.Windows.Style> Vorlageneigenschaft genau wie die anderen Eigenschaftswerte definieren, die wir in a mit einer <xref:System.Windows.Setter>festgelegt haben. Fügen Sie das folgende hervorgehobene Markup zu Ihrem Schaltflächenstil hinzu.

    ```xaml
    <Application.Resources>
      <LinearGradientBrush x:Key="GrayBlueGradientBrush"
        StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>
      <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />
        <Setter Property="Width" Value="80" />
        <Setter Property="Margin" Value="10" />
        <Setter Property="Template">
          <Setter.Value>
            <!-- The button template is defined here. -->
          </Setter.Value>
        </Setter>
      </Style>
    </Application.Resources>
    ```

2. **Änderungsschaltflächenpräsentation:** An diesem Punkt müssen Sie die Vorlage definieren. Fügen Sie das folgende hervorgehobene Markup hinzu. Dieses Markup gibt <xref:System.Windows.Shapes.Rectangle> zwei Elemente mit abgerundeten Kanten an, gefolgt von einer <xref:System.Windows.Controls.DockPanel>. Der <xref:System.Windows.Controls.DockPanel> wird verwendet, <xref:System.Windows.Controls.ContentPresenter> um die Schaltfläche zu hosten. A <xref:System.Windows.Controls.ContentPresenter> zeigt den Inhalt der Schaltfläche an. In dieser exemplarischen Vorgehensweise ist der Inhalt Text ("Button 1", "Button 2", "Button 3"). Alle Vorlagenkomponenten (die Rechtecke <xref:System.Windows.Controls.DockPanel>und die ) sind <xref:System.Windows.Controls.Grid>innerhalb einer angeordnet.

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="Button">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}" ClipToBounds="True">
          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}" RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />
          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20" Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />
          <!-- Present Content (text) of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20" Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>
      </ControlTemplate>
    </Setter.Value>
    ```

     Drücken Sie die Taste F5, um die Anwendung auszuführen. Es sollte wie folgt aussehen.

     ![Fenster mit 3 Tasten](./media/custom-button-animatedbutton-4.gif)

3. **Fügen Sie der Vorlage einen Glaseffekt hinzu:** Als nächstes fügen Sie das Glas hinzu. Zuerst erstellen Sie einige Ressourcen, die einen Glasgradienteneffekt erzeugen. Fügen Sie diese Verlaufsressourcen an einer beliebigen Stelle innerhalb des `Application.Resources` Blocks hinzu:

    ```xaml
    <Application.Resources>
      <GradientStopCollection x:Key="MyGlassGradientStopsResource">
        <GradientStop Color="WhiteSmoke" Offset="0.2" />
        <GradientStop Color="Transparent" Offset="0.4" />
        <GradientStop Color="WhiteSmoke" Offset="0.5" />
        <GradientStop Color="Transparent" Offset="0.75" />
        <GradientStop Color="WhiteSmoke" Offset="0.9" />
        <GradientStop Color="Transparent" Offset="1" />
      </GradientStopCollection>
      <LinearGradientBrush x:Key="MyGlassBrushResource"
        StartPoint="0,0" EndPoint="1,1" Opacity="0.75"
        GradientStops="{StaticResource MyGlassGradientStopsResource}" />
    <!-- Styles and other resources below here. -->
    ```

     Diese Ressourcen werden <xref:System.Windows.Shapes.Shape.Fill%2A> als die für ein <xref:System.Windows.Controls.Grid> Rechteck verwendet, das wir in die der Schaltflächenvorlage einfügen. Fügen Sie der Vorlage das folgende hervorgehobene Markup hinzu.

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="{x:Type Button}">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}"
          ClipToBounds="True">

        <!-- Outer Rectangle with rounded corners. -->
        <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />

        <!-- Inner Rectangle with rounded corners. -->
        <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20"
          Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />

        <!-- Glass Rectangle -->
        <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch"
          StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"
          Fill="{StaticResource MyGlassBrushResource}"
          RenderTransformOrigin="0.5,0.5">
          <Rectangle.Stroke>
            <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">
              <LinearGradientBrush.GradientStops>
                <GradientStop Offset="0.0" Color="LightBlue" />
                <GradientStop Offset="1.0" Color="Gray" />
              </LinearGradientBrush.GradientStops>
            </LinearGradientBrush>
          </Rectangle.Stroke>
          <!-- These transforms have no effect as they are declared here.
          The reason the transforms are included is to be targets
          for animation (see later). -->
          <Rectangle.RenderTransform>
            <TransformGroup>
              <ScaleTransform />
              <RotateTransform />
            </TransformGroup>
          </Rectangle.RenderTransform>
          <!-- A BevelBitmapEffect is applied to give the button a "Beveled" look. -->
          <Rectangle.BitmapEffect>
            <BevelBitmapEffect />
          </Rectangle.BitmapEffect>
        </Rectangle>

        <!-- Present Text of the button. -->
        <DockPanel Name="myContentPresenterDockPanel">
          <ContentPresenter x:Name="myContentPresenter" Margin="20"
            Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
        </DockPanel>
      </Grid>
    </ControlTemplate>
    </Setter.Value>
    ```

     Beachten Sie, dass <xref:System.Windows.UIElement.Opacity%2A> das `x:Name` Rechteck mit der Eigenschaft "glassCube" 0 ist, sodass beim Ausführen des Beispiels das Glasrechteck nicht überlagert wird. Dies liegt daran, dass wir später Trigger zur Vorlage hinzufügen, wenn der Benutzer mit der Schaltfläche interagiert. Sie können jedoch sehen, wie die Schaltfläche <xref:System.Windows.UIElement.Opacity%2A> jetzt aussieht, indem Sie den Wert auf 1 ändern und die Anwendung ausführen. Dies wird in der folgenden Abbildung veranschaulicht. Bevor Sie mit dem nächsten <xref:System.Windows.UIElement.Opacity%2A> Schritt fortfahren, ändern Sie die Rückseite auf 0.

     ![Benutzerdefinierte Schaltflächen, die mit XAML erstellt wurden](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")

## <a name="create-button-interactivity"></a>Erstellen von Button Interaktivität

In diesem Abschnitt erstellen Sie Eigenschaftstrigger und Ereignistrigger, um Eigenschaftswerte zu ändern und Animationen als Reaktion auf Benutzeraktionen auszuführen, z. B. das Verschieben des Mauszeigers über die Schaltfläche und klicken.

Eine einfache Möglichkeit zum Hinzufügen von Interaktivität (Mausüber- und Maus-Leave, Klicken usw.) besteht darin, Trigger in Ihrer Vorlage oder Ihrem Stil zu definieren. Um eine <xref:System.Windows.Trigger>zu erstellen, definieren Sie eine Eigenschaft <xref:System.Windows.UIElement.IsMouseOver%2A> "Bedingung" `true`wie: Der Wert der Schaltflächeneigenschaft ist gleich . Anschließend definieren Sie Setter (Aktionen), die stattfinden, wenn die Triggerbedingung wahr ist.

### <a name="to-create-button-interactivity"></a>So erstellen Sie Schaltflächeninteraktivität

1. **Vorlagentrigger hinzufügen:** Fügen Sie der Vorlage das hervorgehobene Markup hinzu.

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="{x:Type Button}">
        <Grid Width="{TemplateBinding Width}"
          Height="{TemplateBinding Height}" ClipToBounds="True">

          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />

          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"
            VerticalAlignment="Stretch" Stroke="Transparent"
            StrokeThickness="20"
            Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20"
          />

          <!-- Glass Rectangle -->
          <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"
            VerticalAlignment="Stretch"
            StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"
            Fill="{StaticResource MyGlassBrushResource}"
            RenderTransformOrigin="0.5,0.5">
            <Rectangle.Stroke>
              <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">
                <LinearGradientBrush.GradientStops>
                  <GradientStop Offset="0.0" Color="LightBlue" />
                  <GradientStop Offset="1.0" Color="Gray" />
                </LinearGradientBrush.GradientStops>
              </LinearGradientBrush>
            </Rectangle.Stroke>

            <!-- These transforms have no effect as they
                 are declared here.
                 The reason the transforms are included is to be targets
                 for animation (see later). -->
            <Rectangle.RenderTransform>
              <TransformGroup>
                <ScaleTransform />
                <RotateTransform />
              </TransformGroup>
            </Rectangle.RenderTransform>

              <!-- A BevelBitmapEffect is applied to give the button a
                   "Beveled" look. -->
            <Rectangle.BitmapEffect>
              <BevelBitmapEffect />
            </Rectangle.BitmapEffect>
          </Rectangle>

          <!-- Present Text of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20"
              Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>

        <ControlTemplate.Triggers>       <!-- Set action triggers for the buttons and define            what the button does in response to those triggers. -->     </ControlTemplate.Triggers>
      </ControlTemplate>
    </Setter.Value>
    ```

2. **Eigenschaftentrigger hinzufügen:** Fügen Sie dem `ControlTemplate.Triggers` Block das hervorgehobene Markup hinzu:

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>

    <ControlTemplate.Triggers/>
    ```

     Drücken Sie F5, um die Anwendung auszuführen, und sehen Sie den Effekt, während Sie den Mauszeiger über die Schaltflächen ausführen.

3. **Hinzufügen eines Fokustriggers:** Als Nächstes fügen wir einige ähnliche Setter hinzu, um den Fall zu behandeln, wenn die Schaltfläche den Fokus hat (z. B. nachdem der Benutzer darauf geklickt hat).

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->
      <Trigger Property="IsMouseOver" Value="True">

        <!-- Below are three property settings that occur when the
             condition is met (user mouses over button).  -->
        <!-- Change the color of the outer rectangle when user          mouses over it. -->
        <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"
          Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />

        <!-- Sets the glass opacity to 1, therefore, the          glass "appears" when user mouses over it. -->
        <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />

        <!-- Makes the text slightly blurry as though you were          looking at it through blurry glass. -->
        <Setter Property="ContentPresenter.BitmapEffect"       TargetName="myContentPresenter">
          <Setter.Value>
            <BlurBitmapEffect Radius="1" />
          </Setter.Value>
        </Setter>
      </Trigger>
      <!-- Set properties when button has focus. -->   <Trigger Property="IsFocused" Value="true">     <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />     <Setter Property="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />   </Trigger>

    </ControlTemplate.Triggers>
    ```

     Drücken Sie F5, um die Anwendung auszuführen, und klicken Sie auf eine der Schaltflächen. Beachten Sie, dass die Schaltfläche hervorgehoben bleibt, nachdem Sie darauf geklickt haben, da sie immer noch den Fokus hat. Wenn Sie auf eine andere Schaltfläche klicken, erhält die neue Schaltfläche den Fokus, während die letzte Sie verlieren.

4. **Fügen Sie Animationen für** <xref:System.Windows.UIElement.MouseEnter> **und** <xref:System.Windows.UIElement.MouseLeave> **:** Als nächstes fügen wir einige Animationen zu den Triggern hinzu.   Fügen Sie das folgende Markup an einer beliebigen Stelle innerhalb des `ControlTemplate.Triggers` Blocks hinzu.

    ```xaml
    <!-- Animations that start when mouse enters and leaves button. -->
    <EventTrigger RoutedEvent="Mouse.MouseEnter">
      <EventTrigger.Actions>
        <BeginStoryboard Name="mouseEnterBeginStoryboard">
          <Storyboard>
          <!-- This animation makes the glass rectangle shrink in the X direction. -->
            <DoubleAnimation Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleX)"
              By="-0.1" Duration="0:0:0.5" />
            <!-- This animation makes the glass rectangle shrink in the Y direction. -->
            <DoubleAnimation
            Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleY)"
              By="-0.1" Duration="0:0:0.5" />
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger.Actions>
    </EventTrigger>
    <EventTrigger RoutedEvent="Mouse.MouseLeave">
      <EventTrigger.Actions>
        <!-- Stopping the storyboard sets all animated properties back to default. -->
        <StopStoryboard BeginStoryboardName="mouseEnterBeginStoryboard" />
      </EventTrigger.Actions>
    </EventTrigger>
    ```

     Das Glasrechteck wird verkleinert, wenn sich der Mauszeiger über die Schaltfläche bewegt, und kehrt zum normalen Zeiger zurück, wenn der Zeiger verlässt.

     Es gibt zwei Animationen, die ausgelöst werden,<xref:System.Windows.UIElement.MouseEnter> wenn der Zeiger über die Schaltfläche geht (Ereignis wird ausgelöst). Diese Animationen verkleinern das Glasrechteck entlang der X- und Y-Achse. Beachten Sie die <xref:System.Windows.Media.Animation.DoubleAnimation> Eigenschaften <xref:System.Windows.Media.Animation.Timeline.Duration%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>der Elemente — und . Der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> gibt an, dass die Animation <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> mehr als eine halbe Sekunde dauert, und gibt an, dass das Glas um 10 % schrumpft.

     Der zweite Ereignisauslöser (<xref:System.Windows.UIElement.MouseLeave>) stoppt einfach den ersten. Wenn Sie <xref:System.Windows.Media.Animation.Storyboard>eine beenden, kehren alle animierten Eigenschaften zu ihren Standardwerten zurück. Wenn der Benutzer den Mauszeiger von der Schaltfläche entfernt, kehrt die Schaltfläche daher zu der Art zurück, wie sie war, bevor der Mauszeiger über die Schaltfläche bewegt wurde. Weitere Informationen zu Animationen finden Sie unter [Animationsübersicht](../graphics-multimedia/animation-overview.md).

5. **Fügen Sie eine Animation hinzu, wenn auf die Schaltfläche geklickt wird:** Der letzte Schritt besteht darin, einen Trigger hinzuzufügen, wenn der Benutzer auf die Schaltfläche klickt. Fügen Sie das folgende Markup an einer beliebigen Stelle innerhalb des `ControlTemplate.Triggers` Blocks hinzu:

    ```xaml
    <!-- Animation fires when button is clicked, causing glass to spin.  -->
    <EventTrigger RoutedEvent="Button.Click">
      <EventTrigger.Actions>
        <BeginStoryboard>
          <Storyboard>
            <DoubleAnimation Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[1].(RotateTransform.Angle)"
              By="360" Duration="0:0:0.5" />
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger.Actions>
    </EventTrigger>
    ```

     Drücken Sie F5, um die Anwendung auszuführen, und klicken Sie auf eine der Schaltflächen. Wenn Sie auf eine Schaltfläche klicken, dreht sich das Glasrechteck um.

## <a name="summary"></a>Zusammenfassung
 In dieser exemplarischen Vorgehensweise haben Sie die folgenden Übungen durchgeführt:

- Gezielt <xref:System.Windows.Style> a auf einen<xref:System.Windows.Controls.Button>Objekttyp ( ).

- Kontrollierte grundlegende Eigenschaften der Schaltflächen in <xref:System.Windows.Style>der gesamten Anwendung mit der .

- Ressourcen wie Farbverläufe erstellt, die <xref:System.Windows.Style> für Eigenschaftswerte der Setter verwendet werden sollen.

- Angepasst eisern das Aussehen von Schaltflächen in der gesamten Anwendung, indem Sie eine Vorlage auf die Schaltflächen anwenden.

- Angepasstes Verhalten für die Schaltflächen als <xref:System.Windows.UIElement.MouseEnter> <xref:System.Windows.UIElement.MouseLeave>Reaktion <xref:System.Windows.Controls.Primitives.ButtonBase.Click>auf Benutzeraktionen (z. B. , und ), die Animationseffekte enthalten.

## <a name="see-also"></a>Siehe auch

- [Erstellen einer Schaltfläche mit Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Übersicht über Animationen](../graphics-multimedia/animation-overview.md)
- [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [Übersicht über Bitmapeffekte](../graphics-multimedia/bitmap-effects-overview.md)
