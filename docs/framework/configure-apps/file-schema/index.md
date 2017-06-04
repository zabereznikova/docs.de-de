---
title: "Konfigurationsdateischema f&#252;r .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - ".NET Framework-Anwendungskonfiguration, Konfigurationsschema"
  - "app.config-Dateien, Schema"
  - "Anwendungskonfigurationsdateien, Schema"
  - "Anwendungsentwicklung [.NET Framework], Schema"
  - "Konfigurationsschema [.NET Framework]"
  - "Konfigurationseinstellungen [.NET Framework], Anwendungen"
  - "Containertags"
  - "enterprisesec-Konfigurationsdateien"
  - "enterprisesec.config-Dateien"
  - "Computerkonfigurationsdateien"
  - "machine.config-Dateien"
  - "Schemakonfigurationseinstellungen"
  - "Schemas, Konfigurationseinstellungen"
  - "Sicherheit [.NET Framework], Konfigurationsdateien"
  - "security.config-Dateien"
  - "Wohlgeformte XML"
  - "XML-Tags"
ms.assetid: 69003d39-dc8a-460c-a6be-e6d93e690b38
caps.latest.revision: 20
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 18
---
# Konfigurationsdateischema f&#252;r .NET Framework
Konfigurationsdateien sind Standard\-XML\-Dateien, die Sie verwenden können, um für Ihre Apps Einstellungen zu ändern und Richtlinien festzulegen.  Das .NET Framework\-Konfigurationsschema besteht aus Elementen, die Sie in Konfigurationsdateien verwenden können, um das Verhalten der Apps zu steuern.  Das Inhaltsverzeichnis dieses Abschnitts gibt die Schemahierarchie für Startup, Laufzeit, Netzwerk und anderen Arten von Konfigurationseinstellungen wider.  
  
 Informationen über die Typen, das Format und den Speicherort der Konfigurationsdateien finden Sie im Artikel [Konfigurieren von Apps](../../../../docs/framework/configure-apps/index.md).  Sie sollten mit XML vertraut sein, wenn Sie die Konfigurationsdateien direkt bearbeiten möchten.  
  
> [!IMPORTANT]
>  Bei XML\-Tags und \-Attributen in Konfigurationsdateien muss die Groß\-\/Kleinschreibung beachtet werden.  
  
## In diesem Abschnitt  
 [\<configuration\>\-Element](../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
 Beschreibt das `<configuration>`\-Element, das sämtlichen Konfigurationsdateien übergeordnet ist.  
  
 [\<assemblyBinding\>\-Element](../../../../docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)  
 Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.  
  
 [\<linkedConfiguration\>\-Element](../../../../docs/framework/configure-apps/file-schema/linkedconfiguration-element.md)  
 Gibt eine einzuschließende Konfigurationsdatei an.  
  
 [Schema für Starteinstellungen](../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 Beschreibt die Elemente, die angeben, welche Version der Common Language Runtime zu verwenden ist.  
  
 [Schema für Laufzeiteinstellungen](../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 Beschreibt die Elemente, die die Assemblybindung und das Laufzeitverhalten konfigurieren.  
  
 [Netzwerkeinstellungsschema](../../../../docs/framework/configure-apps/file-schema/network/index.md)  
 Beschreibt die Elemente, die angeben, wie Verbindungen zwischen .NET Framework und dem Internet hergestellt werden.  
  
 [Schema für Kryptografieeinstellungen](../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 Beschreibt die Elemente, mit denen angezeigte Algorithmusnamen Klassen zugeordnet werden, die Kryptografiealgorithmen implementieren.  
  
 [Schema für Konfigurationsabschnitte](../../../../docs/framework/configure-apps/file-schema/configuration-sections-schema.md)  
 Beschreibt die Elemente, mit denen Konfigurationsabschnitte für benutzerdefinierte Einstellungen erstellt und verwendet werden.  
  
 [Schema für Ablaufverfolgungs\- und Debugeinstellungen](../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 Beschreibt die Elemente, mit denen Ablaufverfolgungsschalter und \-listener angegeben werden.  
  
 [Schema für Compiler\- und Sprachanbietereinstellungen](../../../../docs/framework/configure-apps/file-schema/compiler/index.md)  
 Beschreibt die Elemente, die die Compilerkonfiguration für verfügbare Sprachanbieter angeben.  
  
 [Schema für Anwendungseinstellungen](../../../../docs/framework/configure-apps/file-schema/application-settings-schema.md)  
 Beschreibt die Elemente, die es Windows Forms\- oder ASP.NET\-Anwendungen ermöglichen, Einstellungen im Gültigkeitsbereich der Anwendung und im Gültigkeitsbereich des Benutzers zu speichern und abzurufen.  
  
 [Webeinstellungsschema](../../../../docs/framework/configure-apps/file-schema/web/index.md)  
 Alle Elemente im Webeinstellungsschema, das Elemente für die Konfiguration von ASP.NET mit einer Hostanwendung wie IIS enthält.  Wird in aspnet.config\-Dateien verwendet.  
  
## Verwandte Abschnitte  
 [Remoting Settings Schema](http://msdn.microsoft.com/de-de/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e)  
 Beschreibt die Elemente, mit denen Client\- und Serveranwendungen konfiguriert werden, die Remotefunktionen implementieren.  
  
 [ASP.NET\-Einstellungsschema](http://msdn.microsoft.com/library/b5ysx397\(v=vs.100\).aspx)  
 Beschreibt die Elemente, die das Verhalten von ASP.NET\-Webanwendungen steuern.  
  
 [Web Services Settings Schema](http://msdn.microsoft.com/de-de/f84d6d55-1add-4eb7-ae46-33df5833ea2e)  
 Beschreibt die Elemente, die das Verhalten von ASP.NET\-Webdiensten und ihren Clients steuern.  
  
 [Configuring .NET Framework Apps](http://msdn.microsoft.com/de-de/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)  
 Beschreibt, wie Sicherheit, Assemblybindung und Remotefunktionen in .NET Framework konfiguriert werden.