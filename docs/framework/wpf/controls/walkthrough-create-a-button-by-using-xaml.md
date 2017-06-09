---
title: "Exemplarische Vorgehensweise: Erstellen einer Schaltfl&#228;che mit XAML | Microsoft Docs"
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
  - "Schaltflächen"
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Exemplarische Vorgehensweise: Erstellen einer Schaltfl&#228;che mit XAML
In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie eine animierte Schaltfläche für eine [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]\-Anwendung erstellen.  In dieser exemplarischen Vorgehensweise werden Stile und eine Vorlage verwendet, um eine benutzerdefinierte Schaltflächenressource zu erstellen, die die Wiederverwendung von Code und die Trennung von Schaltflächenlogik und Schaltflächendeklaration ermöglicht.  Diese exemplarische Vorgehensweise ist vollständig in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] geschrieben.  
  
> [!IMPORTANT]
>  Diese exemplarische Vorgehensweise führt Sie schrittweise durch das Erstellen der Anwendung durch Eingeben bzw. Kopieren und Einfügen von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] in Microsoft [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].  Wenn Sie lieber den Umgang mit einem Entwurfstool \(Microsoft Expression Blend\) erlernen möchten, um dieselbe Anwendung zu erstellen, finden Sie die entsprechenden Informationen unter [Erstellen einer Schaltfläche mit Microsoft Expression Blend](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md).  
  
 In der folgenden Abbildung werden die fertigen Schaltflächen dargestellt.  
  
 ![Benutzerdefinierte Schaltflächen, die mit XAML erstellt wurden](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.png "custom\_button\_AnimatedButton\_5")  
  
## Erstellen von grundlegenden Schaltflächen  
 Zunächst erstellen Sie ein neues Projekt und fügen dem Fenster einige Schaltflächen hinzu.  
  
#### So erstellen Sie ein neues WPF\-Projekt und fügen dem Fenster Schaltflächen hinzu  
  
1.  Starten Sie[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].  
  
2.  **Erstellen Sie ein neues WPF\-Projekt:** Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.  Suchen Sie die Vorlage **Windows\-Anwendung \(WPF\)**, und geben Sie dem Projekt den Namen "AnimatedButton".  Dadurch wird das Skelett für die Anwendung erstellt.  
  
3.  **Fügen Sie grundlegende Standardschaltflächen hinzu:** Alle für diese exemplarische Vorgehensweise benötigten Dateien werden von der Vorlage bereitgestellt.  Öffnen Sie die Datei Window1.xaml, indem Sie im Projektmappen\-Explorer darauf doppelklicken.  Standardmäßig ist in der Datei Window1.xaml ein <xref:System.Windows.Controls.Grid>\-Element vorhanden.  Entfernen Sie das <xref:System.Windows.Controls.Grid>\-Element, und fügen Sie der Seite [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] einige Schaltflächen hinzu, indem Sie den folgenden hervorgehobenen Code in die Datei Window1.xaml eingeben bzw. kopieren und einfügen:  
  
    ```  
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
  
     Drücken Sie F5, um die Anwendung auszuführen; es sollte eine Gruppe von Schaltflächen angezeigt werden, die so aussehen wie in der folgenden Abbildung.  
  
     ![Drei grundlegende Schaltflächen](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-1.png "custom\_button\_AnimatedButton\_1")  
  
     Nachdem Sie nun die grundlegenden Schaltflächen erstellt haben, ist die Bearbeitung der Datei Window1.xaml abgeschlossen.  Im restlichen Teil der exemplarischen Vorgehensweise geht es um die Datei app.xaml sowie um das Definieren von Stilen und einer Vorlage für die Schaltflächen.  
  
## Festlegen von grundlegenden Eigenschaften  
 Als Nächstes werden einige Eigenschaften für diese Schaltflächen festgelegt, um ihre Darstellung und Layout zu steuern.  Anstatt Eigenschaften für die Schaltflächen einzeln festzulegen, definieren Sie die Schaltflächeneigenschaften für die gesamte Anwendung mithilfe von Ressourcen.  Anwendungsressourcen ähneln im Prinzip externen [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)] für Webseiten. Allerdings sind Ressourcen viel leistungsfähiger als [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)], wie Sie am Ende dieser exemplarischen Vorgehensweise feststellen werden.  Weitere Informationen über Ressourcen finden Sie unter [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
#### So verwenden Sie Stile, um grundlegende Eigenschaften für die Schaltflächen festzulegen  
  
1.  **Definieren Sie einen Application.Resources\-Block:** Öffnen Sie die Datei app.xaml, und fügen Sie das folgende hervorgehobene Markup hinzu, sofern es noch nicht vorhanden ist:  
  
    ```  
    <Application x:Class="AnimatedButton.App"  
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
      StartupUri="Window1.xaml"  
      >  
      <Application.Resources>  
  
        <!-- Resources for the entire application can be   
             defined here. -->  
  
      </Application.Resources>  
    </Application>  
    ```  
  
     Der Ressourcenbereich hängt davon ab, an welcher Stelle Sie die Ressource definieren.  Wenn Ressourcen in `Application.Resoureses` in der Datei app.xaml definiert werden, kann die Ressource an jeder Stelle der Anwendung verwendet werden.  Weitere Informationen über das Definieren von Ressourcenbereichen finden Sie unter [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
2.  **Erstellen Sie einen Stil, und definieren Sie dazu grundlegende Eigenschaftswerte:** Fügen Sie dem `Application.Resources`\-Block das folgende Markup hinzu.  Dieses Markup erstellt einen <xref:System.Windows.Style>, der für alle Schaltflächen in der Anwendung gilt. Dabei wird die <xref:System.Windows.FrameworkElement.Width%2A> der Schaltflächen auf 90 und der <xref:System.Windows.FrameworkElement.Margin%2A> auf 10 festgelegt:  
  
    ```  
    <Application.Resources>  
  
      <Style TargetType="Button">  
        <Setter Property="Width" Value="90" />  
        <Setter Property="Margin" Value="10" />  
      </Style>  
  
    </Application.Resources>  
    ```  
  
     Die <xref:System.Windows.Style.TargetType%2A>\-Eigenschaft gibt an, dass der Stil für alle Objekte des Typs <xref:System.Windows.Controls.Button> gilt.  Jeder <xref:System.Windows.Setter> legt einen anderen Eigenschaftswert für den <xref:System.Windows.Style> fest.  Daher weist jede Schaltfläche in der Anwendung zu diesem Zeitpunkt eine Breite von 90 und einen Rand von 10 auf.  Wenn Sie F5 drücken, um die Anwendung auszuführen, wird das folgende Fenster angezeigt.  
  
     ![Schaltflächen mit einer Breite von 90 und einem Rand von 10](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-2.png "custom\_button\_AnimatedButton\_2")  
  
     Die Anwendungsmöglichkeiten von Stilen reichen weit über das Gezeigte hinaus. Dazu zählen eine Reihe von Möglichkeiten, um genauer festzulegen, welche Objekte verwendet werden, die Angabe komplexer Eigenschaftswerte und sogar die Verwendung von Stilen als Eingabe für andere Stile.  Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
3.  **Legen Sie einen Stileigenschaftswert für eine Ressource fest:** Ressourcen bieten eine einfache Möglichkeit, häufig definierte Objekte und Werte wieder zu verwenden.  Es ist besonders nützlich, mit Ressourcen komplexe Werte zu definieren, um den Code modularer zu gestalten.  Fügen Sie der Datei app.xaml das folgende hervorgehobene Markup hinzu.  
  
    ```  
    <Application.Resources>  
  
      <LinearGradientBrush x:Key="GrayBlueGradientBrush"   
        StartPoint="0,0" EndPoint="1,1">  
        <GradientStop Color="DarkGray" Offset="0" />  
        <GradientStop Color="#CCCCFF" Offset="0.5" />  
        <GradientStop Color="DarkGray" Offset="1" />  
      </LinearGradientBrush>  
  
      <Style TargetType="{x:Type Button}">  
        <Setter Property="Background"   
          Value="{StaticResource GrayBlueGradientBrush}" />  
        <Setter Property="Width" Value="80" />  
        <Setter Property="Margin" Value="10" />  
      </Style>  
  
    </Application.Resources>  
    ```  
  
     Direkt unter dem `Application.Resources`\-Block haben Sie eine Ressource mit dem Namen "GrayBlueGradientBrush" erstellt.  Diese Ressource definiert einen horizontalen Farbverlauf.  Diese Ressource lässt sich als Eigenschaftswert an jeder Stelle der Anwendung verwenden, auch im Setter für den Schaltflächenstil für die <xref:System.Windows.Controls.Control.Background%2A>\-Eigenschaft.  Jetzt verfügen alle Schaltflächen über einen <xref:System.Windows.Controls.Control.Background%2A>\-Eigenschaftswert von diesem Farbverlauf.  
  
     Drücken Sie F5, um die Anwendung auszuführen.  Sie sollte wie folgt aussehen.  
  
     ![Schaltflächen mit einem Farbverlaufshintergrund](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-3.png "custom\_button\_AnimatedButton\_3")  
  
## Erstellen einer Vorlage, die das Aussehen der Schaltfläche definiert  
 In diesem Abschnitt wird eine Vorlage erstellt, die das Aussehen \(Darstellung\) der Schaltfläche anpasst.  Die Schaltflächendarstellung besteht aus mehreren Objekten, einschließlich Rechtecken und anderen Komponenten, um der Schaltfläche ein individuelles Aussehen zu verleihen.  
  
 Bislang lässt sich das Aussehen von Schaltflächen in der Anwendung nur über die Änderung der Schaltflächeneigenschaften beeinflussen.  Wie gehen Sie aber vor, wenn Sie tief greifendere Änderungen am Aussehen der Schaltfläche vornehmen möchten?  Vorlagen bieten eine leistungsstarke Steuerung der Darstellung eines Objekts.  Da sich Vorlagen innerhalb von Stilen verwenden lassen, können Sie eine Vorlage auf alle Objekte anwenden, für die der Stil gilt \(in dieser exemplarischen Vorgehensweise ist das die Schaltfläche\).  
  
#### So definieren Sie das Aussehen der Schaltfläche mithilfe der Vorlage  
  
1.  **Richten Sie die Vorlage ein:** Da Steuerelemente wie <xref:System.Windows.Controls.Button> eine <xref:System.Windows.Controls.Control.Template%2A>\-Eigenschaft besitzen, können Sie den Wert der Vorlageneigenschaft wie die anderen Eigenschaftswerte definieren, die Sie in einem <xref:System.Windows.Style> mit einem <xref:System.Windows.Setter> festgelegt haben.  Fügen Sie dem Schaltflächenstil das folgende hervorgehobene Markup hinzu.  
  
    ```  
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
  
2.  **Ändern Sie die Schaltflächendarstellung:** An dieser Stelle müssen Sie die Vorlage definieren.  Fügen Sie das folgende hervorgehobene Markup hinzu.  Dieses Markup gibt zwei <xref:System.Windows.Shapes.Rectangle>\-Elemente mit abgerundeten Ecken an, gefolgt von einem <xref:System.Windows.Controls.DockPanel>.  Mit <xref:System.Windows.Controls.DockPanel> wird der <xref:System.Windows.Controls.ContentPresenter> der Schaltfläche gehostet.  Mit einem <xref:System.Windows.Controls.ContentPresenter> wird der Inhalt der Schaltfläche angezeigt.  In dieser exemplarischen Vorgehensweise besteht der Inhalt aus Text \("Button 1", "Button 2", "Button 3"\).  Alle Vorlagenkomponenten \(die Rechtecke und das <xref:System.Windows.Controls.DockPanel> sind in einem <xref:System.Windows.Controls.Grid> angeordnet.  
  
    ```  
    <Setter.Value>  
      <ControlTemplate TargetType="Button">  
        <Grid Width="{TemplateBinding Width}"   
         Height="{TemplateBinding Height}" ClipToBounds="True">  
  
          <!-- Outer Rectangle with rounded corners. -->  
          <Rectangle x:Name="outerRectangle"   
            HorizontalAlignment="Stretch"   
            VerticalAlignment="Stretch"   
            Stroke="{TemplateBinding Background}"   
            RadiusX="20" RadiusY="20" StrokeThickness="5"   
            Fill="Transparent" />  
  
          <!-- Inner Rectangle with rounded corners. -->  
          <Rectangle x:Name="innerRectangle"   
            HorizontalAlignment="Stretch"   
            VerticalAlignment="Stretch" Stroke="Transparent"   
            StrokeThickness="20"   
            Fill="{TemplateBinding Background}"   
            RadiusX="20" RadiusY="20"   />  
  
          <!-- Present Content (text) of the button. -->  
          <DockPanel Name="myContentPresenterDockPanel">  
            <ContentPresenter x:Name="myContentPresenter" Margin="20"   
              Content="{TemplateBinding  Content}"   
              TextBlock.Foreground="Black" />  
          </DockPanel>  
        </Grid>  
      </ControlTemplate>  
    </Setter.Value>  
    ```  
  
     Drücken Sie F5, um die Anwendung auszuführen.  Sie sollte wie folgt aussehen.  
  
     ![](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-4.gif "custom\_button\_AnimatedButton\_4")  
  
3.  **Fügen Sie der Vorlage einen Glaseffekt hinzu:** Als Nächstes fügen Sie das Glas hinzu.  Zuerst erstellen Sie einige Ressourcen, mit denen ein Farbverlaufseffekt für Glas erstellt wird.  Fügen Sie diese Farbverlaufsressourcen an einer Stelle innerhalb des `Application.Resources`\-Blocks hinzu:  
  
    ```  
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
  
     Diese Ressourcen werden als <xref:System.Windows.Shapes.Shape.Fill%2A> für ein Rechteck verwendet, das in das <xref:System.Windows.Controls.Grid> der Schaltflächenvorlage eingefügt wird.  Fügen Sie der Vorlage das folgende hervorgehobene Markup hinzu.  
  
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
    </ControlTemplate>  
    </Setter.Value>  
    ```  
  
     Beachten Sie, dass die <xref:System.Windows.UIElement.Opacity%2A> des Rechtecks mit der `x:Name`\-Eigenschaft "glassCube" 0 \(null\) ist. Wenn Sie das Beispiel ausführen, sehen Sie daher das überlagernde Glasrechteck nicht.  Das liegt daran, dass der Vorlage später Trigger für den Fall hinzugefügt werden, dass der Benutzer mit der Schaltfläche interagiert.  Sie können jedoch sehen, wie die Schaltfläche jetzt dargestellt wird, indem Sie den <xref:System.Windows.UIElement.Opacity%2A>Wert in 1 ändern und die Anwendung ausführen.  Das Ergebnis wird in der folgende Abbildung gezeigt.  Bevor Sie mit dem nächsten Schritt fortfahren, ändern Sie <xref:System.Windows.UIElement.Opacity%2A> wieder in 0 \(null\).  
  
     ![Benutzerdefinierte Schaltflächen, die mit XAML erstellt wurden](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.png "custom\_button\_AnimatedButton\_5")  
  
## Erstellen von Interaktivitätsfunktionen für die Schaltfläche  
 In diesem Abschnitt werden Eigenschaftentrigger und Ereignistrigger erstellt, um als Reaktion auf Benutzeraktionen wie das Bewegen des Mauszeigers über die Schaltfläche und Klicken auf die Schaltfläche Eigenschaftswerte zu ändern und Animationen auszuführen.  
  
 Eine einfache Möglichkeit, Interaktivitätsfunktionen \(Mouseover, Mouseleave, Klick usw.\) hinzuzufügen, ist die Definition von Triggern in der Vorlage oder im Stil.  Um einen <xref:System.Windows.Trigger> zu erstellen, definieren Sie eine "Eigenschaftenbedingung", z. B.: Der <xref:System.Windows.UIElement.IsMouseOver%2A>\-Eigenschaftswert der Schaltfläche entspricht `true`.  Anschließend definieren Sie Setter \(Aktionen\), die eintreten, wenn die Triggerbedingung den Wert True hat.  
  
#### So erstellen Sie Interaktivitätsfunktionen für die Schaltfläche  
  
1.  **Fügen Sie Vorlagentrigger hinzu:** Fügen Sie der Vorlage das hervorgehobene Markup hinzu.  
  
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
  
        <ControlTemplate.Triggers>  
          <!-- Set action triggers for the buttons and define  
               what the button does in response to those triggers. -->  
        </ControlTemplate.Triggers>  
      </ControlTemplate>  
    </Setter.Value>  
    ```  
  
2.  **Fügen Sie Eigenschaftentrigger hinzu:** Fügen Sie dem `ControlTemplate.Triggers`\-Block das hervorgehobene Markup hinzu:  
  
    ```  
    <ControlTemplate.Triggers>  
  
      <!-- Set properties when mouse pointer is over the button. -->  
      <Trigger Property="IsMouseOver" Value="True">  
  
        <!-- Below are three property settings that occur when the   
             condition is met (user mouses over button).  -->  
        <!-- Change the color of the outer rectangle when user   
             mouses over it. -->  
        <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"  
          Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />  
  
        <!-- Sets the glass opacity to 1, therefore, the   
             glass "appears" when user mouses over it. -->  
        <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />  
  
        <!-- Makes the text slightly blurry as though you   
             were looking at it through blurry glass. -->  
        <Setter Property="ContentPresenter.BitmapEffect"   
          TargetName="myContentPresenter">  
          <Setter.Value>  
            <BlurBitmapEffect Radius="1" />  
          </Setter.Value>  
        </Setter>  
      </Trigger>  
  
    <ControlTemplate.Triggers/>  
    ```  
  
     Drücken Sie F5, um die Anwendung auszuführen, und beobachten Sie den Effekt, wenn Sie den Mauszeiger über die Schaltflächen bewegen.  
  
3.  **Fügen Sie einen Fokustrigger hinzu:** Als Nächstes fügen Sie einige ähnliche Setter hinzu, um den Fall zu behandeln, dass die Schaltfläche den Fokus besitzt \(z. B. nachdem der Benutzer auf sie geklickt hat\).  
  
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
      <!-- Set properties when button has focus. -->  
      <Trigger Property="IsFocused" Value="true">  
        <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />  
        <Setter Property="Rectangle.Stroke" TargetName="outerRectangle"  
          Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />  
        <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />  
      </Trigger>  
  
    </ControlTemplate.Triggers>  
    ```  
  
     Drücken Sie F5, um die Anwendung auszuführen, und klicken Sie auf eine der Schaltflächen.  Beachten Sie, dass die Schaltfläche weiterhin hervorgehoben wird, nachdem Sie auf sie geklickt haben, da sie immer noch den Fokus besitzt.  Wenn Sie auf eine andere Schaltfläche klicken, erhält die neue Schaltfläche den Fokus, während die alte den Fokus verliert.  
  
4.  **Fügen Sie Animationen für**  <xref:System.Windows.UIElement.MouseEnter> **und** <xref:System.Windows.UIElement.MouseLeave> **hinzu:** Als Nächstes fügen Sie den Triggern einige Animationen hinzu.  Fügen Sie innerhalb des `ControlTemplate.Triggers`\-Blocks das folgende Markup hinzu.  
  
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
  
     Das Glasrechteck wird verkleinert, wenn der Mauszeiger über die Schaltfläche bewegt wird. Entfernt sich der Mauszeiger, nimmt das Rechteck wieder die ursprüngliche Größe an.  
  
     Es werden zwei Animationen ausgelöst, wenn der Mauszeiger über die Schaltfläche bewegt wird \(das <xref:System.Windows.UIElement.MouseEnter> \-Ereignis wird ausgelöst\).  Diese Animationen verkleinern das Glasrechteck entlang der x\- und y\-Achse.  Beachten Sie die Eigenschaften für die <xref:System.Windows.Media.Animation.DoubleAnimation>\-Elemente \- <xref:System.Windows.Media.Animation.Timeline.Duration%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.  <xref:System.Windows.Media.Animation.Timeline.Duration%2A> gibt an, dass die Animation eine halbe Sekunde lang dauert, und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> gibt an, dass das Glas um 10 Prozent verkleinert wird.  
  
     Der zweite Ereignistrigger \(<xref:System.Windows.UIElement.MouseLeave>\) beendet einfach den ersten Ereignistrigger.  Wenn Sie ein <xref:System.Windows.Media.Animation.Storyboard> beenden, werden alle animierten Eigenschaften auf ihre Standardwerte zurückgesetzt.  Wenn der Benutzer den Mauszeiger von der Schaltfläche weg bewegt, wird daher die Schaltfläche wieder so dargestellt, wie sie war, bevor der Mauszeiger über die Schaltfläche bewegt wurde.  Weitere Informationen zu Animationen finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
5.  **Fügen Sie eine Animation für den Fall hinzu, dass auf die Schaltfläche geklickt wird:** Im letzten Schritt fügen Sie einen Trigger für den Fall hinzu, dass der Benutzer auf die Schaltfläche klickt.  Fügen Sie innerhalb des `ControlTemplate.Triggers`\-Blocks das folgende Markup hinzu:  
  
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
  
     Drücken Sie F5, um die Anwendung auszuführen, und klicken Sie auf eine der Schaltflächen.  Wenn Sie auf eine Schaltfläche klicken, dreht sich das Glasrechteck.  
  
## Zusammenfassung  
 Im Verlauf dieser exemplarischen Vorgehensweise haben Sie folgenden Übungen ausgeführt:  
  
-   Festlegen eines <xref:System.Windows.Style> für einen Objekttyp \(<xref:System.Windows.Controls.Button>\).  
  
-   Steuern grundlegender Eigenschaften der Schaltflächen in der gesamten Anwendung mit dem <xref:System.Windows.Style>.  
  
-   Erstellen von Ressourcen, z. B. Farbverläufe, für Eigenschaftswerte der <xref:System.Windows.Style>\-Setter.  
  
-   Anpassen des Aussehens von Schaltflächen in der gesamten Anwendung durch Anwenden einer Vorlage auf die Schaltflächen.  
  
-   Anpassen des Verhaltens für die Schaltflächen als Reaktion auf Benutzeraktionen \(z. B. <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave> und <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\), wozu auch Animationseffekte zählen.  
  
## Siehe auch  
 [Erstellen einer Schaltfläche mit Microsoft Expression Blend](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)   
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [Übersicht über Bitmapeffekte](../../../../docs/framework/wpf/graphics-multimedia/bitmap-effects-overview.md)