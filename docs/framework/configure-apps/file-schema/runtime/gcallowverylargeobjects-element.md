---
title: <gcAllowVeryLargeObjects>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: 8b2f39a0867228474afdee788474fda11f14ca82
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154126"
---
# <a name="gcallowverylargeobjects-element"></a>\<gcAllowVeryLargeObjects> Element
Ermöglicht auf 64-Bit-Plattformen Arrays mit einer Gesamtgröße von mehr als 2 Gigabyte (GB).  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<gcAllowVeryLargeObjects
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob Arrays mit einer Gesamtgröße von mehr als 2 GB auf 64-Bit-Plattformen aktiviert werden.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|value|Beschreibung|  
|-----------|-----------------|  
|`false`|Arrays mit einer Gesamtgröße von mehr als 2 GB sind nicht aktiviert. Dies ist die Standardoption.|  
|`true`|Arrays mit einer Gesamtgröße von mehr als 2 GB werden auf 64-Bit-Plattformen aktiviert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Bemerkungen  
 Dieses Element in der Anwendungskonfigurationsdatei ermöglicht Arrays, die größer als 2 GB sind, es werden jedoch keine anderen Beschränkungen der Objekt- oder Arraygröße geändert:  
  
- Die maximale Anzahl der Elemente in einem Array ist <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.  
  
- Der maximale Index in jeder einzelnen Dimension ist 2.147.483.591 (0x7FFFFFC7) für Bytearrays und Arrays von Einzelbytestrukturen sowie 2.146.435.071 (0X7FEFFFFF) für andere Typen.  
  
- Die maximale Größe für Zeichenfolgen und andere Nichtarrayobjekte ist unverändert.  
  
> [!CAUTION]
> Bevor Sie diese Funktion aktivieren, stellen Sie sicher, dass Ihre Anwendung keinen unsicheren Code enthält, der davon ausgeht, dass alle Arrays weniger als 2 GB groß sind. Beispielsweise könnte unsicherer Code, der Arrays als Puffer verwendet, für Pufferüberläufe anfällig sein, wenn dieser ausgehend davon geschrieben wurde, dass Arrays 2 GB nicht überschreiten.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie diese Funktion für eine Anwendung aktiviert wird.  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a>Unterstützt in

.NET Framework 4.5 und neuere Versionen

## <a name="see-also"></a>Weitere Informationen

- [Schema für Laufzeiteinstellungen](index.md)
- [Schema der Konfigurationsdatei](../index.md)
