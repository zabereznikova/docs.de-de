---
title: <system.web>-Element (Webeinstellungen)
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: b9a43c5f5141e364ab9aac1cfdff577a8fb8a161
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2019
ms.locfileid: "67486680"
---
# <a name="systemweb-element-web-settings"></a>\<System.Web >-Element (Webeinstellungen)
Enthält Informationen dazu, wie die hostingebene von ASP.NET prozessübergreifende Verhalten verwaltet.  
  
 \<configuration>  
\<System.Web >-Element (Webeinstellungen)  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<applicationPool>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|Gibt Konfigurationseinstellungen für die IIS-Anwendungspools in eine Datei "aspnet.config" an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Gibt das Stammelement in jeder Konfigurationsdatei an, die von der common Language Runtime und .NET Framework-Anwendungen verwendet wird.|  
  
## <a name="remarks"></a>Hinweise  
 Die `system.web` Element und dessen untergeordnete `applicationPool` Element wurden hinzugefügt, um .NET Framework ab .NET Framework 3.5 SP1. Wenn Sie IIS 7.0 oder höher im integrierten Modus ausführen, Sie können diese Kombination Element konfigurieren, wie sie Anforderungen Warteschlange, wenn ASP.NET in einem IIS-Anwendungspool gehostet wird und wie ASP.NET Threads verwaltet. Wenn Sie IIS 7.0 oder höher im klassischen Bereitstellungsmodell oder ISAPI-Modus ausführen, werden diese Einstellungen ignoriert.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie ASP.NET prozessübergreifende Verhalten in der Datei "aspnet.config" konfigurieren, wenn ASP.NET in einem IIS-Anwendungspool gehostet wird. Im Beispiel wird davon ausgegangen, dass IIS, im integrierten ausgeführt wird Modus und die Anwendung .NET Framework 3.5 SP1 oder höher verwendet wird. Dieses Verhalten tritt nicht in Versionen von .NET Framework-Versionen als .NET Framework 3.5 SP1. Die Werte im Beispiel werden die Standardwerte.  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool   
        maxConcurrentRequestsPerCPU="5000"   
        maxConcurrentThreadsPerCPU="0"   
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a>Elementinformationen  
  
|||  
|-|-|  
|Namespace||  
|Schemaname||  
|Validierungsdatei||  
|Leer kann sein||  
  
## <a name="see-also"></a>Siehe auch

- [\<applicationPool>-Element (Webeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)
