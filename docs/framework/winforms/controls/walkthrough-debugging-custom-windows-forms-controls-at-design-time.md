---
title: 'Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit'
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
ms.openlocfilehash: 9bd3f822e5a1f8572ebb7f5991abccde904150b8
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717829"
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a>Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit
Wenn Sie ein benutzerdefiniertes Steuerelement erstellen, werden häufig finden Sie es erforderlich, um das Verhalten während der Entwurfszeit zu debuggen. Dies ist insbesondere dann, wenn Sie einen benutzerdefinierten Designer für das benutzerdefinierte Steuerelement erstellen. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen eine Windows Forms-Steuerelement, das Visual Studio-Entwurfszeitfunktionen nutzt](creating-a-wf-control-design-time-features.md).  
  
 Sie können Ihre benutzerdefinierten Steuerelemente mithilfe von Visual Studio debuggen, ebenso wie alle anderen .NET Framework-Klassen Sie debuggen. Der Unterschied besteht darin, dass Sie eine separate Instanz von Visual Studio debuggen, die das benutzerdefinierte Steuerelement Code ausgeführt wird  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen ein Windows Forms-Projekt, um Ihr benutzerdefiniertes Steuerelement zu hosten.  
  
-   Erstellen ein Steuerelementbibliothek-Projekt  
  
-   Hinzufügen einer Eigenschaft für Ihr benutzerdefiniertes Steuerelement  
  
-   Das benutzerdefinierte Steuerelement hinzufügen dem Formular host  
  
-   Einrichten des Projekts für das Debuggen zur Entwurfszeit  
  
-   Debuggen von benutzerdefinierten Steuerelements zur Entwurfszeit  
  
 Wenn Sie fertig sind, müssen Sie einen Überblick über die Aufgaben, die für das Debuggen eines benutzerdefinierten Steuerelements das Entwurfszeitverhalten erforderlich sind.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
 Der erste Schritt ist das Anwendungsprojekt zu erstellen. Sie können dieses Projekt zum Erstellen der Anwendung, die das benutzerdefinierte Steuerelement hostet.  
  
#### <a name="to-create-the-project"></a>So erstellen Sie das Projekt  
  
-   Erstellen Sie eine Windows-Anwendungsprojekt mit dem Namen "DebuggingExample" (**Datei** > **neu** > **Projekt**  >  **Visual C#-** oder **Visual Basic** > **Klassischer Desktop** > **Windows Forms-Anwendung**).  
  
## <a name="creating-a-control-library-project"></a>Erstellen ein Steuerelementbibliothek-Projekt  
 Der nächste Schritt ist das Steuerelementbibliothek-Projekt erstellen, und richten Sie das benutzerdefinierte Steuerelement.  
  
#### <a name="to-create-the-control-library-project"></a>Um die Steuerelementbibliothek-Projekt zu erstellen.  
  
1.  Hinzufügen einer **Windows-Steuerelementbibliothek** Projekt der Projektmappe.  
  
2.  Fügen Sie einen neuen **UserControl** dem DebugControlLibrary-Projekt. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen neuer Projektelemente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)). Weisen Sie der neuen Quelldatei einen Basisnamen "DebugControl".  
  
3.  Mithilfe der **Projektmappen-Explorer**, löschen Sie das standardmäßige Steuerelement des Projekts durch Löschen der Codedatei mit dem Basisnamen der "`UserControl1`". Weitere Informationen finden Sie unter [Vorgehensweise: Entfernen, löschen und Ausschließen von Elementen](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).  
  
4.  Erstellen Sie die Projektmappe.  
  
## <a name="checkpoint"></a>Checkpoint  
 Können Sie das benutzerdefinierte Steuerelement in an diesem Punkt werden die **Toolbox**.  
  
#### <a name="to-check-your-progress"></a>Um den Status zu überprüfen.  
  
-   Suchen Sie die neue Registerkarte **DebugControlLibrary Komponenten** und klicken Sie auf, um es auszuwählen. Wenn sie geöffnet wird, sehen Sie das Steuerelement als aufgeführt **DebugControl** mit dem Standardsymbol daneben.  
  
## <a name="adding-a-property-to-your-custom-control"></a>Hinzufügen einer Eigenschaft für Ihr benutzerdefiniertes Steuerelement  
 Um zu veranschaulichen, dass Ihr Code des benutzerdefinierten Steuerelements zur Entwurfszeit ausgeführt wird, Sie fügen eine Eigenschaft hinzu und legen Sie einen Haltepunkt im Code, der die Eigenschaft implementiert.  
  
#### <a name="to-add-a-property-to-your-custom-control"></a>Eine Eigenschaft für Ihr benutzerdefiniertes Steuerelement hinzufügen  
  
1.  Open **DebugControl** in die **Code-Editor**. Fügen Sie den folgenden Code zur Klassendefinition hinzu:  
  
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
  
2.  Erstellen Sie die Projektmappe.  
  
## <a name="adding-your-custom-control-to-the-host-form"></a>Das benutzerdefinierte Steuerelement hinzufügen dem Formular Host  
 Um das Verhalten während der Entwurfszeit des benutzerdefinierten Steuerelements zu debuggen, geben Sie eine Instanz der Klasse des benutzerdefinierten Steuerelements in einem Hostformular an.  
  
#### <a name="to-add-your-custom-control-to-the-host-form"></a>Das benutzerdefinierte Steuerelement dem Formular hinzu  
  
1.  Öffnen Sie im Projekt "DebuggingExample" Form1 im der **Windows Forms-Designer**.  
  
2.  In der **Toolbox**öffnen die **DebugControlLibrary Komponenten** Registerkarte, und ziehen Sie eine **DebugControl** Instanz auf das Formular.  
  
3.  Suchen der `DemoString` benutzerdefinierte Eigenschaft in der **Eigenschaften** Fenster. Beachten Sie, dass Sie den Wert ändern können, wie Sie eine andere Eigenschaft. Beachten Sie außerdem, dass bei der `DemoString` Eigenschaft ausgewählt ist, wird der Eigenschaftenwert Beschreibungszeichenfolge angezeigt wird, am unteren Rand der **Eigenschaften** Fenster.  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a>Einrichten des Projekts für das Debuggen zur Entwurfszeit  
 Um Entwurfszeitverhalten für das benutzerdefinierte Steuerelement zu debuggen, Debuggen Sie eine separate Instanz von Visual Studio, die das benutzerdefinierte Steuerelement Code ausgeführt wird.  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a>Zum Einrichten des Projekts für Design-Time-Debuggen  
  
1.  Mit der rechten Maustaste auf die **DebugControlLibrary** -Projekt in der **Projektmappen-Explorer** , und wählen Sie **Eigenschaften**.  
  
2.  In der **DebugControlLibrary** Eigenschaftenblatt, wählen die **Debuggen** Registerkarte.  
  
     In der **Startaktion** wählen Sie im Abschnitt **externes Programm starten**. Sie Debuggen eine separate Instanz von Visual Studio, klicken Sie auf die Auslassungspunkte (![VisualStudioEllipsesButton-bildschirmabbildung](../media/vbellipsesbutton.png "VbEllipsesButton")) Schaltfläche, um für die Visual Studio-IDE navigieren. Der Name der ausführbaren Datei ist **devenv.exe**, und wenn Sie am Standardspeicherort installiert haben, lautet %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.  
  
3.  Klicken Sie auf **OK**, um das Dialogfeld zu schließen.  
  
4.  Mit der rechten Maustaste die **DebugControlLibrary** Projekt, und wählen **als Startprojekt festlegen** So aktivieren Sie diese Konfiguration für Remotedebugging.  
  
## <a name="debugging-your-custom-control-at-design-time"></a>Debuggen von benutzerdefinierten Steuerelements zur Entwurfszeit  
 Jetzt können Sie Ihr benutzerdefinierte Steuerelement zu debuggen, während der Ausführung im Entwurfsmodus befindet. Wenn Sie die Debugsitzung starten, wird eine neue Instanz von Visual Studio erstellt werden, und Sie verwenden es zum Laden der Projektmappe "DebuggingExample". Wenn öffnen Sie Form1 in der **Formulardesigner**, eine Instanz des benutzerdefinierten Steuerelements erstellt werden, und die Ausführung beginnt.  
  
#### <a name="to-debug-your-custom-control-at-design-time"></a>So debuggen Sie das benutzerdefinierte Steuerelement zur Entwurfszeit  
  
1.  Öffnen der **DebugControl** Quelldatei in die **Code-Editor** und platzieren Sie einen Haltepunkt auf der `Set` Accessor die `DemoString` Eigenschaft.  
  
2.  Drücken Sie F5, um die Debugsitzung zu starten. Beachten Sie, dass eine neue Instanz von Visual Studio erstellt wird. Sie können zwischen den Instanzen auf zwei Arten unterschieden:  
  
    -   Die Debuginstanz enthält das Wort **ausführen** auf dessen eigener Titelleiste  
  
    -   Die Debuginstanz enthält die **starten** Schaltfläche seine **Debuggen** Symbolleiste deaktiviert  
  
     Der Haltepunkt wird in der Debuginstanz festgelegt.  
  
3.  Öffnen Sie in der neuen Instanz von Visual Studio die Projektmappe "DebuggingExample". Finden Sie die Projektmappe durch Auswahl **zuletzt geöffnete Projekte** aus der **Datei** Menü. Die Projektmappendatei "DebuggingExample.sln" wird als die zuletzt Datei verwendete aufgeführt.  
  
4.  Öffnen Sie Form1 in der **Formulardesigner** , und wählen Sie die **DebugControl** Steuerelement.  
  
5.  Ändern Sie den Wert der `DemoString` -Eigenschaft. Beachten Sie, dass Sie die Änderung zu übernehmen, die Debuginstanz von Visual Studio aktiviert und die Ausführung am Breakpoint hält. Können Sie Schritt für Schritt durch den Eigenschaftenaccessor ebenso wie Ihre anderen Code würde.  
  
6.  Wenn Sie mit der Debugsitzung abgeschlossen haben, können Sie beenden, schließen die gehostete Instanz von Visual Studio oder durch Klicken auf die **Debuggen beenden** Schaltfläche in der Debuginstanz.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Nun, dass Sie Ihre benutzerdefinierten Steuerelemente zur Entwurfszeit Debuggen können, gibt es viele Möglichkeiten zum Erweitern des Steuerelements-Interaktion mit Visual Studio-IDE.  
  
-   Können Sie die <xref:System.ComponentModel.Component.DesignMode%2A> Eigenschaft der <xref:System.ComponentModel.Component> Klasse zum Schreiben von Code, der nur zur Entwurfszeit ausgeführt wird. Ausführliche Informationen finden Sie unter <xref:System.ComponentModel.Component.DesignMode%2A>.  
  
-   Es gibt mehrere Attribute können Sie auf die Eigenschaften des Steuerelements zum Bearbeiten des benutzerdefinierten Steuerelements Interaktion mit dem Designer anwenden. Sie finden diese Attribute in der <xref:System.ComponentModel?displayProperty=nameWithType> Namespace.  
  
-   Sie können einen benutzerdefinierten Designer für das benutzerdefinierte Steuerelement schreiben. Dies bietet Ihnen vollständige Kontrolle über die entwurfsumgebung, die mithilfe der erweiterbaren Designer-Infrastruktur, die von Visual Studio verfügbar gemacht werden. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen eine Windows Forms-Steuerelement, das Visual Studio-Entwurfszeitfunktionen nutzt](creating-a-wf-control-design-time-features.md).  
  
## <a name="see-also"></a>Siehe auch
- [Exemplarische Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das von Visual Studio-Entwurfszeitfunktionen nutzt](creating-a-wf-control-design-time-features.md)
- [Vorgehensweise: Während der Entwurfszeit von Access Services](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171822(v=vs.120))
- [Vorgehensweise: Zugriff während der Entwurfszeit-Unterstützung in Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171827(v=vs.120))
