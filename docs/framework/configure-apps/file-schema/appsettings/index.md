---
title: Schema für App-Einstellungen
ms.date: 05/01/2017
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
ms.openlocfilehash: a67689bd9757f7586881fd910ef6103b1dffeab8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550448"
---
# <a name="app-settings-schema"></a>Schema für App-Einstellungen

Dieses Thema enthält benutzerdefinierte Anwendungseinstellungen, z.B. Dateipfade, URLs für den XML-Webdienst oder andere benutzerdefinierte Konfigurationsinformationen für eine Anwendung.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](clear-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](remove-element-for-appsettings.md)

| Element | BESCHREIBUNG |
| ------- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | Enthält **\<add>** **\<clear>** -,-und- **\<remove>** Tags zum Steuern von Anwendungseinstellungen. Verfügt über ein optionales **file**-Attribut. |
| [**\<add>**](add-element-for-appsettings.md) | Definiert eine Einstellung. Untergeordnetes Element von **\<appSettings>** . Erfordert **key**- und **value**-Attribute. |
| [**\<clear>**](clear-element-for-appsettings.md) | Löscht alle Einstellungen. Untergeordnetes Element von **\<appSettings>** . Besitzt keine Attribute. |
| [**\<remove>**](remove-element-for-appsettings.md) | Entfernt eine Einstellung. Untergeordnetes Element von **\<appSettings>** . Erfordert ein **key**-Attribut. |

## <a name="appsettings-element"></a>\<appSettings>-Element

Dieses Element enthält **\<add>** **\<clear>** -,-und- **\<remove>** Tags zum Steuern von Anwendungseinstellungen. Es definiert ein optionales Attribut für **file**.

## <a name="add-element"></a>\<add>-Element

Fügt der Auflistung der Anwendungseinstellungen eine benutzerdefinierte Anwendungseinstellung als Name/Wertpaar hinzu. Es definiert Attribute für **key** und **value**

## <a name="clear-element"></a>\<clear>-Element

Entfernt alle Verweise auf geerbte benutzerdefinierte Anwendungseinstellungen und erlaubt nur die Verweise, die durch **\<add>** Elemente nach dem-Element hinzugefügt werden **\<clear>** . Es definiert keine Attribute.

## <a name="remove-element"></a>\<remove>-Element

Entfernt einen Verweis auf eine geerbte benutzerdefinierte Anwendungseinstellung aus der Auflistung der Anwendungseinstellungen. Definiert ein Attribut für **key**.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt eine externe Anwendungseinstellungsdatei (*custom.config*), die eine benutzerdefinierte Anwendungseinstellung definiert.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

Das folgende Beispiel zeigt eine Anwendungskonfigurationsdatei, die die Einstellung in der externen Einstellungsdatei verarbeitet und eine eigene Anwendungseinstellung festlegt.

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a>Siehe auch

- [Übersicht über Anwendungseinstellungen](/dotnet/desktop/winforms/advanced/application-settings-overview)
- [Architektur der Anwendungseinstellungen](/dotnet/desktop/winforms/advanced/application-settings-architecture)
