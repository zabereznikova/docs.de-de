---
title: Erstellen Ihrer ersten WPF-App in Visual Studio 2019 - .NET Framework
titleSuffix: ''
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
ms.openlocfilehash: facb9ebebd9ce1904886a946277185ac2c2e4bc4
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463926"
---
# <a name="tutorial-create-your-first-wpf-application-in-visual-studio-2019"></a>Tutorial: Erstellen Der ersten WPF-Anwendung in Visual Studio 2019

In diesem Artikel erfahren Sie, wie Sie eine Windows Presentation Foundation (WPF)-Desktopanwendung entwickeln, die die Elemente enthält, die den meisten WPF-Anwendungen gemeinsam sind: XAML-Markup (Extensible Application Markup Language), CodeBehind, Anwendungsdefinitionen, Steuerelemente, Layout, Datenbindung und Stile. Zum Entwickeln der Anwendung verwenden Sie Visual Studio.

In diesem Tutorial lernen Sie Folgendes:
> [!div class="checklist"]
>
> - Erstellen Sie ein WPF-Projekt.
> - Verwenden Sie XAML, um die Darstellung der Benutzeroberfläche der Anwendung zu entwerfen.
> - Schreiben Sie Code, um das Verhalten der Anwendung zu erstellen.
> - Erstellen Sie eine Anwendungsdefinition, um die Anwendung zu verwalten.
> - Fügen Sie Steuerelemente hinzu, und erstellen Sie das Layout, um die Anwendungsbenutzeroberfläche zu erstellen.
> - Erstellen Sie Stile für eine konsistente Darstellung in der gesamten Benutzeroberfläche der Anwendung.
> - Binden Sie die Benutzeroberfläche an Daten, um die Benutzeroberfläche aus Daten aufzufüllen und die Daten und die Benutzeroberfläche zu synchronisieren.

Am Ende des Tutorials haben Sie eine eigenständige Windows-Anwendung erstellt, mit der Benutzer Spesenabrechnungen für ausgewählte Personen anzeigen können. Die Anwendung besteht aus mehreren WPF-Seiten, die in einem Browserfenster gehostet werden.

> [!TIP]
> Der In diesem Tutorial verwendete Beispielcode ist sowohl für Visual Basic als auch für C-Code unter [Tutorial WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp)verfügbar.
>
> Sie können die Codesprache des Beispielcodes zwischen C- und Visual Basic umschalten, indem Sie die Sprachauswahl oben auf dieser Seite verwenden.

## <a name="prerequisites"></a>Voraussetzungen

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) mit der **installierten .NET Desktopentwicklungsworkload.**

   Weitere Informationen zum Installieren der neuesten Version von Visual Studio finden Sie unter Installieren von [Visual Studio](/visualstudio/install/install-visual-studio).

## <a name="create-the-application-project"></a>Erstellen des Anwendungsprojekts

Der erste Schritt besteht darin, die Anwendungsinfrastruktur zu erstellen, die eine Anwendungsdefinition, zwei Seiten und ein Bild enthält.

1. Erstellen Sie ein neues WPF-Anwendungsprojekt in **`ExpenseIt`** Visual Basic oder Visual C mit dem Namen :

   1. Öffnen Sie Visual Studio, und wählen Sie Unter dem Menü **Erste** Schritte **ein neues Projekt** erstellen aus.

      Das Dialogfeld **Neues Projekt** erstellen wird geöffnet.

   2. Wählen Sie in der Dropdown-Liste **Sprache** entweder **"C"** oder **"Visual Basic"** aus.

   3. Wählen Sie die **Vorlage WPF App (.NET Framework)** und dann **Weiter**aus.

      ![Dialogfeld „Neues Projekt erstellen“](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)

      Das Dialogfeld **Konfigurieren des neuen Projekts** wird geöffnet.

   4. Geben Sie **`ExpenseIt`** den Projektnamen ein, und wählen Sie dann **Erstellen**aus.

      ![Konfigurieren eines neuen Projektdialogs](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      Visual Studio erstellt das Projekt und öffnet den Designer für das Standardanwendungsfenster mit dem Namen **MainWindow.xaml**.

2. Öffnen Sie *Application.xaml* (Visual Basic) oder *App.xaml* (C-Wert).

    Diese XAML-Datei definiert eine WPF-Anwendung und alle Anwendungsressourcen. Sie verwenden diese Datei auch, um die Benutzeroberfläche anzugeben, in diesem Fall *MainWindow.xaml*, die automatisch anzeigt, wann die Anwendung gestartet wird.

    Ihr XAML sollte in Visual Basic wie folgt aussehen:

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    Und wie folgt in C':

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. Öffnen *MainWindow.xaml*.

    Diese XAML-Datei ist das Hauptfenster Ihrer Anwendung und zeigt Inhalte an, die auf Seiten erstellt wurden. Die <xref:System.Windows.Window> Klasse definiert die Eigenschaften eines Fensters, z. B. Titel, Größe oder Symbol, und behandelt Ereignisse, z. B. schließen oder ausblenden.

4. Ändern <xref:System.Windows.Window> Sie das <xref:System.Windows.Navigation.NavigationWindow>Element in ein , wie in der folgenden XAML gezeigt:

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   Diese App navigiert zu unterschiedlichen Inhalten, abhängig von der Benutzereingabe. Aus diesem Grund <xref:System.Windows.Window> muss die Hauptsache in eine <xref:System.Windows.Navigation.NavigationWindow>geändert werden. <xref:System.Windows.Navigation.NavigationWindow>erbt alle Eigenschaften <xref:System.Windows.Window>von . Das <xref:System.Windows.Navigation.NavigationWindow> Element in der XAML-Datei <xref:System.Windows.Navigation.NavigationWindow> erstellt eine Instanz der Klasse. Weitere Informationen finden Sie unter [Navigationsübersicht](../app-development/navigation-overview.md).

5. Entfernen <xref:System.Windows.Controls.Grid> Sie die <xref:System.Windows.Navigation.NavigationWindow> Elemente zwischen den Tags.

6. Ändern Sie die folgenden Eigenschaften im <xref:System.Windows.Navigation.NavigationWindow> XAML-Code für das Element:

    - Legen <xref:System.Windows.Window.Title%2A> Sie die`ExpenseIt`Eigenschaft auf " fest.

    - Legen <xref:System.Windows.FrameworkElement.Height%2A> Sie die Eigenschaft auf 350 Pixel fest.

    - Legen <xref:System.Windows.FrameworkElement.Width%2A> Sie die Eigenschaft auf 500 Pixel fest.

    Ihr XAML sollte für Visual Basic wie folgt aussehen:

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    Und wie folgt für C':

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. Öffnen Sie *MainWindow.xaml.vb* oder *MainWindow.xaml.cs*.

    Diese Datei ist eine CodeBehind-Datei, die Code enthält, um die in *MainWindow.xaml*deklarierten Ereignisse zu behandeln. Diese Datei enthält eine partielle Klasse für das in XAML definierte Fenster.

8. Wenn Sie C- verwenden, `MainWindow` ändern Sie die <xref:System.Windows.Navigation.NavigationWindow>Klasse, um von abzuleiten. (In Visual Basic geschieht dies automatisch, wenn Sie das Fenster in XAML ändern.) Ihr C-Code sollte nun wie folgt aussehen:

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a>Hinzufügen von Dateien zur Anwendung

In diesem Abschnitt fügen Sie der Anwendung zwei Seiten und ein Bild hinzu.

1. Fügen Sie dem Projekt eine neue *`ExpenseItHome.xaml`* Seite hinzu, und benennen Sie es:

   1. Klicken Sie im **Projektmappen-Explorer** **`ExpenseIt`** mit der rechten Maustaste auf den Projektknoten, und wählen Sie Seite **hinzufügen** > **Page**aus.

   1. Im Dialogfeld **Neues Element hinzufügen** ist die Vorlage Seite **(WPF)** bereits ausgewählt. Geben Sie **`ExpenseItHome`** den Namen ein, und wählen Sie dann **Hinzufügen**aus.

    Diese Seite ist die erste Seite, die beim Starten der Anwendung angezeigt wird. Es wird eine Liste der Personen angezeigt, aus denen eine Spesenabrechnung ausgewählt werden soll.

1. Öffnen *`ExpenseItHome.xaml`*.

1. Stellen <xref:System.Windows.Controls.Page.Title%2A> Sie`ExpenseIt - Home`die Einstellung auf " ein.

1. Legen `DesignHeight` Sie die auf 350 Pixel und die `DesignWidth` auf 500 Pixel fest.

    Das XAML wird nun wie folgt für Visual Basic angezeigt:

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    Und wie folgt für C':

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. Öffnen *MainWindow.xaml*.

1. Fügen <xref:System.Windows.Navigation.NavigationWindow.Source%2A> Sie dem <xref:System.Windows.Navigation.NavigationWindow> Element eine Eigenschaft`ExpenseItHome.xaml`hinzu, und legen Sie sie auf " fest.

    Dies *`ExpenseItHome.xaml`* wird als die erste Seite festgelegt, die beim Starten der Anwendung geöffnet wird.

    Beispiel XAML in Visual Basic:

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    Und in C':

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > Sie können die **Source-Eigenschaft** auch in der Kategorie **Verschiedenes** des **Fensters Eigenschaften** festlegen.
   >
   > ![Quelleigenschaft im Fenster Eigenschaften](./media/properties-source.png)

1. Fügen Sie dem Projekt eine weitere neue WPF-Seite hinzu, und nennen Sie es *ExpenseReportPage.xaml*::

   1. Klicken Sie im **Projektmappen-Explorer** **`ExpenseIt`** mit der rechten Maustaste auf den Projektknoten, und wählen Sie Seite **hinzufügen** > **Page**aus.

   1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Vorlage Seite **(WPF)** aus. Geben Sie den Namen **ExpenseReportPage**ein, und wählen Sie dann **Hinzufügen**aus.

    Auf dieser Seite wird die Spesenabrechnung **`ExpenseItHome`** für die auf der Seite ausgewählte Person angezeigt.

1. Öffnen Sie *ExpenseReportPage.xaml*.

1. Stellen <xref:System.Windows.Controls.Page.Title%2A> Sie`ExpenseIt - View Expense`die Einstellung auf " ein.

1. Legen `DesignHeight` Sie die auf 350 Pixel und die `DesignWidth` auf 500 Pixel fest.

    *ExpenseReportPage.xaml* sieht jetzt wie folgt in Visual Basic aus:

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    Und wie folgt in C':

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. Öffnen Sie *ExpenseItHome.xaml.vb* und *ExpenseReportPage.xaml.vb*oder *ExpenseItHome.xaml.cs* und *ExpenseReportPage.xaml.cs*.

    Wenn Sie eine neue Seitendatei erstellen, erstellt Visual Studio automatisch die *CodeBehind-Datei.* Diese CodeBehind-Dateien behandeln die Logik zum Reagieren auf Benutzereingabe.

    Ihr Code sollte wie **`ExpenseItHome`** folgt aussehen für:

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    Und wie die folgenden für **ExpenseReportPage**:

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. Fügen Sie dem Projekt ein Bild mit dem Namen *watermark.png* hinzu. Sie können Ein eigenes Image erstellen, die Datei aus dem Beispielcode kopieren oder aus dem [Microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) GitHub-Repository abrufen.

    1. Klicken Sie mit der rechten Maustaste auf den Projektknoten, und wählen Sie**Vorhandenes Element** **hinzufügen** > aus , oder drücken Sie **Umschalttaste**+**Alt**+**A**.

    2. Legen Sie im Dialogfeld **VorhandeneElemente hinzufügen** den Dateifilter auf **Alle Dateien** oder **Bilddateien**fest, navigieren Sie zu der Bilddatei, die Sie verwenden möchten, und wählen Sie dann **Hinzufügen**aus.

## <a name="build-and-run-the-application"></a>Erstellen und Ausführen der Anwendung

1. Um die Anwendung zu erstellen und auszuführen, drücken Sie **F5** oder wählen Sie **Debuggen** im **Debug-Menü** starten aus.

    Die folgende Abbildung zeigt <xref:System.Windows.Navigation.NavigationWindow> die Anwendung mit den Schaltflächen:

    ![Anwendung, nachdem Sie sie erstellt und ausgeführt haben.](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. Schließen Sie die Anwendung, um zu Visual Studio zurückzukehren.

## <a name="create-the-layout"></a>Erstellen des Layouts

Layout bietet eine geordnete Möglichkeit zum Platzieren von UI-Elementen und verwaltet auch die Größe und Position dieser Elemente, wenn die Größe einer Benutzeroberfläche geändert wird. In der Regel erstellen Sie Layout mit einem der folgenden Layoutsteuerelemente:

- <xref:System.Windows.Controls.Canvas>- Definiert einen Bereich, innerhalb dem Sie untergeordnete Elemente explizit positionieren können, indem Sie Koordinaten verwenden, die relativ zum Canvas-Bereich sind.
- <xref:System.Windows.Controls.DockPanel>- Definiert einen Bereich, in dem Sie untergeordnete Elemente entweder horizontal oder vertikal relativ zueinander anordnen können.
- <xref:System.Windows.Controls.Grid>- Definiert einen flexiblen Rasterbereich, der aus Spalten und Zeilen besteht.
- <xref:System.Windows.Controls.StackPanel>- Ordnet untergeordnete Elemente in eine einzelne Linie an, die horizontal oder vertikal ausgerichtet werden kann.
- <xref:System.Windows.Controls.VirtualizingStackPanel>- Ordnet Inhalte auf einer einzigen Linie an, die entweder horizontal oder vertikal ausgerichtet ist.
- <xref:System.Windows.Controls.WrapPanel>- Positioniert untergeordnete Elemente in sequenzieller Position von links nach rechts, indem der Inhalt in die nächste Zeile am Rand des enthaltenden Feldes gebrochen wird. Die nachfolgende Sortierung erfolgt sequenziell von oben nach unten oder von rechts nach links, abhängig vom Wert der Orientation-Eigenschaft.

Jedes dieser Layoutsteuerelemente unterstützt einen bestimmten Layouttyp für seine untergeordneten Elemente. `ExpenseIt`Seiten können in der Größe geändert werden, und jede Seite enthält Elemente, die horizontal und vertikal neben anderen Elementen angeordnet sind. In diesem Beispiel <xref:System.Windows.Controls.Grid> wird der als Layoutelement für die Anwendung verwendet.

> [!TIP]
> Weitere Informationen <xref:System.Windows.Controls.Panel> zu Elementen finden Sie unter [Übersicht der Panels](../controls/panels-overview.md). Weitere Informationen zum Layout finden Sie unter [Layout](../advanced/layout.md).

In diesem Abschnitt erstellen Sie eine einspaltige Tabelle mit drei Zeilen und einem 10-Pixel-Rand, indem Sie Spalten- <xref:System.Windows.Controls.Grid> und Zeilendefinitionen zum in *`ExpenseItHome.xaml`* hinzufügen.

1. Legen *`ExpenseItHome.xaml`* Sie <xref:System.Windows.FrameworkElement.Margin%2A> in die <xref:System.Windows.Controls.Grid> Eigenschaft für das Element auf "10,0,10,10" fest, was dem linken, oberen, rechten und unteren Rand entspricht:

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > Sie können die **Margin-Werte** auch im **Eigenschaftenfenster** unter der Kategorie **Layout** festlegen:
   >
   > ![Margin-Werte im Eigenschaftenfenster](./media/properties-margin.png)

2. Fügen Sie das folgende <xref:System.Windows.Controls.Grid> XAML zwischen den Tags hinzu, um die Zeilen- und Spaltendefinitionen zu erstellen:

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    Die <xref:System.Windows.Controls.RowDefinition.Height%2A> Größe von zwei <xref:System.Windows.GridLength.Auto%2A>Zeilen ist auf festgelegt, was bedeutet, dass die Größe der Zeilen basierend auf dem Inhalt in den Zeilen festgelegt wird. Die <xref:System.Windows.Controls.RowDefinition.Height%2A> Standardgröße ist <xref:System.Windows.GridUnitType.Star> die Größe, was bedeutet, dass die Zeilenhöhe ein gewichteter Anteil des verfügbaren Speicherplatzes ist. Wenn z. B. <xref:System.Windows.Controls.RowDefinition.Height%2A> zwei Zeilen jeweils eine von "*" haben, haben sie jeweils eine Höhe, die die Hälfte des verfügbaren Speicherplatzes beträgt.

    Sie <xref:System.Windows.Controls.Grid> sollten nun Folgendes XAML enthalten:

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a>Hinzufügen von Steuerelementen

In diesem Abschnitt aktualisieren Sie die Benutzeroberfläche der Homepage, um eine Liste von Personen anzuzeigen, in der Sie eine Person auswählen, um deren Spesenabrechnung anzuzeigen. Steuerelemente sind Benutzeroberflächenobjekte, die Benutzern die Interaktion mit der Anwendung ermöglichen. Weitere Informationen finden Sie unter [Steuerelemente](../controls/index.md).

Um diese Benutzeroberfläche zu erstellen, fügen *`ExpenseItHome.xaml`* Sie die folgenden Elemente hinzu:

- A <xref:System.Windows.Controls.ListBox> (für die Personenliste).
- A <xref:System.Windows.Controls.Label> (für den Listenkopf).
- A <xref:System.Windows.Controls.Button> (klicken Sie auf , um die Spesenabrechnung für die in der Liste ausgewählte Person anzuzeigen).

Jedes Steuerelement wird in einer <xref:System.Windows.Controls.Grid> Zeile <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> des durch Festlegen der angefügten Eigenschaft platziert. Weitere Informationen zu angefügten Eigenschaften finden Sie unter [Übersicht über zugeordnete Eigenschaften](../advanced/attached-properties-overview.md).

1. Fügen *`ExpenseItHome.xaml`* Sie in das folgende XAML irgendwo zwischen den <xref:System.Windows.Controls.Grid> Tags hinzu:

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > Sie können die Steuerelemente auch erstellen, indem Sie sie aus dem **Toolbox-Fenster** in das Entwurfsfenster ziehen und dann ihre Eigenschaften im **Eigenschaftenfenster** festlegen.

2. Erstellen Sie die Anwendung, und führen Sie sie aus.

    Die folgende Abbildung zeigt die steuerelemente, die Sie erstellt haben:

![ExpenseIt-Beispiel-Screenshot mit einer Namensliste](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a>Hinzufügen eines Bildes und eines Titels

In diesem Abschnitt aktualisieren Sie die Benutzeroberfläche der Homepage mit einem Bild und einem Seitentitel.

1. Fügen *`ExpenseItHome.xaml`* Sie in eine <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> weitere <xref:System.Windows.Controls.ColumnDefinition.Width%2A> Spalte hinzu, die mit einem festen Von 230 Pixel n:

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewColumn)]

2. Fügen Sie dem <xref:System.Windows.Controls.Grid.RowDefinitions%2A>eine weitere Zeile für insgesamt vier Zeilen hinzu:

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewRows)]

3. Verschieben Sie die Steuerelemente in <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> die zweite Spalte, indem Sie die Eigenschaft in jedem der drei Steuerelemente (Border, ListBox und Button) auf 1 festlegen.

4. Verschieben Sie jedes Steuerelement in <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> einer Zeile nach unten, indem Sie den Wert für jedes der drei Steuerelemente (Border, ListBox und Button) und für das Border-Element um 1 erhöhen.

   Das XAML für die drei Steuerelemente sieht nun wie folgt aus:

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. Legen <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> Sie die Eigenschaft auf die *Bilddatei watermark.png* fest, `<Grid>` `</Grid>` indem Sie das folgende XAML an einer beliebigen Stelle zwischen den und-Tags hinzufügen:

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. Fügen <xref:System.Windows.Controls.Border> Sie vor <xref:System.Windows.Controls.Label> dem Element eine mit dem Inhalt "Spesenabrechnung anzeigen" hinzu. Diese Bezeichnung ist der Titel der Seite.

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. Erstellen Sie die Anwendung, und führen Sie sie aus.

Die folgende Abbildung zeigt die Ergebnisse dessen, was Sie gerade hinzugefügt haben:

![ExpenseIt-Beispiel-Screenshot mit dem neuen Bildhintergrund und Demseitentitel](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a>Hinzufügen von Code zum Behandeln von Ereignissen

1. Fügen *`ExpenseItHome.xaml`* Sie <xref:System.Windows.Controls.Primitives.ButtonBase.Click> dem <xref:System.Windows.Controls.Button> Element einen Ereignishandler hinzu. Weitere Informationen finden Sie unter [Gewusst wie: Erstellen eines einfachen Ereignishandlers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. Öffnen *`ExpenseItHome.xaml.vb`* *`ExpenseItHome.xaml.cs`* oder .

3. Fügen Sie der `ExpenseItHome` Klasse den folgenden Code hinzu, um einen Schaltflächenklick-Ereignishandler hinzuzufügen. Der Ereignishandler öffnet die **Seite ExpenseReportPage.**

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a>Erstellen der Benutzeroberfläche für ExpenseReportPage

*ExpenseReportPage.xaml* zeigt die Spesenabrechnung für die **`ExpenseItHome`** Person an, die auf der Seite ausgewählt ist. In diesem Abschnitt erstellen Sie die Benutzeroberfläche für **ExpenseReportPage**. Außerdem fügen Sie den verschiedenen UI-Elementen Hintergrund- und Füllfarben hinzu.

1. Öffnen Sie *ExpenseReportPage.xaml*.

2. Fügen Sie das folgende <xref:System.Windows.Controls.Grid> XAML zwischen den Tags hinzu:

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    Diese Benutzeroberfläche *`ExpenseItHome.xaml`* ähnelt , außer dass die <xref:System.Windows.Controls.DataGrid>Berichtsdaten in einer angezeigt werden.

3. Erstellen Sie die Anwendung, und führen Sie sie aus.

4. Wählen Sie die Schaltfläche **Ansicht** aus.

    Die Spesenabrechnungsseite wird angezeigt. Beachten Sie auch, dass die Zurück-Navigationstaste aktiviert ist.

Die folgende Abbildung zeigt die UI-Elemente, die *ExpenseReportPage.xaml*hinzugefügt wurden.

![ExpenseIt-Beispiel-Screenshot mit der ui, die gerade für die ExpenseReportPage erstellt wurde.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a>Stilsteuerelemente

Das Erscheinungsbild verschiedener Elemente ist häufig für alle Elemente desselben Typs in einer Benutzeroberfläche gleich. Die Benutzeroberfläche verwendet [Stile,](../controls/styling-and-templating.md) um Darstellungen über mehrere Elemente hinweg wiederverwendbar zu machen. Die Wiederverwendbarkeit von Stilen trägt zur Vereinfachung der XAML-Erstellung und -Verwaltung bei. Dieser Abschnitt ersetzt die Attribute pro Element, die in den vorherigen Schritten mit Stilen definiert wurden.

1. Öffnen Sie *Application.xaml* oder *App.xaml*.

2. Fügen Sie das folgende <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> XAML zwischen den Tags hinzu:

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    Durch diese XAML werden folgende Stile hinzugefügt:

    - `headerTextStyle`: Zum Formatieren des Seitentitels für <xref:System.Windows.Controls.Label>.

    - `labelStyle`: Zum Formatieren der <xref:System.Windows.Controls.Label> -Steuerelemente.

    - `columnHeaderStyle`: Zum Formatieren von <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.

    - `listHeaderStyle`: Zum Formatieren der <xref:System.Windows.Controls.Border> -Kopfzeilensteuerelemente.

    - `listHeaderTextStyle`: So formatieren <xref:System.Windows.Controls.Label>Sie den Listenkopf .

    - `buttonStyle`: Formatieren <xref:System.Windows.Controls.Button> `ExpenseItHome.xaml`der on .

    Beachten Sie, dass es sich <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> bei den Stilen um Ressourcen und untergeordnete Elemente des Eigenschaftselements handelt. An diesem Speicherort werden die Stile auf alle Elemente in einer Anwendung angewendet. Ein Beispiel für die Verwendung von Ressourcen in einer .NET-App finden Sie unter [Verwenden von Anwendungsressourcen](../advanced/how-to-use-application-resources.md).

3. Ersetzen *`ExpenseItHome.xaml`* Sie in <xref:System.Windows.Controls.Grid> alles zwischen den Elementen durch das folgende XAML:

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    Eigenschaften wie <xref:System.Windows.VerticalAlignment> und <xref:System.Windows.Media.FontFamily> , die die Darstellung der einzelnen Steuerelemente definieren, werden entfernt und ersetzt, indem die Stile angewendet werden. Die `headerTextStyle` wird z. B. auf den <xref:System.Windows.Controls.Label>"Spesenbericht anzeigen" angewendet.

4. Öffnen Sie *ExpenseReportPage.xaml*.

5. Ersetzen Sie <xref:System.Windows.Controls.Grid> alles zwischen den Elementen durch das folgende XAML:

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    Dieses XAML fügt <xref:System.Windows.Controls.Label> Stile <xref:System.Windows.Controls.Border> zu den und Elementen hinzu.

6. Erstellen Sie die Anwendung, und führen Sie sie aus. Die Fensterdarstellung ist die gleiche wie zuvor.

    ![ExpenseIt-Beispiel-Screenshot mit der gleichen Erscheinung wie im letzten Abschnitt.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. Schließen Sie die Anwendung, um zu Visual Studio zurückzukehren.

## <a name="bind-data-to-a-control"></a>Binden von Daten an ein Steuerelement

In diesem Abschnitt erstellen Sie die XML-Daten, die an verschiedene Steuerelemente gebunden sind.

1. Fügen *`ExpenseItHome.xaml`* Sie nach <xref:System.Windows.Controls.Grid> dem Öffnenelement das folgende XAML hinzu, um ein <xref:System.Windows.Data.XmlDataProvider> zu erstellen, das die Daten für jede Person enthält:

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    Die Daten werden <xref:System.Windows.Controls.Grid> als Ressource erstellt. Normalerweise würden diese Daten als Datei geladen werden, aber der Einfachheit halber werden die Daten inline hinzugefügt.

2. Fügen `<Grid.Resources>` Sie innerhalb des `<xref:System.Windows.DataTemplate>` Elements das folgende Element hinzu, <xref:System.Windows.Controls.ListBox>das definiert, wie die Daten im nach dem `<XmlDataProvider>` Element angezeigt werden:

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    Weitere Informationen zu Datenvorlagen finden Sie unter Übersicht über die [Datenbearbeitung](../data/data-templating-overview.md).

3. Ersetzen Sie <xref:System.Windows.Controls.ListBox> das vorhandene durch das folgende XAML:

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    Dieser XAML bindet <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> die <xref:System.Windows.Controls.ListBox> Eigenschaft des an die Datenquelle und <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>wendet die Datenvorlage als .

## <a name="connect-data-to-controls"></a>Verbinden von Daten mit Steuerelementen

Als Nächstes fügen Sie Code hinzu, um den **`ExpenseItHome`** auf der Seite ausgewählten Namen abzurufen und an den Konstruktor von **ExpenseReportPage**zu übergeben. **ExpenseReportPage** legt den Datenkontext mit dem übergebenen Element fest, an das die in *ExpenseReportPage.xaml* definierten Steuerelemente gebunden sind.

1. Öffnen Sie *ExpenseReportPage.xaml.vb* oder *ExpenseReportPage.xaml.cs*.

2. Fügen Sie einen Konstruktor hinzu, der ein Objekt akzeptiert, damit Sie die Spesenabrechnungsdaten der ausgewählten Person übergeben können.

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. Öffnen *`ExpenseItHome.xaml.vb`* *`ExpenseItHome.xaml.cs`* oder .

4. Ändern <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Sie den Ereignishandler, um den neuen Konstruktor aufzurufen, der die Spesenabrechnungsdaten der ausgewählten Person übergibt.

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a>Formatieren von Daten mit Datenvorlagen

In diesem Abschnitt aktualisieren Sie die Benutzeroberfläche für jedes Element in den datengebundenen Listen mithilfe von Datenvorlagen.

1. Öffnen Sie *ExpenseReportPage.xaml*.

2. Binden Sie den Inhalt der Elemente <xref:System.Windows.Controls.Label> "Name" und "Department" an die entsprechende Datenquelleneigenschaft. Weitere Informationen zur Datenbindung finden Sie unter [Datenbindungsübersicht](../../../desktop-wpf/data/data-binding-overview.md).

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. Fügen Sie <xref:System.Windows.Controls.Grid> nach dem Öffnenelement die folgenden Datenvorlagen hinzu, die definieren, wie die Spesenabrechnungsdaten angezeigt werden sollen:

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. Ersetzen <xref:System.Windows.Controls.DataGridTextColumn> Sie <xref:System.Windows.Controls.DataGridTemplateColumn> die <xref:System.Windows.Controls.DataGrid> Elemente durch das Element, und wenden Sie die Vorlagen darauf an.

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. Erstellen Sie die Anwendung, und führen Sie sie aus.

6. Wählen Sie eine Person aus, und wählen Sie dann die Schaltfläche **Ansicht** aus.

Die folgende Abbildung zeigt `ExpenseIt` beide Seiten der Anwendung mit Steuerelementen, Layout, Stilen, Datenbindung und Datenvorlagen:

![Beide Seiten der App mit der Namensliste und einer Spesenabrechnung.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> Dieses Beispiel veranschaulicht ein bestimmtes Feature von WPF und befolgt nicht alle bewährten Methoden für Dinge wie Sicherheit, Lokalisierung und Zugänglichkeit. Eine umfassende Abdeckung von WPF und den Best Practices für die .NET-App-Entwicklung finden Sie in den folgenden Themen:
>
> - [Zugriff](../../ui-automation/accessibility-best-practices.md)
> - [Security](../security-wpf.md)
> - [Übersicht über WPF-Globalisierung und -Lokalisierung](../advanced/wpf-globalization-and-localization-overview.md)
> - [WPF-Leistung](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a>Nächste Schritte

In dieser exemplarischen Vorgehensweise haben Sie eine Reihe von Techniken zum Erstellen einer Benutzeroberfläche mit Windows Presentation Foundation (WPF) gelernt. Sie sollten nun über ein grundlegendes Verständnis der Bausteine einer datengebundenen .NET-App verfügen. Weitere Informationen über die WPF-Architektur und -Programmiermodelle finden Sie in den folgenden Themen:

- [WPF-Architektur](../advanced/wpf-architecture.md)
- [XAML-Übersicht (WPF)](../advanced/xaml-overview-wpf.md)
- [Überblick über Abhängigkeitseigenschaften](../advanced/dependency-properties-overview.md)
- [Layout](../advanced/layout.md)

Weitere Informationen zum Erstellen von Anwendungen finden Sie in den folgenden Themen:

- [Anwendungsentwicklung](../app-development/index.md)
- [Steuerelemente](../controls/index.md)
- [Übersicht über Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Grafik und Multimedia](../graphics-multimedia/index.md)
- [Dokumente in WPF](../advanced/documents-in-wpf.md)

## <a name="see-also"></a>Weitere Informationen

- [Panel-Übersicht](../controls/panels-overview.md)
- [Übersicht über die Datenbearbeitbarkeit](../data/data-templating-overview.md)
- [Erstellen einer WPF-Anwendung](../app-development/building-a-wpf-application-wpf.md)
- [Stile und Vorlagen](../controls/styles-and-templates.md)
