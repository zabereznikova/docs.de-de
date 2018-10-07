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
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2018
ms.locfileid: "48839029"
---
# <a name="configuration-file-schema-for-the-net-framework"></a><span data-ttu-id="7d4dd-102">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7d4dd-102">Configuration file schema for the .NET Framework</span></span>

<span data-ttu-id="7d4dd-103">Konfigurationsdateien sind Standard-XML-Dateien, die Sie verwenden können, um für Ihre Apps Einstellungen zu ändern und Richtlinien festzulegen.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-103">Configuration files are standard XML files that you can use to change settings and set policies for your apps.</span></span> <span data-ttu-id="7d4dd-104">Das .NET Framework-Konfigurationsschema besteht aus Elementen, die Sie in Konfigurationsdateien verwenden können, um das Verhalten der Apps zu steuern.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-104">The .NET Framework configuration schema consists of elements that you can use in configuration files to control the behavior of your apps.</span></span> <span data-ttu-id="7d4dd-105">Das Inhaltsverzeichnis dieses Abschnitts gibt die Schemahierarchie für Startup, Laufzeit, Netzwerk und anderen Arten von Konfigurationseinstellungen wider.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-105">The table of contents for this section reflects the schema hierarchy for startup, runtime, network, and other types of configuration settings.</span></span>

<span data-ttu-id="7d4dd-106">Informationen über die Typen, das Format und den Speicherort der Konfigurationsdateien finden Sie im Artikel [Configuring Apps (Konfigurieren von Apps)](~/docs/framework/configure-apps/index.md).</span><span class="sxs-lookup"><span data-stu-id="7d4dd-106">For information about the types, format, and location of configuration files, see the article [Configuring Apps](~/docs/framework/configure-apps/index.md).</span></span> <span data-ttu-id="7d4dd-107">Machen Sie sich mit XML vertraut, wenn Sie die Konfigurationsdateien direkt bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-107">Familiarize yourself with XML if you want to edit the configuration files directly.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d4dd-108">Bei XML-Tags und -Attributen in Konfigurationsdateien muss die Groß-/Kleinschreibung beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-108">XML tags and attributes in configuration files are case-sensitive.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="7d4dd-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7d4dd-109">In this section</span></span>

<span data-ttu-id="7d4dd-110">[**\<configuration>**-Element](~/docs/framework/configure-apps/file-schema/configuration-element.md): Beschreibt das `<configuration>`-Element, das sämtlichen Konfigurationsdateien übergeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-110">[**\<configuration>** Element](~/docs/framework/configure-apps/file-schema/configuration-element.md) Describes the `<configuration>` element, which is the top-level element for all configuration files.</span></span>

<span data-ttu-id="7d4dd-111">[**\<assemblyBinding>**-Element](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md): Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-111">[**\<assemblyBinding>** Element](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="7d4dd-112">[**\<linkedConfiguration>**-Element](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) Gibt eine einzuschließende Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-112">[**\<linkedConfiguration>** Element](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) Specifies a configuration file to include.</span></span>

<span data-ttu-id="7d4dd-113">[Startup Settings Schema (Schema für Starteinstellungen)](~/docs/framework/configure-apps/file-schema/startup/index.md): Beschreibt die Elemente, die angeben, welche Version der Common Language Runtime zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-113">[Startup Settings Schema](~/docs/framework/configure-apps/file-schema/startup/index.md) Describes the elements that specify which version of the common language runtime to use.</span></span>

<span data-ttu-id="7d4dd-114">[Runtime Settings Schema (Schema für Laufzeiteinstellungen)](~/docs/framework/configure-apps/file-schema/runtime/index.md): Beschreibt die Elemente, die die Assemblybindung und das Laufzeitverhalten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-114">[Runtime Settings Schema](~/docs/framework/configure-apps/file-schema/runtime/index.md) Describes the elements that configure assembly binding and runtime behavior.</span></span>

<span data-ttu-id="7d4dd-115">[Network Settings Schema (Schema für Netzwerkeinstellungen)](~/docs/framework/configure-apps/file-schema/network/index.md): Beschreibt die Elemente, die angeben, wie Verbindungen zwischen .NET Framework und dem Internet hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-115">[Network Settings Schema](~/docs/framework/configure-apps/file-schema/network/index.md) Describes the elements that specify how the .NET Framework connects to the Internet.</span></span>

<span data-ttu-id="7d4dd-116">[Cryptography Settings Schema (Schema für Kryptografieeinstellungen)](~/docs/framework/configure-apps/file-schema/cryptography/index.md): Beschreibt die Elemente, mit denen die Anzeigenamen von Algorithmen Klassen zugeordnet werden, die Kryptografiealgorithmen implementieren.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-116">[Cryptography Settings Schema](~/docs/framework/configure-apps/file-schema/cryptography/index.md) Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>

<span data-ttu-id="7d4dd-117">[Configuration Sections Schema (Schema für Konfigurationsabschnitte)](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md): Beschreibt die Elemente, mit denen Konfigurationsabschnitte für benutzerdefinierte Einstellungen erstellt und verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-117">[Configuration Sections Schema](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) Describes the elements used to create and use configuration sections for custom settings.</span></span>

<span data-ttu-id="7d4dd-118">[Trace and Debug Settings Schema (Schema für die Ablaufverfolgungs- und Debugeinstellungen)](~/docs/framework/configure-apps/file-schema/trace-debug/index.md): Beschreibt die Elemente, mit denen Ablaufverfolgungsschalter und -listener angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-118">[Trace and Debug Settings Schema](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) Describes the elements that specify trace switches and listeners.</span></span>

<span data-ttu-id="7d4dd-119">[Compiler and Language Provider Settings Schema (Schema für die Compiler- und Sprachanbietereinstellungen)](~/docs/framework/configure-apps/file-schema/compiler/index.md): Beschreibt die Elemente, die die Compilerkonfiguration für verfügbare Sprachanbieter angeben.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-119">[Compiler and Language Provider Settings Schema](~/docs/framework/configure-apps/file-schema/compiler/index.md) Describes the elements that specify compiler configuration for available language providers.</span></span>

<span data-ttu-id="7d4dd-120">[Application Settings Schema (Schema für die Anwendungseinstellungen)](~/docs/framework/configure-apps/file-schema/application-settings-schema.md): Beschreibt die Elemente, die es Windows Forms- oder ASP.NET-Anwendungen ermöglichen, Einstellungen im Gültigkeitsbereich der Anwendung und im Gültigkeitsbereich des Benutzers zu speichern und abzurufen.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-120">[Application Settings Schema](~/docs/framework/configure-apps/file-schema/application-settings-schema.md) Describes the elements that enable a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span>

<span data-ttu-id="7d4dd-121">[App Settings Schema (Schema für die App-Einstellungen)](~/docs/framework/configure-apps/file-schema/appsettings/index.md): Dieses Thema enthält benutzerdefinierte Anwendungseinstellung, z.B. Dateipfade, URLs für den XML-Webdienst oder andere benutzerdefinierte Konfigurationsinformationen für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-121">[App Settings Schema](~/docs/framework/configure-apps/file-schema/appsettings/index.md) Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="7d4dd-122">[Web Settings Schema (Schema für die Webeinstellungen)](~/docs/framework/configure-apps/file-schema/web/index.md): Alle Elemente im Webeinstellungsschema, einschließlich des Elements für die Konfiguration von ASP.NET mit einer Hostanwendung wie IIS.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-122">[Web Settings Schema](~/docs/framework/configure-apps/file-schema/web/index.md) All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="7d4dd-123">Wird in *Aspnet.config*-Dateien verwendet.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-123">Used in *Aspnet.config* files.</span></span>

<span data-ttu-id="7d4dd-124">[Windows Forms Configuration Schema (Windows Forms-Konfigurationsschema)](winforms/index.md): Alle Elemente im Konfigurationsabschnitt der Windows Forms-Anwendung, einschließlich Anpassungen, z.B. für die Unterstützung von mehreren Bildschirmen und hohen DPI-Werten.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-124">[Windows Forms Configuration Schema](winforms/index.md) All elements in the Windows Forms application configuration section, which includes customizations such as multi-monitor and high DPI support.</span></span>

<span data-ttu-id="7d4dd-125">[WCF Configuration Schema (WCF-Konfigurationsschema)](~/docs/framework/configure-apps/file-schema/wcf/index.md): Alle Elemente, die es Ihnen ermöglichen, WCF-Dienste und -Clientanwendungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-125">[WCF Configuration Schema](~/docs/framework/configure-apps/file-schema/wcf/index.md) All elements that enable you to configure WCF service and client applications.</span></span>

<span data-ttu-id="7d4dd-126">[WCF Directive Syntax (WCF-Anweisungssyntax)](~/docs/framework/configure-apps/file-schema/wcf-directive/index.md): Beschreibt die `@ServiceHost`-Anweisung, die seitenspezifische Attribute definiert, die vom .svc-Compiler verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-126">[WCF Directive Syntax](~/docs/framework/configure-apps/file-schema/wcf-directive/index.md) Describes the `@ServiceHost` directive, which defines page-specific attributes used by the .svc compiler.</span></span>

<span data-ttu-id="7d4dd-127">[WIF Configuration Schema (WIF-Konfigurationsschema)](windows-identity-foundation/index.md): Alle Elemente des WIF-Konfigurationsschemas (Windows Identity Foundation).</span><span class="sxs-lookup"><span data-stu-id="7d4dd-127">[WIF Configuration Schema](windows-identity-foundation/index.md) All elements of the Windows Identity Foundation (WIF) configuration schema.</span></span>

## <a name="related-sections"></a><span data-ttu-id="7d4dd-128">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="7d4dd-128">Related sections</span></span>

<span data-ttu-id="7d4dd-129">[Remoting Settings Schema (Schema für die Remoteeinstellungen)](https://msdn.microsoft.com/library/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e): Beschreibt die Elemente, mit denen Client- und Serveranwendungen konfiguriert werden, die Remotefunktionen implementieren.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-129">[Remoting Settings Schema](https://msdn.microsoft.com/library/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e) Describes the elements that configure client and server applications that implement remoting.</span></span>

<span data-ttu-id="7d4dd-130">[ASP.NET Settings Schema (Schema für die ASP.NET-Einstellungen)](https://msdn.microsoft.com/library/b5ysx397\(v=vs.100\).aspx): Beschreibt die Elemente, die das Verhalten von ASP.NET-Webanwendungen steuern.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-130">[ASP.NET Settings Schema](https://msdn.microsoft.com/library/b5ysx397\(v=vs.100\).aspx) Describes the elements that control the behavior of ASP.NET Web applications.</span></span>

<span data-ttu-id="7d4dd-131">[Web Services Settings Schema (Schema für die Webdiensteinstellungen)](https://msdn.microsoft.com/library/f84d6d55-1add-4eb7-ae46-33df5833ea2e): Das Einstellungsschema für Webdienste definiert Konfigurationsdateielemente, die das Verhalten von ASP.NET-Webdiensten und deren Clients steuern.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-131">[Web Services Settings Schema](https://msdn.microsoft.com/library/f84d6d55-1add-4eb7-ae46-33df5833ea2e) Describes the elements that control the behavior of ASP.NET Web services and their clients.</span></span>

<span data-ttu-id="7d4dd-132">[Configuring .NET Framework Apps (Konfigurieren von .NET Framework-Apps)](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42): Beschreibt, wie Sicherheit, Assemblybindung und Remotefunktionen in .NET Framework konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="7d4dd-132">[Configuring .NET Framework Apps](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42) Describes how to configure security, assembly binding, and remoting in the .NET Framework.</span></span>
