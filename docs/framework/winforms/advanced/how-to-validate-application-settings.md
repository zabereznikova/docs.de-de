---
title: "Gewusst wie: &#220;berpr&#252;fen von Anwendungseinstellungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Anwendungseinstellungen, Validieren"
  - "Anwendungseinstellungen, Windows Forms"
  - "Validieren von Anwendungseinstellungen"
ms.assetid: 9f145ada-4267-436a-aa4c-c4dcffd0afb7
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Gewusst wie: &#220;berpr&#252;fen von Anwendungseinstellungen
In diesem Thema wird beschrieben, wie Anwendungseinstellungen überprüft werden, bevor sie erhalten bleiben.  
  
 Da Anwendungseinstellungen strikt typisiert sind, können Sie weitestgehend sicher sein, dass Benutzer einer Einstellung keine Daten des falschen Typs zuweisen können.  Dennoch kann es passieren, dass ein Benutzer versucht, einer Einstellung einen Wert zuzuweisen, der außerhalb zulässiger Grenzen liegt, beispielsweise bei der Angabe eines Geburtsdatums in der Zukunft.  <xref:System.Configuration.ApplicationSettingsBase>, die übergeordnete Klasse aller Anwendungseinstellungsklassen, stellt vier Ereignisse für die Überprüfung derartiger Grenzen zur Verfügung.  Beim Behandeln dieser Ereignisse wird der gesamte Validierungscode an einem einzelnen Speicherort abgelegt, anstatt ihn über das gesamte Projekt zu verteilen.  
  
 Das verwendete Ereignis hängt davon ab, wann Sie die Einstellungen überprüfen müssen, wie in der folgenden Tabelle beschrieben.  
  
|Ereignis|Vorkommnis und Verwendung|  
|--------------|-------------------------------|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingsLoaded>|Tritt nach dem ersten Laden einer Einstellungseigenschaftengruppe auf.<br /><br /> Verwenden Sie dieses Ereignis, um Anfangswerte für die gesamte Eigenschaftengruppe zu überprüfen, bevor sie innerhalb der Anwendung verwendet werden.|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingChanging>|Tritt auf, bevor der Wert einer einzelnen Einstellungseigenschaft geändert wird.<br /><br /> Verwenden Sie dieses Ereignis, um eine einzelne Eigenschaft zu überprüfen, bevor sie geändert wird.  Es kann Benutzern unmittelbar Feedback hinsichtlich ihrer Aktionen und Auswahl bereitstellen.|  
|<xref:System.Configuration.ApplicationSettingsBase.PropertyChanged>|Tritt auf, nachdem der Wert einer einzelnen Einstellungseigenschaft geändert wurde.<br /><br /> Verwenden Sie dieses Ereignis, um eine einzelne Eigenschaft zu überprüfen, nachdem sie geändert wurde.  Dieses Ereignis wird selten zur Validierung verwendet, außer wenn ein langer, asynchroner Validierungsprozess erforderlich ist.|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>|Tritt auf, bevor die Einstellungseigenschaftengruppe gespeichert wird.<br /><br /> Verwenden Sie dieses Ereignis, um Werte für die gesamte Eigenschaftengruppe zu überprüfen, bevor sie auf der Festplatte erhalten bleiben.|  
  
 Normalerweise verwenden Sie nicht all diese Ereignisse innerhalb der gleichen Anwendung zur Validierung.  Beispielsweise ist es häufig möglich, alle Validierungsanforderungen zu erfüllen, indem nur das <xref:System.Configuration.ApplicationSettingsBase.SettingChanging>\-Ereignis behandelt wird.  
  
 Ein Ereignishandler führt im Allgemeinen eine der folgenden Aktionen aus, wenn er einen ungültigen Wert findet:  
  
-   Er stellt automatisch einen richtigen Wert bereit, z. B. den Standardwert.  
  
-   Er fragt den Benutzer von Servercode erneut nach Informationen ab.  
  
-   Er verwendet für Ereignisse, die vor den zugeordneten Aktionen ausgelöst werden, z. B. <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> und <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>, das <xref:System.ComponentModel.CancelEventArgs>\-Argument, um die Operation abzubrechen.  
  
 Weitere Informationen über das Behandeln von Ereignissen finden Sie unter [Übersicht über Ereignishandler](../../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).  
  
 Die folgenden Prozeduren zeigen, wie Sie entweder mit dem <xref:System.Configuration.ApplicationSettingsBase.SettingChanging>\-Ereignis oder dem <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>\-Ereignis einen Test zu einem gültigen Geburtsdatum durchführen.  Die Prozeduren wurden in der Annahme geschrieben, dass Sie die Anwendungseinstellungen bereits erstellt haben. In diesem Beispiel werden die Grenzen der Einstellung  `DateOfBirth` überprüft.  Weitere Informationen zum Erstellen von Einstellungen finden Sie unter [Gewusst wie: Erstellen von Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).  
  
### So rufen Sie das Anwendungseinstellungsobjekt ab  
  
-   Rufen Sie einen Verweis auf das Anwendungseinstellungsobjekt \(die Wrapperinstanz\) ab, indem Sie einen der folgenden Schritte ausführen:  
  
    -   Wenn Sie die Einstellungen über das Dialogfeld mit den Anwendungseinstellungen von Visual Studio im **Eigenschaften\-Editor** erstellt haben, können Sie mit dem folgenden Ausdruck das standardmäßige Einstellungsobjekt abrufen, das für Ihre Sprache generiert wird.  
  
        ```csharp  
        Configuration.Settings.Default   
        ```  
  
        ```vb  
        MySettings.Default   
        ```  
  
         \- oder \-  
  
    -   Wenn Sie Visual Basic\-Entwickler sind und die Anwendungseinstellungen über den Projekt\-Designer erstellt haben, können Sie die Einstellungen über das [My.Settings\-Objekt](../../../../ocs/visual-basic/language-reference/objects/my-settings-object.md) abrufen.  
  
         \- oder \-  
  
    -   Wenn Sie die Einstellungen durch direktes Ableiten von <xref:System.Configuration.ApplicationSettingsBase> erstellt haben, müssen Sie die Klasse manuell instanziieren.  
  
        ```csharp  
        MyCustomSettings settings = new MyCustomSettings();  
        ```  
  
        ```vb  
        Dim Settings as New MyCustomSettings()  
        ```  
  
 Die folgenden Prozeduren wurden in der Annahme geschrieben, dass das Anwendungseinstellungsobjekt abgerufen wurde, indem Sie den letzten Schritt in der obigen Liste ausgeführt haben.  
  
### So überprüfen Sie die Anwendungseinstellungen, wenn sich eine Einstellung ändert  
  
1.  Wenn Sie C\#\-Entwickler sind, fügen Sie im Formular oder  `Load` \-Ereignis des Steuerelements einen Ereignishandler für das <xref:System.Configuration.ApplicationSettingsBase.SettingChanging>\-Ereignis hinzu.  
  
     \- oder \-  
  
     Wenn Sie Visual Basic\-Entwickler sind, sollten Sie die `Settings`\-Variable mit dem `WithEvents`\-Schlüsselwort deklarieren.  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        settings.SettingChanging += new SettingChangingEventHandler(MyCustomSettings_SettingChanging);  
    }  
    ```  
  
    ```vb  
    Public Sub Form1_Load(sender as Object, e as EventArgs)  
        AddHandler settings.SettingChanging, AddressOf MyCustomSettings_SettingChanging  
    End Sub   
    ```  
  
2.  Definieren Sie den Ereignishandler, und schreiben Sie den Code dafür, um die Grenzen des Geburtsdatums zu überprüfen.  
  
    ```csharp  
    private void MyCustomSettings_SettingChanging(Object sender, SettingChangingEventArgs e)  
    {  
        if (e.SettingName.Equals("DateOfBirth")) {  
            Date newDate = (Date)e.NewValue;  
            If (newDate > Date.Now) {  
                e.Cancel = true;  
                // Inform the user.  
            }  
        }  
    }  
    ```  
  
    ```vb  
    Private Sub MyCustomSettings_SettingChanging(sender as Object, e as SettingChangingEventArgs) Handles Settings.SettingChanging  
        If (e.SettingName.Equals("DateOfBirth")) Then  
            Dim NewDate as Date = CType(e.NewValue, Date)  
            If (NewDate > Date.Now) Then  
                e.Cancel = True  
                ' Inform the user.  
            End If  
        End If  
    End Sub  
    ```  
  
### So überprüfen Sie die Anwendungseinstellungen beim Speichern  
  
1.  Fügen Sie im Formular oder im  `Load` \-Ereignis des Steuerelements einen Ereignishandler für das <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>\-Ereignis hinzu.  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        settings.SettingsSaving += new SettingsSavingEventHandler(MyCustomSettings_SettingsSaving);  
    }  
    ```  
  
    ```vb  
    Public Sub Form1_Load(Sender as Object, e as EventArgs)  
        AddHandler settings.SettingsSaving, AddressOf MyCustomSettings_SettingsSaving  
    End Sub  
    ```  
  
2.  Definieren Sie den Ereignishandler, und schreiben Sie den Code dafür, um die Grenzen des Geburtsdatums zu überprüfen.  
  
    ```csharp  
    private void MyCustomSettings_SettingsSaving(Object sender, SettingsSavingEventArgs e)  
    {  
        if (this["DateOfBirth"] > Date.Now) {  
            e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Private Sub MyCustomSettings_SettingsSaving(Sender as Object, e as SettingsSavingEventArgs)  
        If (Me["DateOfBirth"] > Date.Now) Then  
            e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## Siehe auch  
 [Erstellen von Ereignishandlern in Windows Forms](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)   
 [Gewusst wie: Erstellen von Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md)