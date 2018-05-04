---
title: '&lt;GcAllowVeryLargeObjects&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 750b0dbc925ec484dd80e1796ba991435e354709
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltgcallowverylargeobjectsgt-element"></a>&lt;GcAllowVeryLargeObjects&gt; Element
Ermöglicht auf 64-Bit-Plattformen Arrays mit einer Gesamtgröße von mehr als 2 Gigabyte (GB).  
  
 \<Konfiguration >-Element  
\<Common Language Runtime >-Element  
\<GcAllowVeryLargeObjects >-Element  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<gcAllowVeryLargeObjects    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob Arrays mit einer Gesamtgröße von mehr als 2 GB auf 64-Bit-Plattformen aktiviert werden.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Arrays mit einer Gesamtgröße von mehr als 2 GB sind nicht aktiviert. Dies ist die Standardeinstellung.|  
|`true`|Arrays mit einer Gesamtgröße von mehr als 2 GB werden auf 64-Bit-Plattformen aktiviert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Element in der Anwendungskonfigurationsdatei ermöglicht Arrays, die größer als 2 GB sind, es werden jedoch keine anderen Beschränkungen der Objekt- oder Arraygröße geändert:  
  
-   Die maximale Anzahl der Elemente in einem Array ist <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.  
  
-   Der maximale Index in jeder einzelnen Dimension ist 2.147.483.591 (0x7FFFFFC7) für Bytearrays und Arrays von Einzelbytestrukturen sowie 2.146.435.071 (0X7FEFFFFF) für andere Typen.  
  
-   Die maximale Größe für Zeichenfolgen und andere Nichtarrayobjekte ist unverändert.  
  
> [!CAUTION]
>  Bevor Sie diese Funktion aktivieren, stellen Sie sicher, dass Ihre Anwendung keinen unsicheren Code enthält, der davon ausgeht, dass alle Arrays weniger als 2 GB groß sind. Beispielsweise könnte unsicherer Code, der Arrays als Puffer verwendet, für Pufferüberläufe anfällig sein, wenn dieser ausgehend davon geschrieben wurde, dass Arrays 2 GB nicht überschreiten.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie diese Funktion für eine Anwendung aktiviert wird.  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
