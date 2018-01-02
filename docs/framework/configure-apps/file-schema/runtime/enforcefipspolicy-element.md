---
title: '&lt;EnforceFIPSPolicy&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fb8cb1ea4d011eb25aee14ddd53d3dc882f75d8e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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
