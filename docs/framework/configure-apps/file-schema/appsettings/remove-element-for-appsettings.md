---
title: <remove>-Element für <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a0fcdb75aa733a9d7634ec1c3b31dcbbb87e090e
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088720"
---
# <a name="remove-element-for-appsettings"></a>\<> Element für \<appSettings entfernen >

Entfernt benutzerdefinierte Anwendungseinstellungen.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<entfernen >**

## <a name="syntax"></a>Syntax

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a>Attribut

|         | Beschreibung |
| ------- | ----------- |
| **key** | Erforderliches Attribut.<br><br>Gibt den Namen des zu entfernenden Schlüssels an. |

### <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [ **\<appSettings>** ](appsettings-element-for-configuration.md) | Dieses Thema enthält benutzerdefinierte Anwendungseinstellungen, z.B. Dateipfade, URLs für den XML-Webdienst oder andere benutzerdefinierte Konfigurationsinformationen für eine Anwendung. |

## <a name="child-elements"></a>Untergeordnete Elemente

Keiner

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie eine benutzerdefinierte Konfigurationseinstellung für `ApplicationName`entfernt wird:

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdatei Schema für die .NET Framework](../index.md)
