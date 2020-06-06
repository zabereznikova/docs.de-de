---
title: <disableCommitThreadStack>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCommitThreadStack
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCommitThreadStack
helpviewer_keywords:
- <disableCommitThreadStack> element
- disableCommitThreadStack element
ms.assetid: 3559d46a-7640-4c72-9a11-7e980768929e
ms.openlocfilehash: 8aefb8a20d6a95c5b8062d0c03dcb28a3557ca3d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117473"
---
# <a name="disablecommitthreadstack-element"></a>\<disableCommitThreadStack>-Element
Gibt an, ob beim Starten eines Threads für den vollständigen Threadstapel ein Commit ausgeführt wird  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<disableCommitThreadStack>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|enabled|Erforderliches Attribut.<br /><br /> Gibt an, ob das Standardverhalten, beim Starten des Threads den gesamten Threadstapel zu commiten, deaktiviert ist|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|0|Das Standardverhalten der Common Language Runtime, beim Starten eines Threads einen Commit für den vollständigen Threadstapel auszuführen, ist nicht deaktiviert.|  
|1|Das Standardverhalten der Common Language Runtime, beim Starten eines Threads einen Commit für den vollständigen Threadstapel auszuführen, ist deaktiviert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das Standardverhalten der Common Language Runtime ist, beim Starten eines Threads einen Commit für den vollständigen Threadstapel auszuführen. Wenn eine große Anzahl von Threads auf einem Server erstellt werden muss, der nur über begrenzten Arbeitsspeicher verfügt, und der Großteil dieser Threads nur sehr wenig Stapelspeicher verwenden wird, ist die Leistung des Servers möglicherweise besser, wenn die Common Language Runtime nicht sofort einen Commit für den vollständigen Threadstapel ausführt, wenn ein Thread gestartet wird.  
  
> [!NOTE]
> Nicht verwaltete Hosts können das `STARTUP_DISABLE_COMMITTHREADSTACK` -Startflag in der [STARTUP_FLAGS](../../../unmanaged-api/hosting/startup-flags-enumeration.md) -Enumeration verwenden, um das gleiche Ergebnis zu erzielen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie das Standardverhalten der Common Language Runtime deaktivieren, die während des Threadstarts einen Commit für den vollständigen Threadstapel ausführen soll.  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
