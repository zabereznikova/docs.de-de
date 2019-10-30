---
title: <UseSmallInternalThreadStacks>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
ms.openlocfilehash: 2fd776ce8605e6dcf288dcb3852ded16638a1873
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73114922"
---
# <a name="usesmallinternalthreadstacks-element"></a>\<> Element "Element"
Fordert an, dass die Common Language Runtime (CLR) die Speicherauslastung reduziert, indem explizite Stapel Größen angegeben werden, wenn bestimmte, intern verwendete Threads erstellt werden, anstatt die Standard Stapelgröße für diese Threads zu verwenden.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<** "".  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|enabled|Erforderliches Attribut.<br /><br /> Gibt an, ob die CLR explizite Stapel Größen anstelle der Standard Stapelgröße verwenden soll, wenn bestimmte, intern verwendete Threads erstellt werden. Die expliziten Stapel Größen sind kleiner als die Standard Stapelgröße von 1 MB.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|true|Anfordern von expliziten Stapel Größen.|  
|False|Verwenden Sie die Standard Stapelgröße. Dies ist die Standardeinstellung für die .NET Framework 4.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Konfigurationselement wird verwendet, um eine reduzierte Verwendung des virtuellen Speichers in einem Prozess anzufordern, da die von der CLR für die internen Threads verwendeten expliziten Thread Größen, wenn die Anforderung berücksichtigt wird, kleiner als die Standardgröße sind.  
  
> [!IMPORTANT]
> Bei diesem Konfigurationselement handelt es sich um eine Anforderung an die CLR und nicht um eine absolute Anforderung. In der .NET Framework 4 wird die Anforderung nur für die x86-Architektur berücksichtigt. Dieses Element kann in zukünftigen Versionen der CLR vollständig ignoriert oder durch explizite Stapel Größen ersetzt werden, die immer für ausgewählte interne Threads verwendet werden.  
  
 Wenn Sie dieses Konfigurationselement angeben, wird die Zuverlässigkeit für den geringeren virtuellen Speicher verwendet, wenn die CLR die Anforderung erfüllt, da kleinere Stapel Größen potenziell zu einem Stapelüberlauf führen könnten.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie angefordert wird, dass die CLR explizite Stapel Größen für bestimmte Threads verwendet, die intern verwendet werden.  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
