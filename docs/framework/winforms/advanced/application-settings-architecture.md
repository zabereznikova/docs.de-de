---
title: Architektur der Anwendungseinstellungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application settings [Windows Forms], architecture
ms.assetid: c8eb2ad0-fac6-4ea2-9140-675a4a44d562
ms.openlocfilehash: b5d5a4456bef925cd8093fe9c696145aff83660e
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039414"
---
# <a name="application-settings-architecture"></a>Architektur der Anwendungseinstellungen
In diesem Thema wird beschrieben, wie die Architektur der Anwendungseinstellungen funktioniert. Außerdem werden erweiterte Funktionen der Architektur erläutert, z.B. gruppierte Einstellungen und Einstellungsschlüssel.

 Die Architektur der Anwendungseinstellungen unterstützt definierende, stark typisierte Einstellungen mit Geltungsbereich Anwendung oder Benutzer sowie die Beibehaltung der Einstellungen zwischen Anwendungssitzungen. Die Architektur bietet eine Standardpersistenz-Engine zum Speichern von Einstellungen und Laden aus dem lokalen Dateisystem. Die Architektur definiert auch Schnittstellen zur Bereitstellung einer benutzerdefinierten Persistenz-Engine.

 Schnittstellen werden bereitgestellt, die benutzerdefinierten Komponenten ermöglichen, ihre eigenen Einstellungen beizubehalten, wenn sie in einer Anwendung gehostet werden können. Mithilfe von Einstellungsschlüsseln können Komponenten Einstellungen für mehrere Instanzen der Komponente getrennt halten.

## <a name="defining-settings"></a>Definieren von Einstellungen
 Die Architektur der Anwendungseinstellungen wird sowohl in ASP.net als auch Windows Forms verwendet und enthält eine Reihe von Basisklassen, die in beiden Umgebungen gemeinsam verwendet werden. Das wichtigste ist <xref:System.Configuration.SettingsBase>, das den Zugriff auf Einstellungen über eine Auflistung ermöglicht und Methoden auf niedriger Ebene zum Laden und Speichern von Einstellungen bereitstellt. Jede Umgebung implementiert eine eigene von <xref:System.Configuration.SettingsBase> abgeleitete Klasse, um zusätzliche Einstellungs Funktionen für diese Umgebung bereitzustellen. In einer Windows Forms basierten Anwendung müssen alle Anwendungseinstellungen für eine von der <xref:System.Configuration.ApplicationSettingsBase> -Klasse abgeleitete Klasse definiert werden, die der-Basisklasse die folgenden Funktionen hinzufügt:

- Lade- und Speichervorgänge auf höherer Ebene

- Unterstützung für benutzerspezifische Einstellungen

- Wiederherstellen der vordefinierten Standardeinstellungen eines Benutzers

- Aktualisieren von Einstellungen aus einer früheren Anwendungsversion

- Überprüfen von Einstellungen, bevor sie geändert oder bevor sie gespeichert werden

 Die Einstellungen können mit einer Reihe von Attributen beschrieben werden, die im <xref:System.Configuration> -Namespace definiert sind. Diese werden unter [Attribute für Anwendungseinstellungen](application-settings-attributes.md)beschrieben. Wenn Sie eine Einstellung definieren, müssen Sie Sie entweder <xref:System.Configuration.ApplicationScopedSettingAttribute> mit oder <xref:System.Configuration.UserScopedSettingAttribute>anwenden, wodurch beschrieben wird, ob die Einstellung für die gesamte Anwendung oder nur für den aktuellen Benutzer gilt.

 Das folgende Codebeispiel definiert eine benutzerdefinierte Einstellungsklasse mit einer Einstellung: `BackgroundColor`.

 [!code-csharp[ApplicationSettings.Create#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
 [!code-vb[ApplicationSettings.Create#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]

## <a name="settings-persistence"></a>Beibehaltung von Einstellungen
 Die <xref:System.Configuration.ApplicationSettingsBase> -Klasse speichert oder lädt keine Einstellungen. dieser Auftrag fällt auf den Einstellungs Anbieter, eine Klasse, die von <xref:System.Configuration.SettingsProvider>abgeleitet wird. Wenn eine abgeleitete Klasse <xref:System.Configuration.ApplicationSettingsBase> von keinen Einstellungs Anbieter über den <xref:System.Configuration.SettingsProviderAttribute>angibt, wird der Standardanbieter <xref:System.Configuration.LocalFileSettingsProvider>,, verwendet.

 Das Konfigurationssystem, das ursprünglich mit dem .NET Framework freigegeben wurde, unterstützt die Bereitstellung statischer Anwendungs Konfigurationsdaten entweder über die Datei "Machine `app.`. config" des lokalen Computers oder innerhalb einer Datei "exe. config", die Sie mit Ihre Anwendung. Diese <xref:System.Configuration.LocalFileSettingsProvider> Native Unterstützung wird von der-Klasse wie folgt erweitert:

- Anwendungsspezifische Einstellungen können in der Datei machine.config oder `app.`exe.config gespeichert werden. Die Datei machine.config ist immer schreibgeschützt, während `app`. exe.config aufgrund von Sicherheitsüberlegungen für die meisten Anwendungen schreibgeschützt ist.

- Benutzerspezifische Einstellungen können in `app`. exe.config-Dateien gespeichert werden und werden dann als statische Standardwerte behandelt.

- Nicht standardmäßige benutzerspezifische Einstellungen werden in einer neuen Datei, *benutzer*.config gespeichert, wobei *benutzer* der Benutzername der Person ist, die aktuell die Anwendung ausführt. Sie können einen Standardwert für eine benutzerspezifische Einstellung mit <xref:System.Configuration.DefaultSettingValueAttribute>festlegen. Da sich benutzerspezifische Einstellungen häufig während der Ausführung der Anwendung ändern, hat `user`config Lese-/Schreibzugriff.

 Alle drei Konfigurationsdateien speichern Einstellungen im XML-Format. Das XML-Element der obersten Ebene für anwendungsspezifische Einstellungen ist `<appSettings>`, während `<userSettings>` für die benutzerspezifischen Einstellungen verwendet wird. Eine `app`. exe.config-Datei mit anwendungsspezifischen Einstellungen und Standardwerten für benutzerspezifische Einstellungen sieht wie folgt aus:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
    <configSections>
        <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" >
            <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
        </sectionGroup>
        <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" >
            <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" allowExeDefinition="MachineToLocalUser" />
        </sectionGroup>
    </configSections>
    <applicationSettings>
        <WindowsApplication1.Properties.Settings>
            <setting name="Cursor" serializeAs="String">
                <value>Default</value>
            </setting>
            <setting name="DoubleBuffering" serializeAs="String">
                <value>False</value>
            </setting>
        </WindowsApplication1.Properties.Settings>
    </applicationSettings>
    <userSettings>
        <WindowsApplication1.Properties.Settings>
            <setting name="FormTitle" serializeAs="String">
                <value>Form1</value>
            </setting>
            <setting name="FormSize" serializeAs="String">
                <value>595, 536</value>
            </setting>
        </WindowsApplication1.Properties.Settings>
    </userSettings>
</configuration>
```

 Eine Definition der Elemente im Abschnitt Anwendungseinstellungen einer Konfigurationsdatei finden Sie unter [Schema für Anwendungseinstellungen](../../configure-apps/file-schema/application-settings-schema.md).

### <a name="settings-bindings"></a>Einstellungen für Bindungen
 Anwendungseinstellungen verwenden die Datenbindungsarchitektur von Windows Forms, um die bidirektionale Kommunikation von Einstellungsaktualisierungen zwischen dem Einstellungsobjekt und den Komponenten bereitzustellen. Wenn Sie mit Visual Studio Anwendungseinstellungen erstellen und diese Komponenteneigenschaften zuordnen, werden die Bindungen automatisch generiert.

 Eine Anwendungs Einstellung kann nur an eine Komponente gebunden werden, die die <xref:System.Windows.Forms.IBindableComponent> -Schnittstelle unterstützt. Außerdem muss die Komponente ein Änderungs Ereignis für eine bestimmte gebundene Eigenschaft implementieren oder Anwendungseinstellungen benachrichtigen, dass die Eigenschaft über die <xref:System.ComponentModel.INotifyPropertyChanged> -Schnittstelle geändert wurde. Wenn die Komponente nicht implementiert und <xref:System.Windows.Forms.IBindableComponent> Sie die Bindung über Visual Studio durchführen, werden die gebundenen Eigenschaften zum ersten Mal festgelegt, aber nicht aktualisiert. Wenn die Komponente implementiert <xref:System.Windows.Forms.IBindableComponent> , aber keine Benachrichtigungen über Eigenschafts Änderungen unterstützt, wird die Bindung nicht in der Einstellungsdatei aktualisiert, wenn die-Eigenschaft geändert wird.

 Einige Windows Forms Komponenten, wie z <xref:System.Windows.Forms.ToolStripItem>. b., unterstützen keine Einstellungs Bindungen.

### <a name="settings-serialization"></a>Serialisierung von Einstellungen
 Wenn <xref:System.Configuration.LocalFileSettingsProvider> Einstellungen auf dem Datenträger gespeichert werden müssen, werden die folgenden Aktionen durchführt:

1. Verwendet Reflektion, um alle Eigenschaften zu überprüfen, <xref:System.Configuration.ApplicationSettingsBase> die in der abgeleiteten Klasse definiert sind, und <xref:System.Configuration.ApplicationScopedSettingAttribute> ermittelt <xref:System.Configuration.UserScopedSettingAttribute>die Eigenschaften, die entweder mit oder angewendet werden.

2. Serialisieren der Eigenschaft auf den Datenträger. Zuerst wird versucht, den <xref:System.ComponentModel.TypeConverter.ConvertToString%2A> oder <xref:System.ComponentModel.TypeConverter.ConvertFromString%2A> <xref:System.ComponentModel.TypeConverter>für die zugeordnete des Typs aufzurufen. Schlägt der Versuch fehl, wird stattdessen die XML-Serialisierung angewendet.

3. Bestimmen, welche Einstellungen in welche Datei übergehen, basierend auf dem Attribut der Einstellung.

 Wenn Sie Ihre eigene Einstellungs Klasse implementieren, können Sie mit dem <xref:System.Configuration.SettingsSerializeAsAttribute> eine Einstellung für die binäre oder benutzerdefinierte Serialisierung mithilfe der <xref:System.Configuration.SettingsSerializeAs> -Enumeration markieren. Weitere Informationen zum Erstellen Ihrer eigenen Einstellungs Klasse im Code finden [Sie unter Gewusst wie: Erstellen Sie Anwendungs](how-to-create-application-settings.md)Einstellungen.

### <a name="settings-file-locations"></a>Einstellen von Dateispeicherorten
 Der Speicherort der Dateien `app`. exe.config und *benutzer*.config hängt davon ab, wie die Anwendung installiert ist. Bei einer Windows Forms basierten Anwendung, die auf den lokalen Computer kopiert `app`wurde, befindet sich die Datei. exe. config im selben Verzeichnis wie das Basisverzeichnis der ausführbaren Hauptdatei der Anwendung, und die Datei " *User*. config" befindet sich an dem Speicherort, der von angegeben wird. die <xref:System.Windows.Forms.Application.LocalUserAppDataPath%2A?displayProperty=nameWithType> -Eigenschaft. Für eine Anwendung, die mittels ClickOnce installiert wird, befinden sich beide Dateien im ClickOnce-Datenverzeichnis unter%InstallRoot%\Documents und Settings\\*username*\Local Settings.

 Der Speicherort dieser Dateien unterscheidet sich geringfügig, wenn ein Benutzer Roamingprofile aktiviert hat. Der Benutzer kann dann verschiedene Windows- oder Anwendungseinstellungen definieren, wenn er andere Computer in einer Domäne verwendet. In diesem Fall werden `app`die Dateien exe. config und *User*. config sowohl von ClickOnce-Anwendungen als auch von nicht-ClickOnce-Anwendungen unter%InstallRoot%\Documents und\\Settings*username*\ Application Data gespeichert.

 Weitere Informationen zur Funktionsweise der Anwendungseinstellungen mit der neuen Bereitstellungstechnologie finden Sie unter [ClickOnce und Anwendungseinstellungen](/visualstudio/deployment/clickonce-and-application-settings). Weitere Informationen zum ClickOnce-Datenverzeichnis finden Sie unter [zugreifen auf lokale und Remote Daten in ClickOnce-Anwendungen](/visualstudio/deployment/accessing-local-and-remote-data-in-clickonce-applications).

## <a name="application-settings-and-security"></a>Einstellungen und Sicherheit von Anwendungen
 Anwendungseinstellungen sollen in teilweiser Vertrauenswürdigkeit, einer eingeschränkten Umgebung, funktionieren, die der Standard für über das Internet oder ein Intranet gehostete Windows Forms-Anwendungen ist. Außer teilweiser Vertrauenswürdigkeit sind keine besonderen Berechtigungen erforderlich, um Anwendungseinstellungen mit dem Standardeinstellungsanbieter zu verwenden.

 Wenn Anwendungseinstellungen in einer ClickOnce-Anwendung verwendet werden, `user`wird die config-Datei im ClickOnce-Datenverzeichnis gespeichert. Die Größe der config- `user`Datei der Anwendung darf nicht das von ClickOnce festgelegte Datenverzeichnis Kontingent überschreiten. Weitere Informationen finden Sie unter [ClickOnce und Anwendungseinstellungen](/visualstudio/deployment/clickonce-and-application-settings).

## <a name="custom-settings-providers"></a>Benutzerdefinierte Einstellungsanbieter
 In der Architektur der Anwendungseinstellungen gibt es eine lose Kopplung zwischen der Anwendungs Einstellungs-Wrapper Klasse, die <xref:System.Configuration.ApplicationSettingsBase>von abgeleitet ist, und den zugeordneten Einstellungs Anbietern bzw <xref:System.Configuration.SettingsProvider>. Anbietern, die von abgeleitet werden. Diese Zuordnung wird nur durch das definiert <xref:System.Configuration.SettingsProviderAttribute> , das auf die Wrapper Klasse oder die jeweiligen Eigenschaften angewendet wird. Wenn ein Einstellungs Anbieter nicht explizit angegeben wird, wird der Standardanbieter <xref:System.Configuration.LocalFileSettingsProvider>verwendet. Daher unterstützt diese Architektur das Erstellen und Verwenden von benutzerdefinierten Einstellungsanbietern.

 Nehmen wir beispielsweise an, dass Sie `SqlSettingsProvider`, entwickeln und verwenden möchten, einen Anbieter, der sämtliche Einstellungsdaten in einer Microsoft SQL Server-Datenbank speichert. Die <xref:System.Configuration.SettingsProvider>von abgeleitete Klasse empfängt diese Informationen in Ihrer `Initialize` -Methode als Parameter vom Typ <xref:System.Collections.Specialized.NameValueCollection?displayProperty=nameWithType>. Anschließend implementieren Sie die <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> -Methode, um die Einstellungen aus dem Datenspeicher abzurufen und <xref:System.Configuration.SettingsProvider.SetPropertyValues%2A> zu speichern. Der Anbieter kann den <xref:System.Configuration.SettingsPropertyCollection> bereitgestellten für <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> verwenden, um den Namen, den Typ und den Gültigkeitsbereich der Eigenschaft sowie alle anderen Einstellungs Attribute zu bestimmen, die für diese Eigenschaft definiert sind.

 Der Anbieter muss eine Eigenschaft und eine Methode implementieren, deren Implementierungen möglicherweise nicht offensichtlich sind. Die <xref:System.Configuration.SettingsProvider.ApplicationName%2A> -Eigenschaft ist eine abstrakte Eigenschaft <xref:System.Configuration.SettingsProvider>von. Sie sollten Sie programmieren, um Folgendes zurückzugeben:

 [!code-csharp[ApplicationSettings.Architecture#2](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#2)]
 [!code-vb[ApplicationSettings.Architecture#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#2)]

 Die abgeleitete Klasse muss außerdem eine `Initialize`-Methode implementieren, die keine Argumente akzeptiert und keinen Wert zurückgibt. Diese Methode wird nicht von <xref:System.Configuration.SettingsProvider>definiert.

 Schließlich implementieren Sie für <xref:System.Configuration.IApplicationSettingsProvider> Ihren Anbieter, um Unterstützung für das Aktualisieren von Einstellungen, das Zurücksetzen von Einstellungen auf ihre Standardwerte und das Aktualisieren von Einstellungen von einer Anwendungs Version auf eine andere zu bieten.

 Nachdem Sie Ihren Anbieter implementiert und kompiliert haben, müssen Sie Ihre Einstellungenklasse anweisen, diesen Anbieter anstelle des standardmäßigen Anbieters zu verwenden. Dies erreichen Sie über den <xref:System.Configuration.SettingsProviderAttribute>. Wenn Sie auf eine gesamte Einstellungs Klasse angewendet wird, wird der Anbieter für jede Einstellung verwendet, die von der-Klasse definiert wird. Wenn Sie auf einzelne Einstellungen angewendet wird, verwendet die Architektur der Anwendungseinstellungen diesen Anbieter nur für diese <xref:System.Configuration.LocalFileSettingsProvider> Einstellungen und für den Rest. Das folgende Codebeispiel veranschaulicht, wie die Einstellungenklasse angewiesen wird, den benutzerdefinierten Anbieter zu verwenden.

 [!code-csharp[ApplicationSettings.Architecture#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#1)]
 [!code-vb[ApplicationSettings.Architecture#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#1)]

 Ein Anbieter kann von mehreren Threads gleichzeitig aufgerufen werden, schreibt jedoch immer in den gleichen Speicherort. Aus diesem Grund instanziiert die Architektur für Anwendungseinstellungen immer nur eine einzelne Instanz der Anbieterklasse.

> [!IMPORTANT]
>  Sie sollten sicherstellen, dass der Anbieter threadsicher ist und jeweils nur einem Thread gestattet, in die Konfigurationsdateien zu schreiben.

 Der Anbieter muss nicht alle Einstellungs Attribute <xref:System.Configuration?displayProperty=nameWithType> unterstützen, die im-Namespace definiert sind, er muss jedoch mindestens unterstützt <xref:System.Configuration.ApplicationScopedSettingAttribute> werden und <xref:System.Configuration.UserScopedSettingAttribute>muss ebenfalls unterstützen. <xref:System.Configuration.DefaultSettingValueAttribute> Für die Attribute, die nicht unterstützt werden, sollte der Anbieter ohne Benachrichtigung fehlschlagen und keine Ausnahme auslösen. Wenn die Settings-Klasse eine ungültige Kombination von Attributen verwendet – z. <xref:System.Configuration.ApplicationScopedSettingAttribute> b <xref:System.Configuration.UserScopedSettingAttribute> . Anwenden von und auf dieselbe Einstellung –, sollte der Anbieter eine Ausnahme auslösen und den Vorgang beenden.

## <a name="see-also"></a>Siehe auch

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.SettingsProvider>
- <xref:System.Configuration.LocalFileSettingsProvider>
- [Übersicht über Anwendungseinstellungen](application-settings-overview.md)
- [Application Settings for Custom Controls](application-settings-for-custom-controls.md)
- [ClickOnce und Anwendungseinstellungen](/visualstudio/deployment/clickonce-and-application-settings)
- [Schema für Anwendungseinstellungen](../../configure-apps/file-schema/application-settings-schema.md)
