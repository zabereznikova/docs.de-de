---
title: Neuen WPF-Inhalt auf Windows Forms erstellen
titleSuffix: ''
ms.date: 08/18/2018
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 69a0598b05d1b2bff84b203317d6d5a166ce109d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746388"
---
# <a name="walkthrough-create-new-wpf-content-on-windows-forms-at-design-time"></a>Exemplarische Vorgehensweise: Erstellen eines neuen WPF-Inhalts auf Windows Forms zur Entwurfszeit

In diesem Artikel erfahren Sie, wie Sie ein Windows Presentation Foundation-Steuerelement (WPF) für die Verwendung in Ihren Windows Forms basierten Anwendungen erstellen.

## <a name="prerequisites"></a>Erforderliche Komponenten

Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.

## <a name="create-the-project"></a>Erstellen eines Projekts

Öffnen Sie Visual Studio, und erstellen Sie ein neues Projekt für **Windows Forms-app (.NET Framework)** in Visual Basic oder Visual C# mit dem Namen `HostingWpf`.

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

3. Legen Sie im Fenster **Eigenschaften** den Wert der Eigenschaften <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> auf **200**fest.

4. Ziehen Sie aus der **Toolbox**ein <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>-Steuerelement auf die Entwurfs Oberfläche.

5. Legen Sie im Fenster **Eigenschaften** den Wert der <xref:System.Windows.Controls.TextBox.Text%2A>-Eigenschaft auf **gehosteter Inhalt**fest.

   > [!NOTE]
   > Normalerweise sollten Sie anspruchsvolleren WPF-Inhalt hosten. <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>-Steuerelement wird hier nur zur Veranschaulichung verwendet.

6. Erstellen Sie das Projekt.

## <a name="add-a-wpf-control-to-a-windows-form"></a>Hinzufügen eines WPF-Steuer Elements zu einem Windows Form

Das neue WPF-Steuerelement kann jetzt im Formular verwendet werden. Windows Forms verwendet das <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement zum Hosten von WPF-Inhalt.

So fügen Sie einem Windows Form ein WPF-Steuerelement hinzu:

1. Öffnen Sie `Form1` im Windows Forms-Designer.

2. Suchen Sie in der **Toolbox**die Registerkarte mit der Bezeichnung **wpfusercontrollibrary WPF-Benutzer Steuerelemente**.

3. Ziehen Sie eine Instanz von `UserControl1` auf das Formular.

    - Ein <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement wird automatisch zum Hosten des WPF-Steuerelements auf dem Formular erstellt.

    - Das <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement heißt `elementHost1` und im **Eigenschaften** Fenster sehen Sie, dass seine <xref:System.Windows.Forms.Integration.ElementHost.Child%2A>-Eigenschaft auf **UserControl1**festgelegt ist.

    - Verweise auf WPF-Assemblys werden dem Projekt hinzugefügt.

    - Das `elementHost1`-Steuerelement verfügt über einen Smarttagbereich, in dem die verfügbaren Hostingoptionen anzeigt werden.

4. Wählen Sie im Smarttagbereich **elemelthost Tasks** die Option in übergeordnetem **Container andocken**.

5. Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.

## <a name="next-steps"></a>Nächste Schritte

Windows Forms und WPF sind unterschiedliche Technologien, wurden aber für eine enge Zusammenarbeit entwickelt. Um die Darstellung und das Verhalten in Ihren Anwendungen zu Verb leisten, versuchen Sie Folgendes:

- Hosten eines Windows Forms-Steuerelements in einer WPF-Seite. Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Hosting eines Windows Forms-Steuer Elements in WPF](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).

- Übernehmen von visuellen Windows Forms-Stilen für den WPF-Inhalt. Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren von visuellen Stilen in einer Hybridanwendung](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).

- Ändern des Stils des WPF-Inhalts. Weitere Informationen finden Sie unter Exemplarische Vorgehensweise: Formatieren von [WPF-Inhalt](walkthrough-styling-wpf-content.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migration und Interoperabilität](../../wpf/advanced/migration-and-interoperability.md)
- [Verwenden von WPF-Steuerelementen](using-wpf-controls.md)
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
