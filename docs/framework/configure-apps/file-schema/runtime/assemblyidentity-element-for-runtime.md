---
title: <assemblyIdentity>-Element für <runtime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
ms.openlocfilehash: f3e74b05ac0fd7c57963f2aad047ba3f2d63a10a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170180"
---
# <a name="assemblyidentity-element-for-runtime"></a>\<assemblyIdentity>-Element für \<runtime>

Enthält identifizierende Informationen über die Assembly.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyIdentity>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
   <assemblyIdentity
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`name`|Erforderliches Attribut.<br /><br /> Der Name der Assembly.|  
|`culture`|Optionales Attribut.<br /><br /> Eine Zeichenfolge, die die Sprache und das Land/die Region der Assembly angibt.|  
|`publicKeyToken`|Optionales Attribut.<br /><br /> Ein Hexadezimalwert, der den starken Namen der Assembly angibt.|  
|`processorArchitecture`|Optionales Attribut.<br /><br /> Einer der Werte "x86", "amd64", "MSIL" oder "ia64", der die Prozessorarchitektur für eine Assembly angibt, die Prozessor spezifischen Code enthält. Bei Werten wird die Groß-/Kleinschreibung nicht beachtet. Wenn dem Attribut ein beliebiger anderer Wert zugewiesen wird, `<assemblyIdentity>` wird das gesamte Element ignoriert. Siehe <xref:System.Reflection.ProcessorArchitecture>.|  
  
## <a name="processorarchitecture-attribute"></a>ProcessorArchitecture-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`amd64`|Nur AMD x86-64-Architektur.|  
|`ia64`|Nur Intel Itanium-Architektur.|  
|`msil`|Neutral hinsichtlich des Prozessors und der Bits pro Wort.|  
|`x86`|Ein 32-Bit-x86-Prozessor, entweder System eigen oder in der WOW-Umgebung (Windows on Windows) auf einer 64-Bit-Plattform.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`assemblyBinding`|Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`dependentAssembly`|Kapselt die Bindungsrichtlinie und den Assemblyspeicherort für jede Assembly. Verwenden Sie ein- `<dependentAssembly>` Element für jede Assembly.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Bemerkungen  

 Jedes **\<dependentAssembly>** Element muss über ein untergeordnetes **\<assemblyIdentity>** Element verfügen.  
  
 Wenn das- `processorArchitecture` Attribut vorhanden ist, `<assemblyIdentity>` gilt das-Element nur für die Assembly mit der entsprechenden Prozessorarchitektur. Wenn das- `processorArchitecture` Attribut nicht vorhanden ist, `<assemblyIdentity>` kann das-Element auf eine Assembly mit beliebiger Prozessorarchitektur angewendet werden.  
  
 Das folgende Beispiel zeigt eine Konfigurationsdatei für zwei Assemblys mit dem gleichen Namen, die zwei unterschiedliche zwei Prozessorarchitekturen als Ziel haben und deren Versionen nicht synchron aufbewahrt wurden. Wenn die Anwendung auf der x86-Plattform ausgeführt wird, wird das erste `<assemblyIdentity>` Element angewendet, und das andere wird ignoriert. Wenn die Anwendung auf einer anderen Plattform als x86 oder ia64 ausgeführt wird, werden beide ignoriert.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"  
                  processorArchitecture="x86" />  
            <bindingRedirect oldVersion= "1.0.0.0"
                  newVersion="1.1.0.0" />  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"
                  processorArchitecture="ia64" />  
            <bindingRedirect oldVersion="1.0.0.0"
                  newVersion="2.0.0.0" />  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Wenn eine Konfigurationsdatei ein `<assemblyIdentity>` Element `processorArchitecture` ohne Attribut enthält und kein Element enthält, das mit der Plattform übereinstimmt, wird das-Element ohne das- `processorArchitecture` Attribut verwendet.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird gezeigt, wie Informationen zu einer Assembly bereitgestellt werden.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
- [Umleiten von Assemblyversionen](../../redirect-assembly-versions.md)
