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
ms.openlocfilehash: b026dafbde796bbd8726de56b532ed6710ba2290
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154308"
---
# <a name="assemblyidentity-element-for-runtime"></a>\<assemblyIdentity> \<Element für Laufzeit>
Enthält identifizierende Informationen zur Assembly.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<AssemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyIdentität>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
   <assemblyIdentity
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`name`|Erforderliches Attribut.<br /><br /> Der Name der Assembly|  
|`culture`|Optionales Attribut.<br /><br /> Eine Zeichenfolge, die die Sprache und das Land/die Region der Assembly angibt.|  
|`publicKeyToken`|Optionales Attribut.<br /><br /> Ein hexadezimaler Wert, der den starken Namen der Assembly angibt.|  
|`processorArchitecture`|Optionales Attribut.<br /><br /> Einer der Werte "x86", "amd64", "msil" oder "ia64", der die Prozessorarchitektur für eine Assembly angibt, die prozessorspezifischen Code enthält. Bei den Werten wird die Groß-/Kleinschreibung nicht berücksichtigt. Wenn dem Attribut ein anderer Wert `<assemblyIdentity>` zugewiesen wird, wird das gesamte Element ignoriert. Siehe <xref:System.Reflection.ProcessorArchitecture>.|  
  
## <a name="processorarchitecture-attribute"></a>processorArchitecture-Attribut  
  
|value|Beschreibung|  
|-----------|-----------------|  
|`amd64`|Nur AMD x86-64-Architektur.|  
|`ia64`|Nur Intel Itanium-Architektur.|  
|`msil`|Neutral hinsichtlich des Prozessors und der Bits pro Wort.|  
|`x86`|Ein 32-Bit-x86-Prozessor, entweder nativ oder in der Windows-unter Windows-Umgebung (WOW) auf einer 64-Bit-Plattform.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`assemblyBinding`|Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`dependentAssembly`|Kapselt die Bindungsrichtlinie und den Assemblyspeicherort für jede Assembly. Verwenden `<dependentAssembly>` Sie für jede Baugruppe ein Element.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Bemerkungen  
 Jedes ** \<dependentAssembly>-Element** muss über ein ** \<AssemblyIdentity->** untergeordnetes Element verfügen.  
  
 Wenn `processorArchitecture` das Attribut vorhanden `<assemblyIdentity>` ist, gilt das Element nur für die Assembly mit der entsprechenden Prozessorarchitektur. Wenn `processorArchitecture` das Attribut nicht `<assemblyIdentity>` vorhanden ist, kann das Element auf eine Assembly mit einer beliebigen Prozessorarchitektur angewendet werden.  
  
 Das folgende Beispiel zeigt eine Konfigurationsdatei für zwei Assemblys mit demselben Namen, die auf zwei verschiedene Prozessorarchitekturen abzielen und deren Versionen nicht synchron verwaltet wurden. Wenn die Anwendung auf der x86-Plattform ausgeführt wird, gilt das erste `<assemblyIdentity>` Element, und das andere wird ignoriert. Wenn die Anwendung auf einer anderen Plattform als x86 oder ia64 ausgeführt wird, werden beide ignoriert.  
  
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
  
 Wenn eine Konfigurationsdatei `<assemblyIdentity>` ein `processorArchitecture` Element ohne Attribut enthält und kein Element enthält, `processorArchitecture` das mit der Plattform übereinstimmt, wird das Element ohne attribut verwendet.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Informationen zu einer Assembly bereitstellen werden.  
  
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
- [Schema der Konfigurationsdatei](../index.md)
- [Umleiten von Assemblyversionen](../../redirect-assembly-versions.md)
