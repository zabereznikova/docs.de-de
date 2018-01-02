---
title: "&lt;AssemblyIdentity&gt; -Element für &lt;Common Language Runtime&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
caps.latest.revision: "17"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 0dadf0e07f5e3a9f9152ae7cd57c62721402bff0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltassemblyidentitygt-element-for-ltruntimegt"></a>&lt;AssemblyIdentity&gt; -Element für &lt;Common Language Runtime&gt;
Enthält identifizierende Informationen über die Assembly an.  
  
 \<configuration>  
\<Common Language Runtime >  
\<AssemblyBinding >  
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
|`processorArchitecture`|Optionales Attribut.<br /><br /> Eines der Werte "X86", "amd64", "Msil" oder "ia64" Angeben von der Architektur des Prozessors für eine Assembly, die prozessorspezifischen Code enthält. Die Werte sind nicht in der Groß-/Kleinschreibung beachtet. Wenn das Attribut jedem anderen Wert wird die gesamte zugewiesen ist `<assemblyIdentity>` Element wird ignoriert. Siehe <xref:System.Reflection.ProcessorArchitecture>.|  
  
## <a name="processorarchitecture-attribute"></a>ProcessorArchitecture-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`amd64`|Nur ein 64-Bit-AMD-Prozessor.|  
|`ia64`|Nur ein 64-Bit-Intel-Prozessor.|  
|`msil`|Neutral in Bezug auf Prozessor und die Bits pro Wort|  
|`x86`|Eine 32-Bit-Intel-Prozessor, entweder systemeigen oder in dem Windows on Windows (WOW)-Umgebung auf einer 64-Bit-Plattform.|  
  
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
 Jede  **\<DependentAssembly >** Element benötigen eine  **\<AssemblyIdentity >** untergeordnetes Element.  
  
 Wenn die `processorArchitecture` Attribut vorhanden ist, ist die `<assemblyIdentity>` Element gilt nur für die Assembly mit der entsprechenden Prozessorarchitektur. Wenn die `processorArchitecture` -Attribut nicht vorhanden ist, ist die `<assemblyIdentity>` Element auf eine Assembly mit einer beliebigen Prozessorarchitektur anwenden kann.  
  
 Das folgende Beispiel zeigt eine Konfigurationsdatei für zwei Assemblys mit demselben Namen, die auf zwei verschiedenen zwei Prozessorarchitekturen und deren Versionen sind nicht synchron gehalten wurde. Wenn die Anwendung ausgeführt wird, auf die X86 Plattform den ersten `<assemblyIdentity>` Element angewendet wird und der andere wird ignoriert. Wenn die Anwendung auf einer anderen Plattform als X86 oder ia64 ausgeführt wird, werden beide ignoriert.  
  
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
  
 Wenn eine Konfigurationsdatei enthält ein `<assemblyIdentity>` Element ohne `processorArchitecture` Attribut, und enthält ein Element, das der Plattform, für das Element ohne entspricht nicht der `processorArchitecture` Attribut wird verwendet.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Informationen zu einer Assembly bereit.  
  
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
