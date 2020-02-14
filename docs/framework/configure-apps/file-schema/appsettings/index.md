---
title: Schema für App-Einstellungen
ms.date: 05/01/2017
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
ms.openlocfilehash: 0a3363b35a6fc8bd27753eb034f8a1e95feb5292
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215427"
---
# <a name="app-settings-schema"></a><span data-ttu-id="e7bad-102">Schema für App-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="e7bad-102">App Settings schema</span></span>

<span data-ttu-id="e7bad-103">Dieses Thema enthält benutzerdefinierte Anwendungseinstellungen, z.B. Dateipfade, URLs für den XML-Webdienst oder andere benutzerdefinierte Konfigurationsinformationen für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e7bad-103">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="e7bad-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e7bad-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e7bad-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="e7bad-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)</span></span>\
<span data-ttu-id="e7bad-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<add>** ](add-element-for-appsettings.md)</span><span class="sxs-lookup"><span data-stu-id="e7bad-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-appsettings.md)</span></span>\
<span data-ttu-id="e7bad-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clear>** ](clear-element-for-appsettings.md)</span><span class="sxs-lookup"><span data-stu-id="e7bad-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](clear-element-for-appsettings.md)</span></span>\
<span data-ttu-id="e7bad-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<remove>** ](remove-element-for-appsettings.md)</span><span class="sxs-lookup"><span data-stu-id="e7bad-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](remove-element-for-appsettings.md)</span></span>

| <span data-ttu-id="e7bad-109">Element</span><span class="sxs-lookup"><span data-stu-id="e7bad-109">Element</span></span> | <span data-ttu-id="e7bad-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e7bad-110">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="e7bad-111"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="e7bad-111">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="e7bad-112">Enthält die Tags **\<add>** , **\<clear>** und **\<remove>** zur Steuerung von App-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="e7bad-112">Contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="e7bad-113">Verfügt über ein optionales **file**-Attribut.</span><span class="sxs-lookup"><span data-stu-id="e7bad-113">Has an optional **file** attribute.</span></span> |
| [<span data-ttu-id="e7bad-114"> **\<add>** </span><span class="sxs-lookup"><span data-stu-id="e7bad-114">**\<add>**</span></span>](add-element-for-appsettings.md) | <span data-ttu-id="e7bad-115">Definiert eine Einstellung.</span><span class="sxs-lookup"><span data-stu-id="e7bad-115">Defines a setting.</span></span> <span data-ttu-id="e7bad-116">Untergeordnetes Element von **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="e7bad-116">Child of **\<appSettings>**.</span></span> <span data-ttu-id="e7bad-117">Erfordert **key**- und **value**-Attribute.</span><span class="sxs-lookup"><span data-stu-id="e7bad-117">Requires **key** and **value** attributes.</span></span> |
| [<span data-ttu-id="e7bad-118"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="e7bad-118">**\<clear>**</span></span>](clear-element-for-appsettings.md) | <span data-ttu-id="e7bad-119">Löscht alle Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="e7bad-119">Clears all settings.</span></span> <span data-ttu-id="e7bad-120">Untergeordnetes Element von **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="e7bad-120">Child of **\<appSettings>**.</span></span> <span data-ttu-id="e7bad-121">Besitzt keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="e7bad-121">Has no attributes.</span></span> |
| [<span data-ttu-id="e7bad-122"> **\<remove>** </span><span class="sxs-lookup"><span data-stu-id="e7bad-122">**\<remove>**</span></span>](remove-element-for-appsettings.md) | <span data-ttu-id="e7bad-123">Entfernt eine Einstellung.</span><span class="sxs-lookup"><span data-stu-id="e7bad-123">Removes a setting.</span></span> <span data-ttu-id="e7bad-124">Untergeordnetes Element von **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="e7bad-124">Child of **\<appSettings>**.</span></span> <span data-ttu-id="e7bad-125">Erfordert ein **key**-Attribut.</span><span class="sxs-lookup"><span data-stu-id="e7bad-125">Requires a **key** attribute.</span></span> |

## <a name="appsettings-element"></a><span data-ttu-id="e7bad-126">\<appSettings>-Element</span><span class="sxs-lookup"><span data-stu-id="e7bad-126">\<appSettings> element</span></span>

<span data-ttu-id="e7bad-127">Dieses Element enthält die Tags **\<add>** , **\<clear>** und **\<remove>** zur Steuerung von Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="e7bad-127">This element contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="e7bad-128">Es definiert ein optionales Attribut für **file**.</span><span class="sxs-lookup"><span data-stu-id="e7bad-128">It defines an optional attribute for **file**.</span></span>

## <a name="add-element"></a><span data-ttu-id="e7bad-129">\<add>-Element</span><span class="sxs-lookup"><span data-stu-id="e7bad-129">\<add> element</span></span>

<span data-ttu-id="e7bad-130">Fügt der Auflistung der Anwendungseinstellungen eine benutzerdefinierte Anwendungseinstellung als Name/Wertpaar hinzu.</span><span class="sxs-lookup"><span data-stu-id="e7bad-130">Adds a custom application setting as a name/value pair to the application settings collection.</span></span> <span data-ttu-id="e7bad-131">Es definiert Attribute für **key** und **value**</span><span class="sxs-lookup"><span data-stu-id="e7bad-131">It defines attributes for **key** and **value**.</span></span>

## <a name="clear-element"></a><span data-ttu-id="e7bad-132">\<clear>-Element</span><span class="sxs-lookup"><span data-stu-id="e7bad-132">\<clear> element</span></span>

<span data-ttu-id="e7bad-133">Entfernt alle Verweise auf geerbte benutzerdefinierte Anwendungseinstellung und lässt nur die Verweise zu, die durch **\<add>** -Elemente hinzugefügt werden, die dem **\<clear>** -Element folgen.</span><span class="sxs-lookup"><span data-stu-id="e7bad-133">Removes all references to inherited custom application settings and allows only the references that are added by **\<add>** elements following the **\<clear>** element.</span></span> <span data-ttu-id="e7bad-134">Es definiert keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="e7bad-134">It defines no attributes.</span></span>

## <a name="remove-element"></a><span data-ttu-id="e7bad-135">\<remove>-Element</span><span class="sxs-lookup"><span data-stu-id="e7bad-135">\<remove> element</span></span>

<span data-ttu-id="e7bad-136">Entfernt einen Verweis auf eine geerbte benutzerdefinierte Anwendungseinstellung aus der Auflistung der Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="e7bad-136">Removes a reference to an inherited custom application setting from the application settings collection.</span></span> <span data-ttu-id="e7bad-137">Definiert ein Attribut für **key**.</span><span class="sxs-lookup"><span data-stu-id="e7bad-137">It defines an attribute for **key**.</span></span>

## <a name="example"></a><span data-ttu-id="e7bad-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e7bad-138">Example</span></span>

<span data-ttu-id="e7bad-139">Das folgende Beispiel zeigt eine externe Anwendungseinstellungsdatei (*custom.config*), die eine benutzerdefinierte Anwendungseinstellung definiert.</span><span class="sxs-lookup"><span data-stu-id="e7bad-139">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="e7bad-140">Das folgende Beispiel zeigt eine Anwendungskonfigurationsdatei, die die Einstellung in der externen Einstellungsdatei verarbeitet und eine eigene Anwendungseinstellung festlegt.</span><span class="sxs-lookup"><span data-stu-id="e7bad-140">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="e7bad-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e7bad-141">See also</span></span>

- [<span data-ttu-id="e7bad-142">Übersicht über Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="e7bad-142">Application Settings Overview</span></span>](../../../winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="e7bad-143">Architektur der Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="e7bad-143">Application Settings Architecture</span></span>](../../../winforms/advanced/application-settings-architecture.md)
