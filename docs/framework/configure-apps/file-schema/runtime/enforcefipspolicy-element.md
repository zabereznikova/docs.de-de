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
ms.openlocfilehash: f13243ddef7020f4d7a50e519ae8281702b0d261
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927420"
---
# <a name="enforcefipspolicy-element"></a>\<enforcemepspolicy > Element
Gibt an, ob die Computerkonfigurationsanforderung durchgesetzt wird, dass kryptografische Algorithmen den Federal Information Processing Standards (FIPS) entsprechen müssen.  
  
 \<Configuration >-Element  
\<Runtime-> Element  
\<enforcemepspolicy > Element  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|enabled|Erforderliches Attribut.<br /><br /> Gibt an, ob die Erzwingung einer Computer Konfigurations Anforderung aktiviert werden soll, dass Kryptografiealgorithmen mit "fps" kompatibel sein müssen.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`true`|Wenn Ihr Computer so konfiguriert ist, dass Kryptografiealgorithmen für die Kompatibilität mit der Konformität erforderlich sind, wird diese Anforderung erzwungen. Wenn eine Klasse einen Algorithmus implementiert, der nicht mit "fps" kompatibel ist, lösen `Create` die Konstruktoren oder Methoden für diese Klasse Ausnahmen aus, wenn Sie auf diesem Computer ausgeführt werden. Dies ist die Standardeinstellung.|  
|`false`|Kryptografiealgorithmen, die von der Anwendung verwendet werden, müssen unabhängig von der Computerkonfiguration nicht mit dem PPS kompatibel sein.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Beginnend mit dem .NET Framework 2,0 wird die Erstellung von Klassen, die Kryptografiealgorithmen implementieren, von der Konfiguration des Computers gesteuert. Wenn der Computer so konfiguriert ist, dass er Algorithmen erfordert, dass er mit der Verwendung von "fps" kompatibel ist, und eine Klasse einen Algorithmus implementiert, der nicht mit "fps" kompatibel ist, löst jeder Versuch, eine Instanz dieser Klasse zu erstellen, eine Konstruktoren lösen eine <xref:System.InvalidOperationException> Ausnahme aus, `Create` und-Methoden <xref:System.Reflection.TargetInvocationException> lösen eine-Ausnahme <xref:System.InvalidOperationException> mit einer inneren Ausnahme aus.  
  
 Wenn die Anwendung auf Computern ausgeführt wird, deren Konfigurationen Kompatibilität mit dem-Konfigurationsserver erfordern, und die Anwendung einen Algorithmus verwendet, der nicht mit dem-fps kompatibel ist, können Sie dieses Element in der Konfigurationsdatei verwenden, um zu verhindern, dass die Common Language Runtime (CLR) von Erzwingen der Konformität mit dem PPS Dieses Element wurde in .NET Framework 2,0 Service Pack 1 eingeführt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie verhindert wird, dass die CLR die Konformität mit der Konformität erzwingt.  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
- [Kryptografiemodell](../../../../standard/security/cryptography-model.md)
