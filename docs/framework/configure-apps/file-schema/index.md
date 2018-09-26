---
title: Konfigurationsdateischema für .NET Framework
ms.date: 05/01/2017
helpviewer_keywords:
- .NET Framework application configuration, configuration schema
- machine configuration files
- application configuration files, schema
- app.config files, schema
- schema configuration settings
- schemas, configuration settings
- enterprisesec.config files
- well-formed XML
- enterprisesec configuration files
- security.config files
- security [.NET Framework], configuration files
- application development [.NET Framework], schema
- XML tags
- container tags
- machine.config files
- configuration schema [.NET Framework]
- configuration settings [.NET Framework], applications
- configuration file reference [.NET Framework]
ms.assetid: 69003d39-dc8a-460c-a6be-e6d93e690b38
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 4543802c3918a4761daa5a4fbbab366695823f73
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170540"
---
# <a name="configuration-file-schema-for-the-net-framework"></a>Konfigurationsdateischema für .NET Framework

Konfigurationsdateien sind Standard-XML-Dateien, die Sie verwenden können, um für Ihre Apps Einstellungen zu ändern und Richtlinien festzulegen. Das .NET Framework-Konfigurationsschema besteht aus Elementen, die Sie in Konfigurationsdateien verwenden können, um das Verhalten der Apps zu steuern. Das Inhaltsverzeichnis dieses Abschnitts gibt die Schemahierarchie für Startup, Laufzeit, Netzwerk und anderen Arten von Konfigurationseinstellungen wider.

Informationen über die Typen, das Format und den Speicherort der Konfigurationsdateien finden Sie im Artikel [Configuring Apps (Konfigurieren von Apps)](~/docs/framework/configure-apps/index.md). Machen Sie sich mit XML vertraut, wenn Sie die Konfigurationsdateien direkt bearbeiten möchten.

> [!IMPORTANT]
> Bei XML-Tags und -Attributen in Konfigurationsdateien muss die Groß-/Kleinschreibung beachtet werden.

## <a name="in-this-section"></a>In diesem Abschnitt

[**\<configuration>**-Element](~/docs/framework/configure-apps/file-schema/configuration-element.md): Beschreibt das `<configuration>`-Element, das sämtlichen Konfigurationsdateien übergeordnet ist.

[**\<assemblyBinding>**-Element](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md): Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.

[**\<linkedConfiguration>**-Element](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) Gibt eine einzuschließende Konfigurationsdatei an.

[Startup Settings Schema (Schema für Starteinstellungen)](~/docs/framework/configure-apps/file-schema/startup/index.md): Beschreibt die Elemente, die angeben, welche Version der Common Language Runtime zu verwenden ist.

[Runtime Settings Schema (Schema für Laufzeiteinstellungen)](~/docs/framework/configure-apps/file-schema/runtime/index.md): Beschreibt die Elemente, die die Assemblybindung und das Laufzeitverhalten konfigurieren.

[Network Settings Schema (Schema für Netzwerkeinstellungen)](~/docs/framework/configure-apps/file-schema/network/index.md): Beschreibt die Elemente, die angeben, wie Verbindungen zwischen .NET Framework und dem Internet hergestellt werden.

[Cryptography Settings Schema (Schema für Kryptografieeinstellungen)](~/docs/framework/configure-apps/file-schema/cryptography/index.md): Beschreibt die Elemente, mit denen die Anzeigenamen von Algorithmen Klassen zugeordnet werden, die Kryptografiealgorithmen implementieren.

[Configuration Sections Schema (Schema für Konfigurationsabschnitte)](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md): Beschreibt die Elemente, mit denen Konfigurationsabschnitte für benutzerdefinierte Einstellungen erstellt und verwendet werden.

[Trace and Debug Settings Schema (Schema für die Ablaufverfolgungs- und Debugeinstellungen)](~/docs/framework/configure-apps/file-schema/trace-debug/index.md): Beschreibt die Elemente, mit denen Ablaufverfolgungsschalter und -listener angegeben werden.

[Compiler and Language Provider Settings Schema (Schema für die Compiler- und Sprachanbietereinstellungen)](~/docs/framework/configure-apps/file-schema/compiler/index.md): Beschreibt die Elemente, die die Compilerkonfiguration für verfügbare Sprachanbieter angeben.

[Application Settings Schema (Schema für die Anwendungseinstellungen)](~/docs/framework/configure-apps/file-schema/application-settings-schema.md): Beschreibt die Elemente, die es Windows Forms- oder ASP.NET-Anwendungen ermöglichen, Einstellungen im Gültigkeitsbereich der Anwendung und im Gültigkeitsbereich des Benutzers zu speichern und abzurufen.

[App Settings Schema (Schema für die App-Einstellungen)](~/docs/framework/configure-apps/file-schema/appsettings/index.md): Dieses Thema enthält benutzerdefinierte Anwendungseinstellung, z.B. Dateipfade, URLs für den XML-Webdienst oder andere benutzerdefinierte Konfigurationsinformationen für eine Anwendung.

[Web Settings Schema (Schema für die Webeinstellungen)](~/docs/framework/configure-apps/file-schema/web/index.md): Alle Elemente im Webeinstellungsschema, einschließlich des Elements für die Konfiguration von ASP.NET mit einer Hostanwendung wie IIS. Wird in *Aspnet.config*-Dateien verwendet.

[Windows Forms Configuration Schema (Windows Forms-Konfigurationsschema)](winforms/index.md): Alle Elemente im Konfigurationsabschnitt der Windows Forms-Anwendung, einschließlich Anpassungen, z.B. für die Unterstützung von mehreren Bildschirmen und hohen DPI-Werten.

[WCF Configuration Schema (WCF-Konfigurationsschema)](~/docs/framework/configure-apps/file-schema/wcf/index.md): Alle Elemente, die es Ihnen ermöglichen, WCF-Dienste und -Clientanwendungen zu konfigurieren.

[WCF Directive Syntax (WCF-Anweisungssyntax)](~/docs/framework/configure-apps/file-schema/wcf-directive/index.md): Beschreibt die `@ServiceHost`-Anweisung, die seitenspezifische Attribute definiert, die vom .svc-Compiler verwendet werden.

[WIF Configuration Schema (WIF-Konfigurationsschema)](windows-identity-foundation/index.md): Alle Elemente des WIF-Konfigurationsschemas (Windows Identity Foundation).

## <a name="related-sections"></a>Verwandte Abschnitte

[Remoting Settings Schema (Schema für die Remoteeinstellungen)](https://msdn.microsoft.com/library/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e): Beschreibt die Elemente, mit denen Client- und Serveranwendungen konfiguriert werden, die Remotefunktionen implementieren.

[ASP.NET Settings Schema (Schema für die ASP.NET-Einstellungen)](https://msdn.microsoft.com/library/b5ysx397\(v=vs.100\).aspx): Beschreibt die Elemente, die das Verhalten von ASP.NET-Webanwendungen steuern.

[Web Services Settings Schema (Schema für die Webdiensteinstellungen)](https://msdn.microsoft.com/library/f84d6d55-1add-4eb7-ae46-33df5833ea2e): Das Einstellungsschema für Webdienste definiert Konfigurationsdateielemente, die das Verhalten von ASP.NET-Webdiensten und deren Clients steuern.

[Configuring .NET Framework Apps (Konfigurieren von .NET Framework-Apps)](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42): Beschreibt, wie Sicherheit, Assemblybindung und Remotefunktionen in .NET Framework konfiguriert werden.
