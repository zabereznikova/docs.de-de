---
title: 'Vorgehensweise: Erstellen von Anwendungseinstellungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application settings [Windows Forms], Windows Forms
- application settings [Windows Forms], creating
ms.assetid: 1e7aa347-af75-41e5-89ca-f53cab704f72
ms.openlocfilehash: 5cf109aec8b55650f43f07f5b303c6373df4efc7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004457"
---
# <a name="how-to-create-application-settings"></a>Vorgehensweise: Erstellen von Anwendungseinstellungen
Mithilfe von verwaltetem Code können Sie neue Anwendungseinstellungen erstellen und diese an Eigenschaften für Ihr Formular oder die Steuerelemente Ihres Formulars binden, damit diese Einstellungen zur Laufzeit automatisch geladen und gespeichert werden.  
  
 Im folgenden Verfahren erstellen Sie manuell eine Wrapperklasse, die von <xref:System.Configuration.ApplicationSettingsBase> abgeleitet ist. Dieser Klasse fügen Sie für jede Anwendungseinstellung, die Sie verfügbar machen möchten, eine Eigenschaft hinzu, auf die öffentlich zugegriffen werden kann.  
  
 Sie können dieses Verfahren auch mit minimalem Programmieraufwand in Visual Studio-Designer ausführen.  Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Erstellen von Anwendungseinstellungen mithilfe des Designers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/wabtadw6(v=vs.100)).  
  
### <a name="to-create-new-application-settings-programmatically"></a>So erstellen Sie programmgesteuert neue Anwendungseinstellungen  
  
1. Fügen Sie dem Projekt eine neue Klasse hinzu, und benennen Sie diese um. Für dieses Verfahren müssen wir diese Klasse aufrufen `MyUserSettings`. Ändern Sie die Klassendefinition so, dass die Klasse von <xref:System.Configuration.ApplicationSettingsBase> abgeleitet wird.  
  
2. Definieren Sie eine Eigenschaft für diese Wrapperklasse für jede benötigte Anwendungseinstellung, und wenden Sie diese Eigenschaft mit <xref:System.Configuration.ApplicationScopedSettingAttribute> oder mit <xref:System.Configuration.UserScopedSettingAttribute>, abhängig vom Bereich der Einstellung an. Weitere Informationen zum Einstellungsbereich finden Sie unter [Übersicht über Anwendungseinstellungen](application-settings-overview.md). Ihr Code sollte jetzt wie folgt aussehen.  
  
     [!code-csharp[ApplicationSettings.Create#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
     [!code-vb[ApplicationSettings.Create#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]  
  
3. Erstellen Sie eine Instanz dieser Wrapperklasse in Ihrer Anwendung. Sie wird in der Regel ein privates Element des Hauptformulars sein. Nachdem Sie nun Ihre Klasse definiert haben, müssen Sie sie an eine Eigenschaft binden. In diesem Fall ist dies die Eigenschaft <xref:System.Windows.Forms.Form.BackColor%2A> des Formulars. Sie können dies bewerkstelligen, Ihres Formulars `Load` -Ereignishandler.  
  
     [!code-csharp[ApplicationSettings.Create#2](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/Form1.cs#2)]
     [!code-vb[ApplicationSettings.Create#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/Form1.vb#2)]  
  
4. Wenn Sie eine Möglichkeit zum Ändern von Einstellungen zur Laufzeit bereitstellen, müssen Sie die aktuellen Einstellungen des Benutzers auf dem Datenträger speichern, wenn das Formular geschlossen wird. Andernfalls gehen diese Änderungen verloren.  
  
     [!code-csharp[ApplicationSettings.Create#3](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/Form1.cs#3)]
     [!code-vb[ApplicationSettings.Create#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/Form1.vb#3)]  
  
     Sie haben nun erfolgreich eine neue Anwendungseinstellung erstellt und diese an die angegebene Eigenschaft gebunden.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Der Standardeinstellungsanbieter (<xref:System.Configuration.LocalFileSettingsProvider>) speichert Informationen in Konfigurationsdateien als Nur-Text persistent. Auf diese Weise wird die Sicherheit für die Dateizugriffssicherheit eingeschränkt, die vom Betriebssystem für den aktuellen Benutzer bereitgestellt wird. Aus diesem Grund müssen die Informationen, die in Konfigurationsdateien gespeichert werden, sorgfältig ausgewählt werden. Häufig werden z. B. Anwendungseinstellungen zum Speichern von Verbindungszeichenfolgen verwendet, die auf den Datenspeicher der Anwendung zeigen. Allerdings sollten diese Zeichenfolgen aus Sicherheitsgründen keine Kennwörter enthalten. Weitere Informationen zu Verbindungszeichenfolgen finden Sie unter <xref:System.Configuration.SpecialSetting>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Configuration.SpecialSettingAttribute>
- <xref:System.Configuration.LocalFileSettingsProvider>
- [Übersicht über Anwendungseinstellungen](application-settings-overview.md)
- [Vorgehensweise: Überprüfen von Anwendungseinstellungen](how-to-validate-application-settings.md)
