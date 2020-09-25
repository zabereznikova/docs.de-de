---
title: <webProxyScript>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webProxyScript
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/webProxyScript
helpviewer_keywords:
- <webProxyScript> element
- webProxyScript element
ms.assetid: a13c26db-6218-4af3-9696-38f24b23bfac
ms.openlocfilehash: e36b470b1ec348085b13a58630b0ac6833e43946
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178306"
---
# <a name="webproxyscript-element-network-settings"></a>\<webProxyScript>-Element (Netzwerkeinstellungen)

Konfiguriert die Merkmale des Skripts, das zum Ermitteln von Webproxys verwendet wird.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webProxyScript>**

## <a name="syntax"></a>Syntax  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`downloadTimeout`|Gibt die maximale Zeit für das Herunterladen des Skripts in Stunden, Minuten und Sekunden an. Der Standardwert ist eine Minute.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[settings](settings-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.|  
  
## <a name="remarks"></a>Bemerkungen  
  
## <a name="configuration-files"></a>Konfigurationsdateien  

 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Network Settings Schema (Schema für Netzwerkeinstellungen)](index.md)
