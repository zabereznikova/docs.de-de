---
title: 'Exemplarische Vorgehensweise: Erstellen einer Schaltfläche mit XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: 96d54efbabbd95a24f1fb7118305ddbff4dfd110
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43525350"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a>Exemplarische Vorgehensweise: Erstellen einer Schaltfläche mit XAML
Das Ziel dieser exemplarischen Vorgehensweise werden erfahren, wie Sie eine animierte Schaltfläche für die Verwendung in einer Windows Presentation Foundation (WPF)-Anwendung zu erstellen. In dieser exemplarischen Vorgehensweise verwendet und eine Vorlage zum Erstellen einer benutzerdefinierten Schaltflächenressource, die Wiederverwendung von Code und die Trennung von aus der Schaltflächendeklaration ermöglicht. In dieser exemplarischen Vorgehensweise wird ausschließlich in geschrieben [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
> [!IMPORTANT]
>  Diese exemplarische Vorgehensweise führt Sie durch die Schritte zum Erstellen der Anwendung durch eingeben oder kopieren und Einfügen [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] in Microsoft Visual Studio. Wenn Sie erfahren lieber, wie Sie ein Design-Tool (Microsoft Expression Blend) mit die gleiche Anwendung zu erstellen, finden Sie unter [erstellen Sie eine Schaltfläche mithilfe von Microsoft Expression Blend](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md).  
  
 Die folgende Abbildung zeigt die Schaltflächen fertig.  
  
 ![Benutzerdefinierte Schaltflächen, die mit XAML erstellt wurden](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")  
  
## <a name="create-basic-buttons"></a>Erstellen von grundlegenden Schaltflächen  
 Beginnen Sie durch Erstellen eines neuen Projekts und einige Schaltflächen hinzufügen, um das Fenster.  
  
#### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a>Erstellen eines neuen WPF-Projekts und Hinzufügen von Schaltflächen für das Fenster  
  
1.  Starten Sie Visual Studio.  
  
2.  **Erstellen eines neuen WPF-Projekts:** auf die **Datei** Startmenü **neu**, und klicken Sie dann auf **Projekt**. Suchen der **Windows-Anwendung (WPF)** Vorlage und geben Sie dem Projekt "den Namen AnimatedButton". Dadurch wird das Gerüst für die Anwendung erstellt.  
  
3.  **Hinzufügen von Standardschaltflächen für basic,:** werden alle Dateien, die in dieser exemplarischen Vorgehensweise Sie müssen von der Vorlage bereitgestellt. Öffnen Sie die Datei "Window1.xaml", indem Sie auf die sie im Projektmappen-Explorer doppelklicken. Es wird standardmäßig ein <xref:System.Windows.Controls.Grid> Element in der Datei Window1.xaml. Entfernen der <xref:System.Windows.Controls.Grid> Element, und fügen einige Schaltflächen auf der [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Seite eingeben oder kopieren und Einfügen von den folgenden hervorgehobenen Code in die Datei Window1.xaml:  
  
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
  
     Drücken Sie F5 zum Ausführen der Anwendung verwendet. Daraufhin sollte eine Reihe von Schaltflächen, die in der folgenden Abbildung aussieht.  
  
     ![Drei grundlegende Schaltflächen](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")  
  
     Nun, dass Sie die grundlegende Schaltflächen erstellt haben, können Sie alle erforderlichen Schritte ausgeführt werden, in der Datei "Window1.xaml". Der Rest der exemplarischen Vorgehensweise konzentriert sich auf die Datei "App.xaml" Definieren von Stilen und eine Vorlage für die Schaltflächen.  
  
## <a name="set-basic-properties"></a>Legen Sie grundlegende Eigenschaften  
 Als Nächstes legen wir einige Eigenschaften für diese Schaltflächen, um die Darstellung und Layout steuern. Anstatt Eigenschaften einzeln auf den Schaltflächen festlegen, werden Sie Ressourcen verwenden, um Schaltflächeneigenschaften für die gesamte Anwendung zu definieren. Anwendungsressourcen sind konzeptionell identisch mit externen [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)] für Webseiten jedoch Ressourcen sind wesentlich leistungsfähiger als [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)], wie Sie am Ende dieser exemplarischen Vorgehensweise sehen. Weitere Informationen zu Ressourcen finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
#### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a>Um Stile zu verwenden, um grundlegende Eigenschaften für die Schaltflächen festlegen  
  
1.  **Definieren Sie einen Block Application.Resources:** "App.xaml" zu öffnen und die folgende hervorgehobene Markup hinzufügen, wenn sie nicht bereits vorhanden ist:  
  
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
  
     Ressourcenbereich wird durch Sie die Ressource definieren bestimmt. Definieren von Ressourcen in `Application.Resources` in app.xaml-Datei kann die Ressource aus an einer beliebigen Stelle in der Anwendung verwendet werden. Weitere Informationen zum Definieren des Bereichs Ihrer Ressourcen finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
2.  **Eine Formatvorlage erstellen und grundlegende Eigenschaftswerte mit definieren:** fügen Sie das folgende Markup, das `Application.Resources` Block. Dieses Markup erstellt eine <xref:System.Windows.Style> , die für alle Schaltflächen in der Anwendung, die Einstellung gilt die <xref:System.Windows.FrameworkElement.Width%2A> der Schaltflächen auf 90 und die <xref:System.Windows.FrameworkElement.Margin%2A> auf 10:  
  
    ```xaml  
    <Application.Resources>  
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>  
    </Application.Resources>  
    ```  
  
     Die <xref:System.Windows.Style.TargetType%2A> Eigenschaft gibt an, dass der Stil für alle Objekte des Typs gilt <xref:System.Windows.Controls.Button>. Jede <xref:System.Windows.Setter> legt einen anderen Eigenschaftswert für die <xref:System.Windows.Style>. Daher muss jede Schaltfläche in der Anwendung an diesem Punkt eine Breite von 90 und einem Rand von 10.  Wenn Sie zum Ausführen der Anwendung F5 drücken, wird das folgende Fenster angezeigt.  
  
     ![Schaltflächen mit einer Breite von 90 und einem Rand von 10](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")  
  
     Es gibt viele weitere Möglichkeiten mit Stilen, einschließlich eine Vielzahl von Möglichkeiten zum Optimieren, welche Objekte gelten, komplexe Eigenschaftswerte angeben und auch mithilfe von Stilen als Eingabe für andere Stile. Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
3.  **Legen Sie einen Stil-Eigenschaftswert auf eine Ressource:** Ressourcen ermöglichen eine einfache Möglichkeit, Wiederverwenden von häufig definierten Objekten und Werte. Er ist besonders nützlich, um mit Ressourcen, um den Code etwas modularer gestalten komplexe Werte zu definieren. Fügen Sie die folgende hervorgehobene Markup, um "App.xaml".  
  
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
  
     Direkt unterhalb der `Application.Resources` Block, haben Sie eine Ressource namens "GrayBlueGradientBrush erstellt". Dieser Ressource wird einen horizontalen Farbverlauf definiert. Diese Ressource verwendet werden kann, als Eigenschaftswert von überall aus in der Anwendung, die auch im Setter für den Stil für die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft. Jetzt alle Schaltflächen sind eine <xref:System.Windows.Controls.Control.Background%2A> Eigenschaftswert, der diesem Farbverlauf.  
  
     Drücken Sie F5, um die Anwendung auszuführen. Es sollte wie folgt aussehen.  
  
     ![Schaltflächen mit einem Farbverlaufshintergrund](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")  
  
## <a name="create-a-template-that-defines-the-look-of-the-button"></a>Erstellen Sie eine Vorlage, die das Aussehen der Schaltfläche definiert.  
 In diesem Abschnitt erstellen Sie eine Vorlage, die die Darstellung der Schaltfläche (Presentation) passt. Die Darstellung der Schaltfläche mehrere Objekte, darunter Rechtecke und anderen Komponenten besteht, geben Sie der Schaltfläche ein charakteristisches Aussehen verleihen.  
  
 Bisher wurde die Kontrolle über die Darstellung von Schaltflächen in der Anwendung beschränkt wurde, zum Ändern der Eigenschaften der Schaltfläche. Was geschieht, wenn Sie möchten die Darstellung der Schaltfläche radikalere Änderungen vornehmen? Vorlagen können leistungsstarke Kontrolle über die Darstellung eines Objekts. Da Vorlagen innerhalb von Stilen verwendet werden können, können Sie eine Vorlage für alle Objekte anwenden, denen das Format auf (in dieser exemplarischen Vorgehensweise, die Schaltfläche ") angewendet wird.  
  
#### <a name="to-use-the-template-to-define-the-look-of-the-button"></a>Die Vorlage zu verwenden, um das Aussehen der Schaltfläche zu definieren.  
  
1.  **Richten Sie die Vorlage:** da Steuerelemente wie <xref:System.Windows.Controls.Button> haben eine <xref:System.Windows.Controls.Control.Template%2A> -Eigenschaft, können Sie den Wert der Vorlage genau wie die anderen haben wir auf Eigenschaftswerte definieren eine <xref:System.Windows.Style> mithilfe einer <xref:System.Windows.Setter>. Fügen Sie die folgende hervorgehobene Markup, um die Schaltflächen-Formatvorlage.  
  
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
  
2.  **Ändern der Darstellung der Schaltfläche:** an diesem Punkt müssen Sie die Vorlage zu definieren. Fügen Sie das folgende hervorgehobene Markup hinzu. Dieses Markup gibt zwei <xref:System.Windows.Shapes.Rectangle> Elemente mit abgerundeten Ecken an, gefolgt von einem <xref:System.Windows.Controls.DockPanel>. Die <xref:System.Windows.Controls.DockPanel> wird verwendet, auf dem Host die <xref:System.Windows.Controls.ContentPresenter> der Schaltfläche. Ein <xref:System.Windows.Controls.ContentPresenter> zeigt den Inhalt der Schaltfläche. In dieser exemplarischen Vorgehensweise wird der Inhalt Text ("Schaltfläche" 1","Button 2","Button 3"). Alle von den Komponenten der Dienstvorlage (Rechtecke und die <xref:System.Windows.Controls.DockPanel>) angeordnet sind, in der ein <xref:System.Windows.Controls.Grid>.  
  
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
  
     Drücken Sie F5, um die Anwendung auszuführen. Es sollte wie folgt aussehen.  
  
     ![](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-4.gif "custom_button_AnimatedButton_4")  
  
3.  **Fügen Sie einen Glaseffekt auf die Vorlage:** als Nächstes fügen Sie das Glas. Erstellen Sie zunächst einige Ressourcen, die einen Glaseffekt für den Farbverlauf zu erstellen. Fügen Sie diesen Farbverlauf Ressourcen an einer beliebigen Stelle innerhalb der `Application.Resources` blockieren:  
  
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
  
     Diese Ressourcen dienen dazu, wie die <xref:System.Windows.Shapes.Shape.Fill%2A> für ein Rechteck, das wir in einfügen die <xref:System.Windows.Controls.Grid> der Schaltflächenvorlage. Fügen Sie das folgende hervorgehobene Markup der Vorlage hinzu.  
  
    ```  
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
  
     Beachten Sie, dass die <xref:System.Windows.UIElement.Opacity%2A> des Rechtecks mit der `x:Name` "GlassCube"-Eigenschaft ist 0, damit beim Ausführen des Beispiels nicht das Glasrechteck als Überlagerung auf oben angezeigt wird. Dies ist, da wir später Trigger auf die Vorlage für hinzufügen, wenn der Benutzer mit der Schaltfläche interagiert. Sie können jedoch sehen, wie die Schaltfläche mit der jetzt ändern dargestellt die <xref:System.Windows.UIElement.Opacity%2A> Wert 1 und Ausführen der Anwendung. Das Ergebnis wird in der folgende Abbildung gezeigt. Vor dem Fortfahren mit dem nächsten Schritt ändern Sie die <xref:System.Windows.UIElement.Opacity%2A> auf 0 zurück.  
  
     ![Benutzerdefinierte Schaltflächen, die mit XAML erstellt wurden](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")  
  
## <a name="create-button-interactivity"></a>Gestalten, Schaltfläche  
 In diesem Abschnitt erstellen Sie Eigenschaftstrigger und Ereignistrigger Eigenschaftswerte ändern und Ausführen von Animationen als Reaktion auf Benutzeraktionen wie klicken und den Mauszeiger über der Schaltfläche.  
  
 Eine einfache Möglichkeit zum Hinzufügen von Interaktivität (Mouseover-MouseLeave-, klicken Sie auf und So weiter) werden in der Vorlage oder Stil festlegen. Zum Erstellen einer <xref:System.Windows.Trigger>, definieren Sie z. B. eine Eigenschaft "Condition": die Schaltfläche mit den <xref:System.Windows.UIElement.IsMouseOver%2A> Eigenschaftswert ist gleich `true`. Anschließend definieren Sie die Setter (Aktionen), die stattfinden, wenn die auslöserbedingung erfüllt ist.  
  
#### <a name="to-create-button-interactivity"></a>Schaltfläche Interaktivität  
  
1.  **Hinzufügen von Vorlagentriggern:** fügen Sie das hervorgehobene Markup der Vorlage.  
  
    ```  
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
  
2.  **Eigenschaftsauslöser hinzufügen:** fügen Sie das hervorgehobene Markup, das `ControlTemplate.Triggers` blockieren:  
  
    ```  
    <ControlTemplate.Triggers>  
  
      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>  
  
    <ControlTemplate.Triggers/>  
    ```  
  
     Drücken Sie F5, um die Anwendung auszuführen und die Auswirkung dieser feststellen, wie Sie den Mauszeiger über die Schaltflächen ausführen.  
  
3.  **Hinzufügen eines Triggers Fokus:** als Nächstes fügen wir einige ähnliche Setter, um Fälle zu behandeln, wenn die Schaltfläche den Fokus (z. B. hat, wenn der Benutzer darauf klickt).  
  
    ```  
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
  
     Drücken Sie F5, um die Anwendung auszuführen, und klicken auf eine der Schaltflächen. Beachten Sie, dass die Schaltfläche mit der hervorgehobenen bleibt, wenn Sie darauf klicken, da es immer noch den Fokus besitzt. Wenn Sie eine andere Schaltfläche klicken, erhält die neue Schaltfläche den Fokus, während die verliert.  
  
4.  **Hinzufügen von Animationen für** <xref:System.Windows.UIElement.MouseEnter> **und** <xref:System.Windows.UIElement.MouseLeave> **:** als Nächstes fügen wir einige Animationen für die Trigger hinzu. Fügen Sie das folgende Markup an einer beliebigen Stelle in der die `ControlTemplate.Triggers` Block.  
  
    ```  
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
  
     Das Glasrechteck wird reduziert, wenn der Mauszeiger über die Schaltfläche bewegt, und gibt an die normale Größe zurück, wenn der Mauszeiger verlässt.  
  
     Es werden zwei Animationen, die ausgelöst werden, wenn der Zeiger auf die Schaltfläche befindet (<xref:System.Windows.UIElement.MouseEnter> Ereignis wird ausgelöst). Diese Animationen verkleinert das Glasrechteck entlang der X- und Y-Achse. Beachten Sie die Eigenschaften auf der <xref:System.Windows.Media.Animation.DoubleAnimation> Elemente – <xref:System.Windows.Media.Animation.Timeline.Duration%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>. Die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> gibt an, dass die Animation über mehr als eine halbe Sekunde auftritt und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> gibt an, dass das Glas um 10 % verkleinert wird.  
  
     Der zweite Ereignistrigger (<xref:System.Windows.UIElement.MouseLeave>) einfach beendet das erste Abonnement. Wenn Sie beenden eine <xref:System.Windows.Media.Animation.Storyboard>, alle animierten Eigenschaften auf ihre Standardwerte zurück. Aus diesem Grund, wenn der Benutzer den Zeiger der Schaltfläche weg bewegt, wird die Schaltfläche zurück auf die Art und Weise, die vor der Mauszeiger über die Schaltfläche bewegt. Weitere Informationen zu Animationen finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
5.  **Fügen Sie eine Animation für, wenn die Schaltfläche geklickt wird:** der letzte Schritt ist zum Hinzufügen eines Triggers für, wenn der Benutzer die Schaltfläche klickt. Fügen Sie das folgende Markup an einer beliebigen Stelle in der die `ControlTemplate.Triggers` blockieren:  
  
    ```  
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
  
     Drücken Sie F5, um die Anwendung auszuführen, und klicken Sie auf eine der Schaltflächen. Wenn Sie eine Schaltfläche klicken, dreht sich um das Glasrechteck.  
  
## <a name="summary"></a>Zusammenfassung  
 In dieser exemplarischen Vorgehensweise haben Sie die folgenden Übungen:  
  
-   Ziel einer <xref:System.Windows.Style> in einen Objekttyp (<xref:System.Windows.Controls.Button>).  
  
-   Gesteuert von grundlegenden Eigenschaften von Schaltflächen in der gesamten Anwendung mit der <xref:System.Windows.Style>.  
  
-   Ressourcen wie Farbverläufe, für Eigenschaftswerte erstellt die <xref:System.Windows.Style> Setter.  
  
-   Die Darstellung der Schaltflächen in der gesamten Anwendung wird durch Anwenden einer Vorlage auf die Schaltflächen angepasst.  
  
-   Anpassen des Verhaltens für die Schaltflächen als Reaktion auf Benutzeraktionen (z. B. <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, und <xref:System.Windows.Controls.Primitives.ButtonBase.Click>), die Animationseffekte enthalten.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen einer Schaltfläche mit Microsoft Expression Blend](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [Übersicht über Bitmapeffekte](../../../../docs/framework/wpf/graphics-multimedia/bitmap-effects-overview.md)
