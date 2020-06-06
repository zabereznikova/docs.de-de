---
title: <appSettings>-Element für <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
ms.openlocfilehash: ea341d562f4b163a3a1771da0f20903b7d64bcdf
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155530"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="76504-102">\<appSettings>-Element für \<configuration></span><span class="sxs-lookup"><span data-stu-id="76504-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="76504-103">Enthält benutzerdefinierte Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="76504-103">Contains custom application settings.</span></span> <span data-ttu-id="76504-104">Dies ist ein vordefinierter Konfigurations Abschnitt, der vom .NET Framework bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="76504-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="76504-105">[**\<configuration>**](../configuration-element.md) &nbsp;&nbsp;**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="76504-105">[**\<configuration>**](../configuration-element.md) &nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="76504-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="76504-106">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="76504-107">attribute</span><span class="sxs-lookup"><span data-stu-id="76504-107">Attribute</span></span>

|           | <span data-ttu-id="76504-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="76504-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="76504-109">**Datei**</span><span class="sxs-lookup"><span data-stu-id="76504-109">**file**</span></span>  | <span data-ttu-id="76504-110">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="76504-110">Optional attribute.</span></span><br><br><span data-ttu-id="76504-111">Gibt einen relativen Pfad zu einer externen Datei an, die benutzerdefinierte Anwendungs Konfigurationseinstellungen enthält.</span><span class="sxs-lookup"><span data-stu-id="76504-111">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="76504-112">Die angegebene Datei enthält die gleichen Einstellungen, die in den **\<add>** Elementen, und angegeben sind, **\<remove>** **\<clear>** und verwendet dasselbe Schlüssel-Wert-Paar-Format wie diese Elemente.</span><span class="sxs-lookup"><span data-stu-id="76504-112">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="76504-113">Der angegebene Pfad ist relativ zur Hauptkonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="76504-113">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="76504-114">Bei einer Windows Forms Anwendung ist dies der binäre Ordner (z. b. */bin/debug*) und nicht der Speicherort der Anwendungs Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="76504-114">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="76504-115">Bei Web Forms Anwendungen ist der Pfad relativ zum Anwendungs Stamm, in dem sich die Datei *Web. config* befindet.</span><span class="sxs-lookup"><span data-stu-id="76504-115">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="76504-116">Die Laufzeit ignoriert das-Attribut, wenn die angegebene Datei nicht gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="76504-116">The runtime ignores the attribute if the specified file can't be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="76504-117">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="76504-117">Parent element</span></span>

|     | <span data-ttu-id="76504-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="76504-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="76504-119">**\<configuration>** Gewisses</span><span class="sxs-lookup"><span data-stu-id="76504-119">**\<configuration>** Element</span></span>](../configuration-element.md) | <span data-ttu-id="76504-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="76504-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="76504-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="76504-121">Child elements</span></span>

|     | <span data-ttu-id="76504-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="76504-122">Description</span></span> |
| --- | ----------- |
| [**\<add>**](add-element-for-appsettings.md) | <span data-ttu-id="76504-123">Fügt eine benutzerdefinierte Anwendungs Einstellung hinzu.</span><span class="sxs-lookup"><span data-stu-id="76504-123">Adds a custom application setting.</span></span> |
| [**\<clear>**](clear-element-for-appsettings.md) | <span data-ttu-id="76504-124">Löscht alle zuvor definierten Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="76504-124">Clears all previously defined application settings.</span></span> |
| [**\<remove>**](remove-element-for-appsettings.md) | <span data-ttu-id="76504-125">Entfernt eine zuvor definierte Anwendungs Einstellung.</span><span class="sxs-lookup"><span data-stu-id="76504-125">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="76504-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="76504-126">Remarks</span></span>

<span data-ttu-id="76504-127">Das- **\<appSettings>** Element speichert benutzerdefinierte Konfigurationsinformationen für die Anwendung, z. b. Daten bankverbindungs Zeichenfolgen, Dateipfade, XML-Webdienst-URLs oder andere benutzerdefinierte Konfigurationsinformationen für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="76504-127">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="76504-128">Der Zugriff auf die im-Element angegebenen Schlüssel-Wert-Paare **\<appSettings>** erfolgt im Code mithilfe der- <xref:System.Configuration.ConfigurationSettings> Klasse.</span><span class="sxs-lookup"><span data-stu-id="76504-128">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="76504-129">Sie können das **File** -Attribut im **\<appSettings>** -Element der *Web. config* -Datei und der Anwendungs Konfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="76504-129">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="76504-130">Dieses Attribut gibt eine Konfigurationsdatei an, die zusätzliche Einstellungen bereitstellt oder die im-Element angegebenen Einstellungen überschreibt **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="76504-130">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="76504-131">Das **File** -Attribut kann in Entwicklungsszenarien der Quell Code Verwaltung verwendet werden, z. b. Wenn ein Benutzer die in einer Anwendungs Konfigurationsdatei angegebenen Projekteinstellungen überschreiben möchte.</span><span class="sxs-lookup"><span data-stu-id="76504-131">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="76504-132">Die Konfigurationsdateien, die vom **File** -Attribut angegeben werden, müssen einen Stamm Knoten von anstelle von aufweisen **\<appSettings>** **\<configuration>** .</span><span class="sxs-lookup"><span data-stu-id="76504-132">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="76504-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="76504-133">Example</span></span>

<span data-ttu-id="76504-134">Das folgende Beispiel zeigt eine externe Anwendungseinstellungsdatei (*custom.config*), die eine benutzerdefinierte Anwendungseinstellung definiert.</span><span class="sxs-lookup"><span data-stu-id="76504-134">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="76504-135">Das folgende Beispiel zeigt eine Anwendungskonfigurationsdatei, die die Einstellung in der externen Einstellungsdatei verarbeitet und eine eigene Anwendungseinstellung festlegt.</span><span class="sxs-lookup"><span data-stu-id="76504-135">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="76504-136">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="76504-136">Configuration file</span></span>

<span data-ttu-id="76504-137">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="76504-137">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="76504-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76504-138">See also</span></span>

- [<span data-ttu-id="76504-139">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="76504-139">Configuration file schema for the .NET Framework</span></span>](../index.md)
