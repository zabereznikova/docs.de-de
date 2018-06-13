---
title: Erstellen Sie eine WPF-Anwendung in Visual Studio
ms.date: 04/12/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7ceb4d79bb88e41e62f3ee136b6beb3324b3dbd7
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809715"
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a>Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung

Dieser Artikel beschreibt, wie eine einfache Windows Presentation Foundation (WPF)-Anwendung entwickeln, die die Elemente enthält, die für die meisten WPF-Anwendungen gemeinsam verwendet werden: Extensible Application Markup Language (XAML)-Markup, CodeBehind, Anwendungsdefinitionen, Steuerelemente, Layout, Datenbindung und Stile.

Diese exemplarische Vorgehensweise umfasst die folgenden Schritte aus:

- Verwenden Sie XAML-Code, um die Darstellung der Benutzeroberfläche (UI) der Anwendung entwerfen.

- Schreiben Sie Code, um das Verhalten der Anwendung zu erstellen.

- Erstellen Sie die Anwendungsdefinition einer zum Verwalten der Anwendung.

- Fügen Sie Steuerelemente hinzu, und erstellen Sie das Layout, um die Benutzeroberfläche der Anwendung zu erstellen.

- Stile für eine konsistente Darstellung in der gesamten Benutzeroberfläche einer Anwendung zu erstellen.

- Binden Sie die Benutzeroberfläche an Daten sowohl die Benutzeroberfläche von Daten zu füllen, und behalten Sie die Daten und die Benutzeroberfläche, die synchronisiert.

Am Ende dieser exemplarischen Vorgehensweise müssen Sie einen eigenständigen Windows-Anwendung erstellt haben, die Benutzern ermöglicht, Ausgabenberichte für ausgewählte Benutzer anzeigen. Die Anwendung besteht aus mehreren WPF-Seiten, die in einem Fenster im Webbrowserstil gehostet werden.

> [!TIP]
> Der Beispielcode, der verwendet wird, erstellen Sie in dieser exemplarischen Vorgehensweise steht für Visual Basic- und C#-am [Einführung zum Erstellen von WPF-Anwendungen](http://go.microsoft.com/fwlink/?LinkID=160008).

## <a name="prerequisites"></a>Erforderliche Komponenten

- Visual Studio 2012 oder höher

Weitere Informationen zum Installieren der neuesten Version von Visual Studio finden Sie unter [installieren Sie Visual Studio](/visualstudio/install/install-visual-studio).

## <a name="create-the-application-project"></a>Erstellen Sie das Anwendungsprojekt

Der erste Schritt ist die Anwendungsstruktur, erstellen, die Anwendungsdefinition einer zwei Seiten und ein Bild enthält.

1. Erstellen ein neues WPF-Anwendungsprojekts in Visual Basic oder Visual c# mit dem Namen **ExpenseIt**:

   1. Öffnen Sie Visual Studio, und wählen Sie **Datei** > **neu** > **Projekt**.

      Die **neues Projekt** Dialogfeld wird geöffnet.

   2. Unter den **installiert** Kategorie, erweitern Sie entweder die **Visual C#-** oder **Visual Basic** Knoten, und wählen Sie dann **klassische Windows-Desktop**.

   3. Wählen Sie die **WPF-App ((.NET Framework)** Vorlage. Geben Sie den Namen **ExpenseIt** und wählen Sie dann **OK**.

      ![Dialogfeld "Neues Projekt" mit WPF-app ausgewählt](media/new-project-dialog.png)

      Visual Studio erstellt das Projekt und öffnet den Designer für das standardanwendungsfenster namens **"MainWindow.xaml"**.

   > [!NOTE]
   > Diese exemplarische Vorgehensweise verwendet die <xref:System.Windows.Controls.DataGrid> Steuerelement, das in .NET Framework 4 und höher verfügbar. Stellen Sie sicher, dass Ihr Projekt auf .NET Framework 4 abzielt oder höher. Weitere Informationen finden Sie unter [Vorgehensweise: .NET Framework-Version als Ziel](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).

2. Open *Application.xaml* (Visual Basic) oder *App.xaml* (c#).

    Diese Verwendung von XAML-Datei definiert eine WPF-Anwendung und alle Ressourcen der Anwendung. Mithilfe dieser Datei auch an der Benutzeroberfläche, die automatisch, wann zeigt die Anwendung gestartet wird; In diesem Fall *"MainWindow.xaml"*.

    XAML-Code sollte in Visual Basic wie folgt aussehen:

    [!code-xaml[ExpenseIt#1_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    Oder in C# wie folgt:

    [!code-xaml[ExpenseIt#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. Open *"MainWindow.xaml"*.

    Diese Verwendung von XAML-Datei wird im Hauptfenster der Anwendung und zeigt den Inhalt in Seiten erstellt. Die <xref:System.Windows.Window> Klasse definiert die Eigenschaften eines Fensters, z. B. Titel, Größe oder Symbol, und behandelt Ereignisse, z. B. Schließen oder ausblenden.

4. Ändern der <xref:System.Windows.Window> Element um eine <xref:System.Windows.Navigation.NavigationWindow>, wie in den folgenden XAML-Code dargestellt:

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   Diese app navigiert zu unterschiedlichen Inhalt je nach Benutzereingabe. Deswegen den Hauptknoten <xref:System.Windows.Window> muss geändert werden, um eine <xref:System.Windows.Navigation.NavigationWindow>. <xref:System.Windows.Navigation.NavigationWindow> erbt alle Eigenschaften des <xref:System.Windows.Window>. Die <xref:System.Windows.Navigation.NavigationWindow> Element in der XAML-Datei erstellt eine Instanz der <xref:System.Windows.Navigation.NavigationWindow> Klasse. Weitere Informationen finden Sie unter [Navigation Overview](../../../../docs/framework/wpf/app-development/navigation-overview.md).

5. Ändern Sie die folgenden Eigenschaften auf der <xref:System.Windows.Navigation.NavigationWindow> Element:

    - Legen Sie die <xref:System.Windows.Window.Title%2A> -Eigenschaft auf "ExpenseIt".

    - Legen Sie die <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft auf 500 Pixel.

    - Legen Sie die <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaft auf 350 Pixel.

    - Entfernen Sie die <xref:System.Windows.Controls.Grid> Elemente zwischen den <xref:System.Windows.Navigation.NavigationWindow> Tags.

    XAML-Code sollte in Visual Basic wie folgt aussehen:

    [!code-xaml[ExpenseIt#2_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    Oder in C# wie folgt:

    [!code-xaml[ExpenseIt#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

6. Open *"MainWindow.Xaml.vb"* oder *"MainWindow.Xaml.cs"*.

    Diese Datei ist ein Code-Behind-Datei, die Code zum Behandeln der Ereignisse, die im deklarierten enthält *"MainWindow.xaml"*. Diese Datei enthält eine partielle Klasse für das in XAML definierte Fenster.

7. Wenn Sie c# verwenden, ändern Sie die `MainWindow` Klasse abgeleitet <xref:System.Windows.Navigation.NavigationWindow>. (In Visual Basic geschieht dies automatisch, wenn Sie das Fenster in XAML ändern.)

   Der Code sollte wie folgt aussehen:

   [!code-csharp[ExpenseIt#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml.cs#3)]
   [!code-vb[ExpenseIt#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml.vb#3)]

   > [!TIP]
   > Sie können die Codesprache des Beispielcodes zwischen c# und Visual Basic in Umschalten der **Sprache** Dropdown-Menü in der oberen rechten Ecke dieses Artikels.

## <a name="add-files-to-the-application"></a>Hinzufügen von Dateien zur Anwendung

In diesem Abschnitt fügen Sie der Anwendung zwei Seiten und ein Bild hinzu.

1. Fügen Sie eine neue WPF-Seite auf das Projekt, und nennen Sie sie *ExpenseItHome.xaml*:

   1. In **Projektmappen-Explorer**, mit der rechten Maustaste auf die **ExpenseIt** Projektknoten, und wählen Sie **hinzufügen** > **Seite**.

   1. In der **neues Element hinzufügen** im Dialogfeld die **Seite (WPF)** Vorlage bereits ausgewählt ist. Geben Sie den Namen **ExpenseItHome**, und wählen Sie dann **hinzufügen**.

    Diese Seite ist die erste Seite, die angezeigt wird, wenn die Anwendung gestartet wird. Es zeigt eine Liste der Personen an, wählen Sie aus, um ein Ausgabenbericht für anzuzeigen.

2. Öffnen Sie *ExpenseItHome.xaml*.

3. Legen Sie die <xref:System.Windows.Controls.Page.Title%2A> auf "ExpenseIt – Home".

    XAML-Code sollte in Visual Basic wie folgt aussehen:

    [!code-xaml[ExpenseIt#6_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    Oder in C# wie folgt:

    [!code-xaml[ExpenseIt#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

4. Open *"MainWindow.xaml"*.

5. Legen Sie die <xref:System.Windows.Navigation.NavigationWindow.Source%2A> Eigenschaft auf die <xref:System.Windows.Navigation.NavigationWindow> auf "ExpenseItHome.xaml".

    Dadurch wird *ExpenseItHome.xaml* als erste Seite festgelegt, die beim Start der Anwendung geöffnet wird. XAML-Code sollte in Visual Basic wie folgt aussehen:

    [!code-xaml[ExpenseIt#7_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    Oder in C# wie folgt:

    [!code-xaml[ExpenseIt#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > Sie können auch Festlegen der **Quelle** Eigenschaft in der **Sonstiges** Kategorie der **Eigenschaften** Fenster.
   >
   > ![Source-Eigenschaft im Fenster "Eigenschaften"](media/properties-source.png)

6. Das Projekt eine andere neue WPF-Seite hinzu, und nennen Sie sie *ExpenseReportPage.xaml*::

   1. In **Projektmappen-Explorer**, mit der rechten Maustaste auf die **ExpenseIt** Projektknoten, und wählen Sie **hinzufügen** > **Seite**.

   1. In der **neues Element hinzufügen** im Dialogfeld die **Seite (WPF)** Vorlage bereits ausgewählt ist. Geben Sie den Namen **ExpenseReportPage**, und wählen Sie dann **hinzufügen**.

    Auf dieser Seite wird der Ausgabenbericht angezeigt, für die Person, die für ausgewählt, wird die **ExpenseItHome** Seite.

7. Öffnen Sie *ExpenseReportPage.xaml*.

8. Legen Sie die <xref:System.Windows.Controls.Page.Title%2A> auf "ExpenseIt – View Expense".

    XAML-Code sollte in Visual Basic wie folgt aussehen:

    [!code-xaml[ExpenseIt#4_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    Oder in C# wie folgt:

    [!code-xaml[ExpenseIt#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

9. Open *ExpenseItHome.xaml.vb* und *ExpenseReportPage.xaml.vb*, oder *ExpenseItHome.xaml.cs* und *ExpenseReportPage.xaml.cs*.

    Wenn Sie eine neue Datei erstellen, erstellt Visual Studio automatisch eine *CodeBehind* Datei. Diese CodeBehind-Dateien behandeln die Logik zum Reagieren auf Benutzereingabe.

    Der Code sollte wie folgt für Aussehen **ExpenseItHome**:

    [!code-csharp[ExpenseIt#2_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]
    [!code-vb[ExpenseIt#2_5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    Und wie dies für **ExpenseReportPage**:

    [!code-csharp[ExpenseIt#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]
    [!code-vb[ExpenseIt#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

10. Hinzufügen eines Bilds mit dem Namen *watermark.png* zum Projekt. Sie können Ihr eigenes Image zu erstellen, kopieren Sie die Datei aus dem Beispielcode oder rufen Sie die Anwendung [hier](https://github.com/dotnet/docs/blob/master/docs/framework/wpf/getting-started/media/watermark.png).

   1. Mit der rechten Maustaste auf den Projektknoten, und wählen Sie **hinzufügen** > **vorhandenes Element**, oder drücken Sie **UMSCHALT**+**Alt** + **Ein**.

   2. In der **vorhandenes Element hinzufügen** durchsuchen, um die Abbilddatei, die Sie verwenden möchten, und wählen Sie dann im Dialogfeld **hinzufügen**.

## <a name="build-and-run-the-application"></a>Erstellen eines Builds und Ausführen der Anwendung

1. Drücken Sie zum Erstellen und Ausführen der Anwendung müssen Sie **F5** , oder wählen Sie **Debuggen** aus der **Debuggen** Menü.

    Die folgende Abbildung zeigt die Anwendung mit der <xref:System.Windows.Navigation.NavigationWindow> Schaltflächen:

    ![Bildschirmabbildung für ExpenseIt-Beispiel](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png)

2. Schließen Sie die Anwendung aus, um zu Visual Studio zurückzukehren.

## <a name="create-the-layout"></a>Erstellen Sie das layout

Layout bietet die Möglichkeit, UI-Elemente anzuordnen und verwaltet auch die Größe und Position dieser Elemente beim Ändern der Größe einer Benutzeroberflächenautomatisierungs. In der Regel erstellen Sie Layout mit einem der folgenden Layoutsteuerelemente:

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.VirtualizingStackPanel>
- <xref:System.Windows.Controls.WrapPanel>

Jedes dieser Layoutsteuerelemente unterstützt einen speziellen Layouttyp für seine untergeordneten Elemente. Die Größe von „ExpenseIt“-Seiten kann geändert werden. Jede Seite verfügt über Elemente, die horizontal und vertikal neben anderen Elementen angeordnet sind. Folglich die <xref:System.Windows.Controls.Grid> ist die ideale Layoutelement für die Anwendung.

> [!TIP]
> Weitere Informationen zu <xref:System.Windows.Controls.Panel> Elemente finden Sie unter [Panels Overview](../../../../docs/framework/wpf/controls/panels-overview.md). Weitere Informationen zum Layout finden Sie unter [Layout](../../../../docs/framework/wpf/advanced/layout.md).

Klicken Sie im Abschnitt erstellen Sie eine einspaltige Tabelle mit drei Zeilen und einen 10-Pixel-Rand durch Hinzufügen von Spalten- und Definitionen, um die <xref:System.Windows.Controls.Grid> in *ExpenseItHome.xaml*.

1. Öffnen Sie *ExpenseItHome.xaml*.

2. Legen Sie die <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft auf die <xref:System.Windows.Controls.Grid> -Elements auf "10,0,10,10", den linken, oberen, rechten und unteren Ränder:

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > Sie können auch Festlegen der **Rand** Werte in der **Eigenschaften** Fenster unter dem **Layout** Kategorie:
   >
   > ![Die Werte für Ränder im Fenster "Eigenschaften"](media/properties-margin.png)

3. Fügen Sie den folgenden XAML-Code zwischen den <xref:System.Windows.Controls.Grid> Tags aus, um die Zeilen- und Spaltendefinitionen zu erstellen:

    [!code-xaml[ExpenseIt#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    Die <xref:System.Windows.Controls.RowDefinition.Height%2A> von zwei Zeilen wird festgelegt <xref:System.Windows.GridLength.Auto%2A>, was bedeutet, dass die Größe der Zeilen als Grundlage für den Inhalt in den Zeilen. Die Standardeinstellung <xref:System.Windows.Controls.RowDefinition.Height%2A> ist <xref:System.Windows.GridUnitType.Star> Sizing, was bedeutet, dass die Zeilenhöhe gewichtete Proportion des verfügbaren Speicherplatzes beträgt. Wenn beispielsweise zwei Zeilen haben eine <xref:System.Windows.Controls.RowDefinition.Height%2A> von "*", sie verfügen jeweils über eine Höhe von der Hälfte des verfügbaren Speicherplatzes ist.

    Ihre <xref:System.Windows.Controls.Grid> sollte jetzt wie der folgende XAML-Code aussehen:

    [!code-xaml[ExpenseIt#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a>Hinzufügen von Steuerelementen

Aktualisieren Sie in diesem Abschnitt der Startseite Benutzeroberfläche zum Anzeigen einer Liste der Personen, die zum Anzeigen des Berichts Ausgaben für ein Benutzer auswählen kann. Steuerelemente sind Benutzeroberflächenobjekte, die Benutzern die Interaktion mit der Anwendung ermöglichen. Weitere Informationen finden Sie unter [Steuerelemente](../../../../docs/framework/wpf/controls/index.md).

Um diese Benutzeroberfläche zu erstellen, fügen Sie die folgenden Elemente in *ExpenseItHome.xaml*:

- <xref:System.Windows.Controls.ListBox> (für die Liste der Personen).
- <xref:System.Windows.Controls.Label> (für den List-Header).
- <xref:System.Windows.Controls.Button> (um klicken, um die Ausgabenbericht für die Person anzuzeigen, die in der Liste ausgewählt ist).

Jedes Steuerelement wird in einer Zeile platziert die <xref:System.Windows.Controls.Grid> durch Festlegen der <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> -Eigenschaft. Weitere Informationen über angefügte Eigenschaften finden Sie unter [Eigenschaftenübersicht angefügt](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).

1. Öffnen Sie *ExpenseItHome.xaml*.

2. Fügen Sie den folgenden XAML-Code an einer beliebigen Stelle zwischen den <xref:System.Windows.Controls.Grid> Tags:

   [!code-xaml[ExpenseIt#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > Sie können die Steuerelemente auch erstellen, von Drag & Drop aus der **Toolbox** auf das Entwurfsfenster, und klicken Sie dann deren Eigenschaften der **Eigenschaften** Fenster.

3. Erstellen Sie die Anwendung, und führen Sie sie aus.

Die folgende Abbildung zeigt die Steuerelemente, die Sie soeben erstellt haben:

![Bildschirmabbildung für ExpenseIt-Beispiel](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png)

## <a name="add-an-image-and-a-title"></a>Fügen Sie ein Abbild und einen Titel hinzu

In diesem Abschnitt werden Sie die Benutzeroberfläche der Homepage mit einem Bild und einen Seitentitel aktualisieren.

1. Öffnen Sie *ExpenseItHome.xaml*.

2. Eine weitere Spalte zum Hinzufügen der <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> mit einer festen <xref:System.Windows.Controls.ColumnDefinition.Width%2A> von 230 Pixeln:

    [!code-xaml[ExpenseIt#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11)]

3. Hinzufügen zu einer anderen Zeile die <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, insgesamt vier Zeilen:

    [!code-xaml[ExpenseIt#11b](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11b)]

4. Verschieben Sie die Steuerelemente in die zweite Spalte durch Festlegen der <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> -Eigenschaft auf 1 in jedem der drei Steuerelemente (Rahmen, ListBox und Schaltfläche).

5. Verschieben Sie jedes Steuerelement eine Zeile nach unten durch Erhöhen der <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> -Wert um 1.

   Der XAML-Code für die drei Steuerelemente sieht nun wie folgt:

    [!code-xaml[ExpenseIt#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

6. Festlegen der <xref:System.Windows.Controls.Panel.Background%2A> von der <xref:System.Windows.Controls.Grid> werden die *watermark.png* Bilddatei durch Hinzufügen der folgende XAML-Code an einer beliebigen Stelle zwischen der `<Grid>` und `<\/Grid>` Tags:

    [!code-xaml[ExpenseIt#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

7. Vor der <xref:System.Windows.Controls.Border> Element, Hinzufügen einer <xref:System.Windows.Controls.Label> mit dem Inhalt "View Expense Report". Dies ist der Titel der Seite.

    [!code-xaml[ExpenseIt#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

8. Erstellen Sie die Anwendung, und führen Sie sie aus.

Die folgende Abbildung zeigt die Ergebnisse von was Sie gerade hinzugefügt haben:

![Bildschirmabbildung für ExpenseIt-Beispiel](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png)

## <a name="add-code-to-handle-events"></a>Fügen Sie Code zum Verarbeiten von Ereignissen

1. Öffnen Sie *ExpenseItHome.xaml*.

2. Hinzufügen einer <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler, um die <xref:System.Windows.Controls.Button> Element. Weitere Informationen finden Sie unter [Vorgehensweise: erstellen einen einfachen Ereignishandler](http://msdn.microsoft.com/library/b1456e07-9dec-4354-99cf-18666b64f480).

    [!code-xaml[ExpenseIt#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

3. Öffnen Sie *ExpenseItHome.xaml.vb* oder *ExpenseItHome.xaml.cs*.

4. Fügen Sie folgenden Code, der `ExpenseItHome` Klasse, um eine Schaltfläche hinzuzufügen click-Ereignishandler. Der Ereignishandler öffnet die **ExpenseReportPage** Seite.

    [!code-csharp[ExpenseIt#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a>Erstellen der Benutzeroberfläche für ExpenseReportPage

*ExpenseReportPage.xaml* zeigt die Ausgabenbericht für die Person, die für ausgewählt, wird die **ExpenseItHome** Seite. In diesem Abschnitt legen Sie Steuerelemente und erstellen die Benutzeroberfläche für **ExpenseReportPage**. Sie müssen auch Hintergrund hinzufügen und Füllfarben für die verschiedenen UI-Elemente.

1. Öffnen Sie *ExpenseReportPage.xaml*.

2. Fügen Sie den folgenden XAML-Code zwischen den <xref:System.Windows.Controls.Grid> Tags:

    [!code-xaml[ExpenseIt#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    Diese Benutzeroberfläche ähnelt *ExpenseItHome.xaml*, außer dass die Daten des Berichts, in angezeigt werden einem <xref:System.Windows.Controls.DataGrid>.

3. Erstellen Sie die Anwendung, und führen Sie sie aus.

    > [!NOTE]
    > Wenn Sie eine Fehlermeldung, die erhalten die <xref:System.Windows.Controls.DataGrid> wurde nicht gefunden oder nicht vorhanden ist, stellen Sie sicher, dass das Projekt .NET Framework 4 oder höher abzielt. Weitere Informationen finden Sie unter [Vorgehensweise: .NET Framework-Version als Ziel](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).

4. Wählen Sie die **Ansicht** Schaltfläche.

    Die Spesenabrechnungsseite wird angezeigt. Beachten Sie außerdem, dass die Navigationsschaltfläche "zurück" aktiviert ist.

Die folgende Abbildung zeigt die Elemente der Benutzeroberfläche hinzugefügt *ExpenseReportPage.xaml*.

![Bildschirmabbildung für ExpenseIt-Beispiel](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png)

## <a name="style-controls"></a>-Designstil-Steuerelemente

Die Darstellung der verschiedenen Elemente ist häufig für alle Elemente des gleichen Typs in einer Benutzeroberfläche identisch. Benutzeroberfläche [Stile](../../../../docs/framework/wpf/controls/styling-and-templating.md) eindeutigkeitsmetrik über mehrere Elemente hinweg wieder verwendbare vornehmen. Die Wiederverwendung von Formaten wird die um Verwendung von XAML-Erstellung und Verwaltung zu vereinfachen. Dieser Abschnitt ersetzt die Attribute pro Element, die in den vorherigen Schritten mit Stilen definiert wurden.

1. Open *Application.xaml* oder *App.xaml*.

2. Fügen Sie den folgenden XAML-Code zwischen den <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> Tags:

    [!code-xaml[ExpenseIt#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    Durch diese XAML werden folgende Stile hinzugefügt:

    - `headerTextStyle`: Zum Formatieren des Seitentitels für <xref:System.Windows.Controls.Label>.

    - `labelStyle`: Zum Formatieren der <xref:System.Windows.Controls.Label> -Steuerelemente.

    - `columnHeaderStyle`: Zum Formatieren von <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.

    - `listHeaderStyle`: Zum Formatieren der <xref:System.Windows.Controls.Border> -Kopfzeilensteuerelemente.

    - `listHeaderTextStyle`: Zum Formatieren der Kopfzeile <xref:System.Windows.Controls.Label>.

    - `buttonStyle`: Zum Formatieren der <xref:System.Windows.Controls.Button> auf ExpenseItHome.xaml.

    Beachten Sie, dass die Stile für Ressourcen und die untergeordneten Elemente sind die <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> Property-Element. An diesem Speicherort werden die Stile auf alle Elemente in einer Anwendung angewendet. Ein Beispiel der Verwendung von Ressourcen in einer .NET Framework-Anwendung finden Sie unter [verwenden Anwendungsressourcen](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md).

3. Öffnen Sie *ExpenseItHome.xaml*.

4. Ersetzen Sie alles zwischen dem <xref:System.Windows.Controls.Grid> Elemente mit den folgenden XAML-Code:

    [!code-xaml[ExpenseIt#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    Eigenschaften wie <xref:System.Windows.VerticalAlignment> und <xref:System.Windows.Media.FontFamily> , die die Darstellung der einzelnen Steuerelemente definieren, werden entfernt und ersetzt, indem die Stile angewendet werden. Z. B. die `headerTextStyle` wird angewendet, um die "View Expense Report" <xref:System.Windows.Controls.Label>.

5. Öffnen Sie *ExpenseReportPage.xaml*.

6. Ersetzen Sie alles zwischen dem <xref:System.Windows.Controls.Grid> Elemente mit den folgenden XAML-Code:

    [!code-xaml[ExpenseIt#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    Dadurch werden dem <xref:System.Windows.Controls.Label> -Element und <xref:System.Windows.Controls.Border> -Element Stile hinzugefügt.

## <a name="bind-data-to-a-control"></a>Binden von Daten an ein Steuerelement

In diesem Abschnitt erstellen Sie die XML-Daten, die an verschiedene Steuerelemente gebunden ist.

1. Öffnen Sie *ExpenseItHome.xaml*.

2. Nach dem Öffnen <xref:System.Windows.Controls.Grid> Element, fügen Sie den folgenden XAML-Code zum Erstellen einer <xref:System.Windows.Data.XmlDataProvider> , die Daten für jede Person enthält:

    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]
    [!code-xaml[ExpenseIt#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#23)]
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]

    Die Daten werden als erstellt eine <xref:System.Windows.Controls.Grid> Ressource. Normalerweise würde sie als Datei geladen, aus Gründen der Einfachheit werden die Daten aber inline hinzugefügt.

3. Innerhalb der `<Grid.Resources>` Element, fügen Sie die folgenden <xref:System.Windows.DataTemplate>, die definiert, wie zum Anzeigen der Daten in der <xref:System.Windows.Controls.ListBox>:

    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]
    [!code-xaml[ExpenseIt#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#24)]
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]

    Weitere Informationen zu Daten finden Sie unter [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md).

4. Ersetzen Sie die vorhandene <xref:System.Windows.Controls.ListBox> mit den folgenden XAML-Code:

    [!code-xaml[ExpenseIt#25](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    Dieser XAML-Code bindet die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaft von der <xref:System.Windows.Controls.ListBox> mit der Datenquelle und wendet die Datenvorlage als die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.

## <a name="connect-data-to-controls"></a>Verbinden von Daten an Steuerelemente

Als Nächstes fügen Sie Code aus, um den Namen abzurufen, die für ausgewählt, wird die **ExpenseItHome** Seite sowie deren Übergabe an den Konstruktor des **ExpenseReportPage**. **ExpenseReportPage** legt dessen Datenkontext mithilfe des übergebenen Elements, die die Steuerelemente definierten in *ExpenseReportPage.xaml* zu binden.

1. Öffnen Sie *ExpenseReportPage.xaml.vb* oder *ExpenseReportPage.xaml.cs*.

2. Fügen Sie einen Konstruktor hinzu, der ein Objekt akzeptiert, damit Sie die Spesenabrechnungsdaten der ausgewählten Person übergeben können.

    [!code-csharp[ExpenseIt#26](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. Öffnen Sie *ExpenseItHome.xaml.vb* oder *ExpenseItHome.xaml.cs*.

4. Ändern der <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignishandler aufrufen, den neuen Konstruktor die Spesenabrechnungsdaten der ausgewählten Person übergeben.

    [!code-csharp[ExpenseIt#27](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a>Stil-Daten mit Datenvorlagen

In diesem Abschnitt werden Sie die Benutzeroberfläche für jedes Element in den datengebundenen Listen mithilfe von Datenvorlagen für die aktualisieren.

1. Öffnen Sie *ExpenseReportPage.xaml*.

2. Binden Sie den Inhalt des "Name" und "Department" <xref:System.Windows.Controls.Label> Elemente, die die entsprechenden Daten source-Eigenschaft. Weitere Informationen zur Datenbindung finden Sie unter [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).

    [!code-xaml[ExpenseIt#31](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. Nach der öffnenden <xref:System.Windows.Controls.Grid> Element, fügen Sie die folgenden Datenvorlagen, die definieren, wie die Spesenabrechnungsdaten angezeigt:

    [!code-xaml[ExpenseIt#30](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. Wenden Sie die Vorlagen, die <xref:System.Windows.Controls.DataGrid> Berichtsdaten für Spalten, in denen die Ausgaben angezeigt.

    [!code-xaml[ExpenseIt#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. Erstellen Sie die Anwendung, und führen Sie sie aus.

6. Wählen Sie eine Person ein, und wählen Sie dann die **Ansicht** Schaltfläche.

Die folgende Abbildung zeigt die beiden Seiten der ExpenseIt-Anwendung mit Steuerelementen, Layout, Stilen, Datenbindung und Datenvorlagen, die angewendet:

![Bildschirmabbildungen für ExpenseIt-Beispiel](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png)

> [!NOTE]
> Dieses Beispiel veranschaulicht eine bestimmte Funktion von WPF und nicht befolgen Sie alle bewährten Methoden für Angaben wie Sicherheit, Lokalisierung und Verfügbarkeit. Eine umfassende Erläuterung von WPF und bewährte Methoden für die Anwendungsentwicklung der .NET Framework finden Sie unter den folgenden Themen:
>
> - [Barrierefreiheit](../../../../docs/framework/ui-automation/accessibility-best-practices.md)
>
> - [Sicherheit](../../../../docs/framework/wpf/security-wpf.md)
>
> - [Übersicht über WPF-Globalisierung und -Lokalisierung](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)
>
> - [WPF-Leistung](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a>Nächste Schritte

In dieser exemplarischen Vorgehensweise haben Sie gelernt, eine Reihe von Techniken für das Erstellen einer Benutzeroberfläche mit Windows Presentation Foundation (WPF). Sie verfügen jetzt über grundlegende Kenntnisse der Bausteine einer datengebundenen, .NET Framework-Anwendung. Weitere Informationen über die WPF-Architektur und -Programmiermodelle finden Sie in den folgenden Themen:

- [WPF-Architektur](../../../../docs/framework/wpf/advanced/wpf-architecture.md)
- [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
- [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
- [Layout](../../../../docs/framework/wpf/advanced/layout.md)

Weitere Informationen zum Erstellen von Anwendungen finden Sie in den folgenden Themen:

- [Anwendungsentwicklung](../../../../docs/framework/wpf/app-development/index.md)
- [Steuerelemente](../../../../docs/framework/wpf/controls/index.md)
- [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Grafiken und multimedia](../../../../docs/framework/wpf/graphics-multimedia/index.md)
- [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)

## <a name="see-also"></a>Siehe auch

- [Übersicht über die Bereiche](../../../../docs/framework/wpf/controls/panels-overview.md)
- [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md)
- [Erstellen Sie eine WPF-Anwendung](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)
- [Stile und Vorlagen](../../../../docs/framework/wpf/controls/styles-and-templates.md)
