---
title: <clear>-Element für <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
ms.openlocfilehash: 266d32ccb8b322f0472e0f552f9c0fc877c9a78e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214808"
---
# <a name="clear-element-for-appsettings"></a>\<clear>-Element für \<appSettings>

Löscht benutzerdefinierte Anwendungseinstellungen.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a>Syntax

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a>Attribute

Keine

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | Enthält benutzerdefinierte Anwendungseinstellungen, z. b. Dateipfade, XML-Webdienst-URLs oder andere benutzerdefinierte Konfigurationsinformationen für die Anwendung. |

## <a name="child-elements"></a>Untergeordnete Elemente

Keine

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie benutzerdefinierte Konfigurationseinstellungen gelöscht werden:

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a>Weitere Informationen

- [Konfigurationsdatei Schema für die .NET Framework](../index.md)
