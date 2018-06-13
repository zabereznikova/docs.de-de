---
title: 'Exemplarische Vorgehensweise: Erstellen von behindertengerechten Windows-basierten Anwendungen'
ms.date: 03/30/2017
helpviewer_keywords:
- accessibility [Windows Forms], Windows applications
- Windows applications [Windows Forms], accessibility
- applications [Windows Forms], accessibility
ms.assetid: 654c7f2f-1586-480b-9f12-9d9b8f5cc32b
ms.openlocfilehash: 6c798d0f6a454c7ee819d5556970bca12f1812e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529622"
---
# <a name="walkthrough-creating-an-accessible-windows-based-application"></a>Exemplarische Vorgehensweise: Erstellen von behindertengerechten Windows-basierten Anwendungen
Das Erstellen von barrierefreien Anwendungen ist für Unternehmen von größter Bedeutung. Bei vielen staatlichen Stellen gibt es für den Kauf von Software Vorschriften hinsichtlich der Barrierefreiheit. Das Certified for Windows-Logo beinhaltet Anforderungen zur Barrierefreiheit. Allein in den USA gibt es etwa 30 Millionen Menschen, viele davon potenzielle Kunden, für die die Barrierefreiheit von Software maßgeblich ist.  
  
 In dieser exemplarischen Vorgehensweise werden die fünf Anforderungen zur Barrierefreiheit für das Certified for Windows-Logo erläutert. Entsprechend diesen Anforderungen muss eine barrierefreie Anwendung folgende Forderungen erfüllen:  
  
-   Unterstützung der Systemsteuerungseinstellungen für Größe, Farbe, Schriftart und Eingabe. Wenn ein Benutzer die Einstellungen der Systemsteuerung ändert, wird die Größe der Menüleiste, der Titelleiste, der Ränder und der Statusleiste automatisch geändert. In dieser Anwendung sind keine weiteren Änderungen an den Steuerelementen oder am Code erforderlich.  
  
-   Unterstützung für den Modus für hohe Kontraste.  
  
-   Bereitstellen von dokumentierten Tastaturzugriffen auf alle Features.  
  
-   Visuelle und programmgesteuerte Anzeige der Position des Tastaturfokus.  
  
-   Vermeiden, dass wichtige Informationen ausschließlich akustisch übermittelt werden.  
  
 Weitere Informationen finden Sie unter [Ressourcen für das Entwerfen von Anwendungen mit Barrierefreiheit](/visualstudio/ide/reference/resources-for-designing-accessible-applications).  
  
 Informationen zur Unterstützung der verschiedenen Tastaturlayouts finden Sie unter [Empfehlungen für die Entwicklung weltweit einsatzfähiger Anwendungen](../../../../docs/standard/globalization-localization/best-practices-for-developing-world-ready-apps.md).  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
 In dieser exemplarischen Vorgehensweise wird die Benutzeroberfläche für eine Anwendung erstellt, mit der Pizzabestellungen entgegengenommen werden. Sie besteht aus einem <xref:System.Windows.Forms.TextBox>-Steuerelement für den Namen des Kunden, aus einer <xref:System.Windows.Forms.RadioButton>-Gruppe, um die Pizzagröße auszuwählen, aus einem <xref:System.Windows.Forms.CheckedListBox>-Steuerelement für die Auswahl des Belags, aus zwei Button-Steuerelementen, die mit "Bestellen" bzw. "Abbrechen" beschriftet sind, sowie aus einem Menü mit dem Befehl "Beenden".  
  
 Der Benutzer gibt den Namen des Kunden, die Größe der Pizza und die gewünschten Beläge ein. Klickt der Benutzer auf die Schaltfläche "Bestellen", werden in einem Meldungsfeld eine Zusammenfassung der Bestellung sowie deren Preis angezeigt, und die Inhalte der Steuerelemente werden gelöscht, damit diese für die nächste Bestellung verfügbar sind. Klickt der Benutzer auf die Schaltfläche "Abbrechen", werden die Inhalte der Steuerelemente gelöscht, damit diese für die nächste Bestellung verfügbar sind. Klickt der Benutzer auf das Menüelement "Beenden", wird das Programm beendet.  
  
 Der Schwerpunkt dieser exemplarischen Vorgehensweise liegt nicht auf dem Code für das Bestellsystem, sondern auf der Barrierefreiheit der Benutzeroberfläche. Die exemplarische Vorgehensweise veranschaulicht die Barrierefreiheitsfeatures von einigen häufig verwendeten Steuerelementen wie Schaltflächen, Optionsfelder, Textfelder und Bezeichnungen.  
  
#### <a name="to-begin-making-the-application"></a>So beginnen Sie mit der Erstellung der Anwendung  
  
-   Erstellen Sie eine neue Windows-Anwendung in Visual Basic oder Visual c#. Geben Sie dem Projekt den Namen **Pizzabestellung**. (Weitere Informationen finden Sie unter [Erstellen neuer Projektmappen und Projekte](/visualstudio/ide/creating-solutions-and-projects).)  
  
## <a name="adding-the-controls-to-the-form"></a>Hinzufügen der Steuerelemente zum Formular  
 Wenn Sie Steuerelemente zu einem Formular hinzufügen, sollten Sie die folgenden Richtlinien für eine barrierefreie Anwendung beachten:  
  
-   Legen Sie für die Eigenschaften <xref:System.Windows.Forms.Control.AccessibleDescription%2A> und <xref:System.Windows.Forms.Control.AccessibleName%2A> fest. In diesem Beispiel ist die Einstellung "Default" für <xref:System.Windows.Forms.Control.AccessibleRole%2A> ausreichend. Weitere Informationen zu den Eigenschaften von Barrierefreiheit finden Sie unter [Informationen über die Barrierefreiheit für Steuerelemente in Windows Forms](../../../../docs/framework/winforms/controls/providing-accessibility-information-for-controls-on-a-windows-form.md).  
  
-   Legen Sie den Schriftgrad auf 10 Punkt oder größer fest.  
  
    > [!NOTE]
    >  Wenn Sie den Schriftgrad des Formulars auf 10 festlegen, wenn Sie beginnen, haben alle dem Formular anschließend hinzugefügten Steuerelemente ebenfalls den Schriftgrad 10.  
  
-   Stellen Sie sicher, dass jedes Label-Steuerelement, das ein TextBox-Steuerelement beschreibt, dem TextBox-Steuerelement in der Aktivierreihenfolge direkt vorangestellt ist.  
  
-   Fügen Sie für die <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft jedes Steuerelements, zu dem der Benutzer navigieren können soll, mit dem Zeichen "&" eine Zugriffstaste hinzu.  
  
-   Fügen Sie für die <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft der Bezeichnung, die einem Steuerelement vorangestellt ist, zu dem der Benutzer navigieren können soll, mit dem Zeichen "&" eine Zugriffstaste hinzu. Legen Sie <xref:System.Windows.Forms.Label.UseMnemonic%2A>-Eigenschaft der Bezeichnungen auf `true` fest, sodass der Fokus auf das nächste Steuerelement in der Aktivierreihenfolge festgelegt wird, wenn der Benutzer die Zugriffstaste drückt.  
  
-   Fügen Sie allen Menüelementen Zugriffstasten hinzu.  
  
#### <a name="to-make-your-windows-application-accessible"></a>So gestalten Sie eine Windows-Anwendung barrierefrei  
  
-   Gehen Sie entsprechend der nachstehenden Beschreibung vor, um dem Formular die Steuerelemente hinzuzufügen und die Eigenschaften festzulegen. Am Ende der Tabelle finden Sie ein Bild, das ein Modell für die Anordnung der Steuerelemente auf dem Formular zeigt.  
  
    |Objekt|Eigenschaft|Wert|  
    |------------|--------------|-----------|  
    |Form1|AccessibleDescription|Bestellformular|  
    ||AccessibleName|Bestellformular|  
    ||Schriftgrad|10|  
    ||Text|Pizzabestellformular|  
    |PictureBox|Name|Logo|  
    ||AccessibleDescription|Ein Stück Pizza|  
    ||AccessibleName|Firmenlogo|  
    ||Bild|Ein Symbol oder eine Bitmap|  
    |Bezeichnung|Name|companyLabel|  
    ||Text|Gute Pizza|  
    ||TabIndex|1|  
    ||AccessibleDescription|Firmenname|  
    ||AccessibleName|Firmenname|  
    ||Backcolor|Blau|  
    ||Forecolor|Gelb|  
    ||Schriftgrad|18|  
    |Bezeichnung|Name|customerLabel|  
    ||Text|&Name|  
    ||TabIndex|2|  
    ||AccessibleDescription|Kundennamenbez.|  
    ||AccessibleName|Kundennamenbez.|  
    ||UseMnemonic|True|  
    |TextBox|Name|customerName|  
    ||Text|(keine)|  
    ||TabIndex|3|  
    ||AccessibleDescription|Kundenname|  
    ||AccessibleName|Kundenname|  
    |GroupBox|Name|sizeOptions|  
    ||AccessibleDescription|Mögliche Pizzagrößen|  
    ||AccessibleName|Mögliche Pizzagrößen|  
    ||Text|Pizzagröße|  
    ||TabIndex|4|  
    |RadioButton|Name|smallPizza|  
    ||Text|&Klein 6,00 €|  
    ||Aktiviert|True|  
    ||TabIndex|0|  
    ||AccessibleDescription|Kleine Pizza|  
    ||AccessibleName|Kleine Pizza|  
    |RadioButton|Name|largePizza|  
    ||Text|&Groß 10,00 €|  
    ||TabIndex|1|  
    ||AccessibleDescription|Große Pizza|  
    ||AccessibleName|Große Pizza|  
    |Bezeichnung|Name|toppingsLabel|  
    ||Text|&Beläge (jeder 0,75 €)|  
    ||TabIndex|5|  
    ||AccessibleDescription|Bezeichnung des Belags|  
    ||AccessibleName|Bezeichnung des Belags|  
    ||UseMnemonic|True|  
    |CheckedListBox|Name|toppings|  
    ||TabIndex|6|  
    ||AccessibleDescription|Mögliche Beläge|  
    ||AccessibleName|Mögliche Beläge|  
    ||Elemente|Peperoni, Salami, Champignons|  
    |Schaltfläche|Name|order|  
    ||Text|Reihenf&olge|  
    ||TabIndex|7|  
    ||AccessibleDescription|Gesamtbetrag der Bestellung ermitteln|  
    ||AccessibleName|Gesamtbetrag|  
    |Schaltfläche|Name|cancel|  
    ||Text|&Abbrechen|  
    ||TabIndex|8|  
    ||AccessibleDescription|Abbrechen der Bestellung|  
    ||AccessibleName|Bestellung abbrechen|  
    |MainMenu|Name|theMainMenu|  
    |MenuItem|Name|fileCommands|  
    ||Text|&Datei|  
    |MenuItem|Name|exitApp|  
    ||Text|&Beenden|  
  
     ![Pizzabestellformular](../../../../docs/framework/winforms/advanced/media/vbpizzaorderform.gif "VbPizzaOrderForm")  
Das Formular sieht in etwa wie folgt aus:  
  
## <a name="supporting-high-contrast-mode"></a>Unterstützen des Modus für hohe Kontraste  
 Der Modus für hohe Kontraste ist eine Windows-Systemeinstellung, die die Lesbarkeit verbessert, indem kontrastreiche Farben und Schriftgrade verwendet werden, die für sehbehinderte Benutzer vorteilhaft sind. Die <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> Eigenschaft wird bereitgestellt, um zu bestimmen, ob der Modus für hohe Kontraste festgelegt ist.  
  
 Wenn "SystemInformation.HighContrast" gleich `true` ist, muss die Anwendung wie folgt vorgehen:  
  
-   Sie zeigt alle Elemente der Benutzeroberfläche mit dem Systemfarbschema an.  
  
-   Alle durch Farbe vermittelten Informationen müssen auch durch visuelle Hinweise oder durch Töne vermittelt werden. Wenn beispielsweise bestimmte Listenelemente in roter Schrift hervorgehoben sind, können Sie diese auch noch fett formatieren, sodass der Benutzer einen nicht farblichen Hinweis hat, dass die Elemente hervorgehoben sind.  
  
-   Hinter Text dürfen weder Symbole oder Muster angezeigt werden.  
  
 Die Anwendung muss beim Start die Einstellung von <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> überprüfen und danach auf das Systemereignis <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> reagieren. Das <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>-Ereignis wird immer dann ausgelöst, wenn sich der Wert von <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> geändert hat.  
  
 In der vorliegenden Anwendung ist `lblCompanyName` das einzige Element, für das nicht die Systemeinstellungen für Farbe verwendet werden. Die <xref:System.Drawing.SystemColors> Klasse wird verwendet, um die farbeinstellungen der Bezeichnung, die vom Benutzer ausgewählten Systemfarben zu ändern.  
  
#### <a name="to-enable-high-contrast-mode-in-an-effective-way"></a>So aktivieren Sie den Modus für hohe Kontraste auf effektive Weise  
  
1.  Erstellen Sie eine Methode, mit der die Farben der Bezeichnung auf die Systemfarben festgelegt werden.  
  
    ```  
    ' Visual Basic  
    Private Sub SetColorScheme()  
       If SystemInformation.HighContrast Then  
          companyLabel.BackColor = SystemColors.Window  
          companyLabel.ForeColor = SystemColors.WindowText  
       Else  
          companyLabel.BackColor = Color.Blue  
          companyLabel.ForeColor = Color.Yellow  
       End If  
    End Sub  
  
    // C#  
    private void SetColorScheme()  
    {  
       if (SystemInformation.HighContrast)  
       {  
          companyLabel.BackColor = SystemColors.Window;  
          companyLabel.ForeColor = SystemColors.WindowText;  
       }  
       else  
       {  
          companyLabel.BackColor = Color.Blue;  
          companyLabel.ForeColor = Color.Yellow;  
       }  
    }  
    ```  
  
2.  Rufen Sie die Prozedur `SetColorScheme` im Konstruktor des Formulars (`Public Sub New()`in Visual Basic und `public class Form1` in Visual C#) auf. Damit Sie in Visual Basic auf den Konstruktor zugreifen können, müssen Sie den Bereich **Vom Windows Form-Designer generierter Code** erweitern.  
  
    ```  
    ' Visual Basic   
    Public Sub New()  
       MyBase.New()  
       InitializeComponent()  
       SetColorScheme()  
    End Sub  
  
    // C#  
    public Form1()  
    {  
       InitializeComponent();  
       SetColorScheme();  
    }  
    ```  
  
3.  Erstellen Sie eine Ereignisprozedur mit der entsprechenden Signatur, um auf das <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>-Ereignis zu reagieren.  
  
    ```  
    ' Visual Basic  
    Protected Sub UserPreferenceChanged(ByVal sender As Object, _  
    ByVal e As Microsoft.Win32.UserPreferenceChangedEventArgs)  
       SetColorScheme()  
    End Sub  
  
    // C#  
    public void UserPreferenceChanged(object sender,   
    Microsoft.Win32.UserPreferenceChangedEventArgs e)  
    {  
       SetColorScheme();  
    }  
    ```  
  
4.  Fügen Sie dem Formularkonstruktor hinter dem Aufruf von `InitializeComponents` Code hinzu, der die Ereignisprozedur mit dem Systemereignis verknüpft. Diese Methode ruft die `SetColorScheme`-Prozedur auf.  
  
    ```  
    ' Visual Basic  
    Public Sub New()  
       MyBase.New()  
       InitializeComponent()  
       SetColorScheme()  
       AddHandler Microsoft.Win32.SystemEvents.UserPreferenceChanged, _  
          AddressOf Me.UserPreferenceChanged  
    End Sub  
  
    // C#  
    public Form1()  
    {  
       InitializeComponent();  
       SetColorScheme();  
       Microsoft.Win32.SystemEvents.UserPreferenceChanged   
          += new Microsoft.Win32.UserPreferenceChangedEventHandler(  
          this.UserPreferenceChanged);  
    }  
    ```  
  
5.  Fügen Sie der <xref:System.Windows.Forms.Control.Dispose%2A>-Methode des Formulars vor dem Aufruf der <xref:System.Windows.Forms.Control.Dispose%2A>-Methode der Basisklasse Code hinzu, der das Ereignis freigibt, wenn die Anwendung geschlossen wird. Damit Sie in Visual Basic auf die <xref:System.Windows.Forms.Control.Dispose%2A>-Methode zugreifen können, müssen Sie den Bereich "Vom Windows Form-Designer generierter Code" erweitern.  
  
    > [!NOTE]
    >  Der Systemereigniscode führt getrennt von der Hauptanwendung einen Thread aus. Wenn Sie das Ereignis nicht freigeben, wird auch nach dem Schließen des Programms weiterhin der Code ausgeführt, den Sie mit dem Ereignis verknüpft haben.  
  
    ```  
    ' Visual Basic  
    Protected Overloads Overrides Sub Dispose(ByVal disposing As Boolean)  
       If disposing Then  
          If Not (components Is Nothing) Then  
             components.Dispose()  
          End If  
       End If  
       RemoveHandler Microsoft.Win32.SystemEvents.UserPreferenceChanged, _  
          AddressOf Me.UserPreferenceChanged  
       MyBase.Dispose(disposing)  
    End Sub  
  
    // C#  
    protected override void Dispose( bool disposing )  
    {  
       if( disposing )  
       {  
          if (components != null)   
          {  
             components.Dispose();  
          }  
       }  
       Microsoft.Win32.SystemEvents.UserPreferenceChanged   
          -= new Microsoft.Win32.UserPreferenceChangedEventHandler(  
          this.UserPreferenceChanged);  
       base.Dispose( disposing );  
    }  
    ```  
  
6.  Drücken Sie F5, um die Anwendung auszuführen.  
  
## <a name="conveying-important-information-by-means-other-than-sound"></a>So vermitteln Sie wichtige Informationen anders als mit einer Tonfolge  
 In dieser Anwendung gibt es keine Informationen, die ausschließlich über eine Tonfolge vermittelt werden. Wenn Sie Tonfolgen in Ihrer Anwendung verwenden, sollten Sie die Informationen auch auf andere Weise bereitstellen.  
  
#### <a name="to-supply-information-by-some-other-means-than-sound"></a>So stellen Sie Informationen auf andere Weise als über Tonfolgen bereit  
  
1.  Lassen Sie die Titelleiste mithilfe der Windows-API-Funktion "FlashWindow" blinken. Ein Beispiel, wie Windows-API-Funktionen aufgerufen werden, finden Sie unter [Exemplarische Vorgehensweise: Aufrufen von Windows-APIs](~/docs/visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).  
  
    > [!NOTE]
    >  Möglicherweise hat der Benutzer den Windows-Dienst "Darstellungsoptionen" aktiviert, der ebenfalls bewirkt, dass das Fenster blinkt, wenn Systemsounds über die integrierten Lautsprecher des Computers wiedergegeben werden.  
  
2.  Zeigen Sie die wichtigen Informationen in einem nicht modalen Fenster an, damit der Benutzer darauf reagieren kann.  
  
3.  Zeigen Sie ein Meldungsfeld an, das den Tastaturfokus erhält. Vermeiden Sie diese Methode, wenn der Benutzer eine Eingabe vornimmt.  
  
4.  Zeigen Sie eine Statusanzeige im Statusbereich der Taskleiste an. Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen von Anwendungssymbolen zur Taskleiste mit der NotifyIcon-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).  
  
## <a name="testing-the-application"></a>Testen der Anwendung  
 Bevor Sie die Anwendung bereitstellen, sollten Sie die implementierten Barrierefreiheitsfeatures testen.  
  
#### <a name="to-test-accessibility-features"></a>So testen Sie die Barrierefreiheitsfeatures  
  
1.  Um den Tastaturzugriff zu testen, ziehen Sie den Stecker des Mauskabels heraus, und navigieren Sie in der Benutzeroberfläche nur über die Tastatur zu jedem Feature. Vergewissern Sie sich, dass alle Aufgaben über die Tastatur ausgeführt werden können.  
  
2.  Um die Unterstützung für hohen Kontrast zu testen, wählen Sie in der Systemsteuerung das Symbol "Eingabehilfen" aus. Klicken Sie auf die Registerkarte "Anzeige", und aktivieren Sie das Kontrollkästchen für die Verwendung von hohem Kontrast. Navigieren Sie durch alle Elemente der Benutzeroberfläche, um sich zu vergewissern, dass die Farb- und Schriftartänderungen übernommen wurden. Stellen Sie außerdem sicher, dass hinter Text gezeichnete Symbole und Muster unterdrückt werden.  
  
    > [!NOTE]
    >  In der Systemsteuerung von Windows NT 4 gibt es kein Symbol für Eingabehilfen (Barrierefreiheit). Daher funktioniert diese Vorgehensweise zum Ändern der SystemInformation.HighContrast-Einstellung in Windows NT 4 nicht.  
  
3.  Die Barrierefreiheit einer Anwendung kann außerdem mithilfe direkt verfügbarer Tools getestet werden.  
  
4.  Um die Verfügbarmachung des Tastaturfokus zu testen, führen Sie Bildschirmlupe aus. (Um Bildschirmlupe zu öffnen, klicken Sie auf **Start**, zeigen Sie auf **Programm**e, zeigen Sie auf **Zubehör,** zeigen Sie auf **Barrierefreiheit**, und klicken Sie dann auf **Bildschirmlupe**). Navigieren Sie in der Benutzeroberfläche, wobei Sie sowohl die TAB-Taste als auch die Maus verwenden. Vergewissern Sie sich, dass die gesamte Navigation in **Bildschirmlupe** ordnungsgemäß nachverfolgt wird.  
  
5.  Um die Verfügbarmachung der Bildschirmelemente zu testen, führen Sie Inspect aus, und verwenden Sie die Maus und die TAB-Taste, um jedes Element zu erreichen. Vergewissern Sie sich, dass die Informationen, die im Fenster "Inspect" in den Feldern "Name", "State", "Role", "Location" und "Value" angezeigt werden, für den Benutzer für jedes Objekt in der Benutzeroberfläche aussagekräftig sind.
