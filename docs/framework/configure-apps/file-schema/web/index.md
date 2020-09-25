---
title: Webeinstellungsschema
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- ASP.NET configuration system, Web settings schema
- schema Web settings
- Web settings, schema [ASP.NET]
- configuration files [ASP.NET]
- configuration schema [.NET Framework], Web settings
ms.assetid: ae1ac356-267d-4753-8d7a-7a04eb45a9be
ms.openlocfilehash: c3ac9b42aeff3f7b26f0b36480bc75ceda39e7e6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185599"
---
# <a name="web-settings-schema"></a>Webeinstellungsschema

Webeinstellungen geben die ASP.NET-Einstellungen auf CPU- und Ausführungsebene an, die für das prozessübergreifende Verhalten gelten, das von der ASP.NET-Hostebene verwaltet wird. Diese Einstellungen unterscheiden sich von den Anwendungseinstellungen für den Domänentyp, die in der Web.config-Datei der ASP.NET-Anwendung angegeben werden.  
  
Die Webeinstellungen sind in den Aspnet.config-Dateien enthalten, die sich in den Installationsordnern der .NET Framework-Version befinden. Beispielsweise befindet sich die Aspnet.config-Datei für .NET Framework 2,0 im folgenden Ordner:  
  
`C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
Die Webeinstellungen werden nicht in anderen Konfigurationsdateien wie „machine.config“, der Stammversion von „Web.config“ oder „Web.config“ auf Anwendungsebene verwendet.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<applicationPool>**](applicationpool-element-web-settings.md)

|Element|Beschreibung|  
|-------------|-----------------|  
|[\<system.web>](system-web-element-web-settings.md)|Enthält die Informationen, die die ASP.NET-Hostebene verwendet.|  
|[\<applicationPool>](applicationpool-element-web-settings.md)|Gibt die ASP.NET-Einstellungen auf CPU- und Ausführungsebene an, die für das prozessübergreifende Verhalten gelten, das von der ASP.NET-Hostebene verwaltet wird.|  
  
## <a name="see-also"></a>Siehe auch

- [Konfigurationsdateischema](../index.md)
