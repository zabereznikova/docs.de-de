---
title: Architektur der Anwendungseinstellungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application settings [Windows Forms], architecture
ms.assetid: c8eb2ad0-fac6-4ea2-9140-675a4a44d562
ms.openlocfilehash: 769077ddbe42d4d774d359de75417bdca6bcaeb5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="application-settings-architecture"></a>Architektur der Anwendungseinstellungen
In diesem Thema wird beschrieben, wie die Architektur der Anwendungseinstellungen funktioniert. Außerdem werden erweiterte Funktionen der Architektur erläutert, z.B. gruppierte Einstellungen und Einstellungsschlüssel.  
  
 Die Architektur der Anwendungseinstellungen unterstützt definierende, stark typisierte Einstellungen mit Geltungsbereich Anwendung oder Benutzer sowie die Beibehaltung der Einstellungen zwischen Anwendungssitzungen. Die Architektur bietet ein Standardpersistenzmodul zum Speichern von Einstellungen und Laden aus dem lokalen Dateisystem. Die Architektur definiert auch Schnittstellen zur Bereitstellung eines benutzerdefinierten Persistenzmoduls.  
  
 Schnittstellen werden bereitgestellt, die benutzerdefinierten Komponenten ermöglichen, ihre eigenen Einstellungen beizubehalten, wenn sie in einer Anwendung gehostet werden können. Mithilfe von Einstellungsschlüsseln können Komponenten Einstellungen für mehrere Instanzen der Komponente getrennt halten.  
  
## <a name="defining-settings"></a>Definieren von Einstellungen  
 Die Architektur der Anwendungseinstellungen wird in [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] und in Windows Forms verwendet und enthält eine Reihe von Basisklassen, die beide Umgebungen gemeinsam verwenden. Am wichtigsten ist <xref:System.Configuration.SettingsBase>, die ermöglicht den Zugriff auf Einstellungen durch eine Auflistung, und stellt Low-Level-Methoden zum Laden und Speichern von Einstellungen bereit. Jede Umgebung implementiert eine eigene Klasse abgeleitet <xref:System.Configuration.SettingsBase> um zusätzliche Einstellungsfunktionen für diese Umgebung bereitzustellen. In einer Windows Forms-basierten Anwendung, alle Anwendungseigenschaften definiert werden müssen, in einer abgeleiteten Klasse die <xref:System.Configuration.ApplicationSettingsBase> -Klasse, die die Basisklasse der Klasse die folgende Funktionalität hinzufügt:  
  
-   Lade- und Speichervorgänge auf höherer Ebene  
  
-   Unterstützung für benutzerspezifische Einstellungen  
  
-   Wiederherstellen der vordefinierten Standardeinstellungen eines Benutzers  
  
-   Aktualisieren von Einstellungen aus einer früheren Anwendungsversion  
  
-   Überprüfen von Einstellungen, bevor sie geändert oder bevor sie gespeichert werden  
  
 Die Einstellungen können über eine Reihe von Attributen, die in definierten beschrieben werden die <xref:System.Configuration> Namespace; diese Angaben werden in [Application Settings Attributes](../../../../docs/framework/winforms/advanced/application-settings-attributes.md). Wenn Sie eine Einstellung definieren, müssen Sie sie anwenden, entweder mit <xref:System.Configuration.ApplicationScopedSettingAttribute> oder <xref:System.Configuration.UserScopedSettingAttribute>, das beschreibt, ob die Einstellung für die gesamte Anwendung oder nur für den aktuellen Benutzer gilt.  
  
 Das folgende Codebeispiel definiert eine benutzerdefinierte Einstellungsklasse mit einer Einstellung: `BackgroundColor`.  
  
 [!code-csharp[ApplicationSettings.Create#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
 [!code-vb[ApplicationSettings.Create#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]  
  
## <a name="settings-persistence"></a>Beibehaltung von Einstellungen  
 Die <xref:System.Configuration.ApplicationSettingsBase> ; Klasse nicht selbst persistent zu speichern oder Laden Sie die Einstellungen für diesen Auftrag fragt der Einstellungsanbieter, eine Klasse, die abgeleitet <xref:System.Configuration.SettingsProvider>. Wenn eine abgeleitete Klasse von <xref:System.Configuration.ApplicationSettingsBase> gibt keinen Einstellungsanbieter über die <xref:System.Configuration.SettingsProviderAttribute>, und klicken Sie dann den Standardanbieter <xref:System.Configuration.LocalFileSettingsProvider>, verwendet wird.  
  
 Das Konfigurationssystem, das ursprünglich mit [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] veröffentlicht wurde, unterstützt die Bereitstellung von statischen Anwendungskonfigurationsdaten über die Datei machine.config des lokalen Computers oder in einer Datei `app.`exe.config, die Sie mit Ihrer Anwendung bereitstellen. Die <xref:System.Configuration.LocalFileSettingsProvider> -Klasse erweitert diese systemeigene Unterstützung auf folgende Weise:  
  
-   Anwendungsspezifische Einstellungen können in der Datei machine.config oder `app.`exe.config gespeichert werden. Die Datei machine.config ist immer schreibgeschützt, während `app`. exe.config aufgrund von Sicherheitsüberlegungen für die meisten Anwendungen schreibgeschützt ist.  
  
-   Benutzerspezifische Einstellungen können in `app`. exe.config-Dateien gespeichert werden und werden dann als statische Standardwerte behandelt.  
  
-   Nicht standardmäßige benutzerspezifische Einstellungen werden in einer neuen Datei, *benutzer*.config gespeichert, wobei *benutzer* der Benutzername der Person ist, die aktuell die Anwendung ausführt. Sie können angeben, den Standardwert für eine benutzerspezifische Einstellung mit <xref:System.Configuration.DefaultSettingValueAttribute>. Da sich benutzerspezifische Einstellungen häufig während der Ausführung der Anwendung ändern, hat `user`config Lese-/Schreibzugriff.  
  
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
  
 Eine Definition der Elemente im Abschnitt Anwendungseinstellungen einer Konfigurationsdatei finden Sie unter [Schema für Anwendungseinstellungen](../../../../docs/framework/configure-apps/file-schema/application-settings-schema.md).  
  
### <a name="settings-bindings"></a>Einstellungen für Bindungen  
 Anwendungseinstellungen verwenden die Datenbindungsarchitektur von Windows Forms, um die bidirektionale Kommunikation von Einstellungsaktualisierungen zwischen dem Einstellungsobjekt und den Komponenten bereitzustellen. Wenn Sie mit Visual Studio Anwendungseinstellungen erstellen und diese Komponenteneigenschaften zuordnen, werden die Bindungen automatisch generiert.  
  
 Sie können nur eine anwendungseinstellung binden, um eine Komponente, die unterstützt die <xref:System.Windows.Forms.IBindableComponent> Schnittstelle. Darüber hinaus die Komponente implementieren ein Änderungsereignis für eine bestimmte Eigenschaft gebunden muss, oder benachrichtigen von Anwendungseinstellungen, die über die Eigenschaft geändert wurde die <xref:System.ComponentModel.INotifyPropertyChanged> Schnittstelle. Wenn die Komponente keine implementiert <xref:System.Windows.Forms.IBindableComponent> und Bindung mithilfe von Visual Studio, die gebundenen Eigenschaften werden erstmalig festgelegt werden, aber werden nicht aktualisiert. Wenn die Komponente implementiert <xref:System.Windows.Forms.IBindableComponent> jedoch nicht die Support-Eigenschaft ändert sich Benachrichtigungen, die Bindung wird in der Datei nicht aktualisiert, wenn die Eigenschaft geändert wird.  
  
 Einige Windows Forms-Komponenten, wie z. B. <xref:System.Windows.Forms.ToolStripItem>, Einstellungen für Bindungen nicht unterstützt.  
  
### <a name="settings-serialization"></a>Serialisierung von Einstellungen  
 Wenn <xref:System.Configuration.LocalFileSettingsProvider> müssen Einstellungen auf einem Datenträger gespeichert, er führt die folgenden Aktionen aus:  
  
1.  Verwendet Reflektion, um alle definierten Eigenschaften untersuchen Ihrer <xref:System.Configuration.ApplicationSettingsBase> abgeleitete Klasse, suchen, die entweder mit angewendet werden <xref:System.Configuration.ApplicationScopedSettingAttribute> oder <xref:System.Configuration.UserScopedSettingAttribute>.  
  
2.  Serialisieren der Eigenschaft auf den Datenträger. Zuerst versucht wird, rufen Sie die <xref:System.ComponentModel.TypeConverter.ConvertToString%2A> oder <xref:System.ComponentModel.TypeConverter.ConvertFromString%2A> auf der Typ des verknüpften <xref:System.ComponentModel.TypeConverter>. Schlägt der Versuch fehl, wird stattdessen die XML-Serialisierung angewendet.  
  
3.  Bestimmen, welche Einstellungen in welche Datei übergehen, basierend auf dem Attribut der Einstellung.  
  
 Wenn Sie Ihrer eigenen Einstellungsklasse implementieren, können Sie die <xref:System.Configuration.SettingsSerializeAsAttribute> , markieren Sie eine Einstellung für die binäre oder benutzerdefinierte Serialisierung mithilfe der <xref:System.Configuration.SettingsSerializeAs> Enumeration. Weitere Informationen zum Erstellen eigener Einstellungen finden Sie unter [Vorgehensweise: Erstellen von Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).  
  
### <a name="settings-file-locations"></a>Einstellen von Dateispeicherorten  
 Der Speicherort der Dateien `app`. exe.config und *benutzer*.config hängt davon ab, wie die Anwendung installiert ist. Für eine Windows Forms basierende Anwendung, die auf dem lokalen Computer kopiert `app`. exe.config befindet sich in demselben Verzeichnis wie das Basisverzeichnis der zentralen ausführbaren Datei der Anwendung, und *Benutzer*config befindet sich in der vom angegebenen Speicherort der <xref:System.Windows.Forms.Application.LocalUserAppDataPath%2A?displayProperty=nameWithType> Eigenschaft. Bei einer mit [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] installierten Anwendung befinden sich die beiden Dateien im [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]-Datenverzeichnis unter %InstallRoot%\Dokumente und Einstellungen\\*benutzername*\Lokale Einstellungen.  
  
 Der Speicherort dieser Dateien unterscheidet sich geringfügig, wenn ein Benutzer Roamingprofile aktiviert hat. Der Benutzer kann dann verschiedene Windows- oder Anwendungseinstellungen definieren, wenn er andere Computer in einer Domäne verwendet. In diesem Fall werden die Datei `app`.exe.config und *benutzer*.config von [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]-Anwendungen und Nicht-[!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]-Anwendungen unter %InstallRoot%\Dokumente und Einstellungen \\*benutzername*\Application Data gespeichert.  
  
 Weitere Informationen zur Funktionsweise der Anwendungseinstellungen mit der neuen Bereitstellungstechnologie finden Sie unter [ClickOnce und Anwendungseinstellungen](/visualstudio/deployment/clickonce-and-application-settings). Weitere Informationen zum [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]-Datenverzeichnis finden Sie unter [Zugreifen auf lokale und Remotedaten in einer ClickOnce-Anwendung](/visualstudio/deployment/accessing-local-and-remote-data-in-clickonce-applications).  
  
## <a name="application-settings-and-security"></a>Einstellungen und Sicherheit von Anwendungen  
 Anwendungseinstellungen sollen in teilweiser Vertrauenswürdigkeit, einer eingeschränkten Umgebung, funktionieren, die der Standard für über das Internet oder ein Intranet gehostete Windows Forms-Anwendungen ist. Außer teilweiser Vertrauenswürdigkeit sind keine besonderen Berechtigungen erforderlich, um Anwendungseinstellungen mit dem Standardeinstellungsanbieter zu verwenden.  
  
 Wenn Anwendungseinstellungen in einer [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]-Anwendung verwendet werden, wird die Datei `user`.config im [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]-Datenverzeichnis gespeichert. Die Größe der Datei `user`.config der Anwendung kann das Datenverzeichniskontingent nicht überschreiten, das von [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] festgelegt wurde. Weitere Informationen finden Sie unter [ClickOnce und Anwendungseinstellungen](/visualstudio/deployment/clickonce-and-application-settings).  
  
## <a name="custom-settings-providers"></a>Benutzerdefinierte Einstellungsanbieter  
 In der Application Settings-Architektur besteht eine lose Kopplung zwischen den Einstellungen für Anwendungen Wrapperklasse, abgeleitet <xref:System.Configuration.ApplicationSettingsBase>, und die zugehörigen Einstellungsanbieter oder Anbietern abgeleitete <xref:System.Configuration.SettingsProvider>. Diese Zuordnung wird nur von definiert die <xref:System.Configuration.SettingsProviderAttribute> auf die Wrapperklasse oder ihre einzelnen Eigenschaften angewendet. Wenn ein Einstellungsanbieter nicht explizit den Standardanbieter angegeben, <xref:System.Configuration.LocalFileSettingsProvider>, verwendet wird. Daher unterstützt diese Architektur das Erstellen und Verwenden von benutzerdefinierten Einstellungsanbietern.  
  
 Nehmen wir beispielsweise an, dass Sie `SqlSettingsProvider`, entwickeln und verwenden möchten, einen Anbieter, der sämtliche Einstellungsdaten in einer Microsoft SQL Server-Datenbank speichert. Ihre <xref:System.Configuration.SettingsProvider>-abgeleitete Klasse würde diese Informationen im empfangen der `Initialize` -Methode einen Parameter vom Typ <xref:System.Collections.Specialized.NameValueCollection?displayProperty=nameWithType>. Implementieren Sie dann die <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> Methode, um die Einstellungen aus dem Datenspeicher abzurufen und <xref:System.Configuration.SettingsProvider.SetPropertyValues%2A> zu speichern. Der Anbieter verwenden, kann die <xref:System.Configuration.SettingsPropertyCollection> für angegebene <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> um der Eigenschaft Name, Typ und Bereich zu bestimmen, sowie alle anderen Einstellungsattribute, die für diese Eigenschaft definiert.  
  
 Der Anbieter muss eine Eigenschaft und eine Methode implementieren, deren Implementierungen möglicherweise nicht offensichtlich sind. Die <xref:System.Configuration.SettingsProvider.ApplicationName%2A> Eigenschaft ist eine abstrakte Eigenschaft von <xref:System.Configuration.SettingsProvider>; Sie sollten programmieren sie die folgenden Rückgabewerte:  
  
 [!code-csharp[ApplicationSettings.Architecture#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#2)]
 [!code-vb[ApplicationSettings.Architecture#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#2)]  
  
 Die abgeleitete Klasse muss außerdem eine `Initialize`-Methode implementieren, die keine Argumente akzeptiert und keinen Wert zurückgibt. Diese Methode ist nicht definiert, indem <xref:System.Configuration.SettingsProvider>.  
  
 Implementieren Sie zum Schluss <xref:System.Configuration.IApplicationSettingsProvider> für den Anbieter zu unterstützen, die für das Aktualisieren von Einstellungen, Einstellungen auf ihre Standardwerte zurücksetzen und Aktualisieren von Einstellungen aus Version einer Anwendung in eine andere.  
  
 Nachdem Sie Ihren Anbieter implementiert und kompiliert haben, müssen Sie Ihre Einstellungenklasse anweisen, diesen Anbieter anstelle des standardmäßigen Anbieters zu verwenden. Sie erreichen dies durch die <xref:System.Configuration.SettingsProviderAttribute>. Wenn auf eine ganze Settings-Klasse angewendet wird, wird der Anbieter für jede Einstellung verwendet, die die Klasse definiert; Wenn Sie auf einzelne Einstellungen angewendet Anwendungseinstellungen Architektur verwendet diesen Anbieter für diese Einstellungen nur und <xref:System.Configuration.LocalFileSettingsProvider> für den Rest. Das folgende Codebeispiel veranschaulicht, wie die Einstellungenklasse angewiesen wird, den benutzerdefinierten Anbieter zu verwenden.  
  
 [!code-csharp[ApplicationSettings.Architecture#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#1)]
 [!code-vb[ApplicationSettings.Architecture#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#1)]  
  
 Ein Anbieter kann von mehreren Threads gleichzeitig aufgerufen werden, schreibt jedoch immer in den gleichen Speicherort. Aus diesem Grund instanziiert die Architektur für Anwendungseinstellungen immer nur eine einzelne Instanz der Anbieterklasse.  
  
> [!IMPORTANT]
>  Sie sollten sicherstellen, dass der Anbieter threadsicher ist und jeweils nur einem Thread gestattet, in die Konfigurationsdateien zu schreiben.  
  
 Ihr Anbieter muss nicht alle Einstellungen unterstützen Attribute definiert werden, in der <xref:System.Configuration?displayProperty=nameWithType> Namespace, obwohl es an eine minimale Unterstützung muss <xref:System.Configuration.ApplicationScopedSettingAttribute> und <xref:System.Configuration.UserScopedSettingAttribute>, sollte auch unterstützen <xref:System.Configuration.DefaultSettingValueAttribute>. Für die Attribute, die nicht unterstützt werden, sollte der Anbieter ohne Benachrichtigung fehlschlagen und keine Ausnahme auslösen. Wenn eine ungültige Kombination von Attributen, jedoch werden die Settings-Klasse verwendet – beispielsweise das Anwenden <xref:System.Configuration.ApplicationScopedSettingAttribute> und <xref:System.Configuration.UserScopedSettingAttribute> auf die gleiche Einstellung – sollte der Anbieter eine Ausnahme auslösen und die Operation beendet werden soll.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Configuration.ApplicationSettingsBase>  
 <xref:System.Configuration.SettingsProvider>  
 <xref:System.Configuration.LocalFileSettingsProvider>  
 [Übersicht über Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/application-settings-overview.md)  
 [Anwendungseinstellungen für benutzerdefinierte Steuerelemente](../../../../docs/framework/winforms/advanced/application-settings-for-custom-controls.md)  
 [ClickOnce und Anwendungseinstellungen](/visualstudio/deployment/clickonce-and-application-settings)  
 [Schema für Anwendungseinstellungen](../../../../docs/framework/configure-apps/file-schema/application-settings-schema.md)
