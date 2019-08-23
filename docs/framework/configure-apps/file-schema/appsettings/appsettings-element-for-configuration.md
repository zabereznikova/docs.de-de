---
title: <appSettings>-Element für <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: a64db49b521651ccff8b928720fe3273f8600b68
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921325"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="3b545-102">\<appSettings > Element für \<die Konfigurations ></span><span class="sxs-lookup"><span data-stu-id="3b545-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="3b545-103">Enthält benutzerdefinierte Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="3b545-103">Contains custom application settings.</span></span> <span data-ttu-id="3b545-104">Dies ist ein vordefinierter Konfigurations Abschnitt, der vom .NET Framework bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="3b545-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="3b545-105">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="3b545-105">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="3b545-106">&nbsp;&nbsp; **\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="3b545-106">&nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="3b545-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="3b545-107">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="3b545-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="3b545-108">Attribute</span></span>

|           | <span data-ttu-id="3b545-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3b545-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="3b545-110">**datei**</span><span class="sxs-lookup"><span data-stu-id="3b545-110">**file**</span></span>  | <span data-ttu-id="3b545-111">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="3b545-111">Optional attribute.</span></span><br><br><span data-ttu-id="3b545-112">Gibt einen relativen Pfad zu einer externen Datei an, die benutzerdefinierte Anwendungs Konfigurationseinstellungen enthält.</span><span class="sxs-lookup"><span data-stu-id="3b545-112">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="3b545-113">Die angegebene Datei enthält die gleichen Einstellungen, die in den  **\<Elementen Add >** ,  **\<remove >** und  **\<Clear >** angegeben sind, und verwendet dasselbe Schlüssel-Wert-Paar-Format wie diese Elemente.</span><span class="sxs-lookup"><span data-stu-id="3b545-113">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="3b545-114">Der angegebene Pfad ist relativ zur Hauptkonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="3b545-114">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="3b545-115">Bei einer Windows Forms Anwendung ist dies der binäre Ordner (z. b. */bin/debug*) und nicht der Speicherort der Anwendungs Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="3b545-115">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="3b545-116">Bei Web Forms Anwendungen ist der Pfad relativ zum Anwendungs Stamm, in dem sich die Datei *Web. config* befindet.</span><span class="sxs-lookup"><span data-stu-id="3b545-116">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="3b545-117">Beachten Sie, dass die Laufzeit das-Attribut ignoriert, wenn die angegebene Datei nicht gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="3b545-117">Note that the runtime ignores the attribute if the specified file can not be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="3b545-118">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="3b545-118">Parent element</span></span>

|     | <span data-ttu-id="3b545-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3b545-119">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="3b545-120">Configuration >-Element  **\<** </span><span class="sxs-lookup"><span data-stu-id="3b545-120">**\<configuration>** Element</span></span>](../configuration-element.md) | <span data-ttu-id="3b545-121">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="3b545-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="3b545-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3b545-122">Child elements</span></span>

|     | <span data-ttu-id="3b545-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3b545-123">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="3b545-124"> **\<add>** </span><span class="sxs-lookup"><span data-stu-id="3b545-124">**\<add>**</span></span>](add-element-for-appsettings.md) | <span data-ttu-id="3b545-125">Fügt eine benutzerdefinierte Anwendungs Einstellung hinzu.</span><span class="sxs-lookup"><span data-stu-id="3b545-125">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="3b545-126"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="3b545-126">**\<clear>**</span></span>](clear-element-for-appsettings.md) | <span data-ttu-id="3b545-127">Löscht alle zuvor definierten Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="3b545-127">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="3b545-128"> **\<remove>** </span><span class="sxs-lookup"><span data-stu-id="3b545-128">**\<remove>**</span></span>](remove-element-for-appsettings.md) | <span data-ttu-id="3b545-129">Entfernt eine zuvor definierte Anwendungs Einstellung.</span><span class="sxs-lookup"><span data-stu-id="3b545-129">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="3b545-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3b545-130">Remarks</span></span>

<span data-ttu-id="3b545-131">Das  **\<appSettings->** Element speichert benutzerdefinierte Konfigurationsinformationen für die Anwendung, z. b. Daten bankverbindungs Zeichenfolgen, Dateipfade, XML-Webdienst-URLs oder andere benutzerdefinierte Konfigurationsinformationen für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="3b545-131">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="3b545-132">Der Zugriff auf die Schlüssel-Wert-Paare, die im  **\<appSettings->** Element angegeben <xref:System.Configuration.ConfigurationSettings> sind, erfolgt im Code mithilfe der-Klasse.</span><span class="sxs-lookup"><span data-stu-id="3b545-132">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="3b545-133">Sie können das file-Attribut im  **\<appSettings->** -Element der *Web. config* - **Datei** und der Anwendungs Konfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="3b545-133">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="3b545-134">Dieses Attribut gibt eine Konfigurationsdatei an, die zusätzliche Einstellungen bereitstellt oder die im  **\<appSettings >** -Element angegebenen Einstellungen überschreibt.</span><span class="sxs-lookup"><span data-stu-id="3b545-134">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="3b545-135">Das **File** -Attribut kann in Entwicklungsszenarien der Quell Code Verwaltung verwendet werden, z. b. Wenn ein Benutzer die in einer Anwendungs Konfigurationsdatei angegebenen Projekteinstellungen überschreiben möchte.</span><span class="sxs-lookup"><span data-stu-id="3b545-135">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="3b545-136">Konfigurationsdateien, die durch das **File** -Attribut angegeben werden, müssen einen Stamm Knoten von  **\<**  **\<** appSettings > anstelle von Konfigurations > haben.</span><span class="sxs-lookup"><span data-stu-id="3b545-136">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="3b545-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3b545-137">Example</span></span>

<span data-ttu-id="3b545-138">Das folgende Beispiel zeigt eine externe Anwendungseinstellungsdatei (*custom.config*), die eine benutzerdefinierte Anwendungseinstellung definiert.</span><span class="sxs-lookup"><span data-stu-id="3b545-138">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="3b545-139">Das folgende Beispiel zeigt eine Anwendungskonfigurationsdatei, die die Einstellung in der externen Einstellungsdatei verarbeitet und eine eigene Anwendungseinstellung festlegt.</span><span class="sxs-lookup"><span data-stu-id="3b545-139">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="3b545-140">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="3b545-140">Configuration file</span></span>

<span data-ttu-id="3b545-141">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="3b545-141">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b545-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b545-142">See also</span></span>

- [<span data-ttu-id="3b545-143">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3b545-143">Configuration file schema for the .NET Framework</span></span>](../index.md)
