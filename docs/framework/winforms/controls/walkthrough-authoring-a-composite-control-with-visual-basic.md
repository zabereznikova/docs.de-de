---
title: 'Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual Basic'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Visual Basic]
- user controls [Visual Basic]
- UserControl class [Windows Forms], walkthroughs
- user controls [Windows Forms], creating with Visual Basic
- controls [Windows Forms], composite controls
- composite controls [Windows Forms], creating
- custom controls [Windows Forms], creating
ms.assetid: f50e270e-4db2-409a-8319-6db6ca5c7daf
ms.openlocfilehash: ddc18c571d65d95b8ffc84f9b7d84213e527689b
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2019
ms.locfileid: "56305817"
---
# <a name="walkthrough-authoring-a-composite-control-with-visual-basic"></a>Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual Basic
Zusammengesetzte Steuerelemente bieten eine Möglichkeit, mit der benutzerdefinierte grafische Schnittstellen erstellt und wiederverwendet werden können. Ein zusammengesetztes Steuerelement ist im wesentlichen eine Komponente mit visueller Darstellung. Daher können zusammengesetzte Steuerelemente aus einem oder mehr Windows Forms-Steuerelementen, Komponenten oder Codeblöcken bestehen. Diese erweitern die Funktionalität durch Validieren von Benutzereingaben, verändern Anzeigeeigenschaften oder führen andere vom Autor gewünschte Aufgaben aus. Zusammengesetzte Steuerelemente können genau wie andere Steuerelemente in Windows Forms platziert werden. Im ersten Teil dieser exemplarischen Vorgehensweise erstellen Sie ein einfaches zusammengesetztes Steuerelement namens `ctlClock`. Im zweiten Teil der exemplarischen Vorgehensweise erweitern Sie die Funktionalität von `ctlClock` durch Vererbung.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
 Geben Sie beim Erstellen des Projekts den Namen an, um den Stammnamespace, Assemblynamen und Projektnamen festzulegen und sicherzustellen, dass sich die Standardkomponente im richtigen Namespace befindet.  
  
#### <a name="to-create-the-ctlclocklib-control-library-and-the-ctlclock-control"></a>So erstellen Sie die ctlClockLib-Steuerelementbibliothek und das ctlClock-Steuerelement  
  
1.  Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**, um das Dialogfeld **Neues Projekt** zu öffnen.  
  
2.  Wählen Sie aus der Liste der Visual Basic-Projekte, die **Windows-Steuerelementbibliothek** Projekt aus, geben `ctlClockLib` in die **Namen** ein, und klicken Sie dann auf **OK**.  
  
     Der Projektname `ctlClockLib` wird standardmäßig auch dem Stammnamespace zugewiesen. Der Stammnamespace wird verwendet, um die Namen der Komponenten in der Assembly zu qualifizieren. Wenn z.B. zwei Assemblys Komponenten mit dem Namen `ctlClock` bereitstellen, können Sie Ihre `ctlClock`-Komponente mithilfe von `ctlClockLib.ctlClock.` überprüfen.  
  
3.  Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **UserControl1.vb** und klicken Sie dann auf **Umbenennen**. Ändern Sie den Dateinamen in `ctlClock.vb`. Klicken Sie auf die Schaltfläche **Ja**, wenn Sie gefragt werden, ob alle Verweise auf das Codeelement „UserControl1“ umbenannt werden sollen.  
  
    > [!NOTE]
    >  Standardmäßig erbt ein zusammengesetztes Steuerelement von der <xref:System.Windows.Forms.UserControl> Klasse, die vom System bereitgestellt werden. Die <xref:System.Windows.Forms.UserControl> Klasse bietet Funktionen, die von allen zusammengesetzten Steuerelementen benötigt und implementiert Standardmethoden und-Eigenschaften.  
  
4.  Klicken Sie im Menü **Datei** auf **Alles speichern**, um das Projekt zu speichern.  
  
## <a name="adding-windows-controls-and-components-to-the-composite-control"></a>Hinzufügen von Windows-Steuerelementen und -Komponenten zum zusammengesetzten Steuerelement  
 Eine visuelle Schnittstelle ist ein wesentlicher Bestandteil von zusammengesetzten Steuerelementen. Diese visuelle Schnittstelle wird durch das Hinzufügen eines oder mehrerer Windows-Steuerelemente zur Designeroberfläche implementiert. Im folgenden Beispiel integrieren Sie Windows-Steuerelemente in das zusammengesetzte Steuerelement und schreiben Code, um Funktionalität zu implementieren.  
  
#### <a name="to-add-a-label-and-a-timer-to-your-composite-control"></a>So fügen Sie eine Bezeichnung und einen Timer zum zusammengesetzten Steuerelement hinzu  
  
1.  Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **ctlClock.vb**, und wählen Sie **Designer anzeigen** aus.  
  
2.  Erweitern Sie in der Toolbox den Knoten **Allgemeine Steuerelemente**, und doppelklicken Sie dann auf **Bezeichnung**.  
  
     Ein <xref:System.Windows.Forms.Label> Steuerelement mit dem Namen `Label1` zu Ihrem Steuerelement auf der Designeroberfläche hinzugefügt wird.  
  
3.  Klicken Sie im Designer auf **Label1**. Legen Sie im Eigenschaftenfenster die folgenden Eigenschaften fest.  
  
    |Eigenschaft|Ändern in|  
    |--------------|---------------|  
    |**Name**|`lblDisplay`|  
    |**Text**|`(blank space)`|  
    |**TextAlign**|`MiddleCenter`|  
    |**Font.Size**|`14`|  
  
4.  Erweitern Sie in der **Toolbox** den Knoten **Komponenten**, und doppelklicken Sie dann auf **Timer**.  
  
     Da eine <xref:System.Windows.Forms.Timer> ist eine Komponente, zur Laufzeit keine visuelle Darstellung hat. Er wird daher nicht bei den Steuerelementen auf der Designeroberfläche angezeigt, sondern im Komponenten-Designer (eine Taskleiste am unteren Ende der Designeroberfläche).  
  
5.  Klicken Sie im Komponenten-Designer auf **Timer1**, und legen Sie dann die <xref:System.Windows.Forms.Timer.Interval%2A> Eigenschaft `1000` und die <xref:System.Windows.Forms.Timer.Enabled%2A> Eigenschaft, um `True`.  
  
     Die <xref:System.Windows.Forms.Timer.Interval%2A> Eigenschaft steuert die Häufigkeit, mit dem die Timer-Komponente Teilstriche. Bei jedem Tick von `Timer1` führt sie den Code im Ereignis `Timer1_Tick` aus. Das Intervall stellt die Anzahl von Millisekunden zwischen Ticks dar.  
  
6.  Doppelklicken Sie im Komponenten-Designer auf **Timer1**, um zum `Timer1_Tick`-Ereignis für `ctlClock` zu gelangen.  
  
7.  Ändern Sie den Code so, dass er folgendem Codebeispiel ähnelt. Achten Sie darauf, den Zugriffsmodifizierer von `Private` in `Protected` zu ändern.  
  
    ```vb  
    Protected Sub Timer1_Tick(ByVal sender As Object, ByVal e As _  
        System.EventArgs) Handles Timer1.Tick  
        ' Causes the label to display the current time.    
        lblDisplay.Text = Format(Now, "hh:mm:ss")  
    End Sub  
    ```  
  
     Durch diesen Code wird die aktuelle Zeit in `lblDisplay` angezeigt. Da das Intervall von `Timer1` auf `1000` festgelegt wurde, wird dieses Ereignis alle tausend Millisekunden ausgelöst. Dadurch wird die aktuelle Zeit jede Sekunde aktualisiert.  
  
8.  Ändern Sie die Methode so, dass sie überschreibbar ist. Weitere Informationen finden Sie im Abschnitt „Erben von Benutzersteuerelementen“.  
  
    ```vb  
    Protected Overridable Sub Timer1_Tick(ByVal sender As Object, ByVal _  
        e As System.EventArgs) Handles Timer1.Tick  
    ```  
  
9. Klicken Sie im Menü **Datei** auf **Alles speichern**, um das Projekt zu speichern.  
  
## <a name="adding-properties-to-the-composite-control"></a>Hinzufügen von Eigenschaften zum zusammengesetzten Steuerelement  
 Ihr Uhr-Steuerelement kapselt nun ein <xref:System.Windows.Forms.Label> Steuerelement und ein <xref:System.Windows.Forms.Timer> -Komponente, beide mit eigenen vererbten Eigenschaften. Während nachfolgende Benutzer des Steuerelements nicht auf die einzelnen Eigenschaften dieser Steuerelemente zugreifen können, können Sie benutzerdefinierte Eigenschaften durch Schreiben der geeigneten Codeblöcke erstellen und verfügbar machen. Im folgenden Vorgang fügen Sie Eigenschaften zum Steuerelement hinzu, die dem Benutzer ermöglichen, die Farbe des Hintergrunds und des Texts zu ändern.  
  
#### <a name="to-add-a-property-to-your-composite-control"></a>So fügen Sie eine Eigenschaft zum zusammengesetzten Steuerelement hinzu  
  
1.  Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **ctlClock.vb**, und klicken Sie auf **Code anzeigen**.  
  
     Der Code-Editor für das Steuerelement wird geöffnet.  
  
2.  Suchen Sie die Anweisung `Public Class ctlClock`. Geben Sie darunter den folgenden Code ein.  
  
    ```vb  
    Private colFColor as Color  
    Private colBColor as Color  
    ```  
  
     Diese Anweisungen erstellen die privaten Variablen, die Sie verwenden, um die Werte für die Eigenschaften zu speichern, die Sie gleich erstellen werden.  
  
3.  Fügen Sie den folgenden Code unter den variablen Deklarationen aus Schritt 2 ein.  
  
    ```vb  
    ' Declares the name and type of the property.  
    Property ClockBackColor() as Color  
        ' Retrieves the value of the private variable colBColor.  
        Get  
            Return colBColor  
        End Get  
        ' Stores the selected value in the private variable colBColor, and   
        ' updates the background color of the label control lblDisplay.  
        Set(ByVal value as Color)  
            colBColor = value  
            lblDisplay.BackColor = colBColor     
        End Set  
  
    End Property  
    ' Provides a similar set of instructions for the foreground color.  
    Property ClockForeColor() as Color  
        Get  
            Return colFColor  
        End Get  
        Set(ByVal value as Color)  
            colFColor = value  
            lblDisplay.ForeColor = colFColor  
        End Set  
    End Property  
    ```  
  
     Dieser Code stellt nachfolgenden Benutzern dieses Steuerelements zwei benutzerdefinierte Eigenschaften zur Verfügung, `ClockForeColor` und `ClockBackColor`, indem er die Anweisung `Property` aufruft. Die Anweisungen `Get` und `Set` ermöglichen das Speichern und Abrufen des Eigenschaftswerts sowie des Codes zum Implementieren der geeigneten Funktionalität der Eigenschaft.  
  
4.  Klicken Sie im Menü **Datei** auf **Alles speichern**, um das Projekt zu speichern.  
  
## <a name="testing-the-control"></a>Testen des Steuerelements  
 Steuerelemente sind keine eigenständigen Projekte. Sie müssen in einem Container gehostet werden. Testen Sie das Laufzeitverhalten Ihres Steuerelements, und überprüfen Sie die Eigenschaften im **UserControl-Testcontainer**. Weitere Informationen finden Sie unter [Vorgehensweise: Testen Sie das Laufzeitverhalten eines UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
#### <a name="to-test-your-control"></a>So testen Sie das Steuerelement  
  
1.  Drücken Sie F5, um das Projekt zu erstellen, und führen Sie das Steuerelement im **UserControl-Testcontainer** aus.  
  
2.  Wählen Sie im Eigenschaftenraster des Testcontainers die Eigenschaft `ClockBackColor` aus, und klicken Sie anschließend auf den Dropdownpfeil, um die Farbpalette anzuzeigen.  
  
3.  Wählen Sie eine Farbe aus, indem sie darauf klicken.  
  
     Die Hintergrundfarbe des Steuerelements ändert sich in die ausgewählte Farbe.  
  
4.  Verwenden Sie eine ähnliche Abfolge von Ereignissen, um zu überprüfen, ob die Eigenschaft `ClockForeColor` funktioniert wie erwartet.  
  
5.  Klicken Sie auf **Schließen**, um den **UserControl-Testcontainer** zu beenden.  
  
     In diesem Abschnitt und in den vorherigen Abschnitten haben Sie gesehen, wie Komponenten und Windows-Steuerelemente mit Code und Paketen kombiniert werden können, um benutzerdefinierte Funktionalität in Form eines zusammengesetzten Steuerelements zu bieten. Sie haben gelernt, Eigenschaften in Ihrem zusammengesetzten Steuerelement verfügbar zu machen, und das Steuerelement nach Abschluss zu überprüfen. Im nächsten Abschnitt erfahren Sie, wie man ein vererbtes zusammengesetztes Steuerelement mithilfe von `ctlClock` als Basis verwendet.  
  
## <a name="inheriting-from-a-composite-control"></a>Erben von einem zusammengesetzten Steuerelement  
 In den vorherigen Abschnitten haben Sie gelernt, wie man Windows-Steuerelemente, Komponenten und Code in wiederverwendbare zusammengesetzte Steuerelemente kombiniert. Das zusammengesetzte Steuerelement kann jetzt als Basis für die Erstellung anderer Steuerelemente verwendet werden. Der Vorgang, bei dem eine Klasse von einer Basisklasse abgeleitet wird, nennt man *Vererbung*. In diesem Abschnitt erstellen Sie ein zusammengesetztes Steuerelement namens `ctlAlarmClock`. Dieses Steuerelement wird von seinem übergeordneten Steuerelement, `ctlClock`, abgeleitet. Sie erfahren, wie Sie die Funktionalität von `ctlClock` durch Überschreiben der übergeordneten Methoden und Hinzufügen neuer Methoden und Eigenschaften erweitern können.  
  
 Der erste Schritt beim Erstellen eines geerbten Steuerelements ist das Ableiten vom übergeordneten Steuerelement. Diese Aktion erstellt ein neues Steuerelement, das über alle Eigenschaften, Methoden und grafischen Merkmale des übergeordneten Steuerelements verfügt, aber auch als Basis für das Hinzufügen neuer oder veränderter Funktionalität dienen kann.  
  
#### <a name="to-create-the-inherited-control"></a>So erstellen Sie das geerbte Steuerelement  
  
1.  Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **ctlClockLib**, zeigen Sie auf **Hinzufügen**, und klicken Sie anschließend auf **Benutzersteuerelement**.  
  
     Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.  
  
2.  Wählen Sie die Vorlage **Geerbtes Benutzersteuerelement**.  
  
3.  Geben Sie im Feld **Name** die Bezeichnung `ctlAlarmClock.vb` ein, und klicken Sie dann auf **Hinzufügen**.  
  
     Das Dialogfeld **Vererbungsauswahl** wird angezeigt.  
  
4.  Doppelklicken Sie unter **Komponentenname** auf **ctlClock**.  
  
5.  Durchsuchen Sie die aktuellen Projekte im Projektmappen-Explorer.  
  
    > [!NOTE]
    >  Eine Datei namens **ctlAlarmClock.vb** wurde zum aktuellen Projekt hinzugefügt.  
  
### <a name="adding-the-alarm-properties"></a>Hinzufügen von Wecker-Eigenschaften  
 Eigenschaften werden auf die gleiche Weise zu einem geerbten Steuerelement hinzugefügt wie zu einem zusammengesetzten Steuerelement. Sie verwenden jetzt die Syntax zum Deklarieren von Eigenschaften, um zwei Eigenschaften zu Ihrem Steuerelement hinzuzufügen: `AlarmTime`, wodurch der Wert des Datums und der Uhrzeit gespeichert wird, zu der der Wecker klingelt, und `AlarmSet`, die anzeigt, ob der Wecker eingestellt wurde.  
  
##### <a name="to-add-properties-to-your-composite-control"></a>So fügen Sie Eigenschaften zum zusammengesetzten Steuerelement hinzu  
  
1.  Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **ctlAlarmClock**, und klicken Sie dann auf **Code anzeigen**.  
  
2.  Suchen Sie die Klassendeklaration für das ctlAlarmClock-Steuerelement, das als `Public Class ctlAlarmClock` angezeigt wird.  Fügen Sie den folgenden Code in der Klassendeklaration ein.  
  
    ```vb  
    Private dteAlarmTime As Date  
    Private blnAlarmSet As Boolean  
    ' These properties will be declared as Public to allow future   
    ' developers to access them.  
    Public Property AlarmTime() As Date  
        Get  
            Return dteAlarmTime  
        End Get  
        Set(ByVal value as Date)  
            dteAlarmTime = value  
        End Set  
    End Property  
    Public Property AlarmSet() As Boolean  
        Get  
            Return blnAlarmSet  
        End Get  
        Set(ByVal value as Boolean)  
            blnAlarmSet = value  
        End Set  
    End Property  
    ```  
  
### <a name="adding-to-the-graphical-interface-of-the-control"></a>Hinzufügen zur grafischen Oberfläche des Steuerelements  
 Das geerbte Steuerelement verfügt über eine visuelle Schnittstelle, die mit dem Steuerelement identisch ist, von dem es erbt. Es verfügt über die gleichen konstituierenden Steuerelemente wie das übergeordnete Steuerelement. Allerdings sind die Eigenschaften der konstituierenden Steuerelemente nicht verfügbar, solange sie nicht explizit verfügbar gemacht werden. Sie können zur grafischen Schnittstelle des geerbten zusammengesetzten Steuerelements auf die gleiche Weise hinzufügen, wie Sie zu jedem anderen zusammengesetzten Steuerelement hinzufügen würden. Um den Vorgang fortzusetzen, zur visuellen Schnittstelle Ihres Weckers hinzuzufügen, fügen Sie ein Label-Steuerelement hinzu, das leuchtet, wenn der Wecker klingelt.  
  
##### <a name="to-add-the-label-control"></a>So fügen Sie das Label-Steuerelement hinzu  
  
1.  Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **ctlAlarmClock**, und klicken Sie auf **Designer anzeigen**.  
  
     Der Designer für `ctlAlarmClock` wird im Hauptfenster geöffnet.  
  
2.  Klicken Sie auf `lblDisplay` (der Anzeigebereich des Steuerelements), und zeigen Sie das Eigenschaftenfenster an.  
  
    > [!NOTE]
    >  Alle Eigenschaften werden angezeigt, sind aber abgeblendet. Das bedeutet, dass die Eigenschaften nativ zu `lblDisplay` sind, und dass sie nicht im Eigenschaftenfenster geändert oder auf sie zugegriffen werden können. Standardmäßig sind in einem zusammengesetzten Steuerelement enthaltene Steuerelemente `Private`, und es ist nicht möglich, auf ihre Eigenschaften zuzugreifen.  
  
    > [!NOTE]
    >  Wenn Sie möchten, dass nachfolgende Benutzer des zusammengesetzten Steuerelements Zugriff auf interne Steuerelemente haben, deklarieren Sie sie als `Public` oder `Protected`. Dadurch können Sie Eigenschaften von Steuerelementen, die in Ihrem zusammengesetzten Steuerelement enthalten sind, festlegen und ändern, indem Sie den entsprechenden Code verwenden.  
  
3.  Hinzufügen einer <xref:System.Windows.Forms.Label> Steuerelement zum zusammengesetzten Steuerelement.  
  
4.  Ziehen Sie mit der Maus die <xref:System.Windows.Forms.Label> -Steuerelement direkt unter das Anzeigefeld. Legen Sie im Eigenschaftenfenster die folgenden Eigenschaften fest.  
  
    |Eigenschaft|Einstellung|  
    |--------------|-------------|  
    |**Name**|`lblAlarm`|  
    |**Text**|**Alarm!**|  
    |**TextAlign**|`MiddleCenter`|  
    |**Visible**|`False`|  
  
### <a name="adding-the-alarm-functionality"></a>Hinzufügen der Wecker-Funktionalität  
 In den vorherigen Schritten haben Sie Eigenschaften und ein Steuerelement hinzugefügt, dass die Wecker-Funktionalität in Ihrem zusammengesetzten Steuerelement aktiviert. In diesem Verfahren fügen Sie Code hinzu, um die aktuelle Zeit mit der Weckzeit zu vergleichen, und bei Gleichheit einen Wecker klingeln und leuchten zu lassen. Durch Überschreiben der Methode `Timer1_Tick` von `ctlClock` und Hinzufügen von zusätzlichem Code erweitern Sie die Funktion von `ctlAlarmClock` während alle geerbten Funktionen von `ctlClock` erhalten bleiben.  
  
##### <a name="to-override-the-timer1tick-method-of-ctlclock"></a>So überschreiben Sie die Methode „Timer1_Tick“ von „ctlClock“  
  
1.  Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **ctlAlarmClock.vb**, und klicken Sie dann auf **Code anzeigen**.  
  
2.  Suchen Sie die `Private blnAlarmSet As Boolean`-Anweisung. Fügen Sie direkt darunter die folgende Anweisung hinzu.  
  
    ```vb  
    Dim blnColorTicker as Boolean  
    ```  
  
3.  Suchen Sie die `End Class` Anweisung unten auf der Seite. Fügen Sie direkt vor der Anweisung `End Class` den folgenden Code hinzu.  
  
    ```vb  
    Protected Overrides Sub Timer1_Tick(ByVal sender As Object, ByVal e _  
        As System.EventArgs)  
        ' Calls the Timer1_Tick method of ctlClock.  
        MyBase.Timer1_Tick(sender, e)  
        ' Checks to see if the Alarm is set.  
        If AlarmSet = False Then  
            Exit Sub  
        End If  
        ' If the date, hour, and minute of the alarm time are the same as  
        ' now, flash and beep an alarm.   
        If AlarmTime.Date = Now.Date And AlarmTime.Hour = Now.Hour And _  
            AlarmTime.Minute = Now.Minute Then  
            ' Sounds an audible beep.  
            Beep()  
            ' Sets lblAlarmVisible to True, and changes the background color based on the   
            ' value of blnColorTicker. The background color of the label will   
            ' flash once per tick of the clock.  
            lblAlarm.Visible = True  
            If blnColorTicker = False Then  
                lblAlarm.BackColor = Color.PeachPuff  
                blnColorTicker = True  
            Else  
                lblAlarm.BackColor = Color.Plum  
                blnColorTicker = False  
            End If  
        Else  
            ' Once the alarm has sounded for a minute, the label is made   
            ' invisible again.  
            lblAlarm.Visible = False  
        End If  
    End Sub  
    ```  
  
     Das Hinzufügen dieses Codes dient mehreren Zwecken. Die Anweisung `Overrides` weist das Steuerelement an, diese Methode statt der Methode zu verwenden, die vom Basissteuerelement geerbt wurde. Wenn diese Methode aufgerufen wird, ruft sie durch Aufruf der `MyBase.Timer1_Tick`-Anweisung die überschriebene Methode auf. Damit wird sichergestellt, dass die gesamte Funktionalität, die im ursprünglichen Steuerelement enthalten ist, in diesem Steuerelement reproduziert wird. Anschließend ruft sie zusätzlichen Code auf, um die Wecker-Funktionalität zu integrieren. Ein blinkendes Label-Steuerelement erscheint, wenn der Wecker ausgelöst wird, und ein hörbarer Signalton ertönt.  
  
    > [!NOTE]
    >  Da Sie einen geerbten Ereignishandler außer Kraft setzen, müssen Sie das Ereignis nicht mit dem Schlüsselwort `Handles` angeben. Das Ereignis ist bereits eingebunden. Sie überschreiben lediglich die Implementierung des Handlers.  
  
     Das Wecker-Steuerelement ist fast abgeschlossen. Sie müssen nur noch eine Möglichkeit zum Deaktivieren implementieren. Zu diesem Zweck fügen Sie Code zur Methode `lblAlarm_Click` hinzu.  
  
##### <a name="to-implement-the-shutoff-method"></a>So implementieren Sie die Methode zum Deaktivieren  
  
1.  Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **ctlAlarmClock.vb**, und klicken Sie dann auf **Designer anzeigen**.  
  
2.  Doppelklicken Sie im Designer auf **lblAlarm**. Der **Code-Editor** wird in der Zeile `Private Sub lblAlarm_Click` geöffnet.  
  
3.  Ändern Sie die Methode so, dass sie folgendem Code ähnelt.  
  
    ```vb  
    Private Sub lblAlarm_Click(ByVal sender As Object, ByVal e As _  
     System.EventArgs) Handles lblAlarm.Click  
        ' Turns off the alarm.  
        AlarmSet = False  
        ' Hides the flashing label.  
        lblAlarm.Visible = False  
    End Sub  
    ```  
  
4.  Klicken Sie im Menü **Datei** auf **Alles speichern**, um das Projekt zu speichern.  
  
### <a name="using-the-inherited-control-on-a-form"></a>Verwenden des geerbten Steuerelements in einem Formular  
 Sie können Ihr geerbte Steuerelement die gleiche Weise, wie Sie das Steuerelement Basisklasse getestet testen `ctlClock`: Drücken Sie F5, um das Projekt zu erstellen, und führen Sie das Steuerelement im **UserControl-Testcontainer** aus. Weitere Informationen finden Sie unter [Vorgehensweise: Testen Sie das Laufzeitverhalten eines UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
 Sie müssen das Steuerelement auf einem Formular hosten, um es verwenden zu können. Wie standardmäßige zusammengesetzten Steuerelemente kann ein geerbtes zusammengesetztes Steuerelement nicht alleine stehen und muss in einem Formular oder einem anderen Container gehostet werden. Da `ctlAlarmClock` über eine tiefer gehende Funktionalität verfügt, wird zusätzlicher Code für das Testen benötigt. In dieser Vorgehensweise schreiben Sie ein einfaches Programm, um die Funktionalität von `ctlAlarmClock` zu testen. Sie schreiben Code zum Einstellen und Anzeigen der Eigenschaft `AlarmTime` von `ctlAlarmClock` und testen die geerbten Funktionen.  
  
##### <a name="to-build-and-add-your-control-to-a-test-form"></a>So erstellen Sie ein Steuerelement und fügen es zu einem Testformular hinzu  
  
1.  Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **ctlClockLib**, und klicken Sie auf **Erstellen**.  
  
2.  Zeigen Sie im Menü **Datei** auf die Option **Hinzufügen**, und klicken Sie anschließend auf **Neues Projekt**.  
  
3.  Fügen Sie der Projektmappe ein neues **Windows-Anwendungsprojekt** mit dem Namen `Test` hinzu.  
  
     Das **Test**-Projekt wird zum Projektmappen-Explorer hinzugefügt.  
  
4.  Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf den Projektknoten `Test`, und klicken Sie anschließend auf **Verweis hinzufügen**, um das Dialogfeld **Verweis hinzufügen** anzuzeigen.  
  
5.  Klicken Sie auf die Registerkarte mit der Bezeichnung **Projekte**. Das Projekt **ctlClockLib** wird unter **Projektname** aufgelistet. Doppelklicken Sie auf **ctlClockLib**, um den Verweis auf das Testprojekt hinzuzufügen.  
  
6.  Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **Test**, und klicken Sie dann auf **Erstellen**.  
  
7.  Erweitern Sie in der **Toolbox** den Knoten **ctlClockLib Components**.  
  
8.  Doppelklicken Sie auf **ctlAlarmClock**, um eine Instanz von `ctlAlarmClock` zu Ihrem Formular hinzuzufügen.  
  
9. In der **Toolbox**, suchen, und doppelklicken Sie auf **DateTimePicker** Hinzufügen einer <xref:System.Windows.Forms.DateTimePicker> -Steuerelement auf das Formular, und fügen Sie dann eine <xref:System.Windows.Forms.Label> Steuerelement durch Doppelklicken auf **Bezeichnung**.  
  
10. Verwenden Sie die Maus, um das Steuerelement an einem geeigneten Ort auf dem Formular zu positionieren.  
  
11. Legen Sie die Eigenschaften dieser Steuerelemente wie folgt fest.  
  
    |Steuerelement|Eigenschaft|Wert|  
    |-------------|--------------|-----------|  
    |`label1`|**Text**|`(blank space)`|  
    ||**Name**|`lblTest`|  
    |`dateTimePicker1`|**Name**|`dtpTest`|  
    ||**Format**|<xref:System.Windows.Forms.DateTimePickerFormat.Time>|  
  
12. Doppelklicken Sie im Designer auf **dtpTest**.  
  
     Der **Code-Editor** für `Private Sub dtpTest_ValueChanged` wird geöffnet.  
  
13. Ändern Sie den Code so, dass er folgendem Beispiel ähnelt.  
  
    ```vb  
    Private Sub dtpTest_ValueChanged(ByVal sender As Object, ByVal e As _  
        System.EventArgs) Handles dtpTest.ValueChanged  
        ctlAlarmClock1.AlarmTime = dtpTest.Value  
        ctlAlarmClock1.AlarmSet = True  
        lblTest.Text = "Alarm Time is " & Format(ctlAlarmClock1.AlarmTime, _  
            "hh:mm")  
    End Sub  
    ```  
  
14. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **Test**, und klicken Sie anschließend auf **Als Startprojekt festlegen**.  
  
15. Klicken Sie im Menü **Debuggen** auf **Debuggen starten**.  
  
     Das Testprogramm wird gestartet. Beachten Sie, dass die aktuelle Uhrzeit, in aktualisiert wird der `ctlAlarmClock` -Steuerelement, und die Startzeit in angezeigt wird der <xref:System.Windows.Forms.DateTimePicker> Steuerelement.  
  
16. Klicken Sie auf die <xref:System.Windows.Forms.DateTimePicker> , in dem die Minuten der Stunde angezeigt werden.  
  
17. Legen Sie mithilfe der Tastatur einen Wert für die Minuten fest, der eine Minute höher ist als die aktuell von `ctlAlarmClock` angezeigte Zeit.  
  
     Die Zeit für die Einstellung des Weckers wird in `lblTest` angezeigt. Warten Sie, bis die angezeigte Zeit die für den Wecker eingestellte Zeit erreicht hat. Wenn die angezeigte Zeit die Zeit erreicht, auf die der Wecker eingestellt ist, ertönt ein Signalton und `lblAlarm` leuchtet.  
  
18. Deaktivieren Sie den Wecker, indem Sie auf `lblAlarm` klicken. Sie können den Wecker nun zurücksetzen.  
  
     In dieser exemplarischen Vorgehensweise wurden zahlreiche wichtige Konzepte behandelt. Sie haben gelernt, ein zusammengesetztes Steuerelement zu erstellen, indem Sie Steuerelemente und Komponenten in einem Container für zusammengesetzte Steuerelemente kombiniert haben. Sie haben gelernt, Eigenschaften zu Ihrem Steuerelement hinzuzufügen und Code für das Implementieren benutzerdefinierter Funktionalität zu schreiben. Im letzten Abschnitt haben Sie gelernt, die Funktionalität eines bestimmten zusammengesetzten Steuerelements durch Vererbung zu erweitern und die Funktionalität von Host-Methoden durch außer Kraft setzen dieser Methoden zu ändern.  
  
## <a name="see-also"></a>Siehe auch
- [Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
- [Vorgehensweise: Erstellen von zusammengesetzten Steuerelementen](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)
- [Vorgehensweise: Anzeigen eines Steuerelements in der Toolbox-Elemente-Dialogfeld "auswählen"](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
