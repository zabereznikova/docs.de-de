---
title: 'Vorgehensweise: Überprüfen von Anwendungseinstellungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating application settings
- application settings [Windows Forms], Windows Forms
- application settings [Windows Forms], validating
ms.assetid: 9f145ada-4267-436a-aa4c-c4dcffd0afb7
ms.openlocfilehash: b3b2447b570f0635942183dcc62c0e4ed73800d1
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972247"
---
# <a name="how-to-validate-application-settings"></a>Vorgehensweise: Überprüfen von Anwendungseinstellungen

In diesem Thema wird veranschaulicht, wie Anwendungseinstellungen überprüft werden, bevor sie persistent gespeichert werden.

Da die Anwendungseinstellungen stark typisiert sind, müssen Sie darauf vertrauen, dass Benutzer Daten mit einem falschen Typ keiner bestimmten Einstellung zuweisen können. Ein Benutzer kann weiterhin versuchen, einer Einstellung einen Wert zuzuweisen, der außerhalb der zulässigen Grenzen liegt, z.B. die Angabe eines in der Zukunft liegenden Geburtsdatums. <xref:System.Configuration.ApplicationSettingsBase>, die übergeordnete Klasse aller Anwendungs Einstellungs Klassen, macht vier Ereignisse verfügbar, um die Überprüfung dieser Begrenzungen zu aktivieren. Durch die Bearbeitung dieser Ereignisse befinden sich alle Überprüfungscodes an einem einzigen Speicherort und sind nicht im gesamten Projekt verteilt.

Welches Ereignis Sie verwenden, hängt davon ob, wann Sie Ihre Einstellungen überprüfen müssen, wie in der folgenden Tabelle beschrieben.

|event|Vorkommen und Verwendung|
|-----------|------------------------|
|<xref:System.Configuration.ApplicationSettingsBase.SettingsLoaded>|Tritt nach dem ersten Laden der Eigenschaftengruppe einer Einstellung auf.<br /><br /> Verwenden Sie dieses Ereignis, um die Anfangswerte der gesamten Eigenschaftengruppe zu überprüfen, bevor sie in der Anwendung verwendet werden.|
|<xref:System.Configuration.ApplicationSettingsBase.SettingChanging>|Tritt auf, bevor der Wert einer einzelnen Einstellungseigenschaft geändert wird.<br /><br /> Verwenden Sie dieses Ereignis, um eine einzelne Eigenschaft zu überprüfen, bevor sie geändert wird. Sie kann Benutzern unmittelbares Feedback hinsichtlich ihrer Aktionen und Auswahl geben.|
|<xref:System.Configuration.ApplicationSettingsBase.PropertyChanged>|Tritt auf, nachdem der Wert einer einzelnen Einstellungseigenschaft geändert wurde.<br /><br /> Verwenden Sie dieses Ereignis, um eine einzelne Eigenschaft zu überprüfen, nachdem sie geändert wurde. Dieses Ereignis wird selten zur Überprüfung verwendet, es sei denn, es ist ein langer, asynchroner Überprüfungsprozess erforderlich.|
|<xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>|Tritt auf, bevor die Eingenschaftengruppe der Einstellung gespeichert wird.<br /><br /> Verwenden Sie dieses Ereignis, um Werte der gesamten Eigenschaftengruppe zu überprüfen, bevor sie persistent auf dem Datenträger gespeichert werden.|

Normalerweise verwenden Sie zu Überprüfungszwecken nicht alle diese Ereignisse innerhalb der gleichen Anwendung. Beispielsweise ist es oft möglich, alle Überprüfungsanforderungen zu erfüllen, indem nur das <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> -Ereignis verarbeitet wird.

Ein Ereignishandler führt in der Regel eine der folgenden Aktionen aus, wenn ein ungültiger Wert erkannt wurde:

- Er gibt automatisch einen Wert an, der bekanntermaßen richtig ist, z.B. der Standardwert.

- Er fragt den Benutzer des Servercodes erneut nach Informationen.

- Für Ereignisse, die vor den zugehörigen Aktionen ausgelöst werden <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> , <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>z. b <xref:System.ComponentModel.CancelEventArgs> . und, verwendet das-Argument, um den Vorgang abzubrechen.

Weitere Informationen zur Behandlung von Ereignissen finden Sie unter [Übersicht über Ereignishandler](../event-handlers-overview-windows-forms.md).

Die folgenden Prozeduren zeigen, wie Sie mit dem <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> -Ereignis oder dem <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> -Ereignis auf ein gültiges Geburtsdatum testen. Die Verfahren wurden unter der Annahme geschrieben, dass Sie Ihre Anwendungseinstellungen bereits erstellt haben. In diesem Beispiel wird für die Einstellung mit dem Namen `DateOfBirth` eine Überprüfung der Begrenzungen durchgeführt. Weitere Informationen zum Erstellen von Einstellungen finden [Sie unter Gewusst wie: Erstellen Sie Anwendungs](how-to-create-application-settings.md)Einstellungen.

### <a name="to-obtain-the-application-settings-object"></a>So rufen Sie das Anwendungseinstellungsobjekt ab

- Rufen Sie einen Verweis auf das Anwendungseinstellungsobjekt (die Wrapperinstanz) ab, indem Sie eines der folgenden gegliederten Elemente abschließen:

  - Wenn Sie die Einstellungen über das Dialogfeld „Anwendungseinstellungen von Visual Studio“ im **-Eigenschaften-Editor** erstellt haben, können Sie das Standardeinstellungsobjekt abrufen, das über den folgenden Ausdruck für Ihre Sprache generiert wurde.

    ```csharp
    Configuration.Settings.Default
    ```

    ```vb
    MySettings.Default
    ```

    -oder-

  - Wenn Sie Entwickler von Visual Basic sind und Sie Ihre Anwendungseinstellungen mit dem Projekt-Designer erstellt haben, können Sie Ihre Einstellungen über das [My.Settings-Objekt](../../../visual-basic/language-reference/objects/my-settings-object.md) abrufen.

    -oder-

  - Wenn Sie die Einstellungen durch direktes ableiten von <xref:System.Configuration.ApplicationSettingsBase> erstellt haben, müssen Sie die Klasse manuell instanziieren.

    ```csharp
    MyCustomSettings settings = new MyCustomSettings();
    ```

    ```vb
    Dim Settings as New MyCustomSettings()
    ```

Die folgenden Prozeduren wurden unter der Annahme geschrieben, dass das Anwendungseinstellungsobjekt abgerufen wurde, indem das letzte gegliederte Element in dieser Prozedur abgeschlossen wurde.

### <a name="to-validate-application-settings-when-a-setting-is-changing"></a>So überprüfen Sie Anwendungseinstellungen, wenn eine Einstellung geändert wird

1. Wenn Sie ein C# Entwickler sind, fügen Sie im-Ereignis des `Load` Formulars oder Steuer Elements einen Ereignishandler für <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> das-Ereignis hinzu.

    -oder-

    Wenn Sie Visual Basic-Entwickler sind, sollten Sie die `Settings`-Variablen mithilfe des `WithEvents`-Schlüsselworts deklarieren.

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

2. Definieren Sie den Ereignishandler, und schreiben Sie den Code in den Ereignishandler, um eine Überprüfung der Begrenzungen für das Geburtsdatum durchzuführen.

    ```csharp
    private void MyCustomSettings_SettingChanging(Object sender, SettingChangingEventArgs e)
    {
        if (e.SettingName.Equals("DateOfBirth"))
        {
            var newDate = (DateTime)e.NewValue;
            if (newDate > DateTime.Now)
            {
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

### <a name="to-validate-application-settings-when-a-save-occurs"></a>So überprüfen Sie Anwendungseinstellungen, sobald ein Speichervorgang auftritt

1. Fügen Sie im- `Load` Ereignis des Formulars oder Steuer Elements einen Ereignishandler für das <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> -Ereignis hinzu.

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

2. Definieren Sie den Ereignishandler, und schreiben Sie den Code in den Ereignishandler, um eine Überprüfung der Begrenzungen für das Geburtsdatum durchzuführen.

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

## <a name="see-also"></a>Siehe auch

- [Erstellen von Ereignishandlern in Windows Forms](../creating-event-handlers-in-windows-forms.md)
- [Vorgehensweise: Erstellen von Anwendungseinstellungen](how-to-create-application-settings.md)
