---
title: Schema für App-Einstellungen
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 028fdbeb90a1499459803f24f3aa62923452edba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="app-settings-schema"></a><span data-ttu-id="7183f-102">Schema für App-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="7183f-102">App Settings schema</span></span>

<span data-ttu-id="7183f-103">Dieses Thema enthält benutzerdefinierte Anwendungseinstellungen, z.B. Dateipfade, URLs für den XML-Webdienst oder andere benutzerdefinierte Konfigurationsinformationen für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="7183f-103">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="7183f-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="7183f-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="7183f-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="7183f-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="7183f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) </span><span class="sxs-lookup"><span data-stu-id="7183f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) </span></span>  
<span data-ttu-id="7183f-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) </span><span class="sxs-lookup"><span data-stu-id="7183f-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) </span></span>  
<span data-ttu-id="7183f-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md)</span><span class="sxs-lookup"><span data-stu-id="7183f-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md)</span></span>

| <span data-ttu-id="7183f-109">Element</span><span class="sxs-lookup"><span data-stu-id="7183f-109">Element</span></span> | <span data-ttu-id="7183f-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7183f-110">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="7183f-111">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="7183f-111">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="7183f-112">Enthält die Tags **\<add>**, **\<clear>** und **\<remove>** zur Steuerung von App-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="7183f-112">Contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="7183f-113">Verfügt über ein optionales **file**-Attribut.</span><span class="sxs-lookup"><span data-stu-id="7183f-113">Has an optional **file** attribute.</span></span> |
| [<span data-ttu-id="7183f-114">**\<add>**</span><span class="sxs-lookup"><span data-stu-id="7183f-114">**\<add>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | <span data-ttu-id="7183f-115">Definiert eine Einstellung.</span><span class="sxs-lookup"><span data-stu-id="7183f-115">Defines a setting.</span></span> <span data-ttu-id="7183f-116">Untergeordnetes Element von **\<appSettings>**.</span><span class="sxs-lookup"><span data-stu-id="7183f-116">Child of **\<appSettings>**.</span></span> <span data-ttu-id="7183f-117">Erfordert **key**- und **value**-Attribute.</span><span class="sxs-lookup"><span data-stu-id="7183f-117">Requires **key** and **value** attributes.</span></span> |
| [<span data-ttu-id="7183f-118">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="7183f-118">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | <span data-ttu-id="7183f-119">Löscht alle Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="7183f-119">Clears all settings.</span></span> <span data-ttu-id="7183f-120">Untergeordnetes Element von **\<appSettings>**.</span><span class="sxs-lookup"><span data-stu-id="7183f-120">Child of **\<appSettings>**.</span></span> <span data-ttu-id="7183f-121">Besitzt keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="7183f-121">Has no attributes.</span></span> |
| [<span data-ttu-id="7183f-122">**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="7183f-122">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | <span data-ttu-id="7183f-123">Entfernt eine Einstellung.</span><span class="sxs-lookup"><span data-stu-id="7183f-123">Removes a setting.</span></span> <span data-ttu-id="7183f-124">Untergeordnetes Element von **\<appSettings>**.</span><span class="sxs-lookup"><span data-stu-id="7183f-124">Child of **\<appSettings>**.</span></span> <span data-ttu-id="7183f-125">Erfordert ein **key**-Attribut.</span><span class="sxs-lookup"><span data-stu-id="7183f-125">Requires a **key** attribute.</span></span> |

## <a name="appsettings-element"></a><span data-ttu-id="7183f-126">\<appSettings>-Element</span><span class="sxs-lookup"><span data-stu-id="7183f-126">\<appSettings> element</span></span>

<span data-ttu-id="7183f-127">Dieses Element enthält die Tags **\<add>**, **\<clear>** und **\<remove>** zur Steuerung von Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="7183f-127">This element contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="7183f-128">Es definiert ein optionales Attribut für **file**.</span><span class="sxs-lookup"><span data-stu-id="7183f-128">It defines an optional attribute for **file**.</span></span>

## <a name="add-element"></a><span data-ttu-id="7183f-129">\<add>-Element</span><span class="sxs-lookup"><span data-stu-id="7183f-129">\<add> element</span></span>

<span data-ttu-id="7183f-130">Fügt der Auflistung der Anwendungseinstellungen eine benutzerdefinierte Anwendungseinstellung als Name/Wertpaar hinzu.</span><span class="sxs-lookup"><span data-stu-id="7183f-130">Adds a custom application setting as a name/value pair to the application settings collection.</span></span> <span data-ttu-id="7183f-131">Es definiert Attribute für **key** und **value**</span><span class="sxs-lookup"><span data-stu-id="7183f-131">It defines attributes for **key** and **value**.</span></span>

## <a name="clear-element"></a><span data-ttu-id="7183f-132">\<clear>-Element</span><span class="sxs-lookup"><span data-stu-id="7183f-132">\<clear> element</span></span>

<span data-ttu-id="7183f-133">Entfernt alle Verweise auf geerbte benutzerdefinierte Anwendungseinstellung und lässt nur die Verweise zu, die durch **\<add>**-Elemente hinzugefügt werden, die dem **\<clear>**-Element folgen.</span><span class="sxs-lookup"><span data-stu-id="7183f-133">Removes all references to inherited custom application settings and allows only the references that are added by **\<add>** elements following the **\<clear>** element.</span></span> <span data-ttu-id="7183f-134">Es definiert keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="7183f-134">It defines no attributes.</span></span>

## <a name="remove-element"></a><span data-ttu-id="7183f-135">\<remove>-Element</span><span class="sxs-lookup"><span data-stu-id="7183f-135">\<remove> element</span></span>

<span data-ttu-id="7183f-136">Entfernt einen Verweis auf eine geerbte benutzerdefinierte Anwendungseinstellung aus der Auflistung der Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="7183f-136">Removes a reference to an inherited custom application setting from the application settings collection.</span></span> <span data-ttu-id="7183f-137">Definiert ein Attribut für **key**.</span><span class="sxs-lookup"><span data-stu-id="7183f-137">It defines an attribute for **key**.</span></span>

## <a name="example"></a><span data-ttu-id="7183f-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7183f-138">Example</span></span>

<span data-ttu-id="7183f-139">Das folgende Beispiel zeigt eine externe Anwendungseinstellungsdatei (*custom.config*), die eine benutzerdefinierte Anwendungseinstellung definiert.</span><span class="sxs-lookup"><span data-stu-id="7183f-139">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="7183f-140">Das folgende Beispiel zeigt eine Anwendungskonfigurationsdatei, die die Einstellung in der externen Einstellungsdatei verarbeitet und eine eigene Anwendungseinstellung festlegt.</span><span class="sxs-lookup"><span data-stu-id="7183f-140">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="7183f-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7183f-141">See also</span></span>

<span data-ttu-id="7183f-142">[Übersicht über Anwendungseinstellungen](~/docs/framework/winforms/advanced/application-settings-overview.md) </span><span class="sxs-lookup"><span data-stu-id="7183f-142">[Application Settings Overview](~/docs/framework/winforms/advanced/application-settings-overview.md) </span></span>  
[<span data-ttu-id="7183f-143">Architektur der Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="7183f-143">Application Settings Architecture</span></span>](~/docs/framework/winforms/advanced/application-settings-architecture.md)
