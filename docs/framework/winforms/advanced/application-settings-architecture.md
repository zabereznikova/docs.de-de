---
title: "Architektur der Anwendungseinstellungen | Microsoft Docs"
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
  - "Anwendungseinstellungen [Windows Forms], Architektur"
ms.assetid: c8eb2ad0-fac6-4ea2-9140-675a4a44d562
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# Architektur der Anwendungseinstellungen
In diesem Thema wird die Funktionsweise der Architektur der Anwendungseinstellungen beschrieben, und es werden erweiterte Features der Architektur untersucht, z. B. gruppierte Einstellungen und Einstellungsschlüssel.  
  
 Die Architektur der Anwendungseinstellungen unterstützt die Definition von strikt typisierten Einstellungen für Anwendungen oder Benutzer sowie das Erhalten von Einstellungen zwischen Anwendungssitzungen.  Die Architektur stellt ein standardmäßiges Beibehaltungsmodul bereit, um Einstellungen aus dem lokalen Dateisystem zu laden und darin zu speichern.  Die Architektur definiert zudem Schnittstellen zur Bereitstellung eines benutzerdefinierten Beibehaltungsmoduls.  
  
 Es werden Schnittstellen bereitgestellt, die ermöglichen, dass die eigenen Einstellungen benutzerdefinierter Komponenten erhalten bleiben, wenn sie in einer Anwendung gehostet werden.  Mithilfe von Einstellungsschlüsseln können Komponenten Einstellungen für mehrere Instanzen der Komponente getrennt speichern.  
  
## Definieren von Einstellungen  
 Die Architektur der Anwendungseinstellungen wird sowohl in [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] als auch in Windows Forms verwendet und enthält eine Reihe von Basisklassen, die von beiden Umgebungen gemeinsam verwendet werden.  Die wichtigste Klasse ist <xref:System.Configuration.SettingsBase>, die über eine Auflistung Zugriff auf Einstellungen bietet und auf niedriger Ebene Methoden zum Laden und Speichern von Einstellungen bereitstellt.  Jede Umgebung implementiert ihre eigene von <xref:System.Configuration.SettingsBase> abgeleitete Klasse, um für diese Umgebung zusätzliche Einstellungsfunktionen bereitzustellen.  In einer auf Windows Forms basierenden Anwendung müssen alle Anwendungseinstellungen in einer Klasse definiert werden, die von der <xref:System.Configuration.ApplicationSettingsBase>\-Klasse abgeleitet ist und die die Basisklasse um folgende Funktionen erweitert:  
  
-   Lade\- und Speicheroperationen auf höherer Ebene  
  
-   Unterstützung für benutzerspezifische Einstellungen  
  
-   Zurücksetzen der Einstellungen eines Benutzers auf die vordefinierten Standards  
  
-   Aktualisieren von Einstellungen von einer früheren Anwendungsversion  
  
-   Überprüfen von Einstellungen, bevor sie geändert oder gespeichert werden  
  
 Die Einstellungen können mit einer Reihe von Attributen beschrieben werden, die im <xref:System.Configuration>\-Namespace definiert sind. Diese Attribute werden unter [Attribute für Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/application-settings-attributes.md) beschrieben.  Wenn Sie eine Einstellung definieren, müssen Sie sie entweder mit <xref:System.Configuration.ApplicationScopedSettingAttribute> oder mit <xref:System.Configuration.UserScopedSettingAttribute> anwenden. Diese Attribute beschreiben, ob die Einstellung für die gesamte Anwendung oder nur für den aktuellen Benutzer gültig ist.  
  
 Im folgenden Codebeispiel wird eine benutzerdefinierte Einstellungsklasse allein mit der Einstellung  `BackgroundColor` definiert.  
  
 [!code-csharp[ApplicationSettings.Create#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
 [!code-vb[ApplicationSettings.Create#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]  
  
## Beibehaltung von Einstellungen  
 Einstellungen werden von der <xref:System.Configuration.ApplicationSettingsBase>\-Klasse selbst weder erhalten noch geladen. Diese Aufgabe übernimmt der Einstellungsanbieter, eine von <xref:System.Configuration.SettingsProvider> abgeleitete Klasse.  Wenn eine von <xref:System.Configuration.ApplicationSettingsBase> abgeleitete Klasse keinen Einstellungsanbieter über <xref:System.Configuration.SettingsProviderAttribute> festlegt, wird der Standardanbieter <xref:System.Configuration.LocalFileSettingsProvider> verwendet.  
  
 Das ursprüngliche Konfigurationssystem von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] unterstützt die Bereitstellung von statischen Anwendungskonfigurationsdaten, und zwar entweder über die Datei machine.config des lokalen Computers oder innerhalb einer `app.`exe.config\-Datei, die Sie mit der Anwendung bereitstellen.  Die <xref:System.Configuration.LocalFileSettingsProvider>\-Klasse erweitert diese systemeigene Unterstützung wie folgt:  
  
-   Anwendungsspezifische Einstellungen können entweder in den machine.config\- oder in den `app.`exe.config\-Dateien gespeichert werden.  Machine.config\-Dateien sind stets schreibgeschützt, während `app`.exe.config\-Dateien für die meisten Anwendungen aus Sicherheitsgründen schreibgeschützt sind.  
  
-   Benutzerspezifische Einstellungen können in `app`.exe.config\-Dateien gespeichert werden. In diesem Fall werden sie als statische Standards behandelt.  
  
-   Nicht standardmäßige benutzerspezifische Dateien werden in einer neuen Datei \(*Benutzer*.config\) gespeichert, wobei *Benutzer* dem Benutzernamen der Person entspricht, die die Anwendung derzeit ausführt.  Sie können mithilfe von <xref:System.Configuration.DefaultSettingValueAttribute> einen Standard für eine benutzerspezifische Einstellung festlegen.  Da sich benutzerspezifische Einstellungen während der Anwendungsausführung häufig ändern, ist `user`.config grundsätzlich nicht lese\-\/schreibgeschützt.  
  
 In allen drei Konfigurationsdateien werden Einstellungen im XML\-Format gespeichert.  Das XML\-Element der obersten Ebene für anwendungsspezifische Einstellungen ist `<appSettings>`, während `<userSettings>` für benutzerspezifische Einstellungen verwendet wird.  Eine `app`.exe.config\-Datei, die sowohl anwendungsspezifische als auch Standards für benutzerspezifische Einstellungen enthält, würde wie folgt aussehen:  
  
```  
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
  
 Definitionen der Elemente im Abschnitt Anwendungseinstellungen einer Konfigurationsdatei finden Sie unter [Schema für Anwendungseinstellungen](../../../../docs/framework/configure-apps/file-schema/application-settings-schema.md).  
  
### Bindungen von Einstellungen  
 Anwendungseinstellungen verwenden die Windows Forms\-Datenbindungsarchitektur, um bidirektionale Kommunikation von Einstellungsaktualisierungen zwischen dem Einstellungsobjekt und den Komponenten zu ermöglichen.  Wenn Sie Visual Studio zum Erstellen von Anwendungseinstellungen verwenden und diese Komponenteneigenschaften zuweisen, werden die Bindungen automatisch generiert.  
  
 Anwendungseinstellungen können nur an Komponenten gebunden werden, die die <xref:System.Windows.Forms.IBindableComponent>\-Benutzeroberfläche unterstützen.  Die Komponente muss weiterhin für einzelne gebundene Eigenschaften Änderungsereignisse implementieren oder durch die <xref:System.ComponentModel.INotifyPropertyChanged>\-Benutzeroberfläche die Anwendungseinstellungen benachrichtigen, dass die Eigenschaft geändert wurde.  Wenn die Komponente nicht <xref:System.Windows.Forms.IBindableComponent> implementiert und eine Bindung mithilfe von Visual Studio erstellt wird, werden die gebundenen Eigenschaften beim ersten Mal festgelegt, danach jedoch nicht aktualisiert.  Wenn die Komponente <xref:System.Windows.Forms.IBindableComponent> implementiert, jedoch keine Benachrichtigungen für Eigenschaftsänderungen unterstützt, wird die Bindung in der Einstellungsdatei bei Änderung der Eigenschaft nicht aktualisiert.  
  
 Einige Windows Forms\-Komponenten unterstützen das Binden von Einstellungen nicht, beispielsweise <xref:System.Windows.Forms.ToolStripItem>.  
  
### Serialisierung von Einstellungen  
 Wenn <xref:System.Configuration.LocalFileSettingsProvider> Einstellungen auf der Festplatte speichern muss, werden die folgenden Aktionen ausgeführt:  
  
1.  Er verwendet die Reflektion, um alle in der abgeleiteten <xref:System.Configuration.ApplicationSettingsBase>\-Klasse definierten Eigenschaften zu überprüfen und diejenigen zu ermitteln, die entweder mit <xref:System.Configuration.ApplicationScopedSettingAttribute> oder mit <xref:System.Configuration.UserScopedSettingAttribute> angewendet werden.  
  
2.  Er serialisiert die Eigenschaft auf die Festplatte.  Zunächst versucht er, <xref:System.ComponentModel.TypeConverter.ConvertToString%2A> oder <xref:System.ComponentModel.TypeConverter.ConvertFromString%2A> auf dem zugeordneten <xref:System.ComponentModel.TypeConverter> des Typs aufzurufen.  Wenn dies nicht gelingt, verwendet er stattdessen XML\-Serialisierung.  
  
3.  Er bestimmt anhand des Einstellungsattributs, welche Einstellungen in welchen Dateien gespeichert werden.  
  
 Wenn Sie eine eigene Einstellungsklasse implementieren, können Sie <xref:System.Configuration.SettingsSerializeAsAttribute> verwenden, um eine Einstellung für die binäre oder benutzerdefinierte Serialisierung mit der <xref:System.Configuration.SettingsSerializeAs>\-Enumeration zu markieren.  Weitere Informationen zum Erstellen eigener Einstellungsklassen als Code finden Sie unter [Gewusst wie: Erstellen von Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).  
  
### Speicherorte von Einstellungsdateien  
 Der Speicherort der `app`.exe.config\-Datei und der *Benutzer*.config\-Datei hängt von der Installationsart der Anwendung ab.  In einer auf Windows Forms basierenden Anwendung, die auf den lokalen Computer kopiert wurde, befindet sich `app`.exe.config im gleichen Verzeichnis wie das Basisverzeichnis der Hauptausführungsdatei der Anwendung, während *Benutzer*.config an dem durch die <xref:System.Windows.Forms.Application.LocalUserAppDataPath%2A?displayProperty=fullName>\-Eigenschaft festgelegten Speicherort abgelegt wird.  In einer Anwendung, die mithilfe von [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] installiert wurde, befinden sich beide Dateien im [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]\-Datenverzeichnis unterhalb von %InstallRoot%\\Dokumente und Einstellungen\\*Benutzername*\\Lokale Einstellungen.  
  
 Der Speicherort dieser Dateien lautet geringfügig anders, wenn ein Benutzer Roamingprofile aktiviert hat, die es einem Benutzer ermöglichen, verschiedene Windows\- und Anwendungseinstellungen zu definieren, wenn er innerhalb einer Domäne verschiedene Computer verwendet.  In diesem Fall werden sowohl für [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]\-Anwendungen als auch für Nicht\-[!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]\-Anwendungen die Dateien `app`.exe.config und *Benutzer*.config unter %InstallRoot%\\Dokumente und Einstellungen\\*Benutzername*\\Anwendungsdaten gespeichert.  
  
 Weitere Informationen über die Interaktion des Features Anwendungseinstellungen mit der neuen Bereitstellungstechnologie finden Sie unter [ClickOnce and Application Settings](../Topic/ClickOnce%20and%20Application%20Settings.md).  Weitere Informationen über das [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]\-Datenverzeichnis finden Sie unter [Zugreifen auf lokale und Remotedaten in einer ClickOnce\-Anwendung](../Topic/Accessing%20Local%20and%20Remote%20Data%20in%20ClickOnce%20Applications.md).  
  
## Anwendungseinstellungen und Sicherheit  
 Anwendungseinstellungen sind für die Verwendung in teilweise vertrauenswürdigen Anwendungen konzipiert, d. h. in einer beschränkten Umgebung, die für Windows Forms\-Anwendungen, die über das Internet oder ein Intranet gehostet werden, standardmäßig festgelegt ist.  Zur Verwendung von Anwendungseinstellungen mit dem standardmäßigen Einstellungsanbieter sind neben teilweise vertrauenswürdigen Anwendungen keine besonderen Berechtigungen erforderlich.  
  
 Wenn Anwendungseinstellungen in einer [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]\-Anwendung verwendet werden, wird die Datei`user`.config im [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]\-Datenverzeichnis gespeichert.  Die Größe der Datei `user`.config darf das von [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] festgelegte Datenverzeichniskontingent nicht überschreiten.  Weitere Informationen hierzu finden Sie unter [ClickOnce and Application Settings](../Topic/ClickOnce%20and%20Application%20Settings.md).  
  
## Benutzerdefinierte Einstellungsanbieter  
 In der Architektur der Anwendungseinstellungen besteht eine lose Verknüpfung zwischen der von <xref:System.Configuration.ApplicationSettingsBase> abgeleiteten Wrapperklasse der Anwendungseinstellungen und dem bzw. den von <xref:System.Configuration.SettingsProvider> abgeleiteten zugeordneten Einstellungsprovidern.  Diese Zuordnung wird nur vom <xref:System.Configuration.SettingsProviderAttribute> definiert, das auf die Wrapperklasse oder ihre einzelnen Eigenschaften angewendet wird.  Wenn ein Einstellungsanbieter nicht explizit festgelegt wird, wird der Standardanbieter <xref:System.Configuration.LocalFileSettingsProvider> verwendet.  Demzufolge unterstützt diese Architektur das Erstellen und Verwenden von benutzerdefinierten Einstellungsanbietern.  
  
 Angenommen, Sie möchten `SqlSettingsProvider` entwickeln und verwenden, einen Anbieter, der sämtliche Einstellungsdaten in einer Microsoft SQL Server\-Datenbank speichert.  Die von <xref:System.Configuration.SettingsProvider> abgeleitete Klasse würde diese Informationen in der  `Initialize` \-Methode als Parameter des Typs <xref:System.Collections.Specialized.NameValueCollection?displayProperty=fullName> empfangen.  Anschließend würden Sie die <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A>\-Methode implementieren, um die Einstellungen aus dem Datenspeicher abzurufen, und <xref:System.Configuration.SettingsProvider.SetPropertyValues%2A>, um sie zu speichern.  Der Anbieter kann die <xref:System.Configuration.SettingsPropertyCollection> verwenden, die für <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> bereitgestellt wird, um den Namen, Typ und Bereich der Eigenschaft sowie andere für diese Eigenschaft definierte Einstellungsattribute zu bestimmen.  
  
 Der Anbieter muss eine Eigenschaft implementieren sowie eine Methode, deren Implementierung möglicherweise nicht eindeutig ist.  Die <xref:System.Configuration.SettingsProvider.ApplicationName%2A>\-Eigenschaft ist eine abstrakte Eigenschaft von <xref:System.Configuration.SettingsProvider>; Sie sollten sie so programmieren, dass Folgendes zurückgegeben wird:  
  
 [!code-csharp[ApplicationSettings.Architecture#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#2)]
 [!code-vb[ApplicationSettings.Architecture#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#2)]  
  
 Die abgeleitete Klasse muss außerdem eine `Initialize`\-Methode implementieren, die keine Argumente empfängt und keinen Wert zurückgibt.  Diese Methode wird von <xref:System.Configuration.SettingsProvider> nicht definiert.  
  
 Schließlich implementieren Sie <xref:System.Configuration.IApplicationSettingsProvider> für den Anbieter, um Unterstützung beim Aktualisieren von Einstellungen, Zurücksetzen von Einstellungen auf die Standards und Aktualisieren von Einstellungen von einer Anwendungsversion auf eine andere bereitzustellen.  
  
 Nachdem Sie den Anbieter implementiert und kompiliert haben, müssen Sie die Einstellungsklasse anweisen, diesen Anbieter anstelle des Standardanbieters zu verwenden.  Hierzu verwenden Sie das <xref:System.Configuration.SettingsProviderAttribute>.  Wenn der Anbieter auf eine gesamte Einstellungsklasse angewendet wird, wird er für jede Einstellung verwendet, die die Klasse definiert. Wenn er auf einzelne Einstellungen angewendet wird, verwendet die Architektur der Anwendungseinstellungen diesen Anbieter ausschließlich für diese Einstellungen und <xref:System.Configuration.LocalFileSettingsProvider> für den Rest.  Im folgenden Codebeispiel wird gezeigt, wie die Einstellungsklasse angewiesen wird, den benutzerdefinierten Anbieter zu verwenden.  
  
 [!code-csharp[ApplicationSettings.Architecture#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#1)]
 [!code-vb[ApplicationSettings.Architecture#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#1)]  
  
 Ein Anbieter kann von mehreren Threads gleichzeitig aufgerufen werden, er schreibt jedoch stets in den gleichen Speicherplatz. Daher instanziiert die Architektur der Anwendungseinstellungen grundsätzlich nur eine einzelne Instanz der Anbieterklasse.  
  
> [!IMPORTANT]
>  Sie sollten sicherstellen, dass der Anbieter Thread\-sicher ist und zum Schreiben der Konfigurationsdateien immer nur einen Thread auf einmal zulässt.  
  
 Der Anbieter muss nicht alle im <xref:System.Configuration?displayProperty=fullName>\-Namespace definierten Einstellungsattribute unterstützten, jedoch zumindest <xref:System.Configuration.ApplicationScopedSettingAttribute> und <xref:System.Configuration.UserScopedSettingAttribute>. Darüber hinaus sollte er <xref:System.Configuration.DefaultSettingValueAttribute> unterstützen.  Für die Attribute, die er nicht unterstützt, sollte der Anbieter ohne Benachrichtigung fehlschlagen, aber keine Ausnahme auslösen.  Wenn die Einstellungsklasse jedoch eine ungültige Kombination von Attributen verwendet, z. B. durch Anwenden von <xref:System.Configuration.ApplicationScopedSettingAttribute> und <xref:System.Configuration.UserScopedSettingAttribute> auf die gleiche Einstellung, sollte der Anbieter eine Ausnahme auslösen und die Operation beenden.  
  
## Siehe auch  
 <xref:System.Configuration.ApplicationSettingsBase>   
 <xref:System.Configuration.SettingsProvider>   
 <xref:System.Configuration.LocalFileSettingsProvider>   
 [Übersicht über Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/application-settings-overview.md)   
 [Anwendungseinstellungen für benutzerdefinierte Steuerelemente](../../../../docs/framework/winforms/advanced/application-settings-for-custom-controls.md)   
 [ClickOnce and Application Settings](../Topic/ClickOnce%20and%20Application%20Settings.md)   
 [Schema für Anwendungseinstellungen](../../../../docs/framework/configure-apps/file-schema/application-settings-schema.md)