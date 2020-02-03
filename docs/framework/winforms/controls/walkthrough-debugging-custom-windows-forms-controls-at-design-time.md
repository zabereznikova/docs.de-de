---
title: Debuggen benutzerdefinierter Steuerelemente zur Entwurfszeit
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- custom controls [Windows Forms], walkthroughs
- visual editors
- debugging [Visual Studio], Windows Forms
- custom controls [Windows Forms], debugging
- designers
- controls [Windows Forms], debugging
- walkthroughs [Windows Forms], debugging
- design-time debugging
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d9e292a1219c24571bcb35db2fe357b0197c8812
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740188"
---
# <a name="walkthrough-debug-custom-windows-forms-controls-at-design-time"></a>Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen

Wenn Sie ein benutzerdefiniertes Steuerelement erstellen, ist es häufig erforderlich, das Entwurfszeit Verhalten zu debuggen. Dies trifft vor allem dann zu, wenn Sie einen benutzerdefinierten Designer für Ihr benutzerdefiniertes Steuerelement erstellen. Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Erstellen eines Windows Forms-Steuer Elements, das Visual Studio-Entwurfszeit Funktionen](creating-a-wf-control-design-time-features.md)nutzt.

Sie können Ihre benutzerdefinierten Steuerelemente mithilfe von Visual Studio debuggen, genauso wie Sie alle anderen .NET Framework Klassen debuggen. Der Unterschied besteht darin, dass Sie eine separate Instanz von Visual Studio debuggen, in der der Code des benutzerdefinierten Steuer Elements ausgeführt wird.

## <a name="create-the-project"></a>Erstellen des Projekts

Im ersten Schritt erstellen Sie das Anwendungsprojekt. Sie verwenden dieses Projekt, um die Anwendung zu erstellen, die das benutzerdefinierte Steuerelement hostet.

Erstellen Sie in Visual Studio ein Windows-Anwendungsprojekt, und nennen Sie es **DebuggingExample**.

## <a name="create-the-control-library-project"></a>Erstellen des Steuerelement Bibliothek-Projekts

1. Fügen Sie der Projekt Mappe ein **Windows-Steuerelement Bibliothek** -Projekt hinzu.

2. Fügen Sie dem Projekt "Debug Controller" ein neues **UserControl** -Element hinzu. Nennen Sie es "Debug **Control**".

3. Löschen Sie in **Projektmappen-Explorer**das Standard Steuerelement des Projekts, indem Sie die Codedatei mit dem Basisnamen UserControl1 löschen.

4. Erstellen Sie die Projektmappe.

## <a name="checkpoint"></a>Checkpoint

An diesem Punkt können Sie Ihr benutzerdefiniertes Steuerelement in der **Toolbox**sehen.

Um den Fortschritt zu überprüfen, suchen Sie die neue Registerkarte **DebugControlLibrary Components** , und klicken Sie, um Sie auszuwählen. Beim Öffnen wird das Steuerelement als "Debug **Control** " mit dem Standard Symbol neben diesem angezeigt.

## <a name="add-a-property-to-your-custom-control"></a>Hinzufügen einer Eigenschaft zu einem benutzerdefinierten Steuerelement

Um zu veranschaulichen, dass der Code des benutzerdefinierten Steuer Elements zur Entwurfszeit ausgeführt wird, fügen Sie eine Eigenschaft hinzu, und legen Sie einen Breakpoint im Code fest, der die Eigenschaft implementiert.

1. Öffnen Sie **DebugControl** im **Code-Editor**. Fügen Sie der Klassendefinition folgenden Code hinzu:

    ```vb
    Private demoStringValue As String = Nothing
    <BrowsableAttribute(true)>
    Public Property DemoString() As String

        Get
            Return Me.demoStringValue
        End Get

        Set(ByVal value As String)
            Me.demoStringValue = value
        End Set

    End Property
    ```

    ```csharp
    private string demoStringValue = null;
    [Browsable(true)]
    public string DemoString
    {
        get
        {
            return this.demoStringValue;
        }
        set
        {
            demoStringValue = value;
        }
    }
    ```

2. Erstellen Sie die Projektmappe.

## <a name="add-your-custom-control-to-the-host-form"></a>Hinzufügen des benutzerdefinierten Steuer Elements zum Host Formular

Um das Entwurfszeit Verhalten des benutzerdefinierten Steuer Elements zu debuggen, platzieren Sie eine Instanz der benutzerdefinierten Steuerelement Klasse auf einem Host Formular.

1. Öffnen Sie im Projekt "DebuggingExample" Form1 im **Windows Forms-Designer**.

2. Öffnen Sie in der **Toolbox**die Registerkarte **DebugControlLibrary Components** , und ziehen Sie eine **DebugControl** -Instanz auf das Formular.

3. Suchen Sie im **Eigenschaften** Fenster die Eigenschaft `DemoString` Benutzer definiert. Beachten Sie, dass Sie den Wert wie jede andere Eigenschaft ändern können. Beachten Sie auch, dass die Beschreibungs Zeichenfolge der Eigenschaft im unteren Bereich des Fensters **Eigenschaften** angezeigt wird, wenn die `DemoString`-Eigenschaft ausgewählt ist.

## <a name="set-up-the-project-for-design-time-debugging"></a>Einrichten des Projekts für das Debuggen zur Entwurfszeit

Um das Entwurfszeit Verhalten des benutzerdefinierten Steuer Elements zu debuggen, Debuggen Sie eine separate Instanz von Visual Studio, die den Code des benutzerdefinierten Steuer Elements ausgeführt.

1. Klicken Sie mit **Projektmappen-Explorer** der rechten Maustaste auf das Projekt Projekt Debug **Controller** , und wählen Sie **Eigenschaften**aus.

2. Wählen **Sie im Eigenschaften** Blatt **DebugControlLibrary die Registerkarte Debuggen** aus.

     Wählen Sie im Abschnitt **Start Aktion** die Option **externes Programm starten**aus. Sie Debuggen eine separate Instanz von Visual Studio, und klicken Sie auf die Schaltfläche mit den Auslassungs Punkten (![der Schaltfläche mit den Auslassungs Punkten (...) in der Eigenschaftenfenster von Visual Studio](./media/visual-studio-ellipsis-button.png)), um nach der Visual Studio-IDE zu suchen. Der Name der ausführbaren Datei lautet " **devenv. exe".** Wenn Sie am Standard Speicherort installiert haben, lautet der Pfad *% Program Files (x86)% \ Microsoft Visual studio\2019\\\<Edition > \Common7\IDE*.

3. Klicken Sie auf **OK**, um das Dialogfeld zu schließen.

4. Klicken Sie mit der rechten Maustaste auf das Projekt **DebugControlLibrary** , und wählen Sie **als Startprojekt festlegen** , um diese Debugkonfiguration zu aktivieren.

## <a name="debug-your-custom-control-at-design-time"></a>Debuggen des benutzerdefinierten Steuer Elements zur Entwurfszeit

Nun können Sie das benutzerdefinierte Steuerelement Debuggen, während es im Entwurfs Modus ausgeführt wird. Wenn Sie die Debugsitzung starten, wird eine neue Instanz von Visual Studio erstellt, und Sie verwenden Sie zum Laden der Projekt Mappe "DebuggingExample". Wenn Sie Form1 im Forms- **Designer**öffnen, wird eine Instanz des benutzerdefinierten Steuer Elements erstellt, und die Ausführung wird gestartet.

1. Öffnen Sie die **DebugControl** -Quelldatei im **Code-Editor** , und platzieren Sie einen Haltepunkt für den `Set`-Accessor der `DemoString`-Eigenschaft.

2. Drücken Sie **F5** , um die Debugsitzung zu starten. Es wird eine neue Instanz von Visual Studio erstellt. Es gibt zwei Möglichkeiten, um zwischen den Instanzen zu unterscheiden:

    - In der debugginginstanz wird das Wort in der Titelleiste **ausgeführt** .

    - Die debugginginstanz hat die Schaltfläche **Start** auf der debugsymbolleiste

   Der Breakpoint wird in der debugginginstanz festgelegt.

3. Öffnen Sie in der neuen Instanz von Visual Studio die Projekt Mappe "DebuggingExample". Sie können die Lösung problemlos finden, indem Sie im Menü **Datei** die Option **zuletzt verwendete Projekte** auswählen. Die Projektmappendatei "DebuggingExample. sln" wird als zuletzt verwendete Datei aufgeführt.

4. Öffnen Sie Form1 im **Forms-Designer** , und wählen Sie das Steuerelement Debug **Control** aus.

5. Ändern Sie den Wert der `DemoString` -Eigenschaft. Wenn Sie die Änderung ausführen, erhält die debugginginstanz von Visual Studio den Fokus, und die Ausführung wird am Haltepunkt angehalten. Sie können den Eigenschafts Accessor genau so wie jeden anderen Code in Einzelschritten durchlaufen.

6. Zum Beenden des Debuggens beenden Sie die gehostete Instanz von Visual Studio, oder wählen Sie in der debugginstanz die Schaltfläche **Debugging beenden**

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie Ihre benutzerdefinierten Steuerelemente zur Entwurfszeit debuggen können, gibt es viele Möglichkeiten, die Interaktion Ihres Steuer Elements mit der Visual Studio-IDE zu erweitern.

- Sie können die <xref:System.ComponentModel.Component.DesignMode%2A>-Eigenschaft der <xref:System.ComponentModel.Component>-Klasse verwenden, um Code zu schreiben, der nur zur Entwurfszeit ausgeführt wird. Ausführliche Informationen finden Sie unter <xref:System.ComponentModel.Component.DesignMode%2A>.

- Es gibt mehrere Attribute, die Sie auf die Eigenschaften des Steuer Elements anwenden können, um die Interaktion des benutzerdefinierten Steuer Elements mit dem Designer zu bearbeiten. Diese Attribute finden Sie im <xref:System.ComponentModel?displayProperty=nameWithType>-Namespace.

- Sie können einen benutzerdefinierten Designer für Ihr benutzerdefiniertes Steuerelement schreiben. Dadurch erhalten Sie die komplette Kontrolle über die Entwurfs Möglichkeiten mithilfe der erweiterbaren Designer Infrastruktur, die von Visual Studio verfügbar gemacht wird. Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Erstellen eines Windows Forms-Steuer Elements, das Visual Studio-Entwurfszeit Funktionen](creating-a-wf-control-design-time-features.md)nutzt.

## <a name="see-also"></a>Weitere Informationen

- [Exemplarische Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Visual Studio-Entwurfszeitfunktion nutzt](creating-a-wf-control-design-time-features.md)
