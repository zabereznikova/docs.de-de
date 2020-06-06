---
title: <enforceFIPSPolicy>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
ms.openlocfilehash: 0d6dd291a24928487a040c0427f058dee80bf836
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117387"
---
# <a name="enforcefipspolicy-element"></a>\<enforceFIPSPolicy>-Element
Gibt an, ob die Computerkonfigurationsanforderung durchgesetzt wird, dass kryptografische Algorithmen den Federal Information Processing Standards (FIPS) entsprechen müssen.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<enforceFIPSPolicy>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|enabled|Erforderliches Attribut.<br /><br /> Gibt an, ob die Erzwingung einer Computer Konfigurations Anforderung aktiviert werden soll, dass Kryptografiealgorithmen mit "fps" kompatibel sein müssen.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|`true`|Wenn Ihr Computer so konfiguriert ist, dass Kryptografiealgorithmen für die Kompatibilität mit der Konformität erforderlich sind, wird diese Anforderung erzwungen. Wenn eine Klasse einen Algorithmus implementiert, der nicht mit "fps" kompatibel ist, lösen die Konstruktoren oder `Create` Methoden für diese Klasse Ausnahmen aus, wenn Sie auf diesem Computer ausgeführt werden. Dies ist die Standardeinstellung.|  
|`false`|Kryptografiealgorithmen, die von der Anwendung verwendet werden, müssen unabhängig von der Computerkonfiguration nicht mit dem PPS kompatibel sein.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Bemerkungen  
 Beginnend mit dem .NET Framework 2,0 wird die Erstellung von Klassen, die Kryptografiealgorithmen implementieren, von der Konfiguration des Computers gesteuert. Wenn der Computer so konfiguriert ist, dass er Algorithmen erfordert, dass er mit der Verwendung von "fps" kompatibel ist, und eine Klasse einen Algorithmus implementiert, der nicht mit "fps" kompatibel ist, löst jeder Versuch, eine Instanz dieser Klasse zu erstellen, eine Konstruktoren lösen eine <xref:System.InvalidOperationException> Ausnahme aus, und- `Create` Methoden lösen eine- <xref:System.Reflection.TargetInvocationException> Ausnahme mit einer inneren <xref:System.InvalidOperationException> Ausnahme aus.  
  
 Wenn die Anwendung auf Computern ausgeführt wird, deren Konfigurationen mit dem Einsatz von "fps" kompatibel sein müssen, und die Anwendung einen Algorithmus verwendet, der nicht mit "fps" kompatibel ist, können Sie dieses Element in der Konfigurationsdatei verwenden, um zu verhindern, dass die Common Language Runtime (CLR) die Kompatibilität mit dem Dieses Element wurde in .NET Framework 2,0 Service Pack 1 eingeführt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie verhindert wird, dass die CLR die Konformität mit der Konformität erzwingt.  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
- [Kryptografiemodell](../../../../standard/security/cryptography-model.md)
