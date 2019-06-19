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
ms.openlocfilehash: 0fbc28bb7b871cc245d0fe477ea8e15c147549bb
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2019
ms.locfileid: "67170020"
---
# <a name="web-settings-schema"></a><span data-ttu-id="b5e77-102">Webeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="b5e77-102">Web Settings Schema</span></span>
<span data-ttu-id="b5e77-103">Webeinstellungen geben die ASP.NET-Einstellungen auf CPU- und Ausführungsebene an, die für das prozessübergreifende Verhalten gelten, das von der ASP.NET-Hostebene verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="b5e77-103">Web settings specify CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span> <span data-ttu-id="b5e77-104">Diese Einstellungen unterscheiden sich von den Anwendungseinstellungen für den Domänentyp, die in der Web.config-Datei der ASP.NET-Anwendung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b5e77-104">These settings differ from application domain-type settings that are specified in the Web.config file of an ASP.NET application.</span></span>  
  
 <span data-ttu-id="b5e77-105">Die Webeinstellungen sind in den Aspnet.config-Dateien enthalten, die sich in den Installationsordnern der .NET Framework-Version befinden.</span><span class="sxs-lookup"><span data-stu-id="b5e77-105">Web settings are contained in Aspnet.config files, which are located in the installation folders for versions of the .NET Framework.</span></span> <span data-ttu-id="b5e77-106">Beispielsweise ist die Datei "Aspnet.config" für .NET Framework 2.0 im folgenden Ordner:</span><span class="sxs-lookup"><span data-stu-id="b5e77-106">For example, the Aspnet.config file for .NET Framework 2.0 is in the following folder:</span></span>  
  
 `C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
 <span data-ttu-id="b5e77-107">Die Webeinstellungen werden nicht in anderen Konfigurationsdateien wie „machine.config“, der Stammversion von „Web.config“ oder „Web.config“ auf Anwendungsebene verwendet.</span><span class="sxs-lookup"><span data-stu-id="b5e77-107">Web settings are not used in any other configuration files such as the machine.config file, the root Web.config, or application-level Web.config files.</span></span>  
  
 [<span data-ttu-id="b5e77-108">\<configuration> Element</span><span class="sxs-lookup"><span data-stu-id="b5e77-108">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="b5e77-109">\<system.web>-Element (Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b5e77-109">\<system.web> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)  
  
 [<span data-ttu-id="b5e77-110">\<applicationPool>-Element (Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b5e77-110">\<applicationPool> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)  
  
|<span data-ttu-id="b5e77-111">Element</span><span class="sxs-lookup"><span data-stu-id="b5e77-111">Element</span></span>|<span data-ttu-id="b5e77-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5e77-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5e77-113">\<system.web></span><span class="sxs-lookup"><span data-stu-id="b5e77-113">\<system.web></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|<span data-ttu-id="b5e77-114">Enthält die Informationen, die die ASP.NET-Hostebene verwendet.</span><span class="sxs-lookup"><span data-stu-id="b5e77-114">Contains information that the ASP.NET hosting layer uses.</span></span>|  
|[<span data-ttu-id="b5e77-115">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="b5e77-115">\<applicationPool></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|<span data-ttu-id="b5e77-116">Gibt die ASP.NET-Einstellungen auf CPU- und Ausführungsebene an, die für das prozessübergreifende Verhalten gelten, das von der ASP.NET-Hostebene verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="b5e77-116">Specifies CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b5e77-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5e77-117">See also</span></span>

- [<span data-ttu-id="b5e77-118">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="b5e77-118">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
