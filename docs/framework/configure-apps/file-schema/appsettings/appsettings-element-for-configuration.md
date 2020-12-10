---
title: <appSettings>-Element für <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
ms.openlocfilehash: 66260d15768781b7fa3d9397b8e8a7d9ad68ab95
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009793"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="e13d9-102">\<appSettings>-Element für \<configuration></span><span class="sxs-lookup"><span data-stu-id="e13d9-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="e13d9-103">Enthält benutzerdefinierte Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="e13d9-103">Contains custom application settings.</span></span> <span data-ttu-id="e13d9-104">Dies ist ein vordefinierter Konfigurations Abschnitt, der vom .NET Framework bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e13d9-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<appSettings>**

## <a name="syntax"></a><span data-ttu-id="e13d9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e13d9-105">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="e13d9-106">attribute</span><span class="sxs-lookup"><span data-stu-id="e13d9-106">Attribute</span></span>

|           | <span data-ttu-id="e13d9-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e13d9-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="e13d9-108">**datei**</span><span class="sxs-lookup"><span data-stu-id="e13d9-108">**file**</span></span>  | <span data-ttu-id="e13d9-109">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="e13d9-109">Optional attribute.</span></span><br><br><span data-ttu-id="e13d9-110">Gibt einen relativen Pfad zu einer externen Datei an, die benutzerdefinierte Anwendungs Konfigurationseinstellungen enthält.</span><span class="sxs-lookup"><span data-stu-id="e13d9-110">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="e13d9-111">Die angegebene Datei enthält die gleichen Einstellungen, die in den **\<add>** Elementen, und angegeben sind, **\<remove>** **\<clear>** und verwendet dasselbe Schlüssel-Wert-Paar-Format wie diese Elemente.</span><span class="sxs-lookup"><span data-stu-id="e13d9-111">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="e13d9-112">Der angegebene Pfad ist relativ zur Hauptkonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e13d9-112">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="e13d9-113">Bei einer Windows Forms Anwendung ist dies der binäre Ordner (z. b. */bin/debug*) und nicht der Speicherort der Anwendungs Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e13d9-113">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="e13d9-114">Bei Web Forms-Anwendungen ist der Pfad relativ zum Stamm der Anwendung, in dem sich die Datei *web.config* befindet.</span><span class="sxs-lookup"><span data-stu-id="e13d9-114">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="e13d9-115">Die Laufzeit ignoriert das-Attribut, wenn die angegebene Datei nicht gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="e13d9-115">The runtime ignores the attribute if the specified file can't be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="e13d9-116">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="e13d9-116">Parent element</span></span>

|     | <span data-ttu-id="e13d9-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e13d9-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="e13d9-118">**\<configuration>**-Element</span><span class="sxs-lookup"><span data-stu-id="e13d9-118">**\<configuration>** Element</span></span>](../configuration-element.md) | <span data-ttu-id="e13d9-119">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e13d9-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="e13d9-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e13d9-120">Child elements</span></span>

|     | <span data-ttu-id="e13d9-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e13d9-121">Description</span></span> |
| --- | ----------- |
| [**\<add>**](add-element-for-appsettings.md) | <span data-ttu-id="e13d9-122">Fügt eine benutzerdefinierte Anwendungs Einstellung hinzu.</span><span class="sxs-lookup"><span data-stu-id="e13d9-122">Adds a custom application setting.</span></span> |
| [**\<clear>**](clear-element-for-appsettings.md) | <span data-ttu-id="e13d9-123">Löscht alle zuvor definierten Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="e13d9-123">Clears all previously defined application settings.</span></span> |
| [**\<remove>**](remove-element-for-appsettings.md) | <span data-ttu-id="e13d9-124">Entfernt eine zuvor definierte Anwendungs Einstellung.</span><span class="sxs-lookup"><span data-stu-id="e13d9-124">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="e13d9-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e13d9-125">Remarks</span></span>

<span data-ttu-id="e13d9-126">Das- **\<appSettings>** Element speichert benutzerdefinierte Konfigurationsinformationen für die Anwendung, z. b. Daten bankverbindungs Zeichenfolgen, Dateipfade, XML-Webdienst-URLs oder andere benutzerdefinierte Konfigurationsinformationen für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e13d9-126">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="e13d9-127">Der Zugriff auf die im-Element angegebenen Schlüssel-Wert-Paare **\<appSettings>** erfolgt im Code mithilfe der- <xref:System.Configuration.ConfigurationSettings> Klasse.</span><span class="sxs-lookup"><span data-stu-id="e13d9-127">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="e13d9-128">Sie können das **File** -Attribut im **\<appSettings>** -Element der *Web.config* -und Anwendungs Konfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="e13d9-128">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="e13d9-129">Dieses Attribut gibt eine Konfigurationsdatei an, die zusätzliche Einstellungen bereitstellt oder die im-Element angegebenen Einstellungen überschreibt **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="e13d9-129">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="e13d9-130">Das **File** -Attribut kann in Entwicklungsszenarien der Quell Code Verwaltung verwendet werden, z. b. Wenn ein Benutzer die in einer Anwendungs Konfigurationsdatei angegebenen Projekteinstellungen überschreiben möchte.</span><span class="sxs-lookup"><span data-stu-id="e13d9-130">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="e13d9-131">Die Konfigurationsdateien, die vom **File** -Attribut angegeben werden, müssen einen Stamm Knoten von anstelle von aufweisen **\<appSettings>** **\<configuration>** .</span><span class="sxs-lookup"><span data-stu-id="e13d9-131">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="e13d9-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e13d9-132">Example</span></span>

<span data-ttu-id="e13d9-133">Das folgende Beispiel zeigt eine externe Anwendungseinstellungsdatei (*custom.config*), die eine benutzerdefinierte Anwendungseinstellung definiert.</span><span class="sxs-lookup"><span data-stu-id="e13d9-133">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="e13d9-134">Das folgende Beispiel zeigt eine Anwendungskonfigurationsdatei, die die Einstellung in der externen Einstellungsdatei verarbeitet und eine eigene Anwendungseinstellung festlegt.</span><span class="sxs-lookup"><span data-stu-id="e13d9-134">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="e13d9-135">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="e13d9-135">Configuration file</span></span>

<span data-ttu-id="e13d9-136">Dieses Element kann in der Anwendungs Konfigurationsdatei, der Computer Konfigurationsdatei (*Machine.config*) und *Web.config* Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="e13d9-136">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="e13d9-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e13d9-137">See also</span></span>

- [<span data-ttu-id="e13d9-138">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e13d9-138">Configuration file schema for the .NET Framework</span></span>](../index.md)
