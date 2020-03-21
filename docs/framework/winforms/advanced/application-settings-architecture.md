---
title: Architektur der Anwendungseinstellungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application settings [Windows Forms], architecture
ms.assetid: c8eb2ad0-fac6-4ea2-9140-675a4a44d562
ms.openlocfilehash: 078b5f3fc1cd4273af282580f41e68ca9bd8ff51
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182629"
---
# <a name="application-settings-architecture"></a>Architektur der Anwendungseinstellungen
In diesem Thema wird beschrieben, wie die Architektur der Anwendungseinstellungen funktioniert. Außerdem werden erweiterte Funktionen der Architektur erläutert, z.B. gruppierte Einstellungen und Einstellungsschlüssel.

 Die Architektur der Anwendungseinstellungen unterstützt definierende, stark typisierte Einstellungen mit Geltungsbereich Anwendung oder Benutzer sowie die Beibehaltung der Einstellungen zwischen Anwendungssitzungen. Die Architektur bietet eine Standardpersistenz-Engine zum Speichern von Einstellungen und Laden aus dem lokalen Dateisystem. Die Architektur definiert auch Schnittstellen zur Bereitstellung einer benutzerdefinierten Persistenz-Engine.

 Schnittstellen werden bereitgestellt, die benutzerdefinierten Komponenten ermöglichen, ihre eigenen Einstellungen beizubehalten, wenn sie in einer Anwendung gehostet werden können. Mithilfe von Einstellungsschlüsseln können Komponenten Einstellungen für mehrere Instanzen der Komponente getrennt halten.

## <a name="defining-settings"></a>Definieren von Einstellungen
 Die Architektur der Anwendungseinstellungen wird sowohl in ASP.NET als auch in Windows Forms verwendet und enthält eine Reihe von Basisklassen, die in beiden Umgebungen gemeinsam genutzt werden. Die wichtigste <xref:System.Configuration.SettingsBase>ist , die Zugriff auf Einstellungen über eine Auflistung bietet und Low-Level-Methoden zum Laden und Speichern von Einstellungen bietet. Jede Umgebung implementiert eine eigene <xref:System.Configuration.SettingsBase> Klasse, von der abgeleitet wird, um zusätzliche Einstellungsfunktionen für diese Umgebung bereitzustellen. In einer Windows Forms-basierten Anwendung müssen alle Anwendungseinstellungen für <xref:System.Configuration.ApplicationSettingsBase> eine von der Klasse abgeleitete Klasse definiert werden, wodurch der Basisklasse die folgenden Funktionen hinzugefügt werden:

- Lade- und Speichervorgänge auf höherer Ebene

- Unterstützung für benutzerspezifische Einstellungen

- Wiederherstellen der vordefinierten Standardeinstellungen eines Benutzers

- Aktualisieren von Einstellungen aus einer früheren Anwendungsversion

- Überprüfen von Einstellungen, bevor sie geändert oder bevor sie gespeichert werden

 Die Einstellungen können mit einer Reihe von <xref:System.Configuration> Attributen beschrieben werden, die im Namespace definiert sind. Diese werden unter [Anwendungseinstellungsattribute](application-settings-attributes.md)beschrieben. Wenn Sie eine Einstellung definieren, müssen <xref:System.Configuration.ApplicationScopedSettingAttribute> <xref:System.Configuration.UserScopedSettingAttribute>Sie sie mit einer oder anwenden, die beschreibt, ob die Einstellung für die gesamte Anwendung oder nur für den aktuellen Benutzer gilt.

 Das folgende Codebeispiel definiert eine benutzerdefinierte Einstellungsklasse mit einer Einstellung: `BackgroundColor`.

 [!code-csharp[ApplicationSettings.Create#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
 [!code-vb[ApplicationSettings.Create#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]

## <a name="settings-persistence"></a>Beibehaltung von Einstellungen
 Die <xref:System.Configuration.ApplicationSettingsBase> Klasse selbst besteht nicht oder lädt die Einstellungen nicht. Dieser Auftrag fällt an den Einstellungsanbieter, <xref:System.Configuration.SettingsProvider>eine Klasse, die von ableitet. Wenn eine abgeleitete Klasse von <xref:System.Configuration.ApplicationSettingsBase> keinen <xref:System.Configuration.SettingsProviderAttribute>Einstellungsanbieter über <xref:System.Configuration.LocalFileSettingsProvider>die angibt, wird der Standardanbieter , verwendet.

 Das Konfigurationssystem, das ursprünglich mit .NET Framework veröffentlicht wurde, unterstützt die Bereitstellung statischer Anwendungskonfigurationsdaten entweder über die Computer.config-Datei des lokalen Computers oder in einer `app.`exe.config-Datei, die Sie mit Ihrer Anwendung bereitstellen. Die <xref:System.Configuration.LocalFileSettingsProvider> Klasse erweitert diese systemeigene Unterstützung auf folgende Weise:

- Anwendungsspezifische Einstellungen können in der Datei machine.config oder `app.`exe.config gespeichert werden. Die Datei machine.config ist immer schreibgeschützt, während `app`. exe.config aufgrund von Sicherheitsüberlegungen für die meisten Anwendungen schreibgeschützt ist.

- Benutzerspezifische Einstellungen können in `app`. exe.config-Dateien gespeichert werden und werden dann als statische Standardwerte behandelt.

- Nicht standardmäßige benutzerspezifische Einstellungen werden in einer neuen Datei, *benutzer*.config gespeichert, wobei *benutzer* der Benutzername der Person ist, die aktuell die Anwendung ausführt. Sie können einen Standardwert für eine <xref:System.Configuration.DefaultSettingValueAttribute>benutzerbezogene Einstellung mit angeben. Da sich benutzerspezifische Einstellungen häufig während der Ausführung der Anwendung ändern, hat `user`config Lese-/Schreibzugriff.

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

 Sie können eine Anwendungseinstellung nur an <xref:System.Windows.Forms.IBindableComponent> eine Komponente binden, die die Schnittstelle unterstützt. Außerdem muss die Komponente ein Änderungsereignis für eine bestimmte gebundene Eigenschaft implementieren <xref:System.ComponentModel.INotifyPropertyChanged> oder Anwendungseinstellungen benachrichtigen, dass sich die Eigenschaft über die Schnittstelle geändert hat. Wenn die Komponente <xref:System.Windows.Forms.IBindableComponent> nicht implementiert wird und Sie über Visual Studio binden, werden die gebundenen Eigenschaften beim ersten Mal festgelegt, aber nicht aktualisiert. Wenn die Komponente <xref:System.Windows.Forms.IBindableComponent> Benachrichtigungen über Eigenschaftenänderungen implementiert, aber nicht unterstützt, wird die Bindung in der Einstellungsdatei nicht aktualisiert, wenn die Eigenschaft geändert wird.

 Einige Windows Forms-Komponenten, z. <xref:System.Windows.Forms.ToolStripItem>B. , unterstützen keine Einstellungsbindungen.

### <a name="settings-serialization"></a>Serialisierung von Einstellungen
 Wenn <xref:System.Configuration.LocalFileSettingsProvider> Einstellungen auf dem Datenträger gespeichert werden müssen, führt es die folgenden Aktionen aus:

1. Verwendet Reflektion, um alle Eigenschaften <xref:System.Configuration.ApplicationSettingsBase> zu untersuchen, die für <xref:System.Configuration.ApplicationScopedSettingAttribute> die <xref:System.Configuration.UserScopedSettingAttribute>abgeleitete Klasse definiert sind, und findet diejenigen, die mit entweder oder angewendet werden.

2. Serialisieren der Eigenschaft auf den Datenträger. Es wird zunächst <xref:System.ComponentModel.TypeConverter.ConvertToString%2A> versucht, den oder <xref:System.ComponentModel.TypeConverter.ConvertFromString%2A> <xref:System.ComponentModel.TypeConverter>auf dem zugeordneten Typ aufzurufen. Schlägt der Versuch fehl, wird stattdessen die XML-Serialisierung angewendet.

3. Bestimmen, welche Einstellungen in welche Datei übergehen, basierend auf dem Attribut der Einstellung.

 Wenn Sie eine eigene Einstellungsklasse <xref:System.Configuration.SettingsSerializeAsAttribute> implementieren, können Sie die verwenden, um <xref:System.Configuration.SettingsSerializeAs> eine Einstellung für die binäre oder benutzerdefinierte Serialisierung mithilfe der Enumeration zu markieren. Weitere Informationen zum Erstellen eigener Einstellungen finden Sie unter [Vorgehensweise: Erstellen von Anwendungseinstellungen](how-to-create-application-settings.md).

### <a name="settings-file-locations"></a>Speicherorte für Einstellungsdateien
 Der Speicherort der Dateien `app`. exe.config und *benutzer*.config hängt davon ab, wie die Anwendung installiert ist. Bei einer Windows Forms-basierten Anwendung, die `app`auf den lokalen Computer kopiert wird, befindet sich .exe.config im selben Verzeichnis wie das Basisverzeichnis der <xref:System.Windows.Forms.Application.LocalUserAppDataPath%2A?displayProperty=nameWithType> Hauptdatei der ausführbaren Datei der Anwendung, und *Benutzer*.config befindet sich an dem von der Eigenschaft angegebenen Speicherort. Für eine Anwendung, die mit ClickOnce installiert wird, befinden sich beide Dateien im ClickOnce-Datenverzeichnis unter %InstallRoot%-Documents und\\*Settings-Benutzernamen*.

 Der Speicherort dieser Dateien unterscheidet sich geringfügig, wenn ein Benutzer Roamingprofile aktiviert hat, wodurch ein Benutzer verschiedene Windows- und Anwendungseinstellungen definieren kann, wenn er andere Computer innerhalb einer Domäne verwendet. In diesem Fall werden sowohl ClickOnce-Anwendungen als `app`auch Nicht-ClickOnce-Anwendungen ihre .exe.config- und *Benutzer*-Konfigurationsdateien unter %InstallRoot%-Dokumente und\\*Einstellungen-Benutzernamen*.Application Data gespeichert.

 Weitere Informationen zur Funktionsweise der Anwendungseinstellungen mit der neuen Bereitstellungstechnologie finden Sie unter [ClickOnce und Anwendungseinstellungen](/visualstudio/deployment/clickonce-and-application-settings). Weitere Informationen zum ClickOnce-Datenverzeichnis finden Sie [unter Zugriff auf lokale und Remotedaten in ClickOnce-Anwendungen](/visualstudio/deployment/accessing-local-and-remote-data-in-clickonce-applications).

## <a name="application-settings-and-security"></a>Einstellungen und Sicherheit von Anwendungen
 Anwendungseinstellungen sollen in teilweiser Vertrauenswürdigkeit, einer eingeschränkten Umgebung, funktionieren, die der Standard für über das Internet oder ein Intranet gehostete Windows Forms-Anwendungen ist. Außer teilweiser Vertrauenswürdigkeit sind keine besonderen Berechtigungen erforderlich, um Anwendungseinstellungen mit dem Standardeinstellungsanbieter zu verwenden.

 Wenn Anwendungseinstellungen in einer ClickOnce-Anwendung verwendet werden, wird die `user`.config-Datei im Datenverzeichnis ClickOnce gespeichert. Die Größe der `user`.config-Datei der Anwendung darf das von ClickOnce festgelegte Datenverzeichniskontingent nicht überschreiten. Weitere Informationen finden Sie unter [ClickOnce und Anwendungseinstellungen](/visualstudio/deployment/clickonce-and-application-settings).

## <a name="custom-settings-providers"></a>Benutzerdefinierte Einstellungsanbieter
 In der Architektur der Anwendungseinstellungen gibt es eine lose Kopplung <xref:System.Configuration.ApplicationSettingsBase>zwischen der Wrapperklasse der Anwendungseinstellungen, abgeleitet von , und dem zugehörigen Einstellungsanbieter oder -anbieter, abgeleitet von <xref:System.Configuration.SettingsProvider>. Diese Zuordnung wird nur <xref:System.Configuration.SettingsProviderAttribute> durch die auf die Wrapperklasse oder ihre einzelnen Eigenschaften angewendete Zuordnung definiert. Wenn ein Einstellungsanbieter nicht explizit angegeben <xref:System.Configuration.LocalFileSettingsProvider>ist, wird der Standardanbieter , verwendet. Daher unterstützt diese Architektur das Erstellen und Verwenden von benutzerdefinierten Einstellungsanbietern.

 Nehmen wir beispielsweise an, dass Sie `SqlSettingsProvider`, entwickeln und verwenden möchten, einen Anbieter, der sämtliche Einstellungsdaten in einer Microsoft SQL Server-Datenbank speichert. Ihre <xref:System.Configuration.SettingsProvider>-derived-Klasse würde diese `Initialize` Informationen in ihrer <xref:System.Collections.Specialized.NameValueCollection?displayProperty=nameWithType>Methode als Parameter vom Typ erhalten. Anschließend implementieren Sie <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> die Methode, um Ihre Einstellungen <xref:System.Configuration.SettingsProvider.SetPropertyValues%2A> aus dem Datenspeicher abzurufen und zu speichern. Ihr Anbieter kann <xref:System.Configuration.SettingsPropertyCollection> die <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> angegebene verwenden, um den Namen, typ und den Bereich der Eigenschaft sowie alle anderen für diese Eigenschaft definierten Einstellungsattribute zu bestimmen.

 Der Anbieter muss eine Eigenschaft und eine Methode implementieren, deren Implementierungen möglicherweise nicht offensichtlich sind. Die <xref:System.Configuration.SettingsProvider.ApplicationName%2A> Eigenschaft ist eine <xref:System.Configuration.SettingsProvider>abstrakte Eigenschaft von ; Sie sollten es programmieren, um Folgendes zurückzugeben:

 [!code-csharp[ApplicationSettings.Architecture#2](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#2)]
 [!code-vb[ApplicationSettings.Architecture#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#2)]

 Die abgeleitete Klasse muss außerdem eine `Initialize`-Methode implementieren, die keine Argumente akzeptiert und keinen Wert zurückgibt. Diese Methode ist <xref:System.Configuration.SettingsProvider>nicht durch definiert.

 Schließlich implementieren <xref:System.Configuration.IApplicationSettingsProvider> Sie auf Ihrem Provider, um Unterstützung für Aktualisierungseinstellungen bereitzustellen, Einstellungen auf ihre Standardeinstellungen zurücksetzen und Einstellungen von einer Anwendungsversion auf eine andere aktualisieren.

 Nachdem Sie Ihren Anbieter implementiert und kompiliert haben, müssen Sie Ihre Einstellungenklasse anweisen, diesen Anbieter anstelle des standardmäßigen Anbieters zu verwenden. Sie erreichen dies durch die <xref:System.Configuration.SettingsProviderAttribute>. Wenn er auf eine gesamte Einstellungsklasse angewendet wird, wird der Anbieter für jede Einstellung verwendet, die von der Klasse definiert wird. Wenn die Architektur für Anwendungseinstellungen auf einzelne Einstellungen angewendet <xref:System.Configuration.LocalFileSettingsProvider> wird, wird dieser Anbieter nur für diese Einstellungen verwendet, und für den Rest. Das folgende Codebeispiel veranschaulicht, wie die Einstellungenklasse angewiesen wird, den benutzerdefinierten Anbieter zu verwenden.

 [!code-csharp[ApplicationSettings.Architecture#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#1)]
 [!code-vb[ApplicationSettings.Architecture#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#1)]

 Ein Anbieter kann von mehreren Threads gleichzeitig aufgerufen werden, schreibt jedoch immer in den gleichen Speicherort. Aus diesem Grund instanziiert die Architektur für Anwendungseinstellungen immer nur eine einzelne Instanz der Anbieterklasse.

> [!IMPORTANT]
> Sie sollten sicherstellen, dass der Anbieter threadsicher ist und jeweils nur einem Thread gestattet, in die Konfigurationsdateien zu schreiben.

 Ihr Anbieter muss nicht alle <xref:System.Configuration?displayProperty=nameWithType> im Namespace definierten Einstellungsattribute unterstützen, obwohl <xref:System.Configuration.ApplicationScopedSettingAttribute> er <xref:System.Configuration.UserScopedSettingAttribute>mindestens unterstützt <xref:System.Configuration.DefaultSettingValueAttribute>und unterstützt werden muss. Für die Attribute, die nicht unterstützt werden, sollte der Anbieter ohne Benachrichtigung fehlschlagen und keine Ausnahme auslösen. Wenn die Einstellungsklasse jedoch eine ungültige Kombination von <xref:System.Configuration.ApplicationScopedSettingAttribute> <xref:System.Configuration.UserScopedSettingAttribute> Attributen verwendet, z. B. anwenden und auf dieselbe Einstellung, sollte Ihr Anbieter eine Ausnahme auslösen und den Betrieb beenden.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.SettingsProvider>
- <xref:System.Configuration.LocalFileSettingsProvider>
- [Übersicht über Anwendungseinstellungen](application-settings-overview.md)
- [Application Settings for Custom Controls](application-settings-for-custom-controls.md)
- [ClickOnce und Anwendungseinstellungen](/visualstudio/deployment/clickonce-and-application-settings)
- [Schema für Anwendungseinstellungen](../../configure-apps/file-schema/application-settings-schema.md)
