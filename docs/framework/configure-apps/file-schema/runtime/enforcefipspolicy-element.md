---
title: <enforceFIPSPolicy>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a4e5ba5ac1a5a3c08c351531efc84291925ba4b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267468"
---
# <a name="enforcefipspolicy-element"></a>\<EnforceFIPSPolicy >-Element
Gibt an, ob die Computerkonfigurationsanforderung durchgesetzt wird, dass kryptografische Algorithmen den Federal Information Processing Standards (FIPS) entsprechen müssen.  
  
 \<Configuration >-Element  
\<Common Language Runtime >-Element  
\<EnforceFIPSPolicy >-Element  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|enabled|Erforderliches Attribut.<br /><br /> Gibt an, ob die Erzwingung von computerkonfigurationsanforderung, dass kryptografische Algorithmen mit FIPS konform sein müssen.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`true`|Wenn Ihr Computer konfiguriert ist, um kryptografische Algorithmen, die mit FIPS konform sein müssen, wird die Anforderung erzwungen. Wenn eine Klasse einen Algorithmus implementiert, die nicht mit FIPS, die Konstruktoren kompatibel ist oder `Create` Methoden für diese Klasse die Ausnahmen auslösen, wenn sie auf diesem Computer ausgeführt werden. Dies ist die Standardeinstellung.|  
|`false`|Kryptografische Algorithmen, die von der Anwendung verwendet werden, sind nicht erforderlich, um die Kompatibilität mit FIPS, unabhängig von der Konfiguration des Computers.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Ab .NET Framework 2.0, wird die Erstellung von Klassen, die Kryptografiealgorithmen implementieren von der Konfiguration des Computers gesteuert. Wenn der Computer so konfiguriert ist, dass die Algorithmen mit FIPS kompatibel sein müssen und eine Klasse implementiert einen Algorithmus, der nicht mit FIPS kompatibel ist, löst jeder Versuch, eine Instanz dieser Klasse erstellt eine Ausnahme aus. Auslösen von Konstruktoren eine <xref:System.InvalidOperationException> Ausnahme und `Create` Methoden lösen eine <xref:System.Reflection.TargetInvocationException> Ausnahme mit einer internen <xref:System.InvalidOperationException> Ausnahme.  
  
 Wenn Ihre Anwendung ausgeführt, auf Computern wird, deren Konfigurationen erfordern, dass die Kompatibilität mit FIPS, und die Anwendung verwendet einen Algorithmus, der nicht mit FIPS kompatibel ist, können Sie dieses Element in der Konfigurationsdatei verwenden, um zu verhindern, dass die common Language Runtime (CLR) aus FIPS-Kompatibilität zu erzwingen. Dieses Element wurde in eingeführt, die [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie verhindern, dass die CLR FIPS-Kompatibilität zu erzwingen.  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch
- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Kryptografiemodell](../../../../../docs/standard/security/cryptography-model.md)
