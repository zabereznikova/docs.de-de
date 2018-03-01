---
title: "&lt;\"appSettings\"&gt; -Element für &lt;Konfiguration&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cebb9ba7ebeb483233276324289a4ddc5a0bc381
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="0e943-102">\<"appSettings" >-Element für \<Configuration ></span><span class="sxs-lookup"><span data-stu-id="0e943-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="0e943-103">Enthält Einstellungen, die benutzerdefinierte Anwendung.</span><span class="sxs-lookup"><span data-stu-id="0e943-103">Contains custom application settings.</span></span> <span data-ttu-id="0e943-104">Dies ist eine vordefinierte Konfigurationsabschnitt, der von .NET Framework bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0e943-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="0e943-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="0e943-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="0e943-106">&nbsp;&nbsp;**\<"appSettings" >**</span><span class="sxs-lookup"><span data-stu-id="0e943-106">&nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="0e943-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e943-107">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="0e943-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="0e943-108">Attribute</span></span>

|           | <span data-ttu-id="0e943-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e943-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="0e943-110">**datei**</span><span class="sxs-lookup"><span data-stu-id="0e943-110">**file**</span></span>  | <span data-ttu-id="0e943-111">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="0e943-111">Optional attribute.</span></span><br><br><span data-ttu-id="0e943-112">Gibt einen relativen Pfad zu einer externen Datei mit benutzerdefinierten Anwendung-Konfigurationseinstellungen an.</span><span class="sxs-lookup"><span data-stu-id="0e943-112">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="0e943-113">Die angegebene Datei enthält die gleiche Art von Einstellungen, die im angegebenen der  **\<hinzufügen >**,  **\<entfernen >**, und  **\<deaktivieren >** Elemente und verwendet den gleichen Schlüssel-Wert-Paar als diese Elemente zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="0e943-113">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="0e943-114">Der angegebene Pfad ist relativ zu der Hauptkonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="0e943-114">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="0e943-115">Für eine Windows Forms-Anwendung, die dies ist die binäre Ordner (z. B. */Bin/Debug*), nicht den Speicherort der Konfigurationsdatei der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="0e943-115">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="0e943-116">Für Web Forms-Anwendungen ist der Pfad relativ zum Stammverzeichnis Anwendung, in denen die *"Web.config"* Datei befindet.</span><span class="sxs-lookup"><span data-stu-id="0e943-116">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="0e943-117">Beachten Sie, dass die Laufzeit das Attribut ignoriert, wenn die angegebene Datei nicht gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="0e943-117">Note that the runtime ignores the attribute if the specified file can not be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="0e943-118">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="0e943-118">Parent element</span></span>

|     | <span data-ttu-id="0e943-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e943-119">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="0e943-120">**\<Konfiguration >** Element</span><span class="sxs-lookup"><span data-stu-id="0e943-120">**\<configuration>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="0e943-121">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="0e943-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="0e943-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0e943-122">Child elements</span></span>

|     | <span data-ttu-id="0e943-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e943-123">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="0e943-124">**\<add>**</span><span class="sxs-lookup"><span data-stu-id="0e943-124">**\<add>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | <span data-ttu-id="0e943-125">Fügt eine benutzerdefinierte Anwendung-Einstellung.</span><span class="sxs-lookup"><span data-stu-id="0e943-125">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="0e943-126">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="0e943-126">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | <span data-ttu-id="0e943-127">Löscht alle zuvor definierten Anwendungseigenschaften.</span><span class="sxs-lookup"><span data-stu-id="0e943-127">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="0e943-128">**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="0e943-128">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | <span data-ttu-id="0e943-129">Entfernt eine zuvor definierte anwendungseinstellung an.</span><span class="sxs-lookup"><span data-stu-id="0e943-129">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="0e943-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0e943-130">Remarks</span></span>

<span data-ttu-id="0e943-131">Die  **\<"appSettings" >** Element speichert benutzerdefinierte Anwendungskonfigurationsinformationen wie Datenbankverbindungszeichenfolgen, Dateipfade, XML-Webdienst-URLs oder anderen benutzerdefinierten Konfigurationsinformationen für eine die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="0e943-131">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="0e943-132">Im angegebenen Schlüssel/Wert-Paare der  **\<"appSettings" >** Element erfolgt in Code mit der <xref:System.Configuration.ConfigurationSettings> Klasse.</span><span class="sxs-lookup"><span data-stu-id="0e943-132">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="0e943-133">Können Sie die **Datei** Attribut in der  **\<"appSettings" >** Element von der *"Web.config"* und Anwendungskonfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="0e943-133">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="0e943-134">Dieses Attribut gibt an, eine Konfigurationsdatei, die zusätzliche Einstellungen oder die festgelegten Einstellungen überschreibt die  **\<"appSettings" >** Element.</span><span class="sxs-lookup"><span data-stu-id="0e943-134">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="0e943-135">Die **Datei** Attribut in Source Control Team Entwicklungsszenarien z. B. wenn ein Benutzer in einer Anwendungskonfigurationsdatei angegebenen projekteinstellungen außer Kraft setzen möchte genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="0e943-135">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="0e943-136">Konfigurationsdateien gemäß der **Datei** Attribut benötigen einen Stammknoten des  **\<"appSettings" >** statt  **\<Configuration >**.</span><span class="sxs-lookup"><span data-stu-id="0e943-136">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="0e943-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0e943-137">Example</span></span>

<span data-ttu-id="0e943-138">Das folgende Beispiel zeigt eine externe Anwendungseinstellungsdatei (*custom.config*), die eine benutzerdefinierte Anwendungseinstellung definiert.</span><span class="sxs-lookup"><span data-stu-id="0e943-138">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="0e943-139">Das folgende Beispiel zeigt eine Anwendungskonfigurationsdatei, die die Einstellung in der externen Einstellungsdatei verarbeitet und eine eigene Anwendungseinstellung festlegt.</span><span class="sxs-lookup"><span data-stu-id="0e943-139">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="0e943-140">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="0e943-140">Configuration file</span></span>

<span data-ttu-id="0e943-141">Dieses Element kann in der Anwendungskonfigurationsdatei Computerkonfigurationsdatei verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.</span><span class="sxs-lookup"><span data-stu-id="0e943-141">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e943-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e943-142">See also</span></span>

[<span data-ttu-id="0e943-143">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0e943-143">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
