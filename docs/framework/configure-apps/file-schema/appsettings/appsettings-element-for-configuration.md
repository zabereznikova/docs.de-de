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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155530"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="9e51e-102">\<appSettings>-Element für \<Konfigurations-></span><span class="sxs-lookup"><span data-stu-id="9e51e-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="9e51e-103">Enthält benutzerdefinierte Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="9e51e-103">Contains custom application settings.</span></span> <span data-ttu-id="9e51e-104">Dies ist ein vordefinierter Konfigurationsabschnitt, der von .NET Framework bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="9e51e-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="9e51e-105">Konfiguration &nbsp; &nbsp;>[\*\* \<\*\*](../configuration-element.md) \*\* \<appEinstellungen>\*\*</span><span class="sxs-lookup"><span data-stu-id="9e51e-105">[**\<configuration>**](../configuration-element.md) &nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="9e51e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9e51e-106">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="9e51e-107">attribute</span><span class="sxs-lookup"><span data-stu-id="9e51e-107">Attribute</span></span>

|           | <span data-ttu-id="9e51e-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e51e-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="9e51e-109">**Datei**</span><span class="sxs-lookup"><span data-stu-id="9e51e-109">**file**</span></span>  | <span data-ttu-id="9e51e-110">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="9e51e-110">Optional attribute.</span></span><br><br><span data-ttu-id="9e51e-111">Gibt einen relativen Pfad zu einer externen Datei an, die benutzerdefinierte Anwendungskonfigurationseinstellungen enthält.</span><span class="sxs-lookup"><span data-stu-id="9e51e-111">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="9e51e-112">Die angegebene Datei enthält die gleiche Art von Einstellungen, die in der \*\* \<Add->\*\* angegeben sind, \*\* \<>entfernen **und \*\* \<>** Elemente löschen und das gleiche Schlüssel-Wert-Paarformat wie diese Elemente verwenden.</span><span class="sxs-lookup"><span data-stu-id="9e51e-112">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="9e51e-113">Der angegebene Pfad ist relativ zur Hauptkonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="9e51e-113">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="9e51e-114">Bei einer Windows Forms-Anwendung ist dies der Binärordner (z. B. */bin/debug*), nicht der Speicherort der Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="9e51e-114">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="9e51e-115">Bei Web Forms-Anwendungen ist der Pfad relativ zum Anwendungsstamm, in dem sich die *Datei web.config* befindet.</span><span class="sxs-lookup"><span data-stu-id="9e51e-115">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="9e51e-116">Die Laufzeit ignoriert das Attribut, wenn die angegebene Datei nicht gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="9e51e-116">The runtime ignores the attribute if the specified file can't be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="9e51e-117">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="9e51e-117">Parent element</span></span>

|     | <span data-ttu-id="9e51e-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e51e-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="9e51e-119">\*\* \<Konfiguration>\*\* Element</span><span class="sxs-lookup"><span data-stu-id="9e51e-119">**\<configuration>** Element</span></span>](../configuration-element.md) | <span data-ttu-id="9e51e-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="9e51e-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="9e51e-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9e51e-121">Child elements</span></span>

|     | <span data-ttu-id="9e51e-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e51e-122">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="9e51e-123">**\<hinzufügen>**</span><span class="sxs-lookup"><span data-stu-id="9e51e-123">**\<add>**</span></span>](add-element-for-appsettings.md) | <span data-ttu-id="9e51e-124">Fügt eine benutzerdefinierte Anwendungseinstellung hinzu.</span><span class="sxs-lookup"><span data-stu-id="9e51e-124">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="9e51e-125">**\<klare>**</span><span class="sxs-lookup"><span data-stu-id="9e51e-125">**\<clear>**</span></span>](clear-element-for-appsettings.md) | <span data-ttu-id="9e51e-126">Löscht alle zuvor definierten Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="9e51e-126">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="9e51e-127">**\<entfernen sie>**</span><span class="sxs-lookup"><span data-stu-id="9e51e-127">**\<remove>**</span></span>](remove-element-for-appsettings.md) | <span data-ttu-id="9e51e-128">Entfernt eine zuvor definierte Anwendungseinstellung.</span><span class="sxs-lookup"><span data-stu-id="9e51e-128">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="9e51e-129">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9e51e-129">Remarks</span></span>

<span data-ttu-id="9e51e-130">Das \*\* \<appSettings>-Element\*\* speichert benutzerdefinierte Anwendungskonfigurationsinformationen, z. B. Datenbankverbindungszeichenfolgen, Dateipfade, XML-Webdienst-URLs oder andere benutzerdefinierte Konfigurationsinformationen für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="9e51e-130">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="9e51e-131">Auf die in der <xref:System.Configuration.ConfigurationSettings> \*\* \<appSettings>-Elemente\*\* angegebenen Schlüssel-Wert-Paare wird im Code mithilfe der Klasse zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="9e51e-131">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="9e51e-132">Sie können das **Dateiattribut** im \*\* \<appSettings>-Element\*\* der *Konfigurationsdateien Web.config* und Application verwenden.</span><span class="sxs-lookup"><span data-stu-id="9e51e-132">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="9e51e-133">Dieses Attribut gibt eine Konfigurationsdatei an, die zusätzliche Einstellungen bereitstellt oder die im \*\* \<appSettings>-Element\*\* angegebenen Einstellungen überschreibt.</span><span class="sxs-lookup"><span data-stu-id="9e51e-133">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="9e51e-134">Das **Dateiattribut** kann in Entwicklungsszenarien für Quellcodeverwaltungsteams verwendet werden, z. B. wenn ein Benutzer die in einer Anwendungskonfigurationsdatei angegebenen Projekteinstellungen überschreiben möchte.</span><span class="sxs-lookup"><span data-stu-id="9e51e-134">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="9e51e-135">Konfigurationsdateien, die durch das **Dateiattribut** angegeben werden, müssen über einen Stammknoten von \*\* \<appSettings>\*\* und nicht über \*\* \<eine Konfiguration>\*\* verfügen.</span><span class="sxs-lookup"><span data-stu-id="9e51e-135">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="9e51e-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9e51e-136">Example</span></span>

<span data-ttu-id="9e51e-137">Das folgende Beispiel zeigt eine externe Anwendungseinstellungsdatei (*custom.config*), die eine benutzerdefinierte Anwendungseinstellung definiert.</span><span class="sxs-lookup"><span data-stu-id="9e51e-137">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="9e51e-138">Das folgende Beispiel zeigt eine Anwendungskonfigurationsdatei, die die Einstellung in der externen Einstellungsdatei verarbeitet und eine eigene Anwendungseinstellung festlegt.</span><span class="sxs-lookup"><span data-stu-id="9e51e-138">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="9e51e-139">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="9e51e-139">Configuration file</span></span>

<span data-ttu-id="9e51e-140">Dieses Element kann in der Anwendungskonfigurationsdatei, der Computerkonfigurationsdatei (*Machine.config*) und *web.config-Dateien* verwendet werden, die sich nicht auf Anwendungsverzeichnisebene befinden.</span><span class="sxs-lookup"><span data-stu-id="9e51e-140">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e51e-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9e51e-141">See also</span></span>

- [<span data-ttu-id="9e51e-142">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9e51e-142">Configuration file schema for the .NET Framework</span></span>](../index.md)
