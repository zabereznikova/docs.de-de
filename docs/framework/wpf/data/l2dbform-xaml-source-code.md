---
title: L2DBForm.xaml-Quellcode
ms.date: 10/22/2019
ms.topic: sample
ms.openlocfilehash: 290b00e136f0c49e1b27d4fa1bca7321eebe936e
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921227"
---
# <a name="l2dbformxaml-source-code"></a><span data-ttu-id="8bedb-102">L2DBForm.xaml-Quellcode</span><span class="sxs-lookup"><span data-stu-id="8bedb-102">L2DBForm.xaml source code</span></span>

<span data-ttu-id="8bedb-103">Diese Seite enthält und beschreibt die XAML-Quelldatei für die [WPF-Datenbindung mithilfe LINQ to XML Beispiels](linq-to-xml-data-binding-sample.md).</span><span class="sxs-lookup"><span data-stu-id="8bedb-103">This page contains and describes the XAML source file for the [WPF data binding using LINQ to XML example](linq-to-xml-data-binding-sample.md).</span></span>

## <a name="overall-ui-structure"></a><span data-ttu-id="8bedb-104">Allgemeine Struktur der Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="8bedb-104">Overall UI structure</span></span>

<span data-ttu-id="8bedb-105">Wie bei einem WPF-Projekt üblich, enthält diese Datei ein übergeordnetes Element, ein <xref:System.Windows.Window> XML-Element, das mit der abgeleiteten Klasse `L2XDBFrom` im `LinqToXmlDataBinding` Namespace verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="8bedb-105">As is typical for a WPF project, this file contains one parent element, a <xref:System.Windows.Window> XML element that's associated with the derived class `L2XDBFrom` in the `LinqToXmlDataBinding` namespace.</span></span>

<span data-ttu-id="8bedb-106">Der Client Bereich ist in einer <xref:System.Windows.Controls.StackPanel> enthalten, die einen hellen blauen Hintergrund erhält.</span><span class="sxs-lookup"><span data-stu-id="8bedb-106">The client area is contained within a <xref:System.Windows.Controls.StackPanel> that's given a light blue background.</span></span> <span data-ttu-id="8bedb-107">Dieses Steuerelement enthält vier <xref:System.Windows.Controls.DockPanel> -Benutzeroberflächenabschnitte, die durch <xref:System.Windows.Controls.Separator> -Balken voneinander getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="8bedb-107">This panel contains four <xref:System.Windows.Controls.DockPanel> UI sections separated by <xref:System.Windows.Controls.Separator> bars.</span></span> <span data-ttu-id="8bedb-108">Der Zweck dieser Abschnitte wird [hier](linq-to-xml-data-binding-sample.md#overview)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8bedb-108">The purpose of these sections is described [here](linq-to-xml-data-binding-sample.md#overview).</span></span>

<span data-ttu-id="8bedb-109">Jeder Abschnitt enthält eine Bezeichnung, mit dem er identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="8bedb-109">Each section contains a label that identifies it.</span></span> <span data-ttu-id="8bedb-110">In den ersten beiden Abschnitten wird diese Bezeichnung durch die Verwendung eines <xref:System.Windows.FrameworkElement.LayoutTransform%2A>-Elements um 90° gedreht.</span><span class="sxs-lookup"><span data-stu-id="8bedb-110">In the first two sections, this label is rotated 90 degrees through the use of a <xref:System.Windows.FrameworkElement.LayoutTransform%2A>.</span></span> <span data-ttu-id="8bedb-111">Der Rest des Abschnitts enthält Benutzeroberflächen Elemente, die für den Zweck dieses Abschnitts geeignet sind, z. b. Textblöcke, Textfelder und Schaltflächen.</span><span class="sxs-lookup"><span data-stu-id="8bedb-111">The rest of the section contains UI elements appropriate to the purpose of that section, for example, text blocks, text boxes, and buttons.</span></span> <span data-ttu-id="8bedb-112">Mitunter wird zur Ausrichtung dieser untergeordneten Steuerelemente ein untergeordnetes <xref:System.Windows.Controls.StackPanel> -Steuerelement verwendet.</span><span class="sxs-lookup"><span data-stu-id="8bedb-112">Sometimes a child <xref:System.Windows.Controls.StackPanel> is used to align these child controls.</span></span>

## <a name="window-resource-section"></a><span data-ttu-id="8bedb-113">Abschnitt „Window.Resources“</span><span class="sxs-lookup"><span data-stu-id="8bedb-113">Window resource section</span></span>

<span data-ttu-id="8bedb-114">Das `<Window.Resources>` -Starttag in Zeile 9 gibt den Anfang des Abschnitts &lt;legacyBold&gt;Window.Resources&lt;/legacyBold&gt; an.</span><span class="sxs-lookup"><span data-stu-id="8bedb-114">The opening `<Window.Resources>` tag on line 9 indicates the start of the window resource section.</span></span> <span data-ttu-id="8bedb-115">Der Abschnitt endet mit dem Endtag in Zeile 35.</span><span class="sxs-lookup"><span data-stu-id="8bedb-115">It ends with the closing tag on line 35.</span></span>

<span data-ttu-id="8bedb-116">Das `<ObjectDataProvider>` -Tag, das sich über die Zeilen 11 bis 25 erstreckt, deklariert einen <xref:System.Windows.Data.ObjectDataProvider>mit dem Namen `LoadedBooks`, der als Quelle ein <xref:System.Xml.Linq.XElement> verwendet.</span><span class="sxs-lookup"><span data-stu-id="8bedb-116">The `<ObjectDataProvider>` tag, which spans lines 11 through 25, declares a <xref:System.Windows.Data.ObjectDataProvider>, named `LoadedBooks`, that uses an <xref:System.Xml.Linq.XElement> as the source.</span></span> <span data-ttu-id="8bedb-117">Dieses <xref:System.Xml.Linq.XElement>-Element wird initialisiert, indem ein eingebettetes XML-Dokument (ein `CDATA`-Element) analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="8bedb-117">The <xref:System.Xml.Linq.XElement> is initialized by parsing an embedded XML document (a `CDATA` element).</span></span> <span data-ttu-id="8bedb-118">Beachten Sie, dass Leerraum beim Deklarieren des eingebetteten XML-Dokuments und auch beim Analysieren beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="8bedb-118">Notice that white space is preserved when declaring the embedded XML document and also when it's parsed.</span></span> <span data-ttu-id="8bedb-119">Dies ist der Fall, weil das <xref:System.Windows.Controls.TextBlock>-Steuerelement, das zum Anzeigen des unformatierten XML-Codes verwendet wird, keine speziellen XML-Formatierungsfunktionen besitzt.</span><span class="sxs-lookup"><span data-stu-id="8bedb-119">White space is preserved because the <xref:System.Windows.Controls.TextBlock> control, which is used to display the raw XML, has no special XML formatting capabilities.</span></span>

<span data-ttu-id="8bedb-120">Schließlich wird in den Zeilen 28 bis 34 eine <xref:System.Windows.DataTemplate> mit dem Namen `BookTemplate` definiert.</span><span class="sxs-lookup"><span data-stu-id="8bedb-120">Lastly, a <xref:System.Windows.DataTemplate> named `BookTemplate` is defined on lines 28 through 34.</span></span> <span data-ttu-id="8bedb-121">Diese Vorlage wird zum Anzeigen der Einträge im Abschnitt **Buchliste** der Benutzeroberfläche verwendet.</span><span class="sxs-lookup"><span data-stu-id="8bedb-121">This template is used to display the entries in the **Book List** UI section.</span></span> <span data-ttu-id="8bedb-122">Sie verwendet die Datenbindung und dynamische LINQ to XML-Eigenschaften, um über die folgenden Zuweisungen die Buch-ID und den Buchnamen abzurufen:</span><span class="sxs-lookup"><span data-stu-id="8bedb-122">It uses data binding and LINQ to XML dynamic properties to retrieve the book ID and book name through the following assignments:</span></span>

```xaml
Text="{Binding Path=Attribute[id].Value}"Text="{Binding Path=Value}"
```

## <a name="data-binding-code"></a><span data-ttu-id="8bedb-123">Code für die Datenbindung</span><span class="sxs-lookup"><span data-stu-id="8bedb-123">Data binding code</span></span>

<span data-ttu-id="8bedb-124">Zusätzlich zum <xref:System.Windows.DataTemplate> -Element wird die Datenbindung auch an einer Reihe anderer Stellen in der Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="8bedb-124">In addition to the <xref:System.Windows.DataTemplate> element, data binding is used in a number of other places in this file.</span></span>

<span data-ttu-id="8bedb-125">Im `<StackPanel>` -Starttag in Zeile 38 wird die <xref:System.Windows.FrameworkElement.DataContext%2A> -Eigenschaft dieses Elements auf den `LoadedBooks` -Datenanbieter gesetzt.</span><span class="sxs-lookup"><span data-stu-id="8bedb-125">In the opening `<StackPanel>` tag on line 38, the <xref:System.Windows.FrameworkElement.DataContext%2A> property of this panel is set to the `LoadedBooks` data provider.</span></span>

```xaml
DataContext="{Binding Source={StaticResource LoadedBooks}}
```

<span data-ttu-id="8bedb-126">Damit ist das <xref:System.Windows.Controls.TextBlock>-Element mit dem Namen `tbRawXml` (in Zeile 46) in der Lage, durch Bindung dieser Daten an die `Xml`-Eigenschaft des Datenanbieters das unformatierte XML anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="8bedb-126">Setting the data context makes it possible (on line 46) for the <xref:System.Windows.Controls.TextBlock> named `tbRawXml` to display the raw XML by binding to this data provider's `Xml` property:</span></span>

```xaml
Text="{Binding Path=Xml}"
```

<span data-ttu-id="8bedb-127">Das <xref:System.Windows.Controls.ListBox> -Steuerelement in den Zeilen 58 bis 62 im Abschnitt **Book List** der Benutzeroberfläche legt als Vorlage für ihre Anzeigeelemente die im &lt;legacyBold&gt;Window.Resources&lt;/legacyBold&gt;-Abschnitt definierte `BookTemplate` -Vorlage fest:</span><span class="sxs-lookup"><span data-stu-id="8bedb-127">The <xref:System.Windows.Controls.ListBox> in the **Book List** UI section, on lines 58 through 62, sets the template for its display items to the `BookTemplate` defined in the window resource section:</span></span>

```xaml
ItemTemplate ="{StaticResource BookTemplate}"
```

<span data-ttu-id="8bedb-128">Anschließend werden die tatsächlichen Werte der Bücher in den Zeilen 59 bis 62 an dieses Listenfeld gebunden:</span><span class="sxs-lookup"><span data-stu-id="8bedb-128">Then, on lines 59 through 62, the actual values of the books are bound to this list box:</span></span>

```xaml
<ListBox.ItemsSource>
    <Binding Path="Elements[{http://www.mybooks.com}book]"/>
</ListBox.ItemsSource>
```

<span data-ttu-id="8bedb-129">Der dritte Abschnitt der Benutzeroberfläche, **Edit Selected Book**, bindet zuerst das <xref:System.Windows.FrameworkElement.DataContext%2A> -Element des übergeordneten <xref:System.Windows.Controls.StackPanel> -Steuerelements an den aktuell ausgewählten Eintrag im Abschnitt **Book List** der Benutzeroberfläche (Zeile 82):</span><span class="sxs-lookup"><span data-stu-id="8bedb-129">The third UI section, **Edit Selected Book**, first binds the <xref:System.Windows.FrameworkElement.DataContext%2A> of the parent <xref:System.Windows.Controls.StackPanel> to the currently selected item in from the **Book List** UI section (line 82):</span></span>

```xaml
DataContext="{Binding ElementName=lbBooks, Path=SelectedItem}"
```

<span data-ttu-id="8bedb-130">Anschließend verwendet der Abschnitt die bidirektionale Datenbindung, sodass die aktuellen Werte der Buchelemente in den beiden Textfeldern in diesem Abschnitt angezeigt und entsprechend aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="8bedb-130">It then uses two-way data binding, so that the current values of the book elements are displayed to, and updated from, the two text boxes in this panel.</span></span> <span data-ttu-id="8bedb-131">Die Datenbindung an dynamische Eigenschaften ähnelt der Datenbindung, die in der `BookTemplate`-Datenvorlage verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="8bedb-131">Data binding to dynamic properties is similar to the data binding used in the `BookTemplate` data template:</span></span>

```xaml
Text="{Binding Path=Attribute[id].Value}"...Text="{Binding Path=Value}"
```

<span data-ttu-id="8bedb-132">Im XAML-Code des letzten Benutzeroberflächenabschnitts (**Add New Book** (Neues Buch hinzufügen)) wird keine Datenbindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="8bedb-132">The last UI section, **Add New Book**, doesn't use data binding in its XAML code.</span></span> <span data-ttu-id="8bedb-133">Stattdessen wird die Datenbindung im Ereignisbehandlungscode in der *L2DBForm.xaml.cs*-Datei durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="8bedb-133">Instead, data binding is in its event handling code in the file *L2DBForm.xaml.cs*.</span></span>

## <a name="example"></a><span data-ttu-id="8bedb-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8bedb-134">Example</span></span>

### <a name="description"></a><span data-ttu-id="8bedb-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8bedb-135">Description</span></span>

> [!NOTE]
> <span data-ttu-id="8bedb-136">Wir empfehlen, den folgenden Code in einen Code-Editor, z. B. den C#-Quellcode-Editor in Visual Studio, zu kopieren, weil dort die Zeilennummern einfacher zu verfolgen sind.</span><span class="sxs-lookup"><span data-stu-id="8bedb-136">We recommend that you copy the following code below into a code editor, such as the C# source code editor in Visual Studio, so that line numbers will be easier to track.</span></span>

### <a name="code"></a><span data-ttu-id="8bedb-137">Code</span><span class="sxs-lookup"><span data-stu-id="8bedb-137">Code</span></span>

```xml
<Window x:Class="LinqToXmlDataBinding.L2XDBForm"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:system="clr-namespace:System;assembly=mscorlib"
    xmlns:xlinq="clr-namespace:System.Xml.Linq;assembly=System.Xml.Linq"
    xmlns:local="clr-namespace:LinqToXmlDataBinding"
    Title="WPF Data Binding using LINQ-to-XML" Height="665" Width="500" ResizeMode="NoResize">

    <Window.Resources>
        <!-- Books provider and inline data -->
        <ObjectDataProvider x:Key="LoadedBooks" ObjectType="{x:Type xlinq:XElement}" MethodName="Parse">
            <ObjectDataProvider.MethodParameters>
                <system:String xml:space="preserve">
<![CDATA[
<books xmlns="http://www.mybooks.com">
  <book id="0">book zero</book>
  <book id="1">book one</book>
  <book id="2">book two</book>
  <book id="3">book three</book>
</books>
]]>
                </system:String>
                <xlinq:LoadOptions>PreserveWhitespace</xlinq:LoadOptions>
            </ObjectDataProvider.MethodParameters>
        </ObjectDataProvider>

        <!-- Template for use in Books List listbox. -->
        <DataTemplate x:Key="BookTemplate">
            <StackPanel Orientation="Horizontal">
                <TextBlock Margin="3" Text="{Binding Path=Attribute[id].Value}"/>
                <TextBlock Margin="3" Text="-"/>
                <TextBlock Margin="3" Text="{Binding Path=Value}"/>
            </StackPanel>
        </DataTemplate>
    </Window.Resources>

    <!-- Main visual content container -->
    <StackPanel Background="lightblue" DataContext="{Binding Source={StaticResource LoadedBooks}}">
        <!-- Raw XML display section -->
        <DockPanel Margin="5">
            <Label  Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" FontWeight="Bold">XML
            <Label.LayoutTransform>
                <RotateTransform Angle="90"/>
            </Label.LayoutTransform>
            </Label>
            <TextBlock Name="tbRawXml" Height="200" Background="LightGray" Text="{Binding Path=Xml}" TextTrimming="CharacterEllipsis" />
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- List box to display all books section -->
        <DockPanel Margin="5">
            <Label  Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" FontWeight="Bold">Book List
                <Label.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </Label.LayoutTransform>
            </Label>
            <ListBox Name="lbBooks" Height="200" Width="415" ItemTemplate ="{StaticResource BookTemplate}">
                <ListBox.ItemsSource>
                    <Binding Path="Elements[{http://www.mybooks.com}book]"/>
                </ListBox.ItemsSource>
            </ListBox>
            <Button Margin="5" DockPanel.Dock="Right" Height="30" Width ="130" Content="Remove Selected Book" Click="OnRemoveBook">
            <Button.LayoutTransform>
                <RotateTransform Angle="90"/>
            </Button.LayoutTransform>
            </Button>
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- Edit current selection section -->
        <DockPanel Margin="5">
            <TextBlock Margin="5" Height="30" Width="65" DockPanel.Dock="Right" Background="LightGray" TextWrapping="Wrap" TextAlignment="Center">
                    Changes are live!
                <TextBlock.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </TextBlock.LayoutTransform>
            </TextBlock>
            <StackPanel>
                <Label Width="450" Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Left" FontWeight="Bold">Edit Selected Book</Label>
                <StackPanel Margin="1" DataContext="{Binding ElementName=lbBooks, Path=SelectedItem}">
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">ID:</Label>
                        <TextBox Name="editAttributeTextBox" Width="410" Text="{Binding Path=Attribute[id].Value}">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Edit the selected book ID and see it changed.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">Value:</Label>
                        <TextBox Name="editValueTextBox" Width="410" Text="{Binding Path=Value}" Height="25">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Edit the selected book Value and see it changed.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                </StackPanel>
            </StackPanel>
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- Add new book section -->
        <DockPanel Margin="5">
            <Button Margin="5" Height="30" DockPanel.Dock="Right" Click ="OnAddBook">Add Book
                <Button.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </Button.LayoutTransform>
            </Button>
            <StackPanel>
                <Label Width="450" Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Left" FontWeight="Bold">Add New Book</Label>
                <StackPanel Margin="1">
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">ID:</Label>
                        <TextBox Name="tbAddID" Width="410">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Enter a book ID and Value pair, then click Add Book.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">Value:</Label>
                        <TextBox Name="tbAddValue" Width="410" Height="25">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="UltraBold" TextAlignment="Center">
                                    <Label>Enter a book ID and Value pair, then click Add Book.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                </StackPanel>
            </StackPanel>
        </DockPanel>
    </StackPanel>
</Window>
```

### <a name="comments"></a><span data-ttu-id="8bedb-138">Kommentare</span><span class="sxs-lookup"><span data-stu-id="8bedb-138">Comments</span></span>

<span data-ttu-id="8bedb-139">Den C#-Quellcode für die den WPF-Benutzeroberflächenelementen zugeordneten Ereignishandler finden Sie unter [L2DBForm.xaml.cs-Quellcode](l2dbform-xaml-cs-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="8bedb-139">For the C# source code for the event handlers associated with the WPF UI elements, see [L2DBForm.xaml.cs source code](l2dbform-xaml-cs-source-code.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8bedb-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8bedb-140">See also</span></span>

- [<span data-ttu-id="8bedb-141">Exemplarische Vorgehensweise: LinqToXmlDataBinding-Beispiel</span><span class="sxs-lookup"><span data-stu-id="8bedb-141">Walkthrough: LinqToXmlDataBinding example</span></span>](linq-to-xml-data-binding-sample.md)
- [<span data-ttu-id="8bedb-142">L2DBForm.xaml.cs-Quellcode</span><span class="sxs-lookup"><span data-stu-id="8bedb-142">L2DBForm.xaml.cs source code</span></span>](l2dbform-xaml-cs-source-code.md)
