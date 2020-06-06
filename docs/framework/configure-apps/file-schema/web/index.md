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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088793"
---
# <a name="web-settings-schema"></a><span data-ttu-id="69256-102">Webeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="69256-102">Web Settings Schema</span></span>
<span data-ttu-id="69256-103">Webeinstellungen geben die ASP.NET-Einstellungen auf CPU- und Ausführungsebene an, die für das prozessübergreifende Verhalten gelten, das von der ASP.NET-Hostebene verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="69256-103">Web settings specify CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span> <span data-ttu-id="69256-104">Diese Einstellungen unterscheiden sich von den Anwendungseinstellungen für den Domänentyp, die in der Web.config-Datei der ASP.NET-Anwendung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="69256-104">These settings differ from application domain-type settings that are specified in the Web.config file of an ASP.NET application.</span></span>  
  
<span data-ttu-id="69256-105">Die Webeinstellungen sind in den Aspnet.config-Dateien enthalten, die sich in den Installationsordnern der .NET Framework-Version befinden.</span><span class="sxs-lookup"><span data-stu-id="69256-105">Web settings are contained in Aspnet.config files, which are located in the installation folders for versions of the .NET Framework.</span></span> <span data-ttu-id="69256-106">Beispielsweise befindet sich die ASPNET. config-Datei für .NET Framework 2,0 im folgenden Ordner:</span><span class="sxs-lookup"><span data-stu-id="69256-106">For example, the Aspnet.config file for .NET Framework 2.0 is in the following folder:</span></span>  
  
`C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
<span data-ttu-id="69256-107">Die Webeinstellungen werden nicht in anderen Konfigurationsdateien wie „machine.config“, der Stammversion von „Web.config“ oder „Web.config“ auf Anwendungsebene verwendet.</span><span class="sxs-lookup"><span data-stu-id="69256-107">Web settings are not used in any other configuration files such as the machine.config file, the root Web.config, or application-level Web.config files.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<applicationPool>**](applicationpool-element-web-settings.md)

|<span data-ttu-id="69256-108">Element</span><span class="sxs-lookup"><span data-stu-id="69256-108">Element</span></span>|<span data-ttu-id="69256-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="69256-109">Description</span></span>|  
|-------------|-----------------|  
|[\<system.web>](system-web-element-web-settings.md)|<span data-ttu-id="69256-110">Enthält die Informationen, die die ASP.NET-Hostebene verwendet.</span><span class="sxs-lookup"><span data-stu-id="69256-110">Contains information that the ASP.NET hosting layer uses.</span></span>|  
|[\<applicationPool>](applicationpool-element-web-settings.md)|<span data-ttu-id="69256-111">Gibt die ASP.NET-Einstellungen auf CPU- und Ausführungsebene an, die für das prozessübergreifende Verhalten gelten, das von der ASP.NET-Hostebene verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="69256-111">Specifies CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="69256-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69256-112">See also</span></span>

- [<span data-ttu-id="69256-113">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="69256-113">Configuration File Schema</span></span>](../index.md)
