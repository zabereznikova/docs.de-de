---
title: 'Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual C#'
ms.date: 03/30/2017
dev_langs:
- CSharp
helpviewer_keywords:
- custom controls [C#]
- user controls [Windows Forms], creating with Visual C#
- UserControl class [Windows Forms], walkthroughs
- user controls [C#]
- custom controls [Windows Forms], creating
ms.assetid: f88481a8-c746-4a36-9479-374ce5f2e91f
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: c1d9be77550b1255a24120c68f20d25640e0ebdf
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460630"
---
# <a name="walkthrough-author-a-composite-control-with-c"></a>Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuer Elements mit C-\#

Zusammengesetzte Steuerelemente bieten eine Möglichkeit, mit der benutzerdefinierte grafische Schnittstellen erstellt und wiederverwendet werden können. Ein zusammengesetztes Steuerelement ist im wesentlichen eine Komponente mit visueller Darstellung. Daher können zusammengesetzte Steuerelemente aus einem oder mehr Windows Forms-Steuerelementen, Komponenten oder Codeblöcken bestehen. Diese erweitern die Funktionalität durch Validieren von Benutzereingaben, verändern Anzeigeeigenschaften oder führen andere vom Autor gewünschte Aufgaben aus. Zusammengesetzte Steuerelemente können genau wie andere Steuerelemente in Windows Forms platziert werden. Im ersten Teil dieser exemplarischen Vorgehensweise erstellen Sie ein einfaches zusammengesetztes Steuerelement namens `ctlClock`. Im zweiten Teil der exemplarischen Vorgehensweise erweitern Sie die Funktionalität von `ctlClock` durch Vererbung.

## <a name="create-the-project"></a>Erstellen des Projekts

Geben Sie beim Erstellen des Projekts den Namen an, um den Stammnamespace, Assemblynamen und Projektnamen festzulegen und sicherzustellen, dass sich die Standardkomponente im richtigen Namespace befindet.

### <a name="to-create-the-ctlclocklib-control-library-and-the-ctlclock-control"></a>So erstellen Sie die ctlClockLib-Steuerelementbibliothek und das ctlClock-Steuerelement

1. Erstellen Sie in Visual Studio ein neues **Windows Forms-Steuerelement Bibliothek** -Projekt, und nennen Sie es **ctlClockLib**.

     Der Projektname `ctlClockLib` wird standardmäßig auch dem Stammnamespace zugewiesen. Der Stammnamespace wird verwendet, um die Namen der Komponenten in der Assembly zu qualifizieren. Wenn z.B. zwei Assemblys Komponenten mit dem Namen `ctlClock` bereitstellen, können Sie Ihre `ctlClock`-Komponente mithilfe von `ctlClockLib.ctlClock.` überprüfen.

2. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **UserControl1.cs**, und klicken Sie dann auf **Umbenennen**. Ändern Sie den Dateinamen in `ctlClock.cs`. Klicken Sie auf die Schaltfläche **Ja**, wenn Sie gefragt werden, ob alle Verweise auf das Codeelement „UserControl1“ umbenannt werden sollen.

    > [!NOTE]
    > Standardmäßig erbt ein zusammengesetztes Steuerelement von der <xref:System.Windows.Forms.UserControl> Klasse, die vom System bereitgestellt wird. Die <xref:System.Windows.Forms.UserControl>-Klasse stellt die von allen zusammengesetzten Steuerelementen benötigte Funktionalität bereit und implementiert Standardmethoden und-Eigenschaften.

3. Klicken Sie im Menü **Datei** auf **Alles speichern**, um das Projekt zu speichern.

## <a name="add-windows-controls-and-components-to-the-composite-control"></a>Hinzufügen von Windows-Steuerelementen und Komponenten zum zusammengesetzten Steuerelement

Eine visuelle Schnittstelle ist ein wesentlicher Bestandteil von zusammengesetzten Steuerelementen. Diese visuelle Schnittstelle wird durch das Hinzufügen eines oder mehrerer Windows-Steuerelemente zur Designeroberfläche implementiert. Im folgenden Beispiel integrieren Sie Windows-Steuerelemente in das zusammengesetzte Steuerelement und schreiben Code, um Funktionalität zu implementieren.

### <a name="to-add-a-label-and-a-timer-to-your-composite-control"></a>So fügen Sie eine Bezeichnung und einen Timer zum zusammengesetzten Steuerelement hinzu

1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **ctlClock.cs**, und klicken Sie dann auf **Designer anzeigen**.

2. Erweitern Sie in der **Toolbox** den Knoten **Allgemeine Steuerelemente**, und doppelklicken Sie dann auf **Bezeichnung**.

     Ein <xref:System.Windows.Forms.Label>-Steuerelement mit dem Namen `label1` wird dem Steuerelement auf der Designer Oberfläche hinzugefügt.

3. Klicken Sie im Designer auf **label1**. Legen Sie im Eigenschaftenfenster die folgenden Eigenschaften fest.

    |property|Ändern in|
    |--------------|---------------|
    |**Name**|`lblDisplay`|
    |**Text**|`(blank space)`|
    |**TextAlign**|`MiddleCenter`|
    |**Font.Size**|`14`|

4. Erweitern Sie in der **Toolbox** den Knoten **Komponenten**, und doppelklicken Sie dann auf **Timer**.

     Da eine <xref:System.Windows.Forms.Timer> eine Komponente ist, hat Sie zur Laufzeit keine visuelle Darstellung. Er wird daher nicht bei den Steuerelementen auf der Designeroberfläche angezeigt, sondern im **Komponenten-Designer** (eine Taskleiste am unteren Ende der Designeroberfläche).

5. Klicken Sie im **Komponenten-Designer**auf **Timer1**, und legen Sie dann die Eigenschaft <xref:System.Windows.Forms.Timer.Interval%2A> auf `1000` und die Eigenschaft <xref:System.Windows.Forms.Timer.Enabled%2A> auf `true`fest.

     Die <xref:System.Windows.Forms.Timer.Interval%2A>-Eigenschaft steuert die Häufigkeit, mit der die <xref:System.Windows.Forms.Timer> Komponente Ticks. Bei jedem Tick von `timer1` führt sie den Code im Ereignis `timer1_Tick` aus. Das Intervall stellt die Anzahl von Millisekunden zwischen Ticks dar.

6. Doppelklicken Sie im **Komponenten-Designer** auf **timer1**, um zum `timer1_Tick`-Ereignis für `ctlClock` zu gelangen.

7. Ändern Sie den Code so, dass er folgendem Codebeispiel ähnelt. Achten Sie darauf, den Zugriffsmodifizierer von `private` in `protected` zu ändern.

    ```csharp
    protected void timer1_Tick(object sender, System.EventArgs e)
    {
        // Causes the label to display the current time.
        lblDisplay.Text = DateTime.Now.ToLongTimeString();
    }
    ```

     Durch diesen Code wird die aktuelle Zeit in `lblDisplay` angezeigt. Da das Intervall von `timer1` auf `1000` festgelegt wurde, wird dieses Ereignis alle tausend Millisekunden ausgelöst. Dadurch wird die aktuelle Zeit jede Sekunde aktualisiert.

8. Ändern Sie die Methode so, dass sie mit dem Schlüsselwort `virtual` überschreibbar ist. Weitere Informationen finden Sie im Abschnitt „Erben von Benutzersteuerelementen“.

    ```csharp
    protected virtual void timer1_Tick(object sender, System.EventArgs e)
    ```

9. Klicken Sie im Menü **Datei** auf **Alles speichern**, um das Projekt zu speichern.

## <a name="add-properties-to-the-composite-control"></a>Hinzufügen von Eigenschaften zum zusammengesetzten Steuerelement

Das Clock-Steuerelement kapselt nun ein <xref:System.Windows.Forms.Label>-Steuerelement und eine <xref:System.Windows.Forms.Timer>-Komponente, die jeweils über einen eigenen Satz inhärenter Eigenschaften verfügt. Während nachfolgende Benutzer des Steuerelements nicht auf die einzelnen Eigenschaften dieser Steuerelemente zugreifen können, können Sie benutzerdefinierte Eigenschaften durch Schreiben der geeigneten Codeblöcke erstellen und verfügbar machen. Im folgenden Vorgang fügen Sie Eigenschaften zum Steuerelement hinzu, die dem Benutzer ermöglichen, die Farbe des Hintergrunds und des Texts zu ändern.

### <a name="to-add-a-property-to-your-composite-control"></a>So fügen Sie eine Eigenschaft zum zusammengesetzten Steuerelement hinzu

1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **ctlClock.cs**, und klicken Sie dann auf **Code anzeigen**.

     Der **Code-Editor** für das Steuerelement wird geöffnet.

2. Suchen Sie die `public partial class ctlClock`-Anweisung. Geben Sie unter der öffnenden Klammer (`{)` den folgenden Code ein.

    ```csharp
    private Color colFColor;
    private Color colBColor;
    ```

     Diese Anweisungen erstellen die privaten Variablen, die Sie verwenden, um die Werte für die Eigenschaften zu speichern, die Sie gleich erstellen werden.

3. Geben oder fügen Sie den folgenden Code unter den Variablen Deklarationen aus Schritt 2 ein.

    ```csharp
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

     Dieser Code stellt nachfolgenden Benutzern dieses Steuerelements zwei benutzerdefinierte Eigenschaften zur Verfügung, `ClockForeColor` und `ClockBackColor`. Die Anweisungen `get` und `set` ermöglichen das Speichern und Abrufen des Eigenschaftswerts sowie des Codes zum Implementieren der geeigneten Funktionalität der Eigenschaft.

4. Klicken Sie im Menü **Datei** auf **Alles speichern**, um das Projekt zu speichern.

## <a name="test-the-control"></a>Testen des Steuer Elements

Steuerelemente sind keine eigenständigen Anwendungen. Sie müssen in einem Container gehostet werden. Testen Sie das Laufzeitverhalten Ihres Steuerelements, und überprüfen Sie die Eigenschaften im **UserControl-Testcontainer**. Weitere Informationen finden Sie unter [Vorgehensweise: Testen des Laufzeitverhaltens eines UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).

### <a name="to-test-your-control"></a>So testen Sie das Steuerelement

1. Drücken Sie **F5** , um das Projekt zu erstellen, und führen Sie das Steuerelement im **UserControl-Test Container**aus.

2. Suchen Sie im Eigenschaftenraster des Testcontainers die Eigenschaft `ClockBackColor`, und wählen Sie anschließend die Eigenschaft aus, um die Farbpalette anzuzeigen.

3. Wählen Sie eine Farbe aus, indem sie darauf klicken.

   Die Hintergrundfarbe des Steuerelements ändert sich in die ausgewählte Farbe.

4. Verwenden Sie eine ähnliche Abfolge von Ereignissen, um zu überprüfen, ob die Eigenschaft `ClockForeColor` funktioniert wie erwartet.

   In diesem Abschnitt und in den vorherigen Abschnitten haben Sie gesehen, wie Komponenten und Windows-Steuerelemente mit Code und Paketen kombiniert werden können, um benutzerdefinierte Funktionalität in Form eines zusammengesetzten Steuerelements zu bieten. Sie haben gelernt, Eigenschaften in Ihrem zusammengesetzten Steuerelement verfügbar zu machen, und das Steuerelement nach Abschluss zu überprüfen. Im nächsten Abschnitt erfahren Sie, wie man ein vererbtes zusammengesetztes Steuerelement mithilfe von `ctlClock` als Basis verwendet.

## <a name="inherit-from-a-composite-control"></a>Von einem zusammengesetzten Steuerelement erben

In den vorherigen Abschnitten haben Sie gelernt, wie man Windows-Steuerelemente, Komponenten und Code in wiederverwendbare zusammengesetzte Steuerelemente kombiniert. Das zusammengesetzte Steuerelement kann jetzt als Basis für die Erstellung anderer Steuerelemente verwendet werden. Der Vorgang, bei dem eine Klasse von einer Basisklasse abgeleitet wird, nennt man *Vererbung*. In diesem Abschnitt erstellen Sie ein zusammengesetztes Steuerelement namens `ctlAlarmClock`. Dieses Steuerelement wird von seinem übergeordneten Steuerelement, `ctlClock`, abgeleitet. Sie erfahren, wie Sie die Funktionalität von `ctlClock` durch Überschreiben der übergeordneten Methoden und Hinzufügen neuer Methoden und Eigenschaften erweitern können.

Der erste Schritt beim Erstellen eines geerbten Steuerelements ist das Ableiten vom übergeordneten Steuerelement. Diese Aktion erstellt ein neues Steuerelement, das über alle Eigenschaften, Methoden und grafischen Merkmale des übergeordneten Steuerelements verfügt, aber auch als Basis für das Hinzufügen neuer oder veränderter Funktionalität dienen kann.

### <a name="to-create-the-inherited-control"></a>So erstellen Sie das geerbte Steuerelement

1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **ctlClockLib**, zeigen Sie auf **Hinzufügen**, und klicken Sie dann auf **Benutzer Steuer**Element.

     Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.

2. Wählen Sie die Vorlage **Geerbtes Benutzersteuerelement**.

3. Geben Sie im Feld **Name** die Bezeichnung `ctlAlarmClock.cs` ein, und klicken Sie dann auf **Hinzufügen**.

     Das Dialogfeld **Vererbungsauswahl** wird angezeigt.

4. Doppelklicken Sie unter **Komponentenname** auf **ctlClock**.

5. Navigieren Sie in **Projektmappen-Explorer**zu den aktuellen Projekten.

    > [!NOTE]
    > Eine Datei namens **ctlAlarmClock.cs** wurde zum aktuellen Projekt hinzugefügt.

### <a name="add-the-alarm-properties"></a>Die Alarm Eigenschaften hinzufügen

Eigenschaften werden auf die gleiche Weise zu einem geerbten Steuerelement hinzugefügt wie zu einem zusammengesetzten Steuerelement. Sie verwenden jetzt die Syntax zum Deklarieren von Eigenschaften, um zwei Eigenschaften zu Ihrem Steuerelement hinzuzufügen: `AlarmTime`, wodurch der Wert des Datums und der Uhrzeit gespeichert wird, zu der der Wecker klingelt, und `AlarmSet`, die anzeigt, ob der Wecker eingestellt wurde.

#### <a name="to-add-properties-to-your-composite-control"></a>So fügen Sie Eigenschaften zum zusammengesetzten Steuerelement hinzu

1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **ctlAlarmClock**, und klicken Sie dann auf **Code anzeigen**.

2. Suchen Sie die `public class`-Anweisung. Beachten Sie, dass das Steuerelement von `ctlClockLib.ctlClock` erbt. Geben Sie unter der öffnenden Klammer (`{)`-Anweisung den folgenden Code ein.

    ```csharp
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

### <a name="add-to-the-graphical-interface-of-the-control"></a>Zur grafischen Oberfläche des Steuer Elements hinzufügen

Das geerbte Steuerelement verfügt über eine visuelle Schnittstelle, die mit dem Steuerelement identisch ist, von dem es erbt. Es verfügt über die gleichen konstituierenden Steuerelemente wie das übergeordnete Steuerelement. Allerdings sind die Eigenschaften der konstituierenden Steuerelemente nicht verfügbar, solange sie nicht explizit verfügbar gemacht werden. Sie können zur grafischen Schnittstelle des geerbten zusammengesetzten Steuerelements auf die gleiche Weise hinzufügen, wie Sie zu jedem anderen zusammengesetzten Steuerelement hinzufügen würden. Um den Vorgang fortzusetzen, zur visuellen Schnittstelle Ihres Weckers hinzuzufügen, fügen Sie ein Label-Steuerelement hinzu, das leuchtet, wenn der Wecker klingelt.

#### <a name="to-add-the-label-control"></a>So fügen Sie das Label-Steuerelement hinzu

1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **ctlAlarmClock**, und klicken Sie dann auf **Designer anzeigen**.

     Der Designer für `ctlAlarmClock` wird im Hauptfenster geöffnet.

2. Klicken Sie auf den Anzeigebereich des Steuerelements, und zeigen Sie das Eigenschaftenfenster an.

    > [!NOTE]
    > Alle Eigenschaften werden angezeigt, sind aber abgeblendet. Das bedeutet, dass die Eigenschaften nativ zu `lblDisplay` sind, und dass sie nicht im Eigenschaftenfenster geändert oder auf sie zugegriffen werden können. Standardmäßig sind in einem zusammengesetzten Steuerelement enthaltene Steuerelemente `private`, und es ist nicht möglich, auf ihre Eigenschaften zuzugreifen.

    > [!NOTE]
    > Wenn Sie möchten, dass nachfolgende Benutzer des zusammengesetzten Steuerelements Zugriff auf interne Steuerelemente haben, deklarieren Sie sie als `public` oder `protected`. Dadurch können Sie Eigenschaften von Steuerelementen, die in Ihrem zusammengesetzten Steuerelement enthalten sind, festlegen und ändern, indem Sie den entsprechenden Code verwenden.

3. Fügen Sie dem zusammengesetzten Steuerelement ein <xref:System.Windows.Forms.Label>-Steuerelement hinzu.

4. Ziehen Sie das <xref:System.Windows.Forms.Label>-Steuerelement mit der Maus direkt unterhalb des Anzeige Felds. Legen Sie im Eigenschaftenfenster die folgenden Eigenschaften fest.

    |property|Einstellung|
    |--------------|-------------|
    |**Name**|`lblAlarm`|
    |**Text**|**Alarm!**|
    |**TextAlign**|`MiddleCenter`|
    |**Visible**|`false`|

### <a name="add-the-alarm-functionality"></a>Hinzufügen der Wecker-Funktionalität

In den vorherigen Schritten haben Sie Eigenschaften und ein Steuerelement hinzugefügt, dass die Wecker-Funktionalität in Ihrem zusammengesetzten Steuerelement aktiviert. In diesem Verfahren fügen Sie Code hinzu, um die aktuelle Zeit mit der Weckzeit zu vergleichen, und bei Gleichheit einen Wecker auszulösen. Durch Überschreiben der Methode `timer1_Tick` von `ctlClock` und Hinzufügen von zusätzlichem Code erweitern Sie die Funktion von `ctlAlarmClock`, während alle geerbten Funktionen von `ctlClock` erhalten bleiben.

#### <a name="to-override-the-timer1_tick-method-of-ctlclock"></a>So überschreiben Sie die Methode „Timer1_Tick“ von „ctlClock“

1. Suchen Sie im **Code-Editor** eine `private bool blnAlarmSet;`-Anweisung hinzu. Fügen Sie direkt darunter die folgende Anweisung hinzu.

    ```csharp
    private bool blnColorTicker;
    ```

2. Suchen Sie im **Code-Editor** die schließende Klammer (`})` am Ende der Klasse. Fügen Sie direkt vor der Klammer den folgenden Code hinzu.

    ```csharp
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

     Das Hinzufügen dieses Codes dient mehreren Zwecken. Die Anweisung `override` weist das Steuerelement an, diese Methode statt der Methode zu verwenden, die vom Basissteuerelement geerbt wurde. Wenn diese Methode aufgerufen wird, ruft sie durch Aufruf der `base.timer1_Tick`-Anweisung die überschriebene Methode auf. Damit wird sichergestellt, dass die gesamte Funktionalität, die im ursprünglichen Steuerelement enthalten ist, in diesem Steuerelement reproduziert wird. Anschließend ruft sie zusätzlichen Code auf, um die Wecker-Funktionalität zu integrieren. Ein blinkendes Label-Steuerelement erscheint, wenn der Wecker ausgelöst wird.

     Das Wecker-Steuerelement ist fast abgeschlossen. Sie müssen nur noch eine Möglichkeit zum Deaktivieren implementieren. Zu diesem Zweck fügen Sie Code zur Methode `lblAlarm_Click` hinzu.

#### <a name="to-implement-the-shutoff-method"></a>So implementieren Sie die Methode zum Deaktivieren

1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **ctlAlarmClock.cs**, und klicken Sie dann auf **Designer anzeigen**.

     Der Designer wird geöffnet.

2. Fügen Sie eine Schaltfläche zum Steuerelement hinzu. Legen Sie die Eigenschaften der Schaltfläche wie folgt fest.

    |property|Wert|
    |--------------|-----------|
    |**Name**|`btnAlarmOff`|
    |**Text**|**Wecker deaktivieren**|

3. Doppelklicken Sie im Designer auf **btnAlarmOff**.

     Der **Code-Editor** wird in der Zeile `private void btnAlarmOff_Click` geöffnet.

4. Ändern Sie die Methode so, dass sie folgendem Code ähnelt.

    ```csharp
    private void btnAlarmOff_Click(object sender, System.EventArgs e)
    {
        // Turns off the alarm.
        AlarmSet = false;
        // Hides the flashing label.
        lblAlarm.Visible = false;
    }
    ```

5. Klicken Sie im Menü **Datei** auf **Alles speichern**, um das Projekt zu speichern.

### <a name="use-the-inherited-control-on-a-form"></a>Verwenden des geerbten Steuer Elements in einem Formular

Sie können das geerbte Steuerelement auf die gleiche Weise testen wie das Basisklassen-Steuerelement, `ctlClock`: Drücken Sie **F5** , um das Projekt zu erstellen, und führen Sie das Steuerelement im **UserControl-Test Container**aus. Weitere Informationen finden Sie unter [Vorgehensweise: Testen des Laufzeitverhaltens eines UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).

Sie müssen das Steuerelement auf einem Formular hosten, um es verwenden zu können. Wie standardmäßige zusammengesetzten Steuerelemente kann ein geerbtes zusammengesetztes Steuerelement nicht alleine stehen und muss in einem Formular oder einem anderen Container gehostet werden. Da `ctlAlarmClock` über eine tiefer gehende Funktionalität verfügt, wird zusätzlicher Code für das Testen benötigt. In dieser Vorgehensweise schreiben Sie ein einfaches Programm, um die Funktionalität von `ctlAlarmClock` zu testen. Sie schreiben Code zum Einstellen und Anzeigen der Eigenschaft `AlarmTime` von `ctlAlarmClock` und testen die geerbten Funktionen.

#### <a name="to-build-and-add-your-control-to-a-test-form"></a>So erstellen Sie ein Steuerelement und fügen es zu einem Testformular hinzu

1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **ctlClockLib**, und klicken Sie dann auf **Erstellen**.

2. Fügen Sie der Projekt Mappe ein neues **Windows-Anwendungs** Projekt hinzu, und nennen Sie es " **Test**".

3. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf den Knoten **Verweise** für das Testprojekt. Klicken Sie auf **Verweis hinzufügen**, um das Dialogfeld **Verweis hinzufügen** anzuzeigen. Klicken Sie auf die Registerkarte mit der Bezeichnung **Projekte**. Ihr `ctlClockLib`-Projekt wird unter **Projektname** aufgelistet. Doppelklicken Sie auf das Projekt, um den Verweis auf das Testprojekt hinzuzufügen.

4. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **Test**, und klicken Sie dann auf **Erstellen**.

5. Erweitern Sie in der **Toolbox** den Knoten **ctlClockLib Components**.

6. Doppelklicken Sie auf **ctlAlarmClock**, um eine Kopie von `ctlAlarmClock` zu Ihrem Formular hinzuzufügen.

7. Suchen Sie in der **Toolbox**nach **DateTimePicker** , und doppelklicken Sie darauf, um dem Formular ein <xref:System.Windows.Forms.DateTimePicker>-Steuerelement hinzuzufügen, und fügen Sie dann ein <xref:System.Windows.Forms.Label> Steuerelement hinzu, indem Sie auf **Bezeichnung**doppelklicken.

8. Verwenden Sie die Maus, um das Steuerelement an einem geeigneten Ort auf dem Formular zu positionieren.

9. Legen Sie die Eigenschaften dieser Steuerelemente wie folgt fest.

    |Steuerelement|property|Wert|
    |-------------|--------------|-----------|
    |`label1`|**Text**|`(blank space)`|
    ||**Name**|`lblTest`|
    |`dateTimePicker1`|**Name**|`dtpTest`|
    ||**Format**|<xref:System.Windows.Forms.DateTimePickerFormat.Time>|

10. Doppelklicken Sie im Designer auf **dtpTest**.

     Der **Code-Editor** für `private void dtpTest_ValueChanged` wird geöffnet.

11. Ändern Sie den Code so, dass er folgendem Beispiel ähnelt.

    ```csharp
    private void dtpTest_ValueChanged(object sender, System.EventArgs e)
    {
        ctlAlarmClock1.AlarmTime = dtpTest.Value;
        ctlAlarmClock1.AlarmSet = true;
        lblTest.Text = "Alarm Time is " +
            ctlAlarmClock1.AlarmTime.ToShortTimeString();
    }
    ```

12. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **Test**, und klicken Sie dann auf **als Startprojekt festlegen**.

13. Klicken Sie im Menü **Debuggen** auf **Debuggen starten**.

     Das Testprogramm wird gestartet. Beachten Sie, dass die aktuelle Uhrzeit im `ctlAlarmClock`-Steuerelement aktualisiert wird und die Startzeit im <xref:System.Windows.Forms.DateTimePicker> Steuerelement angezeigt wird.

14. Klicken Sie auf die <xref:System.Windows.Forms.DateTimePicker>, in der die Minuten der Stunde angezeigt werden.

15. Legen Sie mithilfe der Tastatur einen Wert für die Minuten fest, der eine Minute höher ist als die aktuell von `ctlAlarmClock` angezeigte Zeit.

     Die Zeit für die Einstellung des Weckers wird in `lblTest` angezeigt. Warten Sie, bis die angezeigte Zeit die für den Wecker eingestellte Zeit erreicht hat. Wenn die angezeigte Zeit die Zeit erreicht, auf die der Wecker eingestellt ist, leuchtet `lblAlarm`.

16. Deaktivieren Sie den Wecker, indem Sie auf `btnAlarmOff` klicken. Sie können den Wecker nun zurücksetzen.

In diesem Artikel wurde eine Reihe wichtiger Konzepte behandelt. Sie haben gelernt, ein zusammengesetztes Steuerelement zu erstellen, indem Sie Steuerelemente und Komponenten in einem Container für zusammengesetzte Steuerelemente kombiniert haben. Sie haben gelernt, Eigenschaften zu Ihrem Steuerelement hinzuzufügen und Code für das Implementieren benutzerdefinierter Funktionalität zu schreiben. Im letzten Abschnitt haben Sie gelernt, die Funktionalität eines bestimmten zusammengesetzten Steuerelements durch Vererbung zu erweitern und die Funktionalität von Host-Methoden durch außer Kraft setzen dieser Methoden zu ändern.

## <a name="see-also"></a>Siehe auch

- [Arten von benutzerdefinierten Steuerelementen](varieties-of-custom-controls.md)
- [Vorgehensweise: Anzeigen eines Steuerelements im Dialogfeld „Toolboxelemente auswählen“](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [Exemplarische Vorgehensweise: Vererben von einem Windows Forms-Steuerelement mit Visual C#](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
