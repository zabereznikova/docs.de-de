---
title: "Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual&#160;C# | Microsoft Docs"
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
  - "Benutzerdefinierte Steuerelemente [C#]"
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Erstellen"
  - "Benutzersteuerelemente [C#]"
  - "Benutzersteuerelemente [Windows Forms], Erstellen mit Visual C#"
  - "UserControl-Klasse, Exemplarische Vorgehensweisen"
ms.assetid: f88481a8-c746-4a36-9479-374ce5f2e91f
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual&#160;C# #
Mit zusammengesetzten Steuerelementen können benutzerdefinierte grafische Benutzeroberflächen erstellt und wiederverwendet werden.  Es handelt sich hier im Wesentlichen um Komponenten mit visueller Darstellung.  Als solche können sie sich beispielsweise aus einem oder mehreren Steuerelementen, Komponenten oder Codeblöcken aus Windows Forms zusammensetzen, die die Funktionalität erweitern können, indem sie Benutzereingaben validieren, Anzeigeeigenschaften ändern und andere vom Autor angeforderte Aufgaben ausführen.  Zusammengesetzte Steuerelemente können auf die gleiche Weise in Windows Forms platziert werden wie andere Steuerelemente.  Im ersten Teil dieser exemplarischen Vorgehensweise erstellen Sie ein einfaches zusammengesetztes Steuerelement mit der Bezeichnung `ctlClock`.  Im zweiten Teil der exemplarischen Vorgehensweise erweitern Sie die Funktionalität von `ctlClock` durch Vererbung.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Erstellen des Projekts  
 Wenn Sie ein neues Projekt erstellen, geben Sie dessen Namen an, um Stammnamespace, Assemblyname und Projektname einzurichten und sicherzustellen, dass die Standardkomponente sich im richtigen Namespace befindet.  
  
#### So erstellen Sie die ctlClockLib\-Steuerelementbibliothek und das ctlClock\-Steuerelement  
  
1.  Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**, um das Dialogfeld **Neues Projekt** zu öffnen.  
  
2.  Wählen Sie aus der Liste der [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]\-Projekte die Projektvorlage **Windows Forms\-Steuerelementbibliothek**, geben Sie `ctlClockLib` in das Feld **Name** ein, und klicken Sie dann auf **OK**.  
  
     Der Projektname `ctlClockLib` wird standardmäßig auch dem Stammnamespace zugewiesen.  Der Stammnamespace wird dazu verwendet, die Namen der Komponenten in der Assembly zu qualifizieren.  Wenn beispielsweise zwei Assemblys Komponenten mit der Bezeichnung `ctlClock` bereitstellen, können Sie die zu verwendende `ctlClock`\-Komponente mit `ctlClockLib.ctlClock.`  angeben.  
  
3.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **UserControl1.cs**, und klicken Sie dann auf **Umbenennen**.  Ändern Sie den Dateinamen in `ctlClock.cs`.  Klicken Sie auf die Schaltfläche **Ja**, wenn Sie gefragt werden, ob Sie alle Verweise auf das Codeelement "UserControl1" umbenennen möchten.  
  
    > [!NOTE]
    >  Standardmäßig erben zusammengesetzte Steuerelemente von der vom System bereitgestellten <xref:System.Windows.Forms.UserControl>\-Klasse.  Die <xref:System.Windows.Forms.UserControl>\-Klasse stellt Funktionalität bereit, die von allen zusammengesetzten Steuerelementen benötigt wird, und implementiert Standardmethoden und \-eigenschaften.  
  
4.  Klicken Sie im Menü **Datei** auf **Alle speichern**, um das Projekt zu speichern.  
  
## Hinzufügen von Windows\-Steuerelementen und \-Komponenten zu zusammengesetzten Steuerelementen  
 Visuelle Oberflächen sind ein wesentlicher Bestandteil von zusammengesetzten Steuerelementen.  Sie werden implementiert, indem der Designeroberfläche eines oder mehrere Windows\-Steuerelemente hinzugefügt werden.  Im folgenden Beispiel werden Windows\-Steuerelemente in das zusammengesetzte Steuerelement integriert. Anschließend schreiben Sie Code, um Funktionen zu implementieren.  
  
#### So fügen Sie dem zusammengesetzten Steuerelement eine Beschriftung und einen Zeitgeber hinzu  
  
1.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **ctlClock.cs**, und wählen Sie **Designer anzeigen** aus.  
  
2.  Erweitern Sie in der **Toolbox** den Knoten **Allgemeine Steuerelemente**, und doppelklicken Sie dann auf **Label**.  
  
     Ein <xref:System.Windows.Forms.Label>\-Steuerelement mit dem Namen `label1` wird dem Steuerelement auf der Designeroberfläche hinzugefügt.  
  
3.  Klicken Sie im Designer auf **Label1**.  Legen Sie im Eigenschaftenfenster die folgenden Eigenschaften fest.  
  
    |Property|Ändern in|  
    |--------------|---------------|  
    |**Name**|`lblDisplay`|  
    |**Text**|`(leer)`|  
    |**TextAlign**|`MiddleCenter`|  
    |**Font.Size**|`14`|  
  
4.  Erweitern Sie in der **Toolbox** den Knoten **Komponenten**, und doppelklicken Sie dann auf **Timer**.  
  
     Da es sich beim <xref:System.Windows.Forms.Timer> um eine Komponente handelt, verfügt er zur Laufzeit über keine visuelle Darstellung.  Daher wird er nicht zusammen mit den Steuerelementen auf der Designeroberfläche angezeigt, sondern im **Komponenten\-Designer** \(eine Leiste am unteren Rand der Designeroberfläche\).  
  
5.  Klicken Sie im **Komponenten\-Designer** auf **timer1**, und legen Sie die <xref:System.Windows.Forms.Timer.Interval%2A>\-Eigenschaft auf `1000` und die <xref:System.Windows.Forms.Timer.Enabled%2A>\-Eigenschaft auf `true` fest.  
  
     Die <xref:System.Windows.Forms.Timer.Interval%2A>\-Eigenschaft steuert die Zählfrequenz der <xref:System.Windows.Forms.Timer>\-Komponente.  Für jeden Teilstrich von `timer1` wird der Code im `timer1_Tick`\-Ereignis ausgeführt.  Mit der `Interval`\-Eigenschaft legen Sie die Anzahl der Millisekunden zwischen den einzelnen Zählungen fest.  
  
6.  Doppelklicken Sie im **Komponenten\-Designer** auf **timer1**, um zum `timer1_Tick`\-Ereignis für `ctlClock` zu wechseln.  
  
7.  Ändern Sie den Code, sodass er dem folgendem Beispielcode gleicht.  Hierbei müssen Sie den Zugriffsmodifizierer von `private` in `protected` ändern.  
  
     \[C\#\]  
  
    ```  
    protected void timer1_Tick(object sender, System.EventArgs e)  
    {  
        // Causes the label to display the current time.  
        lblDisplay.Text = DateTime.Now.ToLongTimeString();   
    }  
    ```  
  
     Dieser Code zeigt die aktuelle Uhrzeit in `lblDisplay` an.  Da das Intervall von `timer1` auf `1000` festgelegt wurde, wird das Ereignis alle tausend Millisekunden ausgelöst, d. h. die Anzeige der aktuellen Uhrzeit wird einmal pro Sekunde aktualisiert.  
  
8.  Ändern Sie die Methode so, dass sie mit dem `virtual`\-Schlüsselwort überschrieben werden kann.  Weitere Informationen finden Sie im Abschnitt "Erben von einem zusammengesetzten Steuerelement" weiter unten.  
  
    ```  
    protected virtual void timer1_Tick(object sender, System.EventArgs e)  
    ```  
  
9. Klicken Sie im Menü **Datei** auf **Alle speichern**, um das Projekt zu speichern.  
  
## Hinzufügen von Eigenschaften zum zusammengesetzten Steuerelement  
 Das Clock\-Steuerelement kapselt nun ein <xref:System.Windows.Forms.Label>\-Steuerelement und eine <xref:System.Windows.Forms.Timer>\-Komponente, beide mit einem eigenen Satz von inhärenten Eigenschaften.  Während nachfolgende Benutzer des Steuerelements nicht auf die einzelnen Eigenschaften dieser Steuerelemente zugreifen können, sind Sie in der Lage, benutzerdefinierte Eigenschaften zu erstellen und verfügbar zu machen, indem Sie die entsprechenden Codeblöcke schreiben.  In der folgenden Prozedur fügen Sie dem Steuerelement Eigenschaften hinzu, die dem Benutzer ermöglichen, Hintergrund\- und Textfarbe zu ändern.  
  
#### So fügen Sie dem zusammengesetzten Steuerelement eine Eigenschaft hinzu  
  
1.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **ctlClock.cs**, und wählen Sie **Code anzeigen** aus.  
  
     Der **Code\-Editor** für das Steuerelement wird geöffnet.  
  
2.  Suchen Sie die `public partial class ctlClock`\-Anweisung.  Geben Sie unter der öffnenden Klammer \(`{)`\) den folgenden Code ein.  
  
     \[C\#\]  
  
    ```  
    private Color colFColor;  
    private Color colBColor;  
    ```  
  
     Durch diese Anweisungen werden die **Private**\-Variablen erstellt, die Sie zum Speichern der Werte für die zu erstellenden Eigenschaften verwenden.  
  
3.  Geben Sie unter den Variablendeklarationen aus Schritt 2 den folgenden Code ein.  
  
     \[C\#\]  
  
    ```  
    // Declares the name and type of the property.  
    public Color ClockBackColor  
    {  
        // Retrieves the value of the private variable colBColor.  
        get  
        {  
            return colBColor;  
        }  
        // Stores the selected value in the private variable colBColor, and   
        // updates the background color of the label control lblDisplay.  
        set  
        {  
            colBColor = value;  
            lblDisplay.BackColor = colBColor;     
        }  
    }  
    // Provides a similar set of instructions for the foreground color.  
    public Color ClockForeColor  
    {  
        get  
        {  
            return colFColor;  
        }  
        set  
        {  
            colFColor = value;  
            lblDisplay.ForeColor = colFColor;  
        }  
    }  
    ```  
  
     Dieser Code macht zwei benutzerdefinierte Eigenschaften \(`ClockForeColor` und `ClockBackColor`\) für nachfolgende Benutzer des Steuerelements verfügbar.  Die `get`\-Anweisung und die `set`\-Anweisung stellen Speicher zur Verfügung und ermöglichen das Abrufen des Eigenschaftswerts. Darüber hinaus enthalten sie Code, um eine der Eigenschaft angemessene Funktionalität zu implementieren.  
  
4.  Klicken Sie im Menü **Datei** auf **Alle speichern**, um das Projekt zu speichern.  
  
## Testen des Steuerelements  
 Steuerelemente sind keine eigenständigen Anwendungen und müssen daher in einem Container untergebracht werden.  Testen Sie das Laufzeitverhalten des Steuerelements, und probieren Sie seine Eigenschaften mit dem **UserControl\-Testcontainer** aus.  Weitere Informationen finden Sie unter [Gewusst wie: Testen des Laufzeitverhaltens eines UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
#### So testen Sie das Steuerelement  
  
1.  Drücken Sie F5, um das Projekt zu erstellen und das Steuerelement im **UserControl\-Testcontainer** auszuführen.  
  
2.  Suchen Sie im Eigenschaftenraster des Testcontainers die `ClockBackColor`\-Eigenschaft, und wählen Sie sie anschließend aus, um die Farbpalette anzuzeigen.  
  
3.  Klicken Sie auf eine Farbe.  
  
     Die Hintergrundfarbe des Steuerelements ändert sich entsprechend.  
  
4.  Mit dem gleichen Verfahren können Sie prüfen, ob die `ClockForeColor`\-Eigenschaft wie erwartet funktioniert.  
  
     In diesem Abschnitt und in den vorherigen Abschnitten wurde veranschaulicht, wie Komponenten und Windows\-Steuerelemente mit Code und Paketen kombiniert werden können, um in Form eines zusammengesetzten Steuerelements benutzerdefinierte Funktionalität zur Verfügung zu stellen.  Es wurde außerdem gezeigt, wie Eigenschaften in einem zusammengesetzten Steuerelement verfügbar gemacht werden und wie ein Steuerelement nach seiner Fertigstellung getestet wird.  Im folgenden Abschnitt erfahren Sie, wie geerbte zusammengesetzte Steuerelemente mithilfe von `ctlClock` als Basis entworfen werden.  
  
## Erben von einem zusammengesetzten Steuerelement  
 In den vorherigen Abschnitten haben Sie erfahren, wie Windows\-Steuerelemente, Komponenten und Code zu wiederverwendbaren zusammengesetzten Steuerelementen kombiniert werden.  Das zusammengesetzte Steuerelement kann nun bei der Erstellung weiterer Steuerelemente als Basis dienen.  Der Vorgang der Ableitung einer Klasse aus einer Basisklasse wird als *Vererbung* bezeichnet.  In diesem Abschnitt erstellen Sie ein zusammengesetztes Steuerelement mit der Bezeichnung `ctlAlarmClock`.  Dieses Steuerelement wird von `ctlClock`, seinem übergeordneten Steuerelement, abgeleitet.  Sie erfahren, wie die Funktionalität von `ctlClock` durch Überschreiben der übergeordneten Methoden und Hinzufügen neuer Methoden und Eigenschaften erweitert werden kann.  
  
 Der erste Schritt bei der Erstellung eines geerbten Steuerelements besteht in dessen Ableitung vom übergeordneten Element.  Bei diesem Vorgang wird ein neues Steuerelement erstellt, das über alle Eigenschaften, Methoden und grafischen Merkmale des übergeordneten Steuerelements verfügt, jedoch selbst auch als Basis für das Hinzufügen neuer oder geänderter Funktionalität dienen kann.  
  
#### So erstellen Sie das geerbte Steuerelement  
  
1.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **ctlClockLib**, zeigen Sie auf **Hinzufügen**, und klicken Sie dann auf **Benutzersteuerelement**.  
  
     Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.  
  
2.  Wählen Sie die Vorlage **Geerbtes Benutzersteuerelement** aus.  
  
3.  Geben Sie im Feld **Name** die Bezeichnung `ctlAlarmClock.cs` ein, und klicken Sie auf **Hinzufügen**.  
  
     Das Dialogfeld **Vererbungsauswahl** wird angezeigt.  
  
4.  Doppelklicken Sie unter **Komponentenname** auf **ctlClock**.  
  
5.  Durchsuchen Sie im Projektmappen\-Explorer die aktuellen Projekte.  
  
    > [!NOTE]
    >  Dem aktuellen Projekt wurde eine Datei mit dem Namen **ctlAlarmClock.cs** hinzugefügt.  
  
### Hinzufügen von Alarm\-Eigenschaften  
 Einem geerbten Steuerelement werden Eigenschaften auf die gleiche Weise hinzugefügt wie einem zusammengesetzten Steuerelement.  Nun fügen Sie mithilfe der Eigenschaftendeklarations\-Syntax dem Steuerelement zwei Eigenschaften hinzu: `AlarmTime` und `AlarmSet`. Die erste speichert den Wert, der Datum und Uhrzeit für das Auslösen des Alarms angibt; die zweite gibt an, ob der Alarm festgelegt wurde.  
  
##### So fügen Sie dem zusammengesetzten Steuerelement Eigenschaften hinzu  
  
1.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **ctlAlarmClock**, und wählen Sie **Code anzeigen** aus.  
  
2.  Suchen Sie die `public class`\-Anweisung.  Beachten Sie, dass das Steuerelement von `ctlClockLib.ctlClock` erbt.  Geben Sie unter der öffnenden Klammer \(`{)`\) den folgenden Code ein.  
  
     \[C\#\]  
  
    ```  
    private DateTime dteAlarmTime;  
    private bool blnAlarmSet;  
    // These properties will be declared as public to allow future   
    // developers to access them.  
    public DateTime AlarmTime  
    {  
        get  
        {  
            return dteAlarmTime;  
        }  
        set  
        {  
            dteAlarmTime = value;  
        }  
    }  
    public bool AlarmSet  
    {  
        get  
        {  
            return blnAlarmSet;  
        }  
        set  
        {  
            blnAlarmSet = value;  
        }  
    }  
    ```  
  
### Erweitern der grafischen Oberfläche des Steuerelements  
 Die visuelle Oberfläche des geerbten Steuerelements stimmt mit der des Steuerelements, von dem es erbt, überein.  Es besteht aus denselben konstituierenden Steuerelementen wie das übergeordnete Steuerelement, aber die Eigenschaften der konstituierenden Steuerelemente sind nur dann verfügbar, wenn sie speziell verfügbar gemacht wurden.  Die grafische Benutzeroberfläche eines geerbten zusammengesetzten Steuerelements kann auf dieselbe Weise ergänzt werden wie die eines anderen zusammengesetzten Steuerelements.  Der nächste Schritt beim Erweitern der grafischen Oberfläche ist das Hinzufügen eines **Label**\-Steuerelements, das beim Erreichen des Alarmzeitpunkts blinkt.  
  
##### So fügen Sie das Label\-Steuerelement hinzu  
  
1.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **ctlAlarmClock**, und wählen Sie **Designer anzeigen** aus.  
  
     Im Hauptfenster wird der Designer für `ctlAlarmClock` geöffnet.  
  
2.  Klicken Sie auf den Anzeigebereich des Steuerelements, und zeigen Sie das Eigenschaftenfenster an.  
  
    > [!NOTE]
    >  Zwar werden alle Eigenschaften angezeigt, diese sind jedoch abgeblendet.  Dies weist darauf hin, dass diese Eigenschaften `lblDisplay` angehören und im Eigenschaftenfenster weder geändert werden können noch zugänglich sind.  Standardmäßig sind Steuerelemente in einem zusammengesetzten Steuerelement `private`. Es gibt keine Möglichkeit, auf ihre Eigenschaften zuzugreifen.  
  
    > [!NOTE]
    >  Wenn nachfolgende Benutzer des zusammengesetzten Steuerelements Zugriff auf die internen Steuerelemente des Benutzersteuerelements haben sollen, müssen sie als `public` oder `protected` deklariert werden.  Mit dem passenden Code können Sie dann die Eigenschaften der im zusammengesetzten Steuerelement enthaltenen Steuerelemente festlegen und ändern.  
  
3.  Fügen Sie dem zusammengesetzten Steuerelement ein <xref:System.Windows.Forms.Label>\-Steuerelement hinzu.  
  
4.  Ziehen Sie das <xref:System.Windows.Forms.Label>\-Steuerelement mit der Maus direkt unter das Anzeigefeld.  Legen Sie im Eigenschaftenfenster die folgenden Eigenschaften fest.  
  
    |Property|Einstellung|  
    |--------------|-----------------|  
    |**Name**|`lblAlarm`|  
    |**Text**|Alarm\!|  
    |**TextAlign**|`MiddleCenter`|  
    |**Visible**|`false`|  
  
### Hinzufügen der Alarmfunktionalität  
 In den vorherigen Prozeduren haben Sie Eigenschaften und ein Steuerelement hinzugefügt, durch die die Alarmfunktionalität im zusammengesetzten Steuerelement aktiviert wird.  In dieser Prozedur wird Code hinzugefügt, um die aktuelle Uhrzeit mit der Alarmzeit zu vergleichen und einen Blinkalarm auszugeben, wenn beide Zeiten gleich sind.  Indem Sie die `timer1_Tick`\-Methode von `ctlClock` überschreiben und ihr zusätzlichen Code hinzufügen, erweitern Sie die Funktionalität von `ctlAlarmClock`, während die gesamte inhärente Funktionalität von `ctlClock` beibehalten bleibt.  
  
##### So überschreiben Sie die Timer1\_Tick\-Methode von "ctlClock"  
  
1.  Suchen Sie im **Code\-Editor** die `private bool blnAlarmSet;`\-Anweisung.  Fügen Sie direkt darunter die folgende Anweisung ein.  
  
     \[C\#\]  
  
    ```  
    private bool blnColorTicker;  
    ```  
  
2.  Suchen Sie im **Code\-Editor** am Ende der Klasse die schließende Klammer \(`})`\).  Fügen Sie direkt vor der Klammer den folgenden Code ein.  
  
     \[C\#\]  
  
    ```  
    protected override void timer1_Tick(object sender, System.EventArgs e)  
    {  
        // Calls the Timer1_Tick method of ctlClock.  
        base.timer1_Tick(sender, e);  
        // Checks to see if the alarm is set.  
        if (AlarmSet == false)  
            return;  
        else  
            // If the date, hour, and minute of the alarm time are the same as  
            // the current time, flash an alarm.   
        {  
            if (AlarmTime.Date == DateTime.Now.Date && AlarmTime.Hour ==   
                DateTime.Now.Hour && AlarmTime.Minute == DateTime.Now.Minute)  
            {  
                // Sets lblAlarmVisible to true, and changes the background color based on  
                // the value of blnColorTicker. The background color of the label   
                // will flash once per tick of the clock.  
                lblAlarm.Visible = true;  
                if (blnColorTicker == false)   
                {  
                    lblAlarm.BackColor = Color.Red;  
                    blnColorTicker = true;  
                }  
                else  
                {  
                    lblAlarm.BackColor = Color.Blue;  
                    blnColorTicker = false;  
                }  
            }  
            else  
            {  
                // Once the alarm has sounded for a minute, the label is made   
                // invisible again.  
                lblAlarm.Visible = false;  
            }  
        }  
    }  
    ```  
  
     Durch das Hinzufügen dieses Codes werden verschiedene Aufgaben ausgeführt.  Durch die `override`\-Anweisung wird das Steuerelement veranlasst, diese Methode anstelle der vom Basissteuerelement geerbten Methode zu verwenden.  Beim Aufrufen der Methode wird die überschriebene Methode aufgerufen, indem die `base.timer1_Tick`\-Anweisung aufgerufen wird. Dabei wird sichergestellt, dass alle Funktionen des ursprünglichen Steuerelements in diesem Steuerelement reproduziert werden.  Anschließend wird zusätzlicher Code ausgeführt, um die Alarmfunktionalität zu integrieren.  Sobald der Alarm ausgelöst wird, wird ein blinkendes Label\-Steuerelement angezeigt.  
  
     Das Alarmsteuerelement ist nun fast fertig.  Es muss nur noch eine Möglichkeit zum Deaktivieren des Alarms implementiert werden.  Hierzu fügen Sie der `lblAlarm_Click`\-Methode Code hinzu.  
  
##### So implementieren Sie die Methode zum Deaktivieren des Alarms  
  
1.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **ctlAlarmClock.cs**, und wählen Sie **Designer anzeigen** aus.  
  
     Der Designer wird geöffnet.  
  
2.  Fügen Sie dem Steuerelement eine Schaltfläche hinzu.  Legen Sie die Eigenschaften der Schaltfläche wie folgt fest.  
  
    |Property|Wert|  
    |--------------|----------|  
    |**Name**|`btnAlarmOff`|  
    |**Text**|Alarm deaktivieren|  
  
3.  Doppelklicken Sie im Designer auf **btnAlarmOff**.  
  
     Der **Code\-Editor** wird geöffnet und springt zur Zeile `private void btnAlarmOff_Click`.  
  
4.  Ändern Sie diese Methode, sodass sie etwa folgendermaßen lautet.  
  
     \[C\#\]  
  
    ```  
    private void btnAlarmOff_Click(object sender, System.EventArgs e)  
    {  
        // Turns off the alarm.  
        AlarmSet = false;  
        // Hides the flashing label.  
        lblAlarm.Visible = false;  
    }  
    ```  
  
5.  Klicken Sie im Menü **Datei** auf **Alle speichern**, um das Projekt zu speichern.  
  
### Verwenden des geerbten Steuerelements in einem Formular  
 Sie können das geerbte Steuerelement auf dieselbe Weise testen wie das Basisklassensteuerelement `ctlClock`: Drücken Sie F5, um das Projekt zu erstellen, und führen Sie das Steuerelement im **UserControl\-Testcontainer** aus.  Weitere Informationen finden Sie unter [Gewusst wie: Testen des Laufzeitverhaltens eines UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
 Um das Steuerelement verwenden zu können, müssen Sie es auf einem Formular hosten.  Wie normale zusammengesetzte Steuerelemente auch kann ein geerbtes zusammengesetztes Steuerelement nicht eigenständig ausgeführt werden, sondern muss in einem Formular oder einem anderen Container gehostet werden.  Da `ctlAlarmClock` über eine tiefer gehende Funktionalität verfügt, ist beim Test zusätzlicher Code erforderlich.  In dieser Prozedur wird ein einfaches Programm zum Testen der Funktionalität von `ctlAlarmClock` erstellt.  Sie werden Code zum Festlegen und Anzeigen der `AlarmTime`\-Eigenschaft von `ctlAlarmClock` schreiben und die enthaltenen Funktionen testen.  
  
##### So erstellen Sie das Steuerelement und fügen es einem Testformular hinzu  
  
1.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **ctlClockLib**, und wählen Sie **Erstellen** aus.  
  
2.  Fügen Sie der Projektmappe ein neues Projekt vom Typ **Windows\-Anwendung** hinzu, und nennen Sie es `Test`.  
  
3.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf den Knoten **Verweise** des Testprojekts.  Klicken Sie auf **Verweis hinzufügen**, um das Dialogfeld **Verweis hinzufügen** anzuzeigen.  Klicken Sie auf die Registerkarte **Projekte**.  Das `ctlClockLib`\-Projekt wird unter **Projektname** aufgeführt.  Doppelklicken Sie auf das Projekt, um dem Testprojekt den Verweis hinzuzufügen.  
  
4.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **Test**, und wählen Sie **Erstellen** aus.  
  
5.  Erweitern Sie in der **Toolbox** den Knoten **ctlClockLib Components**.  
  
6.  Doppelklicken Sie auf **ctlAlarmClock**, um dem Formular eine Kopie von `ctlAlarmClock` hinzuzufügen.  
  
7.  Suchen Sie in der **Toolbox** die Bezeichnung **DateTimePicker**, und doppelklicken Sie darauf, um dem Formular ein <xref:System.Windows.Forms.DateTimePicker>\-Steuerelement hinzuzufügen. Fügen Sie anschließend ein <xref:System.Windows.Forms.Label>\-Steuerelement hinzu, indem Sie auf **Label** doppelklicken.  
  
8.  Platzieren Sie die Steuerelemente mithilfe der Maus gut erreichbar auf dem Formular.  
  
9. Legen Sie die Eigenschaften dieser Steuerelemente wie folgt fest.  
  
    |Steuerelement|Property|Wert|  
    |-------------------|--------------|----------|  
    |`label1`|**Text**|`(leer)`|  
    ||**Name**|`lblTest`|  
    |`dateTimePicker1`|**Name**|`dtpTest`|  
    ||**Format**|<xref:System.Windows.Forms.DateTimePickerFormat>|  
  
10. Doppelklicken Sie im Designer auf **dtpTest**.  
  
     Der **Code\-Editor** wird bei `private void dtpTest_ValueChanged` geöffnet.  
  
11. Ändern Sie den Code, sodass er etwa folgendermaßen lautet.  
  
     \[C\#\]  
  
    ```  
    private void dtpTest_ValueChanged(object sender, System.EventArgs e)  
    {  
        ctlAlarmClock1.AlarmTime = dtpTest.Value;  
        ctlAlarmClock1.AlarmSet = true;  
        lblTest.Text = "Alarm Time is " +  
            ctlAlarmClock1.AlarmTime.ToShortTimeString();  
    }  
    ```  
  
12. Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **Test**, und wählen Sie **Als Startprojekt festlegen**.  
  
13. Klicken Sie im Menü **Debuggen** auf **Debuggen starten**.  
  
     Das Testprogramm wird gestartet.  Beachten Sie, dass die Uhrzeit im `ctlAlarmClock`\-Steuerelement aktualisiert und die Startzeit im <xref:System.Windows.Forms.DateTimePicker>\-Steuerelement angezeigt wird.  
  
14. Klicken Sie in <xref:System.Windows.Forms.DateTimePicker> auf die Stelle, an der die Minuten angezeigt werden.  
  
15. Geben Sie über die Tastatur einen Wert für die Minuten ein, der um eine Minute größer als die von `ctlAlarmClock` angezeigte aktuelle Zeitangabe ist.  
  
     Die Alarmzeit wird in `lblTest` angezeigt.  Warten Sie, bis die angezeigte Zeitangabe die Zeit der Alarmeinstellung erreicht hat.  Sobald die Zeiten identisch sind, beginnt `lblAlarm` zu blinken.  
  
16. Deaktivieren Sie die Alarmfunktion, indem Sie auf `btnAlarmOff` klicken.  Jetzt können Sie die Alarmeinstellung erneut vornehmen.  
  
     In dieser exemplarischen Vorgehensweise wurden einige wichtige Konzepte behandelt.  Sie wissen nun, wie durch Kombination von Steuerelementen und Komponenten in einem Container für zusammengesetzte Steuerelemente ein zusammengesetztes Steuerelement erstellt wird.  Sie haben gelernt, wie dem Steuerelement Eigenschaften hinzugefügt werden und wie Code zur Implementierung benutzerdefinierter Funktionalität geschrieben wird.  Im letzten Abschnitt haben Sie erfahren, wie die Funktionen eines beliebigen zusammengesetzten Steuerelements durch Vererbung erweitert werden und wie die Funktionalität von Hostmethoden durch Überschreiben geändert wird.  
  
## Siehe auch  
 [Arten von benutzerdefinierten Steuerelementen](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)   
 [Programming with Components](../Topic/Programming%20with%20Components.md)   
 [Component Authoring Walkthroughs](../Topic/Component%20Authoring%20Walkthroughs.md)   
 [Gewusst wie: Anzeigen eines Steuerelements im Dialogfeld "Toolboxelemente auswählen"](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)   
 [Exemplarische Vorgehensweise: Vererben von einem Windows Forms\-Steuerelement mit Visual C\#](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)