---
title: '&lt;NetFx45_CultureAwareComparerGetHashCode_LongStrings&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- NetFx45_CultureAwareComparerGetHashCode_LongStrings element
- <NetFx45_CultureAwareComparerGetHashCode_LongStrings> element
- GetHashCode method
- hash codes, calculating
ms.assetid: 3a5f38d1-ebc8-44de-aaeb-2929f6e6b48f
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e21377b28adb7668108064b770c2c5e0f9fee8f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltnetfx45cultureawarecomparergethashcodelongstringsgt-element"></a>&lt;NetFx45_CultureAwareComparerGetHashCode_LongStrings&gt; Element
Gibt an, ob die Laufzeit eine feste Menge an Arbeitsspeicher zum Berechnen von Hashcodes für die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>-Methode verwendet.  
  
 \<configuration>  
\<Common Language Runtime >  
< NetFx45_CultureAwareComparerGetHashCode_LongStrings >  
  
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
|0|Die Common Language Runtime belegt eine variable Menge an Arbeitsspeicher für die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>-Methode, um Hashcodes zu berechnen. Dies ist die Standardeinstellung.|  
|1|Die Common Language Runtime belegt eine feste Menge an Arbeitsspeicher für die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>-Methode, um Hashcodes zu berechnen.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig belegt die Common Language Runtime eine variable Menge an Arbeitsspeicher für die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>-Methode, und <xref:System.ArgumentException> kann ausgelöst werden, wenn die Methode versucht, den Hashcode sehr großer Zeichenfolgen zu berechnen (über mehrere Millionen Zeichen lang). Indem Sie dieses Element einer Anwendungskonfigurationsdatei hinzufügen und das `enabled`-Attribut auf "1 " festlegen, können Sie angeben, dass die <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>-Methode einen alternativen Algorithmus verwendet, der eine feste Menge an Arbeitsspeicher für die Berechnung von Hashcodes belegt.  
  
> [!IMPORTANT]
>  Das `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` -Element wird nicht in [!INCLUDE[win8](../../../../../includes/win8-md.md)] und höheren Versionen verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
