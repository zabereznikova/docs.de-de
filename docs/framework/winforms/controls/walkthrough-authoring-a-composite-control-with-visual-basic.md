---
title: "Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Zusammengesetzte Steuerelemente, Erstellen"
  - "Steuerelemente [Windows Forms], Zusammengesetzte Steuerelemente"
  - "Benutzerdefinierte Steuerelemente [Visual Basic]"
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Erstellen"
  - "Benutzersteuerelemente [Visual Basic]"
  - "Benutzersteuerelemente [Windows Forms], Erstellen mit Visual Basic"
  - "UserControl-Klasse, Exemplarische Vorgehensweisen"
ms.assetid: f50e270e-4db2-409a-8319-6db6ca5c7daf
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual Basic
Mit zusammengesetzten Steuerelementen können benutzerdefinierte grafische Benutzeroberflächen erstellt und wiederverwendet werden.  Es handelt sich hier im Wesentlichen um Komponenten mit visueller Darstellung.  Als solche können sie sich beispielsweise aus einem oder mehreren Steuerelementen, Komponenten oder Codeblöcken aus Windows Forms zusammensetzen, die die Funktionalität erweitern können, indem sie Benutzereingaben validieren, Anzeigeeigenschaften ändern und andere vom Autor angeforderte Aufgaben ausführen.  Zusammengesetzte Steuerelemente können auf die gleiche Weise in Windows Forms platziert werden wie andere Steuerelemente.  Im ersten Teil dieser exemplarischen Vorgehensweise erstellen Sie ein einfaches zusammengesetztes Steuerelement mit der Bezeichnung `ctlClock`.  Im zweiten Teil der exemplarischen Vorgehensweise erweitern Sie die Funktionalität von `ctlClock` durch Vererbung.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Erstellen des Projekts  
 Wenn Sie ein neues Projekt erstellen, geben Sie dessen Namen an, um Stammnamespace, Assemblyname und Projektname einzurichten und sicherzustellen, dass die Standardkomponente sich im richtigen Namespace befindet.  
  
#### So erstellen Sie die ctlClockLib\-Steuerelementbibliothek und das ctlClock\-Steuerelement  
  
1.  Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**, um das Dialogfeld **Neues Projekt** zu öffnen.  
  
2.  Wählen Sie aus der Liste der [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]\-Projekte die Projektvorlage **Windows\-Steuerelementbibliothek** aus, geben Sie `ctlClockLib` in das Feld **Name** ein, und klicken Sie dann auf **OK**.  
  
     Der Projektname `ctlClockLib` wird standardmäßig auch dem Stammnamespace zugewiesen.  Der Stammnamespace wird dazu verwendet, die Namen der Komponenten in der Assembly zu qualifizieren.  Wenn beispielsweise zwei Assemblys Komponenten mit der Bezeichnung `ctlClock` bereitstellen, können Sie die zu verwendende `ctlClock`\-Komponente mit `ctlClockLib.ctlClock.`  angeben.  
  
3.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **UserControl1.vb**, und klicken Sie dann auf **Umbenennen**.  Ändern Sie den Dateinamen in `ctlClock.vb`.  Klicken Sie auf die Schaltfläche **Ja**, wenn Sie gefragt werden, ob Sie alle Verweise auf das Codeelement "UserControl1" umbenennen möchten.  
  
    > [!NOTE]
    >  Standardmäßig erben zusammengesetzte Steuerelemente von der vom System bereitgestellten <xref:System.Windows.Forms.UserControl>\-Klasse.  Die <xref:System.Windows.Forms.UserControl>\-Klasse stellt Funktionalität bereit, die von allen zusammengesetzten Steuerelementen benötigt wird, und implementiert Standardmethoden und \-eigenschaften.  
  
4.  Klicken Sie im Menü **Datei** auf **Alle speichern**, um das Projekt zu speichern.  
  
## Hinzufügen von Windows\-Steuerelementen und \-Komponenten zu zusammengesetzten Steuerelementen  
 Visuelle Oberflächen sind ein wesentlicher Bestandteil von zusammengesetzten Steuerelementen.  Sie werden implementiert, indem der Designeroberfläche eines oder mehrere Windows\-Steuerelemente hinzugefügt werden.  Im folgenden Beispiel werden Windows\-Steuerelemente in das zusammengesetzte Steuerelement integriert. Anschließend schreiben Sie Code, um Funktionen zu implementieren.  
  
#### So fügen Sie dem zusammengesetzten Steuerelement eine Beschriftung und einen Zeitgeber hinzu  
  
1.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **ctlClock.vb**, und wählen Sie **Designer anzeigen**.  
  
2.  Erweitern Sie in der Toolbox den Knoten **Allgemeine Steuerelemente**, und doppelklicken Sie anschließend auf **Label**.  
  
     Ein <xref:System.Windows.Forms.Label>\-Steuerelement mit dem Namen `Label1` wird dem Steuerelement auf der Designeroberfläche hinzugefügt.  
  
3.  Klicken Sie im Designer auf **Label1**.  Legen Sie im Eigenschaftenfenster die folgenden Eigenschaften fest.  
  
    |Property|Ändern in|  
    |--------------|---------------|  
    |**Name**|`lblDisplay`|  
    |**Text**|`(leer)`|  
    |**TextAlign**|`MiddleCenter`|  
    |**Font.Size**|`14`|  
  
4.  Erweitern Sie in der **Toolbox** den Knoten **Komponenten**, und doppelklicken Sie dann auf **Timer**.  
  
     Da es sich beim <xref:System.Windows.Forms.Timer> um eine Komponente handelt, verfügt er zur Laufzeit über keine visuelle Darstellung.  Daher wird er nicht zusammen mit den Steuerelementen auf der Designeroberfläche angezeigt, sondern im Komponenten\-Designer \(eine Leiste am unteren Rand der Designeroberfläche\).  
  
5.  Klicken Sie im Komponenten\-Designer auf **Timer1**, und legen Sie die <xref:System.Windows.Forms.Timer.Interval%2A>\-Eigenschaft auf `1000` und die <xref:System.Windows.Forms.Timer.Enabled%2A>\-Eigenschaft auf `True` fest.  
  
     Die <xref:System.Windows.Forms.Timer.Interval%2A>\-Eigenschaft steuert die Zählfrequenz der **Timer**\-Komponente.  Für jeden Teilstrich von `Timer1` wird der Code im `Timer1_Tick`\-Ereignis ausgeführt.  Mit der `Interval`\-Eigenschaft legen Sie die Anzahl der Millisekunden zwischen den einzelnen Zählungen fest.  
  
6.  Doppelklicken Sie im Komponenten\-Designer auf **Timer1**, um zum `Timer1_Tick`\-Ereignis für `ctlClock` zu wechseln.  
  
7.  Ändern Sie den Code, sodass er dem folgendem Beispielcode gleicht.  Hierbei müssen Sie den Zugriffsmodifizierer von `Private` in `Protected` ändern.  
  
     \[Visual Basic\]  
  
    ```  
    Protected Sub Timer1_Tick(ByVal sender As Object, ByVal e As _  
        System.EventArgs) Handles Timer1.Tick  
        ' Causes the label to display the current time.    
        lblDisplay.Text = Format(Now, "hh:mm:ss")  
    End Sub  
    ```  
  
     Dieser Code zeigt die aktuelle Uhrzeit in `lblDisplay` an.  Da das Intervall von `Timer1` auf `1000` festgelegt wurde, wird das Ereignis alle tausend Millisekunden ausgelöst, d. h., die Anzeige der aktuellen Uhrzeit wird einmal pro Sekunde aktualisiert.  
  
8.  Ändern Sie die Methode so, dass sie überschrieben werden kann.  Weitere Informationen finden Sie im Abschnitt "Erben von einem zusammengesetzten Steuerelement" weiter unten.  
  
     \[Visual Basic\]  
  
    ```  
    Protected Overridable Sub Timer1_Tick(ByVal sender As Object, ByVal _  
        e As System.EventArgs) Handles Timer1.Tick  
    ```  
  
9. Klicken Sie im Menü **Datei** auf **Alle speichern**, um das Projekt zu speichern.  
  
## Hinzufügen von Eigenschaften zum zusammengesetzten Steuerelement  
 Das Clock\-Steuerelement kapselt nun ein <xref:System.Windows.Forms.Label>\-Steuerelement und eine <xref:System.Windows.Forms.Timer>\-Komponente, beide mit einem eigenen Satz von inhärenten Eigenschaften.  Während nachfolgende Benutzer des Steuerelements nicht auf die einzelnen Eigenschaften dieser Steuerelemente zugreifen können, sind Sie in der Lage, benutzerdefinierte Eigenschaften zu erstellen und verfügbar zu machen, indem Sie die entsprechenden Codeblöcke schreiben.  In der folgenden Prozedur fügen Sie dem Steuerelement Eigenschaften hinzu, die dem Benutzer ermöglichen, Hintergrund\- und Textfarbe zu ändern.  
  
#### So fügen Sie dem zusammengesetzten Steuerelement eine Eigenschaft hinzu  
  
1.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **ctlClock.vb**, und wählen Sie **Code anzeigen**.  
  
     Der Code\-Editor für das Steuerelement wird geöffnet.  
  
2.  Suchen Sie die `Public Class ctlClock`\-Anweisung.  Fügen Sie darunter den folgenden Code ein.  
  
     \[Visual Basic\]  
  
    ```  
    Private colFColor as Color  
    Private colBColor as Color  
    ```  
  
     Durch diese Anweisungen werden die **Private**\-Variablen erstellt, die Sie zum Speichern der Werte für die zu erstellenden Eigenschaften verwenden.  
  
3.  Fügen Sie unter den Variablendeklarationen aus Schritt 2 den folgenden Code ein.  
  
     \[Visual Basic\]  
  
    ```  
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
  
     Dieser Code macht zwei benutzerdefinierte Eigenschaften \(`ClockForeColor` und `ClockBackColor`\) für nachfolgende Benutzer des Steuerelements verfügbar, indem er die `Property`\-Anweisung aufruft.  Die `Get`\-Anweisung und die `Set`\-Anweisung stellen Speicher zur Verfügung und ermöglichen das Abrufen des Eigenschaftswerts. Darüber hinaus enthalten sie Code, um eine der Eigenschaft angemessene Funktionalität zu implementieren.  
  
4.  Klicken Sie im Menü **Datei** auf **Alle speichern**, um das Projekt zu speichern.  
  
## Testen des Steuerelements  
 Steuerelemente sind keine eigenständigen Projekte und müssen daher in einem Container untergebracht werden.  Testen Sie das Laufzeitverhalten des Steuerelements, und probieren Sie seine Eigenschaften mit dem **UserControl\-Testcontainer** aus.  Weitere Informationen finden Sie unter [Gewusst wie: Testen des Laufzeitverhaltens eines UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
#### So testen Sie das Steuerelement  
  
1.  Drücken Sie F5, um das Projekt zu erstellen und das Steuerelement im **UserControl\-Testcontainer** auszuführen.  
  
2.  Wählen Sie im Eigenschaftenraster des Testcontainers die `ClockBackColor`\-Eigenschaft aus, und klicken Sie dann auf den Dropdownpfeil, um die Farbpalette einzublenden.  
  
3.  Klicken Sie auf eine Farbe.  
  
     Die Hintergrundfarbe des Steuerelements ändert sich entsprechend.  
  
4.  Mit dem gleichen Verfahren können Sie prüfen, ob die `ClockForeColor`\-Eigenschaft wie erwartet funktioniert.  
  
5.  Klicken Sie auf **Schließen**, um den **UserControl\-Testcontainer** zu schließen.  
  
     In diesem Abschnitt und in den vorherigen Abschnitten wurde veranschaulicht, wie Komponenten und Windows\-Steuerelemente mit Code und Paketen kombiniert werden können, um in Form eines zusammengesetzten Steuerelements benutzerdefinierte Funktionalität zur Verfügung zu stellen.  Es wurde außerdem gezeigt, wie Eigenschaften in einem zusammengesetzten Steuerelement verfügbar gemacht werden und wie ein Steuerelement nach seiner Fertigstellung getestet wird.  Im folgenden Abschnitt erfahren Sie, wie geerbte zusammengesetzte Steuerelemente mithilfe von `ctlClock` als Basis entworfen werden.  
  
## Erben von einem zusammengesetzten Steuerelement  
 In den vorherigen Abschnitten haben Sie erfahren, wie Windows\-Steuerelemente, Komponenten und Code zu wiederverwendbaren zusammengesetzten Steuerelementen kombiniert werden.  Das zusammengesetzte Steuerelement kann nun bei der Erstellung weiterer Steuerelemente als Basis dienen.  Der Vorgang der Ableitung einer Klasse aus einer Basisklasse wird als *Vererbung* bezeichnet.  In diesem Abschnitt erstellen Sie ein zusammengesetztes Steuerelement mit der Bezeichnung `ctlAlarmClock`.  Dieses Steuerelement wird von `ctlClock`, seinem übergeordneten Steuerelement, abgeleitet.  Sie erfahren, wie die Funktionalität von `ctlClock` durch Überschreiben der übergeordneten Methoden und Hinzufügen neuer Methoden und Eigenschaften erweitert werden kann.  
  
 Der erste Schritt bei der Erstellung eines geerbten Steuerelements besteht in dessen Ableitung vom übergeordneten Element.  Bei diesem Vorgang wird ein neues Steuerelement erstellt, das über alle Eigenschaften, Methoden und grafischen Merkmale des übergeordneten Steuerelements verfügt, jedoch selbst auch als Basis für das Hinzufügen neuer oder geänderter Funktionalität dienen kann.  
  
#### So erstellen Sie das geerbte Steuerelement  
  
1.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **ctlClockLib**, zeigen Sie auf **Hinzufügen**, und klicken Sie dann auf **Benutzersteuerelement**.  
  
     Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.  
  
2.  Wählen Sie die Vorlage **Geerbtes Benutzersteuerelement** aus.  
  
3.  Geben Sie im Feld **Name** die Bezeichnung `ctlAlarmClock.vb` ein, und klicken Sie auf **Hinzufügen**.  
  
     Das Dialogfeld **Vererbungsauswahl** wird angezeigt.  
  
4.  Doppelklicken Sie unter **Komponentenname** auf **ctlClock**.  
  
5.  Durchsuchen Sie im Projektmappen\-Explorer die aktuellen Projekte.  
  
    > [!NOTE]
    >  Dem aktuellen Projekt wurde eine Datei mit dem Namen **ctlAlarmClock.vb** hinzugefügt.  
  
### Hinzufügen von Alarm\-Eigenschaften  
 Einem geerbten Steuerelement werden Eigenschaften auf die gleiche Weise hinzugefügt wie einem zusammengesetzten Steuerelement.  Nun fügen Sie mithilfe der Eigenschaftendeklarations\-Syntax dem Steuerelement zwei Eigenschaften hinzu: `AlarmTime` und `AlarmSet`. Die erste speichert den Wert, der Datum und Uhrzeit für das Auslösen des Alarms angibt; die zweite gibt an, ob der Alarm festgelegt wurde.  
  
##### So fügen Sie dem zusammengesetzten Steuerelement Eigenschaften hinzu  
  
1.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **ctlAlarmClock**, und wählen Sie **Code anzeigen** aus.  
  
2.  Suchen Sie die Klassendeklaration für das ctlAlarmClock\-Steuerelement, das als `Public Class ctlAlarmClock` angezeigt wird.  Fügen Sie folgenden Code in die Klassendeklaration ein.  
  
     \[Visual Basic\]  
  
    ```  
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
  
### Erweitern der grafischen Oberfläche des Steuerelements  
 Die visuelle Oberfläche des geerbten Steuerelements stimmt mit der des Steuerelements, von dem es erbt, überein.  Es besteht aus denselben konstituierenden Steuerelementen wie das übergeordnete Steuerelement, aber die Eigenschaften der konstituierenden Steuerelemente sind nur dann verfügbar, wenn sie speziell verfügbar gemacht wurden.  Die grafische Benutzeroberfläche eines geerbten zusammengesetzten Steuerelements kann auf dieselbe Weise ergänzt werden wie die eines anderen zusammengesetzten Steuerelements.  Der nächste Schritt beim Erweitern der grafischen Oberfläche ist das Hinzufügen eines **Label**\-Steuerelements, das beim Erreichen des Alarmzeitpunkts blinkt.  
  
##### So fügen Sie das Label\-Steuerelement hinzu  
  
1.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **ctlAlarmClock**, und wählen Sie **Designer anzeigen** aus.  
  
     Im Hauptfenster wird der Designer für `ctlAlarmClock` geöffnet.  
  
2.  Klicken Sie auf `lblDisplay` \(den Anzeigebereich des Steuerelements\), und zeigen Sie das Eigenschaftenfenster an.  
  
    > [!NOTE]
    >  Zwar werden alle Eigenschaften angezeigt, diese sind jedoch abgeblendet.  Dies weist darauf hin, dass diese Eigenschaften `lblDisplay` angehören und im Eigenschaftenfenster weder geändert werden können noch zugänglich sind.  Standardmäßig sind Steuerelemente in einem zusammengesetzten Steuerelement `Private`. Es gibt keine Möglichkeit, auf ihre Eigenschaften zuzugreifen.  
  
    > [!NOTE]
    >  Wenn nachfolgende Benutzer des zusammengesetzten Steuerelements Zugriff auf die internen Steuerelemente des Benutzersteuerelements haben sollen, müssen sie als `Public` oder `Protected` deklariert werden.  Mit dem passenden Code können Sie dann die Eigenschaften der im zusammengesetzten Steuerelement enthaltenen Steuerelemente festlegen und ändern.  
  
3.  Fügen Sie dem zusammengesetzten Steuerelement ein <xref:System.Windows.Forms.Label>\-Steuerelement hinzu.  
  
4.  Ziehen Sie das <xref:System.Windows.Forms.Label>\-Steuerelement mit der Maus direkt unter das Anzeigefeld.  Legen Sie im Eigenschaftenfenster die folgenden Eigenschaften fest.  
  
    |Property|Einstellung|  
    |--------------|-----------------|  
    |**Name**|`lblAlarm`|  
    |**Text**|Alarm\!|  
    |**TextAlign**|`MiddleCenter`|  
    |**Visible**|`False`|  
  
### Hinzufügen der Alarmfunktionalität  
 In den vorherigen Prozeduren haben Sie Eigenschaften und ein Steuerelement hinzugefügt, durch die die Alarmfunktionalität im zusammengesetzten Steuerelement aktiviert wird.  In dieser Prozedur fügen Sie Code hinzu, um die aktuelle und die Alarmzeit miteinander zu vergleichen und im Falle der Übereinstimmung ein Alarmsignal blinken und ertönen zu lassen.  Indem Sie die `Timer1_Tick`\-Methode von `ctlClock` überschreiben und ihr zusätzlichen Code hinzufügen, erweitern Sie die Funktionalität von `ctlAlarmClock`, während die gesamte inhärente Funktionalität von `ctlClock` beibehalten bleibt.  
  
##### So überschreiben Sie die Timer1\_Tick\-Methode von ctlClock  
  
1.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **ctlAlarmClock.vb**, und wählen Sie **Code anzeigen** aus.  
  
2.  Suchen Sie die `Private blnAlarmSet As Boolean`\-Anweisung.  Fügen Sie direkt darunter die folgende Anweisung ein.  
  
     \[Visual Basic\]  
  
    ```  
    Dim blnColorTicker as Boolean  
    ```  
  
3.  Suchen Sie die `End Class`\-Anweisung unten auf der Seite.  Fügen Sie den folgenden Code direkt vor der `End Class`\-Anweisung ein.  
  
     \[Visual Basic\]  
  
    ```  
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
  
     Durch das Hinzufügen dieses Codes werden verschiedene Aufgaben ausgeführt.  Durch die `Overrides`\-Anweisung wird das Steuerelement veranlasst, diese Methode anstelle der vom Basissteuerelement geerbten Methode zu verwenden.  Beim Aufrufen der Methode wird die überschriebene Methode aufgerufen, indem die `MyBase.Timer1_Tick`\-Anweisung aufgerufen wird. Dabei wird sichergestellt, dass alle Funktionen des ursprünglichen Steuerelements in diesem Steuerelement reproduziert werden.  Anschließend wird zusätzlicher Code ausgeführt, um die Alarmfunktionalität zu integrieren.  Wenn der Alarm einsetzt, sehen Sie ein blinkendes Label\-Steuerelement und hören einen Signalton.  
  
    > [!NOTE]
    >  Da ein geerbter Ereignishandler überschrieben wird, müssen Sie das Ereignis nicht mithilfe des `Handles`\-Schlüsselworts festlegen.  Der Ereignishandler wurde bereits verknüpft.  Es wird lediglich die Implementierung des Handlers überschrieben.  
  
     Das Alarmsteuerelement ist nun fast fertig.  Es muss nur noch eine Möglichkeit zum Deaktivieren des Alarms implementiert werden.  Hierzu fügen Sie der `lblAlarm_Click`\-Methode Code hinzu.  
  
##### So implementieren Sie die Methode zum Deaktivieren des Alarms  
  
1.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **ctlAlarmClock.vb**, und wählen Sie **Designer anzeigen** aus.  
  
2.  Doppelklicken Sie im Designer auf **lblAlarm**.  Der **Code\-Editor** wird geöffnet und springt zur Zeile `Private Sub lblAlarm_Click`.  
  
3.  Ändern Sie diese Methode, sodass sie etwa folgendermaßen lautet.  
  
     \[Visual Basic\]  
  
    ```  
    Private Sub lblAlarm_Click(ByVal sender As Object, ByVal e As _  
     System.EventArgs) Handles lblAlarm.Click  
        ' Turns off the alarm.  
        AlarmSet = False  
        ' Hides the flashing label.  
        lblAlarm.Visible = False  
    End Sub  
    ```  
  
4.  Klicken Sie im Menü **Datei** auf **Alle speichern**, um das Projekt zu speichern.  
  
### Verwenden des geerbten Steuerelements in einem Formular  
 Sie können das geerbte Steuerelement auf dieselbe Weise testen wie das Basisklassensteuerelement `ctlClock`: Drücken Sie F5, um das Projekt zu erstellen, und führen Sie das Steuerelement im **UserControl\-Testcontainer** aus.  Weitere Informationen finden Sie unter [Gewusst wie: Testen des Laufzeitverhaltens eines UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
 Um das Steuerelement verwenden zu können, müssen Sie es auf einem Formular hosten.  Wie normale zusammengesetzte Steuerelemente auch kann ein geerbtes zusammengesetztes Steuerelement nicht eigenständig ausgeführt werden, sondern muss in einem Formular oder einem anderen Container gehostet werden.  Da `ctlAlarmClock` über eine tiefer gehende Funktionalität verfügt, ist beim Test zusätzlicher Code erforderlich.  In dieser Prozedur wird ein einfaches Programm zum Testen der Funktionalität von `ctlAlarmClock` erstellt.  Sie werden Code zum Festlegen und Anzeigen der `AlarmTime`\-Eigenschaft von `ctlAlarmClock` schreiben und die enthaltenen Funktionen testen.  
  
##### So erstellen Sie das Steuerelement und fügen es einem Testformular hinzu  
  
1.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **ctlClockLib**, und wählen Sie **Erstellen** aus.  
  
2.  Zeigen Sie im Menü **Datei** auf **Hinzufügen**, und klicken Sie auf **Neues Projekt**.  
  
3.  Fügen Sie der Projektmappe ein neues Projekt vom Typ **Windows\-Anwendung** hinzu, und nennen Sie es `Test`.  
  
     Das **Test**projekt wird dem Projektmappen\-Explorer hinzugefügt.  
  
4.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf den Projektknoten `Test`, und klicken Sie dann auf **Verweis hinzufügen**, um das Dialogfeld **Verweis hinzufügen** anzuzeigen.  
  
5.  Klicken Sie auf die Registerkarte **Projekte**.  Das Projekt **ctlClockLib** wird unter **Projektname** aufgeführt.  Doppelklicken Sie auf **ctlClockLib**, um den Verweis dem Testprojekt hinzuzufügen.  
  
6.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **Test**, und wählen Sie **Erstellen** aus.  
  
7.  Erweitern Sie in der **Toolbox** den Knoten **ctlClockLib Components**.  
  
8.  Doppelklicken Sie auf **ctlAlarmClock**, um dem Formular eine Instanz von `ctlAlarmClock` hinzuzufügen.  
  
9. Suchen Sie in der **Toolbox** die Bezeichnung **DateTimePicker**, und doppelklicken Sie darauf, um dem Formular ein <xref:System.Windows.Forms.DateTimePicker>\-Steuerelement hinzuzufügen. Fügen Sie anschließend ein <xref:System.Windows.Forms.Label>\-Steuerelement hinzu, indem Sie auf **Label** doppelklicken.  
  
10. Platzieren Sie die Steuerelemente mithilfe der Maus gut erreichbar auf dem Formular.  
  
11. Legen Sie die Eigenschaften dieser Steuerelemente wie folgt fest.  
  
    |Steuerelement|Property|Wert|  
    |-------------------|--------------|----------|  
    |`label1`|**Text**|`(leer)`|  
    ||**Name**|`lblTest`|  
    |`dateTimePicker1`|**Name**|`dtpTest`|  
    ||**Format**|<xref:System.Windows.Forms.DateTimePickerFormat>|  
  
12. Doppelklicken Sie im Designer auf **dtpTest**.  
  
     Der **Code\-Editor** wird bei `Private Sub dtpTest_ValueChanged` geöffnet.  
  
13. Ändern Sie den Code, sodass er etwa folgendermaßen lautet.  
  
     \[Visual Basic\]  
  
    ```  
    Private Sub dtpTest_ValueChanged(ByVal sender As Object, ByVal e As _  
        System.EventArgs) Handles dtpTest.ValueChanged  
        ctlAlarmClock1.AlarmTime = dtpTest.Value  
        ctlAlarmClock1.AlarmSet = True  
        lblTest.Text = "Alarm Time is " & Format(ctlAlarmClock1.AlarmTime, _  
            "hh:mm")  
    End Sub  
    ```  
  
14. Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **Test**, und wählen Sie **Als Startprojekt festlegen**.  
  
15. Klicken Sie im Menü **Debuggen** auf **Debuggen starten**.  
  
     Das Testprogramm wird gestartet.  Beachten Sie, dass die Uhrzeit im `ctlAlarmClock`\-Steuerelement aktualisiert und die Startzeit im <xref:System.Windows.Forms.DateTimePicker>\-Steuerelement angezeigt wird.  
  
16. Klicken Sie in <xref:System.Windows.Forms.DateTimePicker> auf die Stelle, an der die Minuten angezeigt werden.  
  
17. Geben Sie über die Tastatur einen Wert für die Minuten ein, der um eine Minute größer als die von `ctlAlarmClock` angezeigte aktuelle Zeitangabe ist.  
  
     Die Alarmzeit wird in `lblTest` angezeigt.  Warten Sie, bis die angezeigte Zeitangabe die Zeit der Alarmeinstellung erreicht hat.  Wenn die angezeigte Zeit die Zeit der Alarmeinstellung erreicht, hören Sie den Signalton, und `lblAlarm` blinkt.  
  
18. Deaktivieren Sie die Alarmfunktion, indem Sie auf `lblAlarm` klicken.  Jetzt können Sie die Alarmeinstellung erneut vornehmen.  
  
     In dieser exemplarischen Vorgehensweise wurden einige wichtige Konzepte behandelt.  Sie wissen nun, wie durch Kombination von Steuerelementen und Komponenten in einem Container für zusammengesetzte Steuerelemente ein zusammengesetztes Steuerelement erstellt wird.  Sie haben gelernt, wie dem Steuerelement Eigenschaften hinzugefügt werden und wie Code zur Implementierung benutzerdefinierter Funktionalität geschrieben wird.  Im letzten Abschnitt haben Sie erfahren, wie die Funktionen eines beliebigen zusammengesetzten Steuerelements durch Vererbung erweitert werden und wie die Funktionalität von Hostmethoden durch Überschreiben geändert wird.  
  
## Siehe auch  
 [Arten von benutzerdefinierten Steuerelementen](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)   
 [Gewusst wie: Erstellen von zusammengesetzten Steuerelementen](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)   
 [Gewusst wie: Anzeigen eines Steuerelements im Dialogfeld "Toolboxelemente auswählen"](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)   
 [Component Authoring Walkthroughs](../Topic/Component%20Authoring%20Walkthroughs.md)