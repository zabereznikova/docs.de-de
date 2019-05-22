---
title: Erstellen einer WPF-Anwendung in Visual Studio
ms.date: 03/20/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
author: mairaw
ms.author: mairaw
ms.custom: vs-dotnet
ms.openlocfilehash: c3440ddf6cdae6b24bcf1059ab2c76d8fb957263
ms.sourcegitcommit: 11deacc8ec9f229ab8ee3cd537515d4c2826515f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2019
ms.locfileid: "66003854"
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a>Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung

In diesem Artikel erfahren Sie, wie Sie eine Windows Presentation Foundation (WPF) desktop-Anwendung entwickeln, die die Elemente enthält, die für die meisten WPF-Anwendungen gelten: Extensible Application Markup Language (XAML) Markup, CodeBehind, Anwendungsdefinitionen, Steuerelemente, Layout, Datenbindung und Stile. Um die Anwendung zu entwickeln, verwenden Sie Visual Studio. 

Diese exemplarische Vorgehensweise umfasst die folgenden Schritte aus:

- Verwenden Sie XAML zum Entwerfen der Darstellung der Benutzeroberfläche (UI) der Anwendung.

- Schreiben Sie Code, um das Verhalten der Anwendung zu erstellen.

- Erstellen Sie eine Anwendungsdefinition, um die Anwendung zu verwalten.

- Fügen Sie Steuerelemente hinzu, und erstellen Sie das Layout der Benutzeroberfläche die Anwendung zu erstellen.

- Stile für ein konsistentes Erscheinungsbild in der Benutzeroberfläche der Anwendung zu erstellen.

- Binden Sie die Benutzeroberfläche mit Daten füllen Sie die Benutzeroberfläche von Daten und die Daten und die Benutzeroberfläche, die synchronisiert zu halten.

Am Ende dieser exemplarischen Vorgehensweise werden Sie eine eigenständigen Windows-Anwendung erstellt haben, die Benutzer spesenabrechnungen für bestimmte Personen anzeigen können. Die Anwendung besteht aus der WPF-Seiten, die in einem Fenster im Browserstil gehostet werden.

> [!TIP]
> Der Beispielcode, der verwendet wird, in dieser exemplarischen Vorgehensweise ist für Visual Basic verfügbar und C# am [Exemplarische Vorgehensweise WPF-App-Beispielcodes](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).
>
> Sie können die Codesprache des Beispielcodes zwischen umschalten C# und Visual Basic mithilfe der **\< />** Dropdownliste oben rechts auf der in diesem Artikel.

## <a name="prerequisites"></a>Vorraussetzungen

- Visual Studio 2017 oder höher (in diesem Artikel wird Visual Studio-2019 verwendet)

   Weitere Informationen zum Installieren der neuesten Version von Visual Studio finden Sie unter [Installieren von Visual Studio](/visualstudio/install/install-visual-studio).

## <a name="create-the-application-project"></a>Erstellen des Anwendungsprojekts

Der erste Schritt ist die Erstellung von Infrastruktur der Anwendung, die eine Anwendungsdefinition, zwei Seiten und ein Bild enthält.

1. Erstellen Sie ein neues WPF-Anwendungsprojekt in Visual Basic oder Visual c# mit dem Namen **`ExpenseIt`**:

   1. Öffnen Sie Visual Studio, und wählen Sie **Erstellen eines neuen Projekts** unter der **Einstieg** Menü.

      Die **Erstellen eines neuen Projekts** Dialogfeld wird geöffnet.

   2. In der **Sprache** Dropdownliste, wählen Sie entweder **C#** oder **Visual Basic**.
      
   3. Wählen Sie die **WPF-App ((.NET Framework)** Vorlage, und wählen Sie dann **Weiter**. 
     
      ![Erstellen Sie ein Dialogfeld "Neues Projekt"](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)
    
      Die **konfigurieren Sie das neue Projekt** Dialogfeld wird geöffnet.

   4. Geben Sie den Namen des Projekts **`ExpenseIt`** und wählen Sie dann **erstellen**.

      ![Konfigurieren Sie ein Dialogfeld "Neues Projekt"](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      Visual Studio erstellt das Projekt und öffnet den Designer für das standardanwendungsfenster namens **"MainWindow.xaml"**.

2. Open *"Application.xaml"* (Visual Basic) oder *"App.xaml"* (c#).

    Diese XAML-Datei definiert eine WPF-Anwendung und alle Anwendungsressourcen. Sie verwenden diese Datei auch in diesem Fall an der Benutzeroberfläche *"MainWindow.xaml"*, das automatisch wird angezeigt, wenn die Anwendung gestartet wird.

    Ihre XAML sollte in Visual Basic wie folgt aussehen:

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    Und wie der folgende in C#:

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. Open *"MainWindow.xaml"*.

    Dieser XAML-Datei ist das Hauptfenster der Anwendung und zeigt erstellten Inhalt auf Seiten. Die <xref:System.Windows.Window> Klasse definiert die Eigenschaften eines Fensters wie Titel, Größe oder Symbol, und behandelt Ereignisse wie schließen oder ausblenden.

4. Ändern der <xref:System.Windows.Window> Element eine <xref:System.Windows.Navigation.NavigationWindow>, wie in den folgenden XAML dargestellt:

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   Diese app navigiert zu anderem Inhalt, abhängig von der Benutzereingabe. Deshalb ist die Main <xref:System.Windows.Window> muss geändert werden, um eine <xref:System.Windows.Navigation.NavigationWindow>. <xref:System.Windows.Navigation.NavigationWindow> erbt alle Eigenschaften des <xref:System.Windows.Window>. Die <xref:System.Windows.Navigation.NavigationWindow> Element in der XAML-Datei erstellt eine Instanz der <xref:System.Windows.Navigation.NavigationWindow> Klasse. Weitere Informationen finden Sie unter [Übersicht über die Navigation](../app-development/navigation-overview.md).

5. Entfernen Sie die <xref:System.Windows.Controls.Grid> Elemente zwischen den <xref:System.Windows.Navigation.NavigationWindow> Tags.

6. Ändern Sie die folgenden Eigenschaften in der XAML-Code für die <xref:System.Windows.Navigation.NavigationWindow> Element:

    - Legen Sie die <xref:System.Windows.Window.Title%2A> Eigenschaft "`ExpenseIt`".

    - Legen Sie die <xref:System.Windows.FrameworkElement.Height%2A> -Eigenschaft auf 350 Pixel.

    - Legen Sie die <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft auf 500 Pixel.

    Ihre XAML sieht wie folgt für Visual Basic:

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    Und wie folgt für C#:

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. Open *"MainWindow.Xaml.vb"* oder *"MainWindow.Xaml.cs"*.

    Diese Datei ist eine Code-Behind-Datei Code zum Behandeln der Ereignisse, die im deklarierten mit *"MainWindow.xaml"*. Diese Datei enthält eine partielle Klasse für das in XAML definierte Fenster.

8. Bei Verwendung von C#, ändern Sie die `MainWindow` Klasse abgeleitet <xref:System.Windows.Navigation.NavigationWindow>. (In Visual Basic geschieht dies automatisch, wenn Sie das Fenster in XAML ändern.) Ihre C# Code sollte jetzt wie folgt aussehen:

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a>Hinzufügen von Dateien zur Anwendung

In diesem Abschnitt fügen Sie der Anwendung zwei Seiten und ein Bild hinzu.

1. Fügen Sie dem Projekt eine neue Seite, und nennen Sie sie *`ExpenseItHome.xaml`*:

   1. In **Projektmappen-Explorer**, mit der rechten Maustaste auf die **`ExpenseIt`** Projektknoten und wählen **hinzufügen** > **Seite**.

   1. In der **neues Element hinzufügen** im Dialogfeld die **Seite (WPF)** Vorlage bereits ausgewählt ist. Geben Sie den Namen **`ExpenseItHome`**, und wählen Sie dann **hinzufügen**.

    Diese Seite ist die erste Seite, die angezeigt wird, wenn die Anwendung gestartet wird. Es zeigt eine Liste der Personen an, wählen aus, um eine Spesenabrechnung anzuzeigen.

1. Open *`ExpenseItHome.xaml`*.

1. Legen Sie die <xref:System.Windows.Controls.Page.Title%2A> auf "`ExpenseIt - Home`".

1. Legen Sie die `DesignHeight` und `DesignWidth` Elementwerte auf 300 Pixel.

    Die XAML sieht nun folgendermaßen für Visual Basic:

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    Und wie folgt für C#:

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. Open *"MainWindow.xaml"*.

1. Hinzufügen einer <xref:System.Windows.Navigation.NavigationWindow.Source%2A> Eigenschaft, um die <xref:System.Windows.Navigation.NavigationWindow> Element, und legen Sie sie auf "`ExpenseItHome.xaml`".

    Hiermit *`ExpenseItHome.xaml`* werden von der ersten Seite geöffnet werden soll, wenn die Anwendung gestartet wird. 

    Beispiel für XAML in Visual Basic:

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    Und in C#:

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > Sie können auch Festlegen der **Quelle** -Eigenschaft in der **Sonstiges** Kategorie der **Eigenschaften** Fenster.
   >
   > ![Source-Eigenschaft im Fenster "Eigenschaften"](./media/properties-source.png)

1. Hinzufügen einer anderen neuen WPF-Seite auf das Projekt, und nennen Sie sie *"ExpenseReportPage.xaml"*::

   1. In **Projektmappen-Explorer**, mit der rechten Maustaste auf die **`ExpenseIt`** Projektknoten und wählen **hinzufügen** > **Seite**.

   1. In der **neues Element hinzufügen** wählen Sie im Dialogfeld die **Seite (WPF)** Vorlage. Geben Sie den Namen **ExpenseReportPage**, und wählen Sie dann **hinzufügen**.

    Auf dieser Seite zeigt die Spesenabrechnung für die Person, die für ausgewählt, wird die **`ExpenseItHome`** Seite.

1. Öffnen Sie *ExpenseReportPage.xaml*.

1. Legen Sie die <xref:System.Windows.Controls.Page.Title%2A> auf "`ExpenseIt - View Expense`".

1. Legen Sie die `DesignHeight` und `DesignWidth` Elementwerte auf 300 Pixel.

    *"ExpenseReportPage.xaml"* jetzt sieht wie in Visual Basic die folgenden:

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    Und wie der folgende in C#:

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. Open *"ExpenseItHome.Xaml.vb"* und *ExpenseReportPage.xaml.vb*, oder *"ExpenseItHome.Xaml.cs"* und *"ExpenseReportPage.Xaml.cs"*.

    Wenn Sie eine neue Seitendatei erstellen, erstellt Visual Studio automatisch die *CodeBehind* Datei. Diese CodeBehind-Dateien behandeln die Logik zum Reagieren auf Benutzereingabe.

    Der Code sollte aussehen wie folgt für **`ExpenseItHome`**:

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    Und wie folgt für **ExpenseReportPage**:

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. Fügen Sie ein Bild mit dem Namen *watermark.png* zum Projekt. Sie können Ihr eigenes Image erstellen, kopieren Sie die Datei aus dem Beispielcode oder erhalten sie [hier](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).

    1. Mit der rechten Maustaste auf den Projektknoten, und wählen Sie **hinzufügen** > **vorhandenes Element**, oder drücken Sie **UMSCHALT**+**Alt** + **Ein**.

    2. In der **vorhandenes Element hinzufügen** Dialogfeld legen Sie den Dateifilter entweder **alle Dateien** oder **Bilddateien**, navigieren Sie zu dem Image-Datei, die Sie verwenden möchten, und wählen Sie dann **hinzufügen** .

## <a name="build-and-run-the-application"></a>Erstellen eines Builds und Ausführen der Anwendung

1. Zum Erstellen und die Anwendung auszuführen, drücken Sie die **F5** oder wählen Sie **Debuggen starten** aus der **Debuggen** Menü.

    Die folgende Abbildung zeigt die Anwendung mit der <xref:System.Windows.Navigation.NavigationWindow> Schaltflächen:

    ![Die Anwendung nach dem Erstellen und ausführen.](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. Schließen Sie die Anwendung zu Visual Studio zurückzukehren.

## <a name="create-the-layout"></a>Erstellen Sie das layout

Layout bietet die Möglichkeit, Elemente der Benutzeroberfläche zu platzieren und verwaltet auch die Größe und Position dieser Elemente beim Ändern der Größe einer Benutzeroberflächenautomatisierungs. In der Regel erstellen Sie Layout mit einem der folgenden Layoutsteuerelemente:

- <xref:System.Windows.Controls.Canvas> : Definiert einen Bereich, in dem Sie explizit untergeordnete Elemente positionieren können mithilfe von Koordinaten, die relativ zur Canvas sind.
- <xref:System.Windows.Controls.DockPanel> : Definiert einen Bereich, in dem Sie untergeordnete Elemente entweder horizontal oder vertikal relativ zueinander anordnen können.
- <xref:System.Windows.Controls.Grid> : Definiert einen flexiblen Rasterbereich, der aus Spalten und Zeilen besteht.
- <xref:System.Windows.Controls.StackPanel> : Ordnet untergeordnete Elemente in einer einzelnen Zeile, die horizontal oder vertikal ausgerichtet werden kann.
- <xref:System.Windows.Controls.VirtualizingStackPanel> -Ordnet die und virtualisiert Inhalt in einer einzelnen Zeile, die horizontal oder vertikal ausgerichtet ist.
- <xref:System.Windows.Controls.WrapPanel> -Positionen untergeordnete Elemente nacheinander von links nach rechts und umbricht den Inhalt in die nächste Zeile am Rand des enthaltenden Felds. Die nachfolgende Sortierung erfolgt sequenziell von oben nach unten oder von rechts nach links, abhängig vom Wert der Orientation-Eigenschaft.

Jedes dieser Layoutsteuerelemente unterstützt einen bestimmten Typ von Layout für die untergeordneten Elemente. `ExpenseIt` Seiten geändert werden können, und jede Seite verfügt über Elemente, die horizontal und vertikal neben anderen Elementen angeordnet sind. In diesem Beispiel die <xref:System.Windows.Controls.Grid> als Layoutelement für die Anwendung verwendet wird.

> [!TIP]
> Weitere Informationen zu <xref:System.Windows.Controls.Panel> Elemente finden Sie unter [Übersicht über Panel](../controls/panels-overview.md). Weitere Informationen zum Layout finden Sie unter [Layout](../advanced/layout.md).

In diesem Abschnitt erstellen Sie eine einspaltige Tabelle mit drei Zeilen und einen 10-Pixel-Rand durch Hinzufügen von Spalten- und Zeilendefinitionen zu den <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.

1. In *`ExpenseItHome.xaml`* legen die <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft für die <xref:System.Windows.Controls.Grid> Element auf "10,0,10,10", auf der linken, oberen, rechten und unteren Ränder entspricht:

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > Sie können auch Festlegen der **Rand** Werte in der **Eigenschaften** Fenster unter dem **Layout** Kategorie:
   >
   > ![Randwerte in Fenster "Eigenschaften"](./media/properties-margin.png)

2. Fügen Sie das folgende XAML zwischen den <xref:System.Windows.Controls.Grid> Tags aus, um die Zeilen- und Spaltendefinitionen zu erstellen:

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    Die <xref:System.Windows.Controls.RowDefinition.Height%2A> zwei Zeilen wird festgelegt <xref:System.Windows.GridLength.Auto%2A>, was bedeutet, dass die Größe der Zeilen basierend auf dem Inhalt in den Zeilen. Der Standardwert <xref:System.Windows.Controls.RowDefinition.Height%2A> ist <xref:System.Windows.GridUnitType.Star> größenanpassung, was bedeutet, dass die Zeilenhöhe eine gewichtete Proportion des verfügbaren Platzes ist. Wenn z. B. zwei Zeilen jeweils eine <xref:System.Windows.Controls.RowDefinition.Height%2A> von "*", sie verfügen jeweils über eine Höhe von der Hälfte des verfügbaren Platzes ist.

    Ihre <xref:System.Windows.Controls.Grid> sollte nun dem folgenden XAML enthalten:

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a>Hinzufügen von Steuerelementen

In diesem Abschnitt Aktualisieren Sie die Homepage Benutzeroberfläche, um eine Liste der Personen, anzuzeigen, wählen Sie, in dem eine Person, die die Spesenabrechnung angezeigt. Steuerelemente sind Benutzeroberflächenobjekte, die Benutzern die Interaktion mit der Anwendung ermöglichen. Weitere Informationen finden Sie unter [Steuerelemente](../controls/index.md).

Um diese Benutzeroberfläche zu erstellen, fügen Sie die folgenden Elemente zu *`ExpenseItHome.xaml`*:

- Ein <xref:System.Windows.Controls.ListBox> (für die Liste der Personen).
- Ein <xref:System.Windows.Controls.Label> (für den Listenheader).
- Ein <xref:System.Windows.Controls.Button> (zum klicken, um die Spesenabrechnung für die Person anzuzeigen, die in der Liste ausgewählt ist).

Jedes Steuerelement wird in einer Zeile platziert die <xref:System.Windows.Controls.Grid> durch Festlegen der <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> angefügte Eigenschaft. Weitere Informationen zu angefügten Eigenschaften finden Sie unter [Übersicht über angefügte Eigenschaften](../advanced/attached-properties-overview.md).

1. In *`ExpenseItHome.xaml`*, fügen Sie den folgenden XAML an einer beliebigen Stelle zwischen den <xref:System.Windows.Controls.Grid> Tags:

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > Sie können die Steuerelemente auch erstellen, ziehen sie aus der **Toolbox** Fenster in das Entwurfsfenster, und klicken Sie dann ihre Einstellungen der **Eigenschaften** Fenster.

2. Erstellen Sie die Anwendung, und führen Sie sie aus.

    Die folgende Abbildung zeigt die Steuerelemente, die Sie erstellt haben:

![Bildschirmabbildung für ExpenseIt-beispielscreenshot zeigt eine Liste von Namen](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a>Fügen Sie ein Image und einen Titel hinzu

In diesem Abschnitt Aktualisieren Sie die Benutzeroberfläche der Homepage mit einem Bild und einem Seitentitel.

1. In *`ExpenseItHome.xaml`*, fügen Sie eine andere Spalte als die <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> mit einer festen <xref:System.Windows.Controls.ColumnDefinition.Width%2A> von 230 Pixel:

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=52-55)]

2. Hinzufügen zu einer anderen Zeile der <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, also insgesamt vier Zeilen:

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=57-62)]

3. Verschieben Sie die Steuerelemente in die zweite Spalte, durch Festlegen der <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> -Eigenschaft auf 1 in jedem der drei Steuerelemente (Rahmen, ListBox und Schaltfläche ").

4. Verschieben Sie jedes Steuerelement eine Zeile nach unten durch Erhöhen der <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> Wert 1 für jedes der drei Steuerelemente (Rahmen, ListBox und Schaltfläche ") und Border-Elements.

   Der XAML für die drei Steuerelemente sieht nun folgendermaßen aus:

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. Legen Sie die <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> Eigenschaft, um die *watermark.png* Image-Datei, indem Sie den folgenden XAML an einer beliebigen Stelle zwischen Hinzufügen der `<Grid>` und `</Grid>` Tags:

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. Vor der <xref:System.Windows.Controls.Border> -Element, Hinzufügen einer <xref:System.Windows.Controls.Label> mit dem Inhalt "View Expense Report". Diese Bezeichnung wird der Titel der Seite.

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. Erstellen Sie die Anwendung, und führen Sie sie aus.

Die folgende Abbildung zeigt die Ergebnisse von was Sie gerade hinzugefügt haben:

![Bildschirmabbildung für ExpenseIt-beispielscreenshot zeigt die neue Image Hintergrund und den Seitentitel](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a>Fügen Sie Code zum Verarbeiten von Ereignissen

1. In *`ExpenseItHome.xaml`*, Hinzufügen einer <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler der <xref:System.Windows.Controls.Button> Element. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines einfachen ereignishandlers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. Open *`ExpenseItHome.xaml.vb`* oder *`ExpenseItHome.xaml.cs`*.

3. Fügen Sie den folgenden Code der `ExpenseItHome` Klasse, um eine Schaltfläche hinzufügen-click-Ereignishandler. Der Ereignishandler öffnet die **ExpenseReportPage** Seite.

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a>Erstellen der Benutzeroberfläche für ExpenseReportPage

*"ExpenseReportPage.xaml"* zeigt die Spesenabrechnung für die Person, die für ausgewählt, wird die **`ExpenseItHome`** Seite. In diesem Abschnitt erstellen Sie die Benutzeroberfläche für **ExpenseReportPage**. Außerdem fügen Hintergrund und Füllfarben zwischen den verschiedenen UI-Elementen.

1. Öffnen Sie *ExpenseReportPage.xaml*.

2. Fügen Sie das folgende XAML zwischen den <xref:System.Windows.Controls.Grid> Tags:

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    Diese Benutzeroberfläche ähnelt *`ExpenseItHome.xaml`*, außer dass die Daten des Berichts, in angezeigt werden einem <xref:System.Windows.Controls.DataGrid>.

3. Erstellen Sie die Anwendung, und führen Sie sie aus.

4. Wählen Sie die **Ansicht** Schaltfläche.

    Die Spesenabrechnungsseite wird angezeigt. Beachten Sie außerdem, dass die Navigationsschaltfläche "zurück" aktiviert ist.

Die folgende Abbildung zeigt die Elemente der Benutzeroberfläche hinzugefügt *"ExpenseReportPage.xaml"*.

![Bildschirmabbildung für ExpenseIt-Beispiel-Screenshot Anzeigen der Benutzeroberfläche, die gerade erstellt haben, für die ExpenseReportPage.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a>Formatieren von Steuerelementen

Die Darstellung verschiedener Elemente ist häufig für alle Elemente des gleichen Typs in einer Benutzeroberfläche identisch. Benutzeroberfläche verwendet [Stile](../controls/styling-and-templating.md) Darstellungen in mehreren Elementen wieder verwendbaren vornehmen. Die wiederverwendbarkeit von Stilen können Sie die um XAML-Erstellung und Verwaltung zu vereinfachen. Dieser Abschnitt ersetzt die Attribute pro Element, die in den vorherigen Schritten mit Stilen definiert wurden.

1. Open *"Application.xaml"* oder *"App.xaml"*.

2. Fügen Sie das folgende XAML zwischen den <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> Tags:

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    Durch diese XAML werden folgende Stile hinzugefügt:

    - `headerTextStyle`: Zum Formatieren des Seitentitels <xref:System.Windows.Controls.Label>.

    - `labelStyle`: Zum Formatieren der <xref:System.Windows.Controls.Label> Steuerelemente.

    - `columnHeaderStyle`: Zum Formatieren der <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.

    - `listHeaderStyle`: Zum Formatieren der Kopfzeile <xref:System.Windows.Controls.Border> Steuerelemente.

    - `listHeaderTextStyle`: Zum Formatieren der Kopfzeile <xref:System.Windows.Controls.Label>.

    - `buttonStyle`: Zum Formatieren der <xref:System.Windows.Controls.Button> auf `ExpenseItHome.xaml`.

    Beachten Sie, dass die Ressourcen und die untergeordneten Elemente werden der <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> Property-Element. An diesem Speicherort werden die Stile auf alle Elemente in einer Anwendung angewendet. Ein Beispiel für die Verwendung von Ressourcen in einer .NET-App, finden Sie unter [Verwenden von Anwendungsressourcen](../advanced/how-to-use-application-resources.md).

3. In *`ExpenseItHome.xaml`*, ersetzen Sie alles zwischen dem <xref:System.Windows.Controls.Grid> Elemente mit den folgenden XAML:

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    Eigenschaften wie <xref:System.Windows.VerticalAlignment> und <xref:System.Windows.Media.FontFamily> , die die Darstellung der einzelnen Steuerelemente definieren, werden entfernt und ersetzt, indem die Stile angewendet werden. Z. B. die `headerTextStyle` gilt für die "View Expense Report" <xref:System.Windows.Controls.Label>.

4. Öffnen Sie *ExpenseReportPage.xaml*.

5. Ersetzen Sie alles zwischen dem <xref:System.Windows.Controls.Grid> Elemente mit den folgenden XAML:

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    Dieses XAML Stile hinzugefügt. die <xref:System.Windows.Controls.Label> und <xref:System.Windows.Controls.Border> Elemente.

6. Erstellen Sie die Anwendung, und führen Sie sie aus. Die Darstellung des Fensters ist der gleiche wie zuvor.

    ![Bildschirmabbildung für ExpenseIt-Beispiel-Screenshot mit die gleiche Darstellung wie im letzten Abschnitt.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. Schließen Sie die Anwendung zu Visual Studio zurückzukehren.

## <a name="bind-data-to-a-control"></a>Binden von Daten an ein Steuerelement

In diesem Abschnitt erstellen Sie die XML-Daten, die an verschiedene Steuerelemente gebunden ist.

1. In *`ExpenseItHome.xaml`*, nach dem öffnenden <xref:System.Windows.Controls.Grid> -Element, fügen Sie den folgenden XAML zum Erstellen einer <xref:System.Windows.Data.XmlDataProvider> , die Daten für jede Person enthält:

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    Die Daten werden als erstellt eine <xref:System.Windows.Controls.Grid> Ressource. Normalerweise würde diese Daten als Datei geladen, aber die Daten werden aus Gründen der Einfachheit Inline hinzugefügt.

2. In der `<Grid.Resources>` -Element, fügen Sie die folgenden `<xref:System.Windows.DataTemplate>` -Element, das definiert, wie Sie die Anzeige der Daten in die <xref:System.Windows.Controls.ListBox>, nachdem die `<XmlDataProvider>` Element:

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    Weitere Informationen zu Datenvorlagen finden Sie unter [Übersicht über Datenvorlagen](../data/data-templating-overview.md).

3. Ersetzen Sie die vorhandene <xref:System.Windows.Controls.ListBox> mit den folgenden XAML:

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    Dieses XAML bindet die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaft der <xref:System.Windows.Controls.ListBox> an die Datenquelle und wendet die Datenvorlage als die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.

## <a name="connect-data-to-controls"></a>Verbinden Sie Daten an Steuerelemente

Anschließend fügen Sie Code zum Abrufen des Namens, der ausgewählt wird die **`ExpenseItHome`** Seite, und übergeben Sie es an den Konstruktor der **ExpenseReportPage**. **ExpenseReportPage** legt den Datenkontext mithilfe des übergebenen Elements, die die Steuerelemente definierten in *"ExpenseReportPage.xaml"* Binden an.

1. Öffnen Sie *ExpenseReportPage.xaml.vb* oder *ExpenseReportPage.xaml.cs*.

2. Fügen Sie einen Konstruktor hinzu, der ein Objekt akzeptiert, damit Sie die Spesenabrechnungsdaten der ausgewählten Person übergeben können.

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. Open *`ExpenseItHome.xaml.vb`* oder *`ExpenseItHome.xaml.cs`*.

4. Ändern der <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler aufrufen, den neuen Konstruktor, der die Spesenabrechnungsdaten der ausgewählten Person übergeben.

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a>Style-Daten mit Datenvorlagen

In diesem Abschnitt Aktualisieren Sie die Benutzeroberfläche für jedes Element in den datengebundenen Listen mithilfe von Datenvorlagen.

1. Öffnen Sie *ExpenseReportPage.xaml*.

2. Binden Sie den Inhalt der "Name" und "Department" <xref:System.Windows.Controls.Label> Elemente an die entsprechende Datenquelleneigenschaft. Weitere Informationen zur Datenbindung finden Sie unter [Übersicht über die Datenbindung](../data/data-binding-overview.md).

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. Nach dem öffnenden <xref:System.Windows.Controls.Grid> -Element, fügen Sie die folgenden Datenvorlagen, die definieren, wie die Spesenabrechnungsdaten angezeigt werden:

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. Ersetzen Sie die <xref:System.Windows.Controls.DataGridTextColumn> Elemente mit <xref:System.Windows.Controls.DataGridTemplateColumn> unter der <xref:System.Windows.Controls.DataGrid> Element und die Vorlagen auf sie angewendet.

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. Erstellen Sie die Anwendung, und führen Sie sie aus.

6. Wählen Sie eine Person ein, und wählen Sie dann die **Ansicht** Schaltfläche.

Die folgende Abbildung zeigt die beiden Seiten von der `ExpenseIt` Anwendung mit Steuerelementen, Layout, Stilen, Datenbindung und Datenvorlagen angewendet:

![Beide Seiten der app die Liste der Namen und eine Spesenabrechnung angezeigt.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> In diesem Beispiel wird veranschaulicht, eine bestimmte Funktion von WPF und nicht alle bewährte Methoden für Aspekte wie Sicherheit, Lokalisierung und Eingabehilfen. Von WPF und die bewährten Methoden für .NET-app-Entwicklung und umfassend behandelt finden Sie unter den folgenden Themen:
>
> - [Barrierefreiheit](../../ui-automation/accessibility-best-practices.md)
>
> - [Sicherheit](../security-wpf.md)
>
> - [Übersicht über WPF-Globalisierung und -Lokalisierung](../advanced/wpf-globalization-and-localization-overview.md)
>
> - [Von WPF](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a>Nächste Schritte

In dieser exemplarischen Vorgehensweise haben Sie gelernt, eine Reihe von Techniken zum Erstellen einer Benutzeroberfläche mit Windows Presentation Foundation (WPF). Sie verfügen nun über einen grundlegenden Überblick über die Bausteine einer datengebundenen .NET-App. Weitere Informationen über die WPF-Architektur und -Programmiermodelle finden Sie in den folgenden Themen:

- [WPF-Architektur](../advanced/wpf-architecture.md)
- [Übersicht über XAML (WPF)](../advanced/xaml-overview-wpf.md)
- [Übersicht über Abhängigkeitseigenschaften](../advanced/dependency-properties-overview.md)
- [Layout](../advanced/layout.md)

Weitere Informationen zum Erstellen von Anwendungen finden Sie in den folgenden Themen:

- [Anwendungsentwicklung](../app-development/index.md)
- [Steuerelemente](../controls/index.md)
- [Übersicht über Datenbindung](../data/data-binding-overview.md)
- [Grafiken und multimedia](../graphics-multimedia/index.md)
- [Dokumente in WPF](../advanced/documents-in-wpf.md)

## <a name="see-also"></a>Siehe auch

- [Übersicht über Panel](../controls/panels-overview.md)
- [Übersicht über Datenvorlagen](../data/data-templating-overview.md)
- [Erstellen einer WPF-Anwendung](../app-development/building-a-wpf-application-wpf.md)
- [Stile und-Vorlagen](../controls/styles-and-templates.md)
