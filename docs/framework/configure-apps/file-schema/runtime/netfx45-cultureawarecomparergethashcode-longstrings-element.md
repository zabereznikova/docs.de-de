---
title: <NetFx45_CultureAwareComparerGetHashCode_LongStrings>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- NetFx45_CultureAwareComparerGetHashCode_LongStrings element
- <NetFx45_CultureAwareComparerGetHashCode_LongStrings> element
- GetHashCode method
- hash codes, calculating
ms.assetid: 3a5f38d1-ebc8-44de-aaeb-2929f6e6b48f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 854b58a1f57008326874b5e5ee60cc9e6297960b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085908"
---
# <a name="netfx45cultureawarecomparergethashcodelongstrings-element"></a>\<NetFx45_CultureAwareComparerGetHashCode_LongStrings > Element
Gibt an, ob die Laufzeit eine feste Menge an Arbeitsspeicher zum Berechnen von Hashcodes für die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> -Methode verwendet.  
  
 \<configuration>  
\<runtime>  
<NetFx45_CultureAwareComparerGetHashCode_LongStrings>  
  
## <a name="syntax"></a>Syntax  
  
```xml
<NetFx45_CultureAwareComparerGetHashCode_LongStrings enabled="0|1">  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Common Language Runtime eine feste Menge an Arbeitsspeicher beim Berechnen von Hashcodes belegt.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|0|Die Common Language Runtime belegt eine variable Menge an Arbeitsspeicher für die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> -Methode, um Hashcodes zu berechnen. Dies ist die Standardeinstellung.|  
|1|Die Common Language Runtime belegt eine feste Menge an Arbeitsspeicher für die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> -Methode, um Hashcodes zu berechnen.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig belegt die Common Language Runtime eine variable Menge an Arbeitsspeicher für die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> -Methode, und <xref:System.ArgumentException> kann ausgelöst werden, wenn die Methode versucht, den Hashcode sehr großer Zeichenfolgen zu berechnen (über mehrere Millionen Zeichen lang). Indem Sie dieses Element einer Anwendungskonfigurationsdatei hinzufügen und das `enabled` -Attribut auf "1 " festlegen, können Sie angeben, dass die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> -Methode einen alternativen Algorithmus verwendet, der eine feste Menge an Arbeitsspeicher für die Berechnung von Hashcodes belegt.  
  
> [!IMPORTANT]
>  Das `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` -Element wird nicht in [!INCLUDE[win8](../../../../../includes/win8-md.md)] und höheren Versionen verwendet.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
