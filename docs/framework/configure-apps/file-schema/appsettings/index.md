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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215427"
---
# <a name="app-settings-schema"></a><span data-ttu-id="d2452-102">Schema für App-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="d2452-102">App Settings schema</span></span>

<span data-ttu-id="d2452-103">Dieses Thema enthält benutzerdefinierte Anwendungseinstellungen, z.B. Dateipfade, URLs für den XML-Webdienst oder andere benutzerdefinierte Konfigurationsinformationen für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="d2452-103">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](clear-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](remove-element-for-appsettings.md)

| <span data-ttu-id="d2452-104">Element</span><span class="sxs-lookup"><span data-stu-id="d2452-104">Element</span></span> | <span data-ttu-id="d2452-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d2452-105">Description</span></span> |
| ------- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="d2452-106">Enthält **\<add>** **\<clear>** -,-und- **\<remove>** Tags zum Steuern von Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="d2452-106">Contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="d2452-107">Verfügt über ein optionales **file**-Attribut.</span><span class="sxs-lookup"><span data-stu-id="d2452-107">Has an optional **file** attribute.</span></span> |
| [**\<add>**](add-element-for-appsettings.md) | <span data-ttu-id="d2452-108">Definiert eine Einstellung.</span><span class="sxs-lookup"><span data-stu-id="d2452-108">Defines a setting.</span></span> <span data-ttu-id="d2452-109">Untergeordnetes Element von **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="d2452-109">Child of **\<appSettings>**.</span></span> <span data-ttu-id="d2452-110">Erfordert **key**- und **value**-Attribute.</span><span class="sxs-lookup"><span data-stu-id="d2452-110">Requires **key** and **value** attributes.</span></span> |
| [**\<clear>**](clear-element-for-appsettings.md) | <span data-ttu-id="d2452-111">Löscht alle Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="d2452-111">Clears all settings.</span></span> <span data-ttu-id="d2452-112">Untergeordnetes Element von **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="d2452-112">Child of **\<appSettings>**.</span></span> <span data-ttu-id="d2452-113">Besitzt keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="d2452-113">Has no attributes.</span></span> |
| [**\<remove>**](remove-element-for-appsettings.md) | <span data-ttu-id="d2452-114">Entfernt eine Einstellung.</span><span class="sxs-lookup"><span data-stu-id="d2452-114">Removes a setting.</span></span> <span data-ttu-id="d2452-115">Untergeordnetes Element von **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="d2452-115">Child of **\<appSettings>**.</span></span> <span data-ttu-id="d2452-116">Erfordert ein **key**-Attribut.</span><span class="sxs-lookup"><span data-stu-id="d2452-116">Requires a **key** attribute.</span></span> |

## <a name="appsettings-element"></a><span data-ttu-id="d2452-117">\<appSettings>-Element</span><span class="sxs-lookup"><span data-stu-id="d2452-117">\<appSettings> element</span></span>

<span data-ttu-id="d2452-118">Dieses Element enthält **\<add>** **\<clear>** -,-und- **\<remove>** Tags zum Steuern von Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="d2452-118">This element contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="d2452-119">Es definiert ein optionales Attribut für **file**.</span><span class="sxs-lookup"><span data-stu-id="d2452-119">It defines an optional attribute for **file**.</span></span>

## <a name="add-element"></a><span data-ttu-id="d2452-120">\<add>-Element</span><span class="sxs-lookup"><span data-stu-id="d2452-120">\<add> element</span></span>

<span data-ttu-id="d2452-121">Fügt der Auflistung der Anwendungseinstellungen eine benutzerdefinierte Anwendungseinstellung als Name/Wertpaar hinzu.</span><span class="sxs-lookup"><span data-stu-id="d2452-121">Adds a custom application setting as a name/value pair to the application settings collection.</span></span> <span data-ttu-id="d2452-122">Es definiert Attribute für **key** und **value**</span><span class="sxs-lookup"><span data-stu-id="d2452-122">It defines attributes for **key** and **value**.</span></span>

## <a name="clear-element"></a><span data-ttu-id="d2452-123">\<clear>-Element</span><span class="sxs-lookup"><span data-stu-id="d2452-123">\<clear> element</span></span>

<span data-ttu-id="d2452-124">Entfernt alle Verweise auf geerbte benutzerdefinierte Anwendungseinstellungen und erlaubt nur die Verweise, die durch **\<add>** Elemente nach dem-Element hinzugefügt werden **\<clear>** .</span><span class="sxs-lookup"><span data-stu-id="d2452-124">Removes all references to inherited custom application settings and allows only the references that are added by **\<add>** elements following the **\<clear>** element.</span></span> <span data-ttu-id="d2452-125">Es definiert keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="d2452-125">It defines no attributes.</span></span>

## <a name="remove-element"></a><span data-ttu-id="d2452-126">\<remove>-Element</span><span class="sxs-lookup"><span data-stu-id="d2452-126">\<remove> element</span></span>

<span data-ttu-id="d2452-127">Entfernt einen Verweis auf eine geerbte benutzerdefinierte Anwendungseinstellung aus der Auflistung der Anwendungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="d2452-127">Removes a reference to an inherited custom application setting from the application settings collection.</span></span> <span data-ttu-id="d2452-128">Definiert ein Attribut für **key**.</span><span class="sxs-lookup"><span data-stu-id="d2452-128">It defines an attribute for **key**.</span></span>

## <a name="example"></a><span data-ttu-id="d2452-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d2452-129">Example</span></span>

<span data-ttu-id="d2452-130">Das folgende Beispiel zeigt eine externe Anwendungseinstellungsdatei (*custom.config*), die eine benutzerdefinierte Anwendungseinstellung definiert.</span><span class="sxs-lookup"><span data-stu-id="d2452-130">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="d2452-131">Das folgende Beispiel zeigt eine Anwendungskonfigurationsdatei, die die Einstellung in der externen Einstellungsdatei verarbeitet und eine eigene Anwendungseinstellung festlegt.</span><span class="sxs-lookup"><span data-stu-id="d2452-131">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="d2452-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d2452-132">See also</span></span>

- [<span data-ttu-id="d2452-133">Übersicht über Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="d2452-133">Application Settings Overview</span></span>](../../../winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="d2452-134">Architektur der Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="d2452-134">Application Settings Architecture</span></span>](../../../winforms/advanced/application-settings-architecture.md)
