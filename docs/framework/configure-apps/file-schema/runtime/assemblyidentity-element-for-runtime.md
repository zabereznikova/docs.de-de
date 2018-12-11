---
title: '&lt;AssemblyIdentity&gt; -Element für &lt;Common Language Runtime&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 2d82aed13e185b2957a22f097b60e12265a5f190
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128205"
---
# <a name="ltassemblyidentitygt-element-for-ltruntimegt"></a>&lt;AssemblyIdentity&gt; -Element für &lt;Common Language Runtime&gt;
Enthält identifizierende Informationen für die Assembly an.  
  
 \<configuration>  
\<Common Language Runtime >  
\<assemblyBinding>  
\<DependentAssembly >  
\<AssemblyIdentity >  
  
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
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`name`|Erforderliches Attribut.<br /><br /> Der Name der assembly|  
|`culture`|Optionales Attribut.<br /><br /> Eine Zeichenfolge, die Sprache und Land/Region der Assembly angibt.|  
|`publicKeyToken`|Optionales Attribut.<br /><br /> Ein Hexadezimalwert, der den starken Namen der Assembly angibt.|  
|`processorArchitecture`|Optionales Attribut.<br /><br /> Eines der Werte "X86", "amd64", "Msil" oder "ia64" Angeben von der Prozessorarchitektur für eine Assembly, die Prozessor-spezifischen Code enthält. Die Werte sind keine Groß-/Kleinschreibung beachtet. Wenn das Attribut auf einen anderen Wert, den gesamten zugewiesen ist `<assemblyIdentity>` Element wird ignoriert. Siehe <xref:System.Reflection.ProcessorArchitecture>.|  
  
## <a name="processorarchitecture-attribute"></a>ProcessorArchitecture-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`amd64`|Nur AMD X86-64-Architektur.|  
|`ia64`|Nur Intel Itanium-Architektur.|  
|`msil`|Neutral hinsichtlich des Prozessors und die Bits pro Wort.|  
|`x86`|Eine 32-Bit-X86 Prozessor, entweder systemeigen oder in der Windows auf Windows (WOW)-Umgebung auf einer 64-Bit-Plattform.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`assemblyBinding`|Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`dependentAssembly`|Kapselt die Bindungsrichtlinie und den Assemblyspeicherort für jede Assembly. Verwenden Sie eine `<dependentAssembly>` -Element für jede Assembly.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Jede  **\<DependentAssembly >** Element benötigen einen  **\<AssemblyIdentity >** untergeordnetes Element.  
  
 Wenn die `processorArchitecture` -Attribut vorhanden ist, die `<assemblyIdentity>` Element gilt nur für die Assembly mit der entsprechenden Prozessorarchitektur. Wenn die `processorArchitecture` Attribut ist nicht vorhanden, die `<assemblyIdentity>` Element auf eine Assembly mit einer beliebigen Prozessorarchitektur anwenden kann.  
  
 Das folgende Beispiel zeigt eine Konfigurationsdatei für zwei Assemblys mit demselben Namen, die zwei verschiedene Prozessorarchitekturen in zwei vorgesehen und, deren Versionen müssen nicht synchron beibehalten wurde. Wenn die Anwendung ausgeführt wird, auf die X86 Plattform die erste `<assemblyIdentity>` Element angewendet wird und der andere Wert wird ignoriert. Wenn die Anwendung auf einer anderen Plattform als X86 oder ia64 ausgeführt wird, werden beide ignoriert.  
  
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
  
 Wenn eine Konfigurationsdatei enthält eine `<assemblyIdentity>` Element ohne `processorArchitecture` Attribut, und enthält ein Element, das der Plattform, die dem Element ohne entspricht nicht der `processorArchitecture` Attribut wird verwendet.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Informationen zu einer Assembly bereitgestellt wird.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Umleiten von Assemblyversionen](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
