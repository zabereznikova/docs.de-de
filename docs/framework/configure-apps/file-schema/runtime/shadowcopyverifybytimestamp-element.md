---
title: <shadowCopyVerifyByTimestamp>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79d44ff255b1fc12efc6e8488eeab231b9276b90
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252319"
---
# <a name="shadowcopyverifybytimestamp-element"></a>\<shadowCopyVerifyByTimestamp>-Element
Gibt an, ob beim Schatten kopieren das standardmäßige Startverhalten verwendet wird, das in der .NET Framework 4 eingeführt wurde, oder ob das Startverhalten früherer Versionen der .NET Framework wieder hergestellt wird.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<shadowcopyverifybytimestamp->**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|enabled|Erforderliches Attribut.<br /><br /> Gibt an, ob Anwendungs Domänen, die die Schatten Kopien verwenden, beim Start assemblyzeit Stempel vergleichen, um zu bestimmen, ob eine Assembly vor dem Kopieren der Assembly aktualisiert wurde.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|true|Beim Start von werden nur Assemblys kopiert, die aktualisiert wurden, seit Sie zuletzt in das schattenkopiesverzeichnis kopiert wurden. Dies ist die Standardeinstellung für die .NET Framework 4.|  
|false|Setzt auf das Startverhalten vorheriger Versionen der .NET Framework zurück, bei der alle Dateien beim Start kopiert wurden.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Beginnend mit dem .NET Framework 4 werden Assemblys nur dann als Schatten kopiert, wenn Ihre Zeitstempel darauf hindeuten, dass Sie geändert wurden, seit Sie zuletzt in das schattenkopieverzeichnis kopiert wurden. Dies verbessert die Startzeiten für viele Anwendungen, die Schatten Kopien verwenden, wie in [Schatten Kopien](../../../app-domains/shadow-copy-assemblies.md)von Assemblys beschrieben. Anwendungen, die einen hohen Prozentsatz und eine Häufigkeit von Assemblyaktualisierungen aufweisen, profitieren möglicherweise nicht von dieser Änderung des Verhaltens. In diesem Fall können Sie dieses Element verwenden, um das Verhalten vorheriger Versionen des .NET Framework wiederherzustellen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie das Standard Startverhalten des schattenkopierens in .NET Framework 4 deaktivieren und das Startverhalten vorheriger Versionen der .NET Framework wiederherstellen.  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
- [Erstellen von Schattenkopien von Assemblys](../../../app-domains/shadow-copy-assemblies.md)
