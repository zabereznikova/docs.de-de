---
title: '&lt;SupportPortability&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a0332a642f9377eed2769ea5aedb1be85853274
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49122753"
---
# <a name="ltsupportportabilitygt-element"></a>&lt;SupportPortability&gt; Element
Gibt an, dass eine Anwendung in zwei verschiedenen Implementierungen von .NET Framework durch das Deaktivieren des Standardverhaltens, das die Assemblys zu Anwendungsportabilitätszwecken als gleich behandelt, auf die gleiche Assembly verweisen kann.  
  
 \<Configuration >-Element  
\<Common Language Runtime >-Element  
\<AssemblyBinding >-Element  
\<SupportPortability >-Element  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|PKT|Erforderliches Attribut.<br /><br /> Gibt das öffentliche Schlüsseltoken der betreffenden Assembly als Zeichenfolge an.|  
|enabled|Optionales Attribut.<br /><br /> Gibt an, ob Unterstützung für Portabilität zwischen Implementierungen der angegebenen .NET Framework-Assembly aktiviert werden soll.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|true|Aktivieren Sie die Unterstützung für Portabilität zwischen Implementierungen der angegebenen .NET Framework-Assembly. Dies ist die Standardeinstellung.|  
|False|Deaktivieren Sie die Unterstützung für Portabilität zwischen Implementierungen der angegebenen .NET Framework-Assembly. Dadurch kann die Anwendung Verweise auf mehrere Implementierungen besitzen.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
|`assemblyBinding`|Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.|  
  
## <a name="remarks"></a>Hinweise  
 Beginnend mit der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], wird automatisch unterstützt für Anwendungen, die beide Implementierungen von .NET Framework verwenden, können z. B. die Implementierung von .NET Framework oder .NET Framework for Silverlight-Implementierung. Die zwei Implementierungen einer bestimmten .NET Framework-Assembly werden vom Assemblybinder als äquivalent betrachtet. In einigen Szenarien verursacht diese Anwendungsportabilitätsfunktion Probleme. In jenen Szenarien kann das `<supportPortability>`-Element verwendet werden, um die Funktion zu deaktivieren.  
  
 Ein solches Szenario ist eine Assembly, die sowohl die .NET Framework-Implementierung als auch die .NET Framework for Silverlight-Implementierung einer bestimmten Verweisassembly mit Verweisen versehen muss. Ein in Windows Presentation Foundation (WPF) geschriebener XAML-Designer müsste möglicherweise sowohl auf die WPF-Desktopimplementierung, für die Benutzeroberfläche des Designers, als auch die Teilmenge von WPF, die in der Silverlight-Implementierung enthalten ist, verweisen. Standardmäßig verursachen die separaten Verweise einen Compilerfehler, da die Assemblybindung die zwei Assemblys als Entsprechung ansieht. Dieses Element deaktiviert das Standardverhalten und ermöglicht eine erfolgreiche Kompilierung.  
  
> [!IMPORTANT]
>  Damit der Compiler die Informationen an die Assemblybindungs-Logik der Common Language Runtime übergibt, müssen Sie den Speicherort der Datei „app.config“, die dieses Element enthält, mithilfe der `/appconfig`-Compileroption angeben.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel ermöglicht einer Anwendung, über Verweise sowohl auf die .NET Framework-Implementierung als auch die .NET Framework for Silverlight-Implementierung jeder die oft ausgegebene Befehlszeilen  .NET Framework-Assembly, die in beiden Implementierungen vorhanden ist, zu verfügen. Mit der `/appconfig`-Compileroption muss der Speicherort dieser app.config-Datei angegeben werden.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding>  
         <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
         <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [/ appconfig (C#-Compileroptionen)](../../../../../docs/csharp/language-reference/compiler-options/appconfig-compiler-option.md)  
 [Übersicht über die Vereinheitlichung von .NET Framework-Assembly](https://msdn.microsoft.com/library/8d8cc65e-031d-463b-bde3-2c6dc2e3bc48)
