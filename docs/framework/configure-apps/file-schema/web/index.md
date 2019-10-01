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
ms.openlocfilehash: 71b9e46a8c2d60c853af63ee78e2ed5dbe6e98f4
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699138"
---
# <a name="web-settings-schema"></a><span data-ttu-id="b5c0e-102">Webeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="b5c0e-102">Web Settings Schema</span></span>
<span data-ttu-id="b5c0e-103">Webeinstellungen geben die ASP.NET-Einstellungen auf CPU- und Ausführungsebene an, die für das prozessübergreifende Verhalten gelten, das von der ASP.NET-Hostebene verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="b5c0e-103">Web settings specify CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span> <span data-ttu-id="b5c0e-104">Diese Einstellungen unterscheiden sich von den Anwendungseinstellungen für den Domänentyp, die in der Web.config-Datei der ASP.NET-Anwendung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b5c0e-104">These settings differ from application domain-type settings that are specified in the Web.config file of an ASP.NET application.</span></span>  
  
<span data-ttu-id="b5c0e-105">Die Webeinstellungen sind in den Aspnet.config-Dateien enthalten, die sich in den Installationsordnern der .NET Framework-Version befinden.</span><span class="sxs-lookup"><span data-stu-id="b5c0e-105">Web settings are contained in Aspnet.config files, which are located in the installation folders for versions of the .NET Framework.</span></span> <span data-ttu-id="b5c0e-106">Beispielsweise befindet sich die ASPNET. config-Datei für .NET Framework 2,0 im folgenden Ordner:</span><span class="sxs-lookup"><span data-stu-id="b5c0e-106">For example, the Aspnet.config file for .NET Framework 2.0 is in the following folder:</span></span>  
  
`C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
<span data-ttu-id="b5c0e-107">Die Webeinstellungen werden nicht in anderen Konfigurationsdateien wie „machine.config“, der Stammversion von „Web.config“ oder „Web.config“ auf Anwendungsebene verwendet.</span><span class="sxs-lookup"><span data-stu-id="b5c0e-107">Web settings are not used in any other configuration files such as the machine.config file, the root Web.config, or application-level Web.config files.</span></span>  
  
[<span data-ttu-id="b5c0e-108"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="b5c0e-108">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="b5c0e-109">&nbsp; @ no__t-1[ **@no__t -4system. Web >** ](system-web-element-web-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b5c0e-109">&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)</span></span>  
<span data-ttu-id="b5c0e-110">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<applicationpool >** ](applicationpool-element-web-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b5c0e-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<applicationPool>**](applicationpool-element-web-settings.md)</span></span>  
  
|<span data-ttu-id="b5c0e-111">Element</span><span class="sxs-lookup"><span data-stu-id="b5c0e-111">Element</span></span>|<span data-ttu-id="b5c0e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5c0e-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5c0e-113">\<system.web></span><span class="sxs-lookup"><span data-stu-id="b5c0e-113">\<system.web></span></span>](system-web-element-web-settings.md)|<span data-ttu-id="b5c0e-114">Enthält die Informationen, die die ASP.NET-Hostebene verwendet.</span><span class="sxs-lookup"><span data-stu-id="b5c0e-114">Contains information that the ASP.NET hosting layer uses.</span></span>|  
|[<span data-ttu-id="b5c0e-115">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="b5c0e-115">\<applicationPool></span></span>](applicationpool-element-web-settings.md)|<span data-ttu-id="b5c0e-116">Gibt die ASP.NET-Einstellungen auf CPU- und Ausführungsebene an, die für das prozessübergreifende Verhalten gelten, das von der ASP.NET-Hostebene verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="b5c0e-116">Specifies CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b5c0e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5c0e-117">See also</span></span>

- [<span data-ttu-id="b5c0e-118">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="b5c0e-118">Configuration File Schema</span></span>](../index.md)
