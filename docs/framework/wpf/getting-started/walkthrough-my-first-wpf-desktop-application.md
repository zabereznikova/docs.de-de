---
title: Erstellen Sie Ihre erste WPF-App in Visual Studio 2019-.NET Framework
titleSuffix: ''
description: Entwickeln Sie eine Windows Presentation Foundation (WPF)-Desktop Anwendung, die Elemente enthält, die für die meisten WPF-Anwendungen gemeinsam sind.
ms.date: 09/06/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
ms.topic: tutorial
ms.custom: mvc,vs-dotnet
ms.openlocfilehash: c9af988bcf291325b11df4fd22827b47090c0b48
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853884"
---
# <a name="tutorial-create-your-first-wpf-application-in-visual-studio-2019"></a>Tutorial: Erstellen Ihrer ersten WPF-Anwendung in Visual Studio 2019

In diesem Artikel erfahren Sie, wie Sie eine WPF-Desktop Anwendung (Windows Presentation Foundation) entwickeln, die die Elemente enthält, die den meisten WPF-Anwendungen gemeinsam sind: Extensible Application Markup Language (XAML)-Markup, Code Behind, Anwendungs Definitionen, Steuerelemente, Layout, Datenbindung und Stile. Zum Entwickeln der Anwendung verwenden Sie Visual Studio.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> - Erstellen Sie ein WPF-Projekt.
> - Verwenden Sie XAML, um die Darstellung der Benutzeroberfläche der Anwendung zu entwerfen.
> - Schreiben Sie Code, um das Verhalten der Anwendung zu erstellen.
> - Erstellen Sie eine Anwendungs Definition, um die Anwendung zu verwalten.
> - Fügen Sie Steuerelemente hinzu, und erstellen Sie das Layout zum Verfassen der Anwendungs Benutzeroberfläche.
> - Erstellen Sie Stile für ein konsistentes Erscheinungsbild in der Benutzeroberfläche der Anwendung.
> - Binden Sie die Benutzeroberfläche an Daten, um die Benutzeroberfläche von Daten aufzufüllen und die Daten und die Benutzeroberfläche zu synchronisieren.

Am Ende des Tutorials haben Sie eine eigenständige Windows-Anwendung erstellt, die es Benutzern ermöglicht, Ausgaben Berichte für ausgewählte Personen anzuzeigen. Die Anwendung besteht aus mehreren WPF-Seiten, die in einem Browserfenster gehostet werden.

> [!TIP]
> Der Beispielcode, der in diesem Tutorial verwendet wird, ist sowohl für Visual Basic als auch für c# unter [Tutorial WPF-App-Beispielcode](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp)verfügbar.
>
> Sie können die Codesprache des Beispielcodes zwischen c# und Visual Basic umschalten, indem Sie die Sprachauswahl auf dieser Seite verwenden.

## <a name="prerequisites"></a>Voraussetzungen

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) mit installierter **.net-desktopentwicklungs-** Arbeitsauslastung.

   Weitere Informationen zum Installieren der neuesten Version von Visual Studio finden Sie unter [Installieren von Visual Studio](/visualstudio/install/install-visual-studio).

## <a name="create-the-application-project"></a>Erstellen des Anwendungs Projekts

Der erste Schritt besteht darin, die Anwendungs Infrastruktur zu erstellen, die eine Anwendungs Definition, zwei Seiten und ein Bild enthält.

1. Erstellen Sie ein neues WPF-Anwendungsprojekt in Visual Basic oder Visual c# mit dem Namen **`ExpenseIt`** :

   1. Öffnen Sie Visual Studio, und wählen Sie im Menü " **Get Started** " die Option **Neues Projekt erstellen** aus.

      Das Dialogfeld **Neues Projekt erstellen** wird geöffnet.

   2. Wählen Sie in der Dropdown Liste **Sprache** entweder **c#** oder **Visual Basic**aus.

   3. Wählen Sie die Vorlage **WPF-App (.NET Framework)** aus, und klicken Sie dann auf **weiter**.

      ![Dialogfeld „Neues Projekt erstellen“](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)

      Das Dialogfeld **Neues Projekt konfigurieren** wird geöffnet.

   4. Geben Sie den Projektnamen ein, **`ExpenseIt`** und wählen Sie dann **Erstellen**aus.

      ![Dialogfeld "Neues Projekt konfigurieren"](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      Visual Studio erstellt das Projekt und öffnet den Designer für das Standard Anwendungsfenster namens **MainWindow. XAML**.

2. Öffnen Sie " *Application. XAML* (Visual Basic)" oder " *app. XAML* " (c#).

    Diese XAML-Datei definiert eine WPF-Anwendung und alle Anwendungs Ressourcen. Außerdem verwenden Sie diese Datei, um die Benutzeroberfläche anzugeben, in diesem Fall " *MainWindow. XAML*", die automatisch anzeigt, wann die Anwendung gestartet wird.

    Der XAML-Code sollte in Visual Basic wie folgt aussehen:

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    Und wie im folgenden Beispiel in c#:

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. Öffnen Sie " *MainWindow. XAML*".

    Diese XAML-Datei ist das Hauptfenster der Anwendung und zeigt in Seiten erstellte Inhalte an. Die <xref:System.Windows.Window> -Klasse definiert die Eigenschaften eines Fensters, z. b. Titel, Größe oder Symbol, und behandelt Ereignisse, z. b. das Schließen oder ausblenden.

4. Ändern Sie das- <xref:System.Windows.Window> Element in ein-Element <xref:System.Windows.Navigation.NavigationWindow> , wie im folgenden XAML-Code dargestellt:

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   Diese APP navigiert abhängig von der Benutzereingabe zu einem anderen Inhalt. Aus diesem Grund muss der Hauptgrund <xref:System.Windows.Window> in geändert werden <xref:System.Windows.Navigation.NavigationWindow> . <xref:System.Windows.Navigation.NavigationWindow>erbt alle Eigenschaften von <xref:System.Windows.Window> . Das- <xref:System.Windows.Navigation.NavigationWindow> Element in der XAML-Datei erstellt eine Instanz der- <xref:System.Windows.Navigation.NavigationWindow> Klasse. Weitere Informationen finden Sie unter [Übersicht über die Navigation](../app-development/navigation-overview.md).

5. Entfernen Sie die <xref:System.Windows.Controls.Grid> Elemente zwischen den <xref:System.Windows.Navigation.NavigationWindow> Tags.

6. Ändern Sie die folgenden Eigenschaften im XAML-Code für das- <xref:System.Windows.Navigation.NavigationWindow> Element:

    - Legen Sie die- <xref:System.Windows.Window.Title%2A> Eigenschaft auf " `ExpenseIt` " fest.

    - Legen Sie die- <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaft auf 350 Pixel fest.

    - Legen Sie die- <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft auf 500 Pixel fest.

    Der XAML-Code sollte für Visual Basic wie folgt aussehen:

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    Und wie im folgenden für c#:

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. Öffnen Sie " *MainWindow. XAML. vb* " oder " *MainWindow.XAML.cs*".

    Bei dieser Datei handelt es sich um eine Code Behind-Datei, die Code zum Behandeln der in " *MainWindow. XAML*" deklarierten Ereignisse enthält. Diese Datei enthält eine partielle Klasse für das in XAML definierte Fenster.

8. Wenn Sie c# verwenden, ändern Sie die Klasse so, dass Sie `MainWindow` von abgeleitet wird <xref:System.Windows.Navigation.NavigationWindow> . (In Visual Basic erfolgt dies automatisch, wenn Sie das Fenster in XAML ändern.) Der c#-Code sollte nun wie folgt aussehen:

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a>Hinzufügen von Dateien zur Anwendung

In diesem Abschnitt fügen Sie der Anwendung zwei Seiten und ein Bild hinzu.

1. Fügen Sie dem Projekt eine neue Seite hinzu, und benennen Sie Sie *`ExpenseItHome.xaml`* :

   1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf den **`ExpenseIt`** Projekt Knoten, und wählen Sie Seite **Hinzufügen**aus  >  **Page**.

   1. Im Dialogfeld **Neues Element hinzufügen** ist die **Seite (WPF** -Vorlage) bereits ausgewählt. Geben Sie den Namen ein **`ExpenseItHome`** , und klicken Sie dann auf **Hinzufügen**.

    Diese Seite ist die erste Seite, die angezeigt wird, wenn die Anwendung gestartet wird. Es wird eine Liste der Personen angezeigt, aus denen Sie auswählen können, um einen Spesen Abrechnungs Bericht anzuzeigen.

1. Öffnen Sie *`ExpenseItHome.xaml`* .

1. Legen <xref:System.Windows.Controls.Page.Title%2A> Sie auf " `ExpenseIt - Home` " fest.

1. Legen `DesignHeight` Sie auf 350 Pixel und `DesignWidth` auf 500 Pixel fest.

    Der XAML-Code wird nun wie folgt für Visual Basic angezeigt:

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    Und wie im folgenden für c#:

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. Öffnen Sie " *MainWindow. XAML*".

1. Fügen Sie <xref:System.Windows.Navigation.NavigationWindow.Source%2A> dem-Element eine Eigenschaft hinzu, <xref:System.Windows.Navigation.NavigationWindow> und legen Sie es auf " `ExpenseItHome.xaml` " fest.

    Dadurch *`ExpenseItHome.xaml`* wird die erste Seite festgelegt, die beim Start der Anwendung geöffnet wird.

    Beispiel-XAML in Visual Basic:

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    Und in c#:

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > Sie können auch die Eigenschaft **Quelle** in der Kategorie **Verschiedenes** im Fenster **Eigenschaften** festlegen.
   >
   > ![Quell Eigenschaft in Eigenschaftenfenster](./media/properties-source.png)

1. Fügen Sie dem Projekt eine weitere neue WPF-Seite hinzu, und nennen Sie Sie *ExpenseReportPage. XAML*::

   1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf den **`ExpenseIt`** Projekt Knoten, und wählen Sie Seite **Hinzufügen**aus  >  **Page**.

   1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Vorlage **Page (WPF)** aus. Geben Sie den Namen **ExpenseReportPage**ein, und klicken Sie dann auf **Hinzufügen**.

    Auf dieser Seite wird der Ausgaben Bericht für die Person angezeigt, die auf der **`ExpenseItHome`** Seite ausgewählt ist.

1. Öffnen Sie *ExpenseReportPage. XAML*.

1. Legen <xref:System.Windows.Controls.Page.Title%2A> Sie auf " `ExpenseIt - View Expense` " fest.

1. Legen `DesignHeight` Sie auf 350 Pixel und `DesignWidth` auf 500 Pixel fest.

    *ExpenseReportPage. XAML* sieht nun in Visual Basic wie folgt aus:

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    Und wie im folgenden Beispiel in c#:

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. Öffnen Sie *expenseithome. XAML. vb* und *ExpenseReportPage. XAML. vb*oder *ExpenseItHome.XAML.cs* und *ExpenseReportPage.XAML.cs*.

    Wenn Sie eine neue Auslagerungs Datei erstellen, erstellt Visual Studio automatisch die *zugehörige Code Behind-* Datei. Diese CodeBehind-Dateien behandeln die Logik zum Reagieren auf Benutzereingabe.

    Der Code sollte wie folgt aussehen **`ExpenseItHome`** :

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    Und wie im folgenden für **ExpenseReportPage**:

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. Fügen Sie dem Projekt ein Bild mit dem Namen *watermark.png* hinzu. Sie können ein eigenes Image erstellen, die Datei aus dem Beispielcode kopieren oder aus dem GitHub [-Repository Microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) herunterladen.

    1. Klicken Sie mit der rechten Maustaste auf den Projekt **Add**Knoten, und wählen Sie  >  **Vorhandenes Element**hinzufügen, oder drücken Sie **UMSCHALT** + **alt** + **A**.

    2. Legen Sie im Dialogfeld **Vorhandenes Element hinzufügen** für den Dateifilter entweder **alle Dateien** oder **Bilddateien**fest, navigieren Sie zu der Bilddatei, die Sie verwenden möchten, und wählen Sie dann **Hinzufügen**aus.

## <a name="build-and-run-the-application"></a>Erstellen und Ausführen der Anwendung

1. Zum Erstellen und Ausführen der Anwendung drücken Sie **F5** , oder wählen Sie im Menü **Debuggen** die Option **Debuggen starten**

    Die folgende Abbildung zeigt die Anwendung mit den <xref:System.Windows.Navigation.NavigationWindow> Schaltflächen:

    ![Anwendung, nachdem Sie Sie erstellt und ausgeführt haben.](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. Schließen Sie die Anwendung, um zu Visual Studio zurückzukehren.

## <a name="create-the-layout"></a>Layout erstellen

Layout bietet eine geordnete Methode zum Platzieren von Benutzeroberflächen Elementen und verwaltet auch die Größe und Position dieser Elemente, wenn die Größe einer Benutzeroberfläche geändert wird. In der Regel erstellen Sie Layout mit einem der folgenden Layoutsteuerelemente:

- <xref:System.Windows.Controls.Canvas>-Definiert einen Bereich, in dem Sie untergeordnete Elemente explizit mithilfe von Koordinaten positionieren können, die relativ zum Canvas-Bereich sind.
- <xref:System.Windows.Controls.DockPanel>-Definiert einen Bereich, in dem Sie untergeordnete Elemente entweder horizontal oder vertikal relativ zueinander anordnen können.
- <xref:System.Windows.Controls.Grid>: Definiert einen flexiblen Raster Bereich, der aus Spalten und Zeilen besteht.
- <xref:System.Windows.Controls.StackPanel>Ordnet untergeordnete Elemente in einer einzelnen Zeile an, die horizontal oder vertikal ausgerichtet werden kann.
- <xref:System.Windows.Controls.VirtualizingStackPanel>: Ordnet den Inhalt in einer einzelnen Zeile an, die horizontal oder vertikal ausgerichtet ist, und virtualisiert diesen.
- <xref:System.Windows.Controls.WrapPanel>-Positioniert untergeordnete Elemente in sequenzieller Position von links nach rechts, wobei der Inhalt in die nächste Zeile am Rand des enthaltenden Felds unterteilt wird. Die nachfolgende Reihenfolge erfolgt nacheinander von oben nach unten oder von rechts nach links, abhängig vom Wert der Orientation-Eigenschaft.

Jedes dieser Layoutsteuerelemente unterstützt einen bestimmten Layouttyp für seine untergeordneten Elemente. `ExpenseIt`die Größe der Seiten kann geändert werden, und jede Seite weist Elemente auf, die horizontal und vertikal zusammen mit anderen Elementen angeordnet werden. In diesem Beispiel <xref:System.Windows.Controls.Grid> wird als Layout-Element für die Anwendung verwendet.

> [!TIP]
> Weitere Informationen zu <xref:System.Windows.Controls.Panel> Elementen finden Sie unter [Übersicht über Panels](../controls/panels-overview.md). Weitere Informationen zum Layout finden Sie unter [Layout](../advanced/layout.md).

In diesem Abschnitt erstellen Sie eine einspaltige Tabelle mit drei Zeilen und einem 10-Pixel-Rand, indem Sie der in Spalten-und Zeilen Definitionen hinzufügen <xref:System.Windows.Controls.Grid> *`ExpenseItHome.xaml`* .

1. *`ExpenseItHome.xaml`* Legen Sie in die-Eigenschaft des- <xref:System.Windows.FrameworkElement.Margin%2A> Elements auf <xref:System.Windows.Controls.Grid> "10, 0, 10, 10" fest, was dem linken, oberen, rechten und unteren Rand entspricht:

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > Sie können auch die **Rand** Werte im **Eigenschaften** Fenster unter der Kategorie **Layout** festlegen:
   >
   > ![Margin-Werte in Eigenschaftenfenster](./media/properties-margin.png)

2. Fügen Sie den folgenden XAML-Code zwischen den <xref:System.Windows.Controls.Grid> Tags hinzu, um die Zeilen-und Spaltendefinitionen zu erstellen:

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    Der <xref:System.Windows.Controls.RowDefinition.Height%2A> von zwei Zeilen wird auf festgelegt <xref:System.Windows.GridLength.Auto%2A> , was bedeutet, dass die Zeilen auf Grundlage des Inhalts in den Zeilen skaliert werden. Der Standardwert <xref:System.Windows.Controls.RowDefinition.Height%2A> ist " <xref:System.Windows.GridUnitType.Star> Sizing", was bedeutet, dass die Zeilenhöhe ein gewichteter Anteil des verfügbaren Speicherplatzes ist. Wenn beispielsweise zwei Zeilen <xref:System.Windows.Controls.RowDefinition.Height%2A> den Wert "*" aufweisen, haben Sie jeweils eine Höhe, die der Hälfte des verfügbaren Speicherplatzes entspricht.

    Ihr <xref:System.Windows.Controls.Grid> sollte nun den folgenden XAML-Code enthalten:

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a>Hinzufügen von Steuerelementen

In diesem Abschnitt aktualisieren Sie die Benutzeroberfläche der Startseite, um eine Liste der Personen anzuzeigen, in der Sie eine Person auswählen, um Ihren Abrechnungs Bericht anzuzeigen. Steuerelemente sind Benutzeroberflächenobjekte, die Benutzern die Interaktion mit der Anwendung ermöglichen. Weitere Informationen finden Sie unter Steuer [Elemente](../controls/index.md).

Um diese Benutzeroberfläche zu erstellen, fügen Sie die folgenden Elemente hinzu *`ExpenseItHome.xaml`* :

- A <xref:System.Windows.Controls.ListBox> (für die Liste der Personen).
- Eine <xref:System.Windows.Controls.Label> (für den Listen Header).
- A <xref:System.Windows.Controls.Button> (Klicken Sie auf diese Option, um den Ausgaben Bericht für die in der Liste ausgewählte Person anzuzeigen).

Jedes Steuerelement wird in eine Zeile der eingefügt, <xref:System.Windows.Controls.Grid> indem die <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> angefügte-Eigenschaft festgelegt wird. Weitere Informationen zu angefügten Eigenschaften finden Sie unter [Übersicht über angefügte Eigenschaften](../advanced/attached-properties-overview.md).

1. *`ExpenseItHome.xaml`* Fügen Sie in den folgenden XAML-Code irgendwo zwischen den- <xref:System.Windows.Controls.Grid> Tags hinzu:

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > Sie können die Steuerelemente auch erstellen, indem Sie Sie aus dem Fenster **Toolbox** in das Entwurfs Fenster ziehen und dann ihre Eigenschaften im **Eigenschaften** Fenster festlegen.

2. Erstellen Sie die Anwendung, und führen Sie sie aus.

    Die folgende Abbildung zeigt die Steuerelemente, die Sie erstellt haben:

![ExpenseIt-Beispiel Bildschirm Abbildung mit einer Liste von Namen](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a>Hinzufügen eines Bilds und Titels

In diesem Abschnitt aktualisieren Sie die Benutzeroberfläche der Startseite mit einem Bild und einem Seitentitel.

1. *`ExpenseItHome.xaml`* Fügen Sie in eine weitere Spalte <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> mit einem fester Größe <xref:System.Windows.Controls.ColumnDefinition.Width%2A> von 230 Pixeln hinzu:

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewColumn)]

2. Fügen Sie eine weitere Zeile hinzu <xref:System.Windows.Controls.Grid.RowDefinitions%2A> , für insgesamt vier Zeilen:

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewRows)]

3. Verschieben Sie die Steuerelemente in die zweite Spalte, indem Sie die- <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> Eigenschaft in jedem der drei Steuerelemente (Border, ListBox und Button) auf 1 festlegen.

4. Verschieben Sie jedes Steuerelement um eine Zeile nach unten, indem Sie den <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> Wert für jedes der drei Steuerelemente (Border, ListBox und Button) und für das Border-Element um 1 erhöhen.

   Die XAML-Datei für die drei Steuerelemente sieht nun wie folgt aus:

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. Legen <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> Sie die-Eigenschaft auf die *watermark.png* Bilddatei fest, indem Sie den folgenden XAML-Code zwischen den `<Grid>` Tags und hinzufügen `</Grid>` :

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. Fügen Sie vor dem- <xref:System.Windows.Controls.Border> Element ein-Element <xref:System.Windows.Controls.Label> mit dem Inhalt "Ansichts Ausgaben Bericht" hinzu. Diese Bezeichnung ist der Titel der Seite.

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. Erstellen Sie die Anwendung, und führen Sie sie aus.

Die folgende Abbildung zeigt die Ergebnisse, die Sie soeben hinzugefügt haben:

![ExpenseIt-Beispiel Bildschirm Abbildung des neuen Bild Hintergrunds und Seitentitels](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a>Hinzufügen von Code zum Behandeln von Ereignissen

1. *`ExpenseItHome.xaml`* Fügen Sie in einen- <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignishandler zum- <xref:System.Windows.Controls.Button> Element hinzu. Weitere Informationen finden Sie unter Gewusst [wie: Erstellen eines einfachen Ereignis Handlers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. Öffnen Sie *`ExpenseItHome.xaml.vb`* oder *`ExpenseItHome.xaml.cs`* .

3. Fügen Sie der-Klasse den folgenden Code hinzu `ExpenseItHome` , um einen Schaltflächen-Click-Ereignishandler hinzuzufügen. Der Ereignishandler öffnet die Seite **ExpenseReportPage** .

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a>Erstellen der Benutzeroberfläche für ExpenseReportPage

*ExpenseReportPage. XAML* zeigt den Ausgaben Bericht für die Person an, die auf der **`ExpenseItHome`** Seite ausgewählt ist. In diesem Abschnitt erstellen Sie die Benutzeroberfläche für **ExpenseReportPage**. Außerdem fügen Sie den verschiedenen Benutzeroberflächen Elementen Hintergrund-und Füll Farben hinzu.

1. Öffnen Sie *ExpenseReportPage. XAML*.

2. Fügen Sie den folgenden XAML-Code zwischen den- <xref:System.Windows.Controls.Grid> Tags hinzu:

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    Diese Benutzeroberfläche ähnelt *`ExpenseItHome.xaml`* , mit dem Unterschied, dass die Berichtsdaten in einer angezeigt werden <xref:System.Windows.Controls.DataGrid> .

3. Erstellen Sie die Anwendung, und führen Sie sie aus.

4. Wählen Sie die Schaltfläche **Ansicht** aus.

    Die Spesenabrechnungsseite wird angezeigt. Beachten Sie auch, dass die Navigations Schaltfläche zurück aktiviert ist.

Die folgende Abbildung zeigt die Benutzeroberflächen Elemente, die zu *ExpenseReportPage. XAML*hinzugefügt werden.

![Der ExpenseIt-Beispiel-Screenshot mit der Benutzeroberfläche, die soeben für die ExpenseReportPage erstellt wurde.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a>Stil Steuerelemente

Die Darstellung verschiedener Elemente ist für alle Elemente desselben Typs in einer Benutzeroberfläche häufig identisch. Die Benutzeroberfläche verwendet [Stile](../../../desktop-wpf/fundamentals/styles-templates-overview.md) , um die übergreifende Wiederverwendung über mehrere Elemente hinweg Die Wiederverwendbarkeit von Stilen vereinfacht die Erstellung und Verwaltung von XAML. Dieser Abschnitt ersetzt die Attribute pro Element, die in den vorherigen Schritten mit Stilen definiert wurden.

1. Öffnen Sie " *Application. XAML* " oder " *app. XAML*".

2. Fügen Sie den folgenden XAML-Code zwischen den- <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> Tags hinzu:

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    Durch diese XAML werden folgende Stile hinzugefügt:

    - `headerTextStyle`: Zum Formatieren des Seitentitels für <xref:System.Windows.Controls.Label>.

    - `labelStyle`: Zum Formatieren der <xref:System.Windows.Controls.Label> -Steuerelemente.

    - `columnHeaderStyle`: Zum Formatieren von <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.

    - `listHeaderStyle`: Zum Formatieren der <xref:System.Windows.Controls.Border> -Kopfzeilensteuerelemente.

    - `listHeaderTextStyle`: Zum Formatieren des Listen Headers <xref:System.Windows.Controls.Label> .

    - `buttonStyle`: Zum Formatieren <xref:System.Windows.Controls.Button> von on `ExpenseItHome.xaml` .

    Beachten Sie, dass die Stile Ressourcen und untergeordnete <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> Elemente des Property-Elements sind. An diesem Speicherort werden die Stile auf alle Elemente in einer Anwendung angewendet. Ein Beispiel für die Verwendung von Ressourcen in einer .net-App finden Sie unter [Verwenden von Anwendungs Ressourcen](../advanced/how-to-use-application-resources.md).

3. Ersetzen Sie in *`ExpenseItHome.xaml`* alles zwischen den <xref:System.Windows.Controls.Grid> Elementen durch den folgenden XAML-Code:

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    Eigenschaften wie <xref:System.Windows.VerticalAlignment> und <xref:System.Windows.Media.FontFamily> , die die Darstellung der einzelnen Steuerelemente definieren, werden entfernt und ersetzt, indem die Stile angewendet werden. Beispielsweise `headerTextStyle` wird auf den Bericht "Ausgaben anzeigen" angewendet <xref:System.Windows.Controls.Label> .

4. Öffnen Sie *ExpenseReportPage. XAML*.

5. Ersetzen Sie alles zwischen den <xref:System.Windows.Controls.Grid> Elementen durch den folgenden XAML-Code:

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    Dieses XAML fügt dem <xref:System.Windows.Controls.Label> -Element und dem-Element Stile hinzu <xref:System.Windows.Controls.Border> .

6. Erstellen Sie die Anwendung, und führen Sie sie aus. Die Fenster Darstellung ist das gleiche wie zuvor.

    ![Der ExpenseIt-Beispiel Bildschirm mit derselben Darstellung wie im letzten Abschnitt.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. Schließen Sie die Anwendung, um zu Visual Studio zurückzukehren.

## <a name="bind-data-to-a-control"></a>Binden von Daten an ein Steuerelement

In diesem Abschnitt erstellen Sie die XML-Daten, die an verschiedene Steuerelemente gebunden sind.

1. *`ExpenseItHome.xaml`* Fügen Sie in nach dem öffnenden- <xref:System.Windows.Controls.Grid> Element den folgenden XAML-Code hinzu, um ein-Element zu erstellen <xref:System.Windows.Data.XmlDataProvider> , das die Daten für jede Person enthält:

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    Die Daten werden als Ressource erstellt <xref:System.Windows.Controls.Grid> . Normalerweise werden diese Daten als Datei geladen, aber aus Gründen der Einfachheit werden die Daten Inline hinzugefügt.

2. `<Grid.Resources>`Fügen Sie im-Element das folgende- `<xref:System.Windows.DataTemplate>` Element hinzu, das definiert, wie die Daten in <xref:System.Windows.Controls.ListBox> nach dem-Element angezeigt werden sollen `<XmlDataProvider>` :

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    Weitere Informationen zu Datenvorlagen finden Sie unter [Übersicht über Daten](../data/data-templating-overview.md)Vorlagen.

3. Ersetzen Sie die vorhandene <xref:System.Windows.Controls.ListBox> durch den folgenden XAML-Code:

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    Dieses XAML bindet die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> -Eigenschaft von <xref:System.Windows.Controls.ListBox> an die Datenquelle und wendet die Daten Vorlage als an <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> .

## <a name="connect-data-to-controls"></a>Verbinden von Daten mit Steuerelementen

Als Nächstes fügen Sie Code hinzu, um den auf der Seite ausgewählten Namen abzurufen **`ExpenseItHome`** und an den Konstruktor von **ExpenseReportPage**zu übergeben. **ExpenseReportPage** legt seinen Datenkontext mit dem bestandenen Element fest. Dies ist das, an das die Steuerelemente, die in *ExpenseReportPage. XAML* definiert sind, an gebunden werden.

1. Öffnen Sie *ExpenseReportPage.xaml.vb* oder *ExpenseReportPage.xaml.cs*.

2. Fügen Sie einen Konstruktor hinzu, der ein Objekt akzeptiert, damit Sie die Spesenabrechnungsdaten der ausgewählten Person übergeben können.

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. Öffnen Sie *`ExpenseItHome.xaml.vb`* oder *`ExpenseItHome.xaml.cs`* .

4. Ändern <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Sie den Ereignishandler, um den neuen Konstruktor aufzurufen, der die Spesen Abrechnungsdaten der ausgewählten Person übergibt.

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a>Formatieren von Daten mit Datenvorlagen

In diesem Abschnitt aktualisieren Sie die Benutzeroberfläche für jedes Element in den Daten gebundenen Listen mithilfe von Datenvorlagen.

1. Öffnen Sie *ExpenseReportPage. XAML*.

2. Binden Sie den Inhalt der Elemente "Name" und "Department" <xref:System.Windows.Controls.Label> an die entsprechende Datenquellen Eigenschaft. Weitere Informationen zur Datenbindung finden Sie unter [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md).

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. Fügen Sie nach dem öffnenden <xref:System.Windows.Controls.Grid> Element die folgenden Datenvorlagen hinzu, die definieren, wie die Spesen Abrechnungsdaten angezeigt werden sollen:

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. Ersetzen <xref:System.Windows.Controls.DataGridTextColumn> Sie die Elemente durch <xref:System.Windows.Controls.DataGridTemplateColumn> unter dem <xref:System.Windows.Controls.DataGrid> -Element, und wenden Sie die Vorlagen auf diese an.

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. Erstellen Sie die Anwendung, und führen Sie sie aus.

6. Wählen Sie eine Person aus, und wählen Sie dann die Schaltfläche **Ansicht** .

Die folgende Abbildung zeigt die beiden Seiten der `ExpenseIt` Anwendung mit den angewendeten Steuerelementen, Layout, Stilen, Datenbindung und Datenvorlagen:

![Beide Seiten der APP zeigen die Liste der Namen und einen Spesen Bericht an.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> Dieses Beispiel veranschaulicht eine bestimmte Funktion von WPF und folgt nicht allen bewährten Methoden für Dinge wie Sicherheit, Lokalisierung und Barrierefreiheit. Eine umfassende Abdeckung von WPF und bewährten Methoden für die Entwicklung von .net-apps finden Sie in den folgenden Themen:
>
> - [Bedienungshilfen](../../ui-automation/accessibility-best-practices.md)
> - [Security](../security-wpf.md)
> - [Übersicht über WPF-Globalisierung und -Lokalisierung](../advanced/wpf-globalization-and-localization-overview.md)
> - [WPF-Leistung](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a>Nächste Schritte

In dieser exemplarischen Vorgehensweise haben Sie eine Reihe von Techniken zum Erstellen einer Benutzeroberfläche mithilfe von Windows Presentation Foundation (WPF) kennengelernt. Sie sollten jetzt grundlegende Kenntnisse der Bausteine einer Daten gebundenen .net-APP haben. Weitere Informationen über die WPF-Architektur und -Programmiermodelle finden Sie in den folgenden Themen:

- [WPF-Architektur](../advanced/wpf-architecture.md)
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Übersicht über Abhängigkeitseigenschaften](../advanced/dependency-properties-overview.md)
- [Layout](../advanced/layout.md)

Weitere Informationen zum Erstellen von Anwendungen finden Sie in den folgenden Themen:

- [Anwendungsentwicklung](../app-development/index.md)
- [Steuerelemente](../controls/index.md)
- [Übersicht über Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Grafiken und Multimedia](../graphics-multimedia/index.md)
- [Dokumente in WPF](../advanced/documents-in-wpf.md)

## <a name="see-also"></a>Siehe auch

- [Übersicht über Panels](../controls/panels-overview.md)
- [Übersicht über Datenvorlagen](../data/data-templating-overview.md)
- [Erstellen einer WPF-Anwendung](../app-development/building-a-wpf-application-wpf.md)
- [Stile und Vorlagen](../controls/styles-and-templates.md)
