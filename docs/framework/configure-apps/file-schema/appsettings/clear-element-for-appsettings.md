---
title: <clear>-Element für <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 5d4d96143dbd1db440de2247a7dc2f0c66f20403
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301299"
---
# <a name="clear-element-for-appsettings"></a>\<clear >-Element für \<AppSettings >

Löscht die benutzerdefinierte Anwendungseinstellungen.

[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[ **\<appSettings>** ](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<clear>**

## <a name="syntax"></a>Syntax

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a>Attribute

Keiner

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [ **\<appSettings>** ](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | Enthält benutzerdefinierte anwendungseinstellung, z.B. Dateipfade, URLs für den XML-Webdienst oder andere benutzerdefinierte Anwendung-Konfigurationsinformationen. |

## <a name="child-elements"></a>Untergeordnete Elemente

Keiner

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie benutzerdefinierte Konfigurationseinstellungen deaktivieren:

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdateischema für .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
