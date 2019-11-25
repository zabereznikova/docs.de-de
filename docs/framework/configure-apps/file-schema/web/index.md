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
ms.openlocfilehash: 030841330ff37cddb0c9e3e466a55a4be098e784
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088793"
---
# <a name="web-settings-schema"></a>Webeinstellungsschema
Webeinstellungen geben die ASP.NET-Einstellungen auf CPU- und Ausführungsebene an, die für das prozessübergreifende Verhalten gelten, das von der ASP.NET-Hostebene verwaltet wird. Diese Einstellungen unterscheiden sich von den Anwendungseinstellungen für den Domänentyp, die in der Web.config-Datei der ASP.NET-Anwendung angegeben werden.  
  
Die Webeinstellungen sind in den Aspnet.config-Dateien enthalten, die sich in den Installationsordnern der .NET Framework-Version befinden. Beispielsweise befindet sich die ASPNET. config-Datei für .NET Framework 2,0 im folgenden Ordner:  
  
`C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
Die Webeinstellungen werden nicht in anderen Konfigurationsdateien wie „machine.config“, der Stammversion von „Web.config“ oder „Web.config“ auf Anwendungsebene verwendet.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. Web >** ](system-web-element-web-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ApplicationPool >** ](applicationpool-element-web-settings.md)

|Element|Beschreibung|  
|-------------|-----------------|  
|[\<system.web>](system-web-element-web-settings.md)|Enthält die Informationen, die die ASP.NET-Hostebene verwendet.|  
|[\<applicationPool>](applicationpool-element-web-settings.md)|Gibt die ASP.NET-Einstellungen auf CPU- und Ausführungsebene an, die für das prozessübergreifende Verhalten gelten, das von der ASP.NET-Hostebene verwaltet wird.|  
  
## <a name="see-also"></a>Siehe auch

- [Konfigurationsdateischema](../index.md)
