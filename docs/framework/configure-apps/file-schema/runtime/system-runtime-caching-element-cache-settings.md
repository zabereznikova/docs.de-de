---
title: <system.runtime.caching>-Element (Cacheeinstellungen)
ms.date: 03/30/2017
helpviewer_keywords:
- <system.runtime.caching> element
- caching [.NET Framework], configuration
- system.runtime.caching element
ms.assetid: 9b44daee-874a-4bd1-954e-83bf53565590
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbb977e05fa54b726b0cd584d287dc00c8ced995
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423252"
---
# <a name="systemruntimecaching-element-cache-settings"></a>\<System.Runtime.Caching >-Element (Cacheeinstellungen)

Stellt die Konfiguration für die standardmäßige speicherinterne Implementierung <xref:System.Runtime.Caching.ObjectCache> über den `memoryCache` -Eintrag in der Konfigurationsdatei bereit.  
  
 \<configuration>  
\<system.runtime.caching>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.runtime.caching >  
   <!-- child elements -->  
</system.runtime.caching >  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute

`None`  

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|  
|-------------|-----------------|  
|[\<memoryCache>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|Definiert ein Element, das für die Konfiguration des Cache verwendet wird, der auf der <xref:System.Runtime.Caching.MemoryCache> -Klasse basiert.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Gibt das Stammelement in jeder Konfigurationsdatei an, die von der common Language Runtime und .NET Framework-Anwendungen verwendet wird.|  
  
## <a name="remarks"></a>Hinweise

Die Klassen in diesem Namespace bieten eine Möglichkeit, Zwischenspeicherfunktionen wie jene in ASP.NET zu verwenden, jedoch ohne eine Abhängigkeit von der `System.Web` -Assembly. Weitere Informationen finden Sie unter [Caching in .NET Framework Applications](../../../../../docs/framework/performance/caching-in-net-framework-applications.md).  
  
> [!NOTE]
>  Die ausgabezwischenspeicherung und Ihre Typen in der <xref:System.Runtime.Caching> Namespace sind neu in .NET Framework 4.  
  
## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt die Konfiguration eines Cache, der auf der <xref:System.Runtime.Caching.MemoryCache> -Klasse basiert. Das Beispiel veranschaulicht, wie eine Instanz des `namedCaches` -Eintrags für den Arbeitsspeichercache konfiguriert wird. Der Name des Caches auf dem Standard-Cache-Eintragsnamen festgelegt ist, durch Festlegen der `name` -Attribut auf "Default".  
  
Das `cacheMemoryLimitMegabytes` - und das `physicalMemoryPercentage` -Attribut werden auf 0 (Null) festgelegt. Werden diese Attribute auf 0 (Null) festgelegt, wird die <xref:System.Runtime.Caching.MemoryCache> -Heuristik zum automatischen Anpassen als Standard verwendet. Die Cacheimplementierung sollte die aktuelle Auslastung des Arbeitsspeichers alle zwei Minuten mit den absoluten und prozentualen Speichergrenzen vergleichen.  
  
```xml  
<configuration>  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [\<MemoryCache >-Element (Cacheeinstellungen)](memorycache-element-cache-settings.md)
