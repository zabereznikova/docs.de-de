---
title: '&lt;EnforceFIPSPolicy&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9040bf2548964cf6df5f4fd87ee9f6d979c7df1e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746214"
---
# <a name="ltenforcefipspolicygt-element"></a>&lt;EnforceFIPSPolicy&gt; Element
Gibt an, ob die Computerkonfigurationsanforderung durchgesetzt wird, dass kryptografische Algorithmen den Federal Information Processing Standards (FIPS) entsprechen müssen.  
  
 \<Konfiguration >-Element  
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
|enabled|Erforderliches Attribut.<br /><br /> Gibt an, ob die Erzwingung von einem Computer erforderlich, dass kryptografische Algorithmen mit FIPS kompatibel sein müssen.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`true`|Wenn Ihr Computer konfiguriert ist, um kryptografische Algorithmen FIPS-konform sein müssen, wird diese Anforderung erzwungen. Wenn eine Klasse einen Algorithmus implementiert, der nicht mit FIPS, die Konstruktoren kompatibel ist oder `Create` Methoden für diese Klasse Ausnahmen auslösen, wenn sie auf diesem Computer ausgeführt werden. Dies ist die Standardeinstellung.|  
|`false`|Kryptografische Algorithmen, die von der Anwendung verwendet werden sind nicht kompatibel mit FIPS, unabhängig von der Konfiguration des Computers ist erforderlich.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Beginnend mit .NET Framework 2.0, wird die Erstellung von Klassen, die Kryptografiealgorithmen implementieren von der Konfiguration des Computers gesteuert. Wenn der Computer so konfiguriert ist, dass Algorithmen mit FIPS kompatibel sein müssen, und eine Klasse implementiert einen Algorithmus, der nicht mit FIPS kompatibel ist, löst jeder Versuch, eine Instanz dieser Klasse erstellen eine Ausnahme aus. Konstruktoren Auslösen einer <xref:System.InvalidOperationException> Ausnahme und `Create` Methoden lösen eine <xref:System.Reflection.TargetInvocationException> Ausnahme mit einer internen <xref:System.InvalidOperationException> Ausnahme.  
  
 Wenn die Anwendung ausgeführt, auf Computern wird, deren Konfigurationen mit FIPS-Konformität erforderlich ist, und Ihre Anwendung verwendet einen Algorithmus, der nicht mit FIPS kompatibel ist, können dieses Element in der Konfigurationsdatei Sie zu verhindern, dass die common Language Runtime (CLR) Erzwingen der FIPS-Kompatibilität. Dieses Element wurde in eingeführt, die [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie zu verhindern, dass die CLR Erzwingen der FIPS-Kompatibilität.  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Kryptografiemodell](../../../../../docs/standard/security/cryptography-model.md)
