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
ms.openlocfilehash: ab6f12be01899f5b7e54a7ec2d9675d502d88bc3
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555132"
---
# <a name="configuration-file-schema-for-the-net-framework"></a><span data-ttu-id="d596f-102">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d596f-102">Configuration file schema for the .NET Framework</span></span>

<span data-ttu-id="d596f-103">Konfigurationsdateien sind Standard-XML-Dateien, die Sie verwenden können, um für Ihre Apps Einstellungen zu ändern und Richtlinien festzulegen.</span><span class="sxs-lookup"><span data-stu-id="d596f-103">Configuration files are standard XML files that you can use to change settings and set policies for your apps.</span></span> <span data-ttu-id="d596f-104">Das .NET Framework-Konfigurationsschema besteht aus Elementen, die Sie in Konfigurationsdateien verwenden können, um das Verhalten der Apps zu steuern.</span><span class="sxs-lookup"><span data-stu-id="d596f-104">The .NET Framework configuration schema consists of elements that you can use in configuration files to control the behavior of your apps.</span></span> <span data-ttu-id="d596f-105">Das Inhaltsverzeichnis dieses Abschnitts gibt die Schemahierarchie für Startup, Laufzeit, Netzwerk und anderen Arten von Konfigurationseinstellungen wider.</span><span class="sxs-lookup"><span data-stu-id="d596f-105">The table of contents for this section reflects the schema hierarchy for startup, runtime, network, and other types of configuration settings.</span></span>

<span data-ttu-id="d596f-106">Informationen zu den Typen, dem Format und dem Speicherort der Konfigurationsdateien finden Sie unter [Konfigurieren von apps](../index.md).</span><span class="sxs-lookup"><span data-stu-id="d596f-106">For information about the types, format, and location of configuration files, see [Configure apps](../index.md).</span></span> <span data-ttu-id="d596f-107">Machen Sie sich mit XML vertraut, wenn Sie die Konfigurationsdateien direkt bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="d596f-107">Familiarize yourself with XML if you want to edit the configuration files directly.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d596f-108">Bei XML-Tags und -Attributen in Konfigurationsdateien muss die Groß-/Kleinschreibung beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="d596f-108">XML tags and attributes in configuration files are case-sensitive.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d596f-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d596f-109">In this section</span></span>

<span data-ttu-id="d596f-110">[**\<configuration>** Gewisses](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d596f-110">[**\<configuration>** Element](configuration-element.md)</span></span>\
<span data-ttu-id="d596f-111">Das Element der obersten Ebene für alle Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="d596f-111">The top-level element for all configuration files.</span></span>

<span data-ttu-id="d596f-112">[**\<assemblyBinding>** Gewisses](assemblybinding-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="d596f-112">[**\<assemblyBinding>** Element](assemblybinding-element-for-configuration.md)</span></span>\
<span data-ttu-id="d596f-113">Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.</span><span class="sxs-lookup"><span data-stu-id="d596f-113">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="d596f-114">[**\<linkedConfiguration>** Gewisses](linkedconfiguration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d596f-114">[**\<linkedConfiguration>** Element](linkedconfiguration-element.md)</span></span>\
<span data-ttu-id="d596f-115">Gibt eine einzuschließende Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="d596f-115">Specifies a configuration file to include.</span></span>

<span data-ttu-id="d596f-116">[Schema für Start Einstellungen](./startup/index.md)</span><span class="sxs-lookup"><span data-stu-id="d596f-116">[Startup Settings Schema](./startup/index.md)</span></span>\
<span data-ttu-id="d596f-117">-Elemente, die angeben, welche Version des Common Language Runtime verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d596f-117">Elements that specify which version of the common language runtime to use.</span></span>

<span data-ttu-id="d596f-118">[Lauf Zeit Einstellungs Schema](./runtime/index.md)</span><span class="sxs-lookup"><span data-stu-id="d596f-118">[Runtime Settings Schema](./runtime/index.md)</span></span>\
<span data-ttu-id="d596f-119">Elemente, die Assemblybindung und Laufzeitverhalten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d596f-119">Elements that configure assembly binding and runtime behavior.</span></span>

<span data-ttu-id="d596f-120">[Netzwerk Einstellungs Schema](./network/index.md)</span><span class="sxs-lookup"><span data-stu-id="d596f-120">[Network Settings Schema](./network/index.md)</span></span>\
<span data-ttu-id="d596f-121">-Elemente, die angeben, wie die .NET Framework eine Verbindung mit dem Internet herstellt.</span><span class="sxs-lookup"><span data-stu-id="d596f-121">Elements that specify how the .NET Framework connects to the internet.</span></span>

<span data-ttu-id="d596f-122">[Schema für Kryptografieeinstellungen](./cryptography/index.md)</span><span class="sxs-lookup"><span data-stu-id="d596f-122">[Cryptography Settings Schema](./cryptography/index.md)</span></span>\
<span data-ttu-id="d596f-123">Elemente, die den Klassen, die Kryptografiealgorithmen implementieren, benutzerfreundliche Algorithmusnamen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="d596f-123">Elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>

<span data-ttu-id="d596f-124">[Schema für Konfigurations Abschnitte](configuration-sections-schema.md)</span><span class="sxs-lookup"><span data-stu-id="d596f-124">[Configuration Sections Schema](configuration-sections-schema.md)</span></span>\
<span data-ttu-id="d596f-125">Elemente, mit denen Konfigurations Abschnitte für benutzerdefinierte Einstellungen erstellt und verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d596f-125">Elements used to create and use configuration sections for custom settings.</span></span>

<span data-ttu-id="d596f-126">[Schema der Ablauf Verfolgung und Debugeinstellungen](./trace-debug/index.md)</span><span class="sxs-lookup"><span data-stu-id="d596f-126">[Trace and Debug Settings Schema](./trace-debug/index.md)</span></span>\
<span data-ttu-id="d596f-127">-Elemente, die Ablauf Verfolgungs Schalter und-Listener angeben.</span><span class="sxs-lookup"><span data-stu-id="d596f-127">Elements that specify trace switches and listeners.</span></span>

<span data-ttu-id="d596f-128">[Schema für Compiler-und Sprachanbieter Einstellungen](./compiler/index.md)</span><span class="sxs-lookup"><span data-stu-id="d596f-128">[Compiler and Language Provider Settings Schema](./compiler/index.md)</span></span>\
<span data-ttu-id="d596f-129">-Elemente, die die Compilerkonfiguration für verfügbare Sprachanbieter angeben.</span><span class="sxs-lookup"><span data-stu-id="d596f-129">Elements that specify compiler configuration for available language providers.</span></span>

<span data-ttu-id="d596f-130">[Schema für Anwendungseinstellungen](application-settings-schema.md)</span><span class="sxs-lookup"><span data-stu-id="d596f-130">[Application Settings Schema](application-settings-schema.md)</span></span>\
<span data-ttu-id="d596f-131">Elemente, die eine Windows Forms-oder ASP.NET-Anwendung zum Speichern und Abrufen von anwendungsbezogenen und Benutzer bezogenen Einstellungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d596f-131">Elements that enable a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span>

<span data-ttu-id="d596f-132">[Schema für App-Einstellungen](./appsettings/index.md)</span><span class="sxs-lookup"><span data-stu-id="d596f-132">[App Settings Schema](./appsettings/index.md)</span></span>\
<span data-ttu-id="d596f-133">Dieses Thema enthält benutzerdefinierte Anwendungseinstellungen, z.B. Dateipfade, URLs für den XML-Webdienst oder andere benutzerdefinierte Konfigurationsinformationen für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="d596f-133">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="d596f-134">[Webeinstellungs Schema](./web/index.md)</span><span class="sxs-lookup"><span data-stu-id="d596f-134">[Web Settings Schema](./web/index.md)</span></span>\
<span data-ttu-id="d596f-135">Elemente zum Konfigurieren, wie ASP.net mit einer Host Anwendung wie IIS funktioniert.</span><span class="sxs-lookup"><span data-stu-id="d596f-135">Elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="d596f-136">Wird in *Aspnet.config*-Dateien verwendet.</span><span class="sxs-lookup"><span data-stu-id="d596f-136">Used in *Aspnet.config* files.</span></span>

<span data-ttu-id="d596f-137">[Windows Forms Konfigurations Schema](winforms/index.md)</span><span class="sxs-lookup"><span data-stu-id="d596f-137">[Windows Forms Configuration Schema](winforms/index.md)</span></span>\
<span data-ttu-id="d596f-138">Alle Elemente im Konfigurations Abschnitt Windows Forms-Anwendung, der Anpassungen wie Multimonitor-und High-dpi-Unterstützung umfasst.</span><span class="sxs-lookup"><span data-stu-id="d596f-138">All elements in the Windows Forms application configuration section, which includes customizations such as multi-monitor and high-DPI support.</span></span>

<span data-ttu-id="d596f-139">[WCF-Konfigurations Schema](./wcf/index.md)</span><span class="sxs-lookup"><span data-stu-id="d596f-139">[WCF Configuration Schema](./wcf/index.md)</span></span>\
<span data-ttu-id="d596f-140">Alle Elemente, die es Ihnen ermöglichen, WCF-Dienst-und-Client Anwendungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d596f-140">All elements that enable you to configure WCF service and client applications.</span></span>

<span data-ttu-id="d596f-141">[Syntax der WCF-Anweisung](./wcf-directive/index.md)</span><span class="sxs-lookup"><span data-stu-id="d596f-141">[WCF Directive Syntax](./wcf-directive/index.md)</span></span>\
<span data-ttu-id="d596f-142">Beschreibt die- `@ServiceHost` Direktive, die Seiten spezifische Attribute definiert, die vom SVC-Compiler verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d596f-142">Describes the `@ServiceHost` directive, which defines page-specific attributes used by the .svc compiler.</span></span>

<span data-ttu-id="d596f-143">[WIF-Konfigurations Schema](windows-identity-foundation/index.md)</span><span class="sxs-lookup"><span data-stu-id="d596f-143">[WIF Configuration Schema](windows-identity-foundation/index.md)</span></span>\
<span data-ttu-id="d596f-144">Alle Elemente des Windows Identity Foundation (WIF)-Konfigurations Schemas.</span><span class="sxs-lookup"><span data-stu-id="d596f-144">All elements of the Windows Identity Foundation (WIF) configuration schema.</span></span>

## <a name="related-sections"></a><span data-ttu-id="d596f-145">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="d596f-145">Related sections</span></span>

<span data-ttu-id="d596f-146">[Schema für Remote Einstellungen](/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d596f-146">[Remoting Settings Schema](/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span>\
<span data-ttu-id="d596f-147">Beschreibt die Elemente, mit denen Client- und Serveranwendungen konfiguriert werden, die Remotefunktionen implementieren.</span><span class="sxs-lookup"><span data-stu-id="d596f-147">Describes the elements that configure client and server applications that implement remoting.</span></span>

<span data-ttu-id="d596f-148">[ASP.net-Einstellungs Schema](/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d596f-148">[ASP.NET Settings Schema](/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span>\
<span data-ttu-id="d596f-149">Beschreibt die Elemente, die das Verhalten von ASP.NET-Webanwendungen steuern.</span><span class="sxs-lookup"><span data-stu-id="d596f-149">Describes the elements that control the behavior of ASP.NET Web applications.</span></span>

<span data-ttu-id="d596f-150">[Schema für Webdienst Einstellungen](/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d596f-150">[Web Services Settings Schema](/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span>\
<span data-ttu-id="d596f-151">Beschreibt die Elemente, die das Verhalten von ASP.NET-Webdiensten und ihren Clients steuern.</span><span class="sxs-lookup"><span data-stu-id="d596f-151">Describes the elements that control the behavior of ASP.NET Web services and their clients.</span></span>

<span data-ttu-id="d596f-152">[Konfigurieren von .NET Framework-apps](/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d596f-152">[Configuring .NET Framework Apps](/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100))</span></span>\
<span data-ttu-id="d596f-153">Beschreibt, wie Sicherheit, Assemblybindung und Remotefunktionen in .NET Framework konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="d596f-153">Describes how to configure security, assembly binding, and remoting in the .NET Framework.</span></span>
