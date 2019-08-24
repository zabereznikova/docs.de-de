---
title: 'Exemplarische Vorgehensweise: Anordnen von WPF-Inhalt in Windows Forms zur Entwurfszeit'
ms.date: 08/18/2018
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 5e5112aa0b025648ce68a93f0f3da026ec99fe89
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987145"
---
# <a name="walkthrough-create-new-wpf-content-on-windows-forms-at-design-time"></a>Exemplarische Vorgehensweise: Erstellen eines neuen WPF-Inhalts auf Windows Forms zur Entwurfszeit

In diesem Artikel erfahren Sie, wie Sie ein Windows Presentation Foundation-Steuerelement (WPF) für die Verwendung in Ihren Windows Forms basierten Anwendungen erstellen.

## <a name="prerequisites"></a>Erforderliche Komponenten

Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.

## <a name="create-the-project"></a>Erstellen eines Projekts

Öffnen Sie Visual Studio, und erstellen Sie ein neues Projekt **Windows Forms app (.NET Framework)** in C# Visual Basic `HostingWpf`oder Visual mit dem Namen.

> [!NOTE]
> Beim Hosten von WPF-Inhalt werden nur C#- und Visual Basic-Projekte unterstützt.

## <a name="create-a-new-wpf-control"></a>Erstellen eines neuen WPF-Steuer Elements

Das Erstellen eines neuen WPF-Steuerelements und das Hinzufügen des Steuerelements zum Projekt ist genauso einfach wie das Hinzufügen eines beliebigen anderen Elements zum Projekt. Der Windows Forms-Designer funktioniert mit einer bestimmten Art von Steuerelement, das als zusammen *gesetztes Steuer*Element oder *Benutzer Steuer*Element bezeichnet wird Weitere Informationen zu benutzerdefinierten WPF-Steuerelementen finden Sie unter <xref:System.Windows.Controls.UserControl>.

> [!NOTE]
> Der <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>-Typ für WPF unterscheidet sich vom Windows Forms-Benutzersteuerelementtyp, der ebenfalls den Namen <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType> hat.

So erstellen Sie ein neues WPF-Steuerelement:

1. Fügen Sie in **Projektmappen-Explorer**der Projekt Mappe ein neues Projekt für eine **WPF-Benutzer Steuerelement Bibliothek (.NET Framework)** hinzu. Verwenden Sie den Standardnamen `WpfControlLibrary1` für die Steuerelementbibliothek. Der Standardname für das Steuerelement lautet `UserControl1.xaml`.

   Das Hinzufügen des neuen Steuer Elements hat die folgenden Auswirkungen:

   - Die Datei UserControl1.xaml wird hinzugefügt.

   - Die Datei UserControl1.XAML.cs (oder UserControl1. XAML. vb) wurde hinzugefügt. Diese Datei enthält das Code-Behind-Modell für Ereignishandler und andere Implementierungen.

   - Es werden Verweise auf die WPF-Assemblys hinzugefügt.

   - Die Datei UserControl1. XAML wird im WPF-Designer für Visual Studio geöffnet.

2. Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist.

3. Legen Sie im Fenster **Eigenschaften** den Wert <xref:System.Windows.FrameworkElement.Width%2A> der-Eigenschaft und der- <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaft auf 200 fest.

4. Ziehen Sie aus der **Toolbox**ein <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> -Steuerelement auf die Entwurfs Oberfläche.

5. Legen Sie im Fenster **Eigenschaften** den Wert <xref:System.Windows.Controls.TextBox.Text%2A> der-Eigenschaft auf **gehosteter Inhalt**fest.

   > [!NOTE]
   > Normalerweise sollten Sie anspruchsvolleren WPF-Inhalt hosten. <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>-Steuerelement wird hier nur zur Veranschaulichung verwendet.

6. Erstellen Sie das Projekt.

## <a name="add-a-wpf-control-to-a-windows-form"></a>Hinzufügen eines WPF-Steuer Elements zu einem Windows Form

Das neue WPF-Steuerelement kann jetzt im Formular verwendet werden. Windows Forms verwendet das <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement zum Hosten von WPF-Inhalt.

So fügen Sie einem Windows Form ein WPF-Steuerelement hinzu:

1. Öffnen Sie `Form1` im Windows Forms-Designer.

2. Suchen Sie in der **Toolbox**die Registerkarte mit der Bezeichnung **wpfusercontrollibrary WPF-Benutzer Steuerelemente**.

3. Ziehen Sie eine Instanz von `UserControl1` auf das Formular.

    - Ein <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement wird automatisch zum Hosten des WPF-Steuerelements auf dem Formular erstellt.

    - Das <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement hat `elementHost1` den Namen, <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> und im Fenster Eigenschaften wird die-Eigenschaft auf **UserControl1**festgelegt.

    - Verweise auf WPF-Assemblys werden dem Projekt hinzugefügt.

    - Das `elementHost1`-Steuerelement verfügt über einen Smarttagbereich, in dem die verfügbaren Hostingoptionen anzeigt werden.

4. Wählen Sie im Smarttagbereich **elemelthost Tasks** die Option in übergeordnetem **Container andocken**.

5. Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.

## <a name="next-steps"></a>Nächste Schritte

Windows Forms und WPF sind unterschiedliche Technologien, wurden aber für eine enge Zusammenarbeit entwickelt. Um die Darstellung und das Verhalten in Ihren Anwendungen zu Verb leisten, versuchen Sie Folgendes:

- Hosten eines Windows Forms-Steuerelements in einer WPF-Seite. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Hosting eines Windows Forms-Steuer Elements in](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)WPF.

- Übernehmen von visuellen Windows Forms-Stilen für den WPF-Inhalt. Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren von visuellen Stilen in einer Hybrid](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)Anwendung.

- Ändern des Stils des WPF-Inhalts. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Formatieren von WPF-Inhalt](walkthrough-styling-wpf-content.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migration und Interoperabilität](../../wpf/advanced/migration-and-interoperability.md)
- [Verwenden von WPF-Steuerelementen](using-wpf-controls.md)
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
