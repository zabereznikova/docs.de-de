---
title: gcAllowVeryLargeObjects-Element
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: 1e54b0780ffb5bbe81ab1be2b376ff7a038ee05c
ms.sourcegitcommit: 0273f8845eb1ea8de64086bef2271b4f22182c91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2021
ms.locfileid: "98058128"
---
# <a name="gcallowverylargeobjects-element"></a>\<gcAllowVeryLargeObjects>-Element

Ermöglicht auf 64-Bit-Plattformen Arrays mit einer Gesamtgröße von mehr als 2 Gigabyte (GB).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<gcAllowVeryLargeObjects enabled="true|false" />  
```  
  
## <a name="attributes"></a>Attribute
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob Arrays mit einer Gesamtgröße von mehr als 2 GB auf 64-Bit-Plattformen aktiviert werden.|  
  
### <a name="enabled-attribute"></a>aktiviertes Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|`false`|Arrays mit einer Gesamtgröße von mehr als 2 GB sind nicht aktiviert. Dies ist die Standardoption.|  
|`true`|Arrays mit einer Gesamtgröße von mehr als 2 GB werden auf 64-Bit-Plattformen aktiviert.|  
  
## <a name="child-elements"></a>Untergeordnete Elemente  

Keine  
  
## <a name="parent-elements"></a>Übergeordnete Elemente
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Bemerkungen  

 Dieses Element in der Anwendungskonfigurationsdatei ermöglicht Arrays, die größer als 2 GB sind, es werden jedoch keine anderen Beschränkungen der Objekt- oder Arraygröße geändert:  
  
- Die maximale Anzahl der Elemente in einem Array ist <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.  
  
- Die maximale Größe in einer einzelnen Dimension beträgt 2.147.483.591 (0x7fffffc7) für Byte Arrays und Arrays von Einzel Byte Strukturen und 2.146.435.071 (0x7fefffff) für Arrays, die andere Typen enthalten.  
  
- Die maximale Größe für Zeichenfolgen und andere Nichtarrayobjekte ist unverändert.  
  
> [!CAUTION]
> Bevor Sie diese Funktion aktivieren, stellen Sie sicher, dass Ihre Anwendung keinen unsicheren Code enthält, der davon ausgeht, dass alle Arrays weniger als 2 GB groß sind. Beispielsweise ist unsicherer Code, der Arrays als Puffer verwendet, möglicherweise anfällig für Pufferüberläufe, wenn er unter der Annahme geschrieben wird, dass Arrays 2 GB nicht überschreiten.  
  
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

.NET Framework 4,5 und höhere Versionen

## <a name="see-also"></a>Weitere Informationen

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
