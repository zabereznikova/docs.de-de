---
title: '&lt;"appSettings"&gt; -Element für &lt;Konfiguration&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 0ba57f51d3b1e78239677317933507ff009db035
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50190930"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="e0cf0-102">\<AppSettings >-Element für \<Configuration ></span><span class="sxs-lookup"><span data-stu-id="e0cf0-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="e0cf0-103">Enthält benutzerdefinierte anwendungseinstellung an.</span><span class="sxs-lookup"><span data-stu-id="e0cf0-103">Contains custom application settings.</span></span> <span data-ttu-id="e0cf0-104">Dies ist eine vordefinierte Konfigurationsabschnitt von .NET Framework bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e0cf0-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="e0cf0-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="e0cf0-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="e0cf0-106">&nbsp;&nbsp;**\<AppSettings >**</span><span class="sxs-lookup"><span data-stu-id="e0cf0-106">&nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e0cf0-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0cf0-107">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="e0cf0-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="e0cf0-108">Attribute</span></span>

|           | <span data-ttu-id="e0cf0-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0cf0-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="e0cf0-110">**datei**</span><span class="sxs-lookup"><span data-stu-id="e0cf0-110">**file**</span></span>  | <span data-ttu-id="e0cf0-111">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="e0cf0-111">Optional attribute.</span></span><br><br><span data-ttu-id="e0cf0-112">Gibt einen relativen Pfad zu einer externen Datei, die Konfigurationseinstellungen für die benutzerdefinierte Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="e0cf0-112">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="e0cf0-113">Die angegebene Datei enthält die gleiche Art von Einstellungen, die im angegebenen die  **\<hinzufügen >**,  **\<entfernen >**, und  **\<Löschen >** -Elemente an und verwendet die gleichen Schlüssel-Wert-Paar als dieser Elemente zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="e0cf0-113">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="e0cf0-114">Der angegebene Pfad ist relativ zu der Hauptkonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e0cf0-114">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="e0cf0-115">Für eine Windows Forms-Anwendung ist dies der Ordner "binary" (z. B. */Bin/Debug*), nicht der Speicherort der Konfigurationsdatei der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e0cf0-115">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="e0cf0-116">Für Web Forms-Anwendungen wird der Pfad relativ zum Stammverzeichnis Anwendung, ist, in denen die *"Web.config"* Datei befindet.</span><span class="sxs-lookup"><span data-stu-id="e0cf0-116">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="e0cf0-117">Beachten Sie, dass die Laufzeit das Attribut ignoriert, wenn die angegebene Datei nicht gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="e0cf0-117">Note that the runtime ignores the attribute if the specified file can not be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="e0cf0-118">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="e0cf0-118">Parent element</span></span>

|     | <span data-ttu-id="e0cf0-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0cf0-119">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="e0cf0-120">**\<Konfiguration >** Element</span><span class="sxs-lookup"><span data-stu-id="e0cf0-120">**\<configuration>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="e0cf0-121">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e0cf0-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="e0cf0-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e0cf0-122">Child elements</span></span>

|     | <span data-ttu-id="e0cf0-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0cf0-123">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="e0cf0-124">**\<add>**</span><span class="sxs-lookup"><span data-stu-id="e0cf0-124">**\<add>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | <span data-ttu-id="e0cf0-125">Fügt eine benutzerdefinierte anwendungseinstellung an.</span><span class="sxs-lookup"><span data-stu-id="e0cf0-125">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="e0cf0-126">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="e0cf0-126">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | <span data-ttu-id="e0cf0-127">Löscht alle zuvor definierten Anwendungseigenschaften.</span><span class="sxs-lookup"><span data-stu-id="e0cf0-127">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="e0cf0-128">**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="e0cf0-128">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | <span data-ttu-id="e0cf0-129">Entfernt eine zuvor definierte anwendungseinstellung an.</span><span class="sxs-lookup"><span data-stu-id="e0cf0-129">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="e0cf0-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e0cf0-130">Remarks</span></span>

<span data-ttu-id="e0cf0-131">Die  **\<AppSettings >** Element speichert Informationen der benutzerdefinierten Anwendung, wie Datenbank-Verbindungszeichenfolgen, Dateipfade, URLs für den XML-Webdienst oder andere benutzerdefinierte Konfigurationsinformationen für eine die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e0cf0-131">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="e0cf0-132">Die Schlüssel-/Wertpaaren, die im angegebenen die  **\<AppSettings >** Element erfolgt in Code mithilfe der <xref:System.Configuration.ConfigurationSettings> Klasse.</span><span class="sxs-lookup"><span data-stu-id="e0cf0-132">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="e0cf0-133">Können Sie die **Datei** -Attribut in der  **\<"appSettings" >** Element der *"Web.config"* und Konfigurationsdateien der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e0cf0-133">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="e0cf0-134">Dieses Attribut gibt an, eine Konfigurationsdatei, die zusätzliche Einstellungen bereitstellt oder die angegebenen Einstellungen überschreibt die  **\<AppSettings >** Element.</span><span class="sxs-lookup"><span data-stu-id="e0cf0-134">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="e0cf0-135">Die **Datei** Attribut in Source Control Team Entwicklungsszenarios, z. B. wenn ein Benutzer möchte, überschreiben Sie die projekteinstellungen, die in einer Anwendungskonfigurationsdatei angegeben verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e0cf0-135">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="e0cf0-136">Konfigurationsdateien, die gemäß der **Datei** Attribut muss einen Stammknoten aufweisen  **\<AppSettings >** statt  **\<Configuration >**.</span><span class="sxs-lookup"><span data-stu-id="e0cf0-136">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="e0cf0-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e0cf0-137">Example</span></span>

<span data-ttu-id="e0cf0-138">Das folgende Beispiel zeigt eine externe Anwendungseinstellungsdatei (*custom.config*), die eine benutzerdefinierte Anwendungseinstellung definiert.</span><span class="sxs-lookup"><span data-stu-id="e0cf0-138">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="e0cf0-139">Das folgende Beispiel zeigt eine Anwendungskonfigurationsdatei, die die Einstellung in der externen Einstellungsdatei verarbeitet und eine eigene Anwendungseinstellung festlegt.</span><span class="sxs-lookup"><span data-stu-id="e0cf0-139">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="e0cf0-140">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="e0cf0-140">Configuration file</span></span>

<span data-ttu-id="e0cf0-141">Dieses Element kann in der Anwendungskonfigurationsdatei, Konfigurationsdatei des Computers verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.</span><span class="sxs-lookup"><span data-stu-id="e0cf0-141">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0cf0-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0cf0-142">See also</span></span>

- [<span data-ttu-id="e0cf0-143">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e0cf0-143">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
