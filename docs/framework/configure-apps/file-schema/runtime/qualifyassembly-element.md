---
title: '&lt;QualifyAssembly&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 521bbccd83f224cc824dae41309715d65472454e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltqualifyassemblygt-element"></a>&lt;QualifyAssembly&gt; Element
Gibt den vollständigen Namen der Assembly an, die dynamisch geladen werden soll, wenn Sie ein Teilname verwendet wird.  
  
 \<configuration>  
\<Common Language Runtime >  
\<AssemblyBinding >  
\<QualifyAssembly >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`partialName`|Erforderliches Attribut.<br /><br /> Gibt die partielle Name der Assembly an, wie er im Code angezeigt wird.|  
|`fullName`|Erforderliches Attribut.<br /><br /> Gibt den vollständigen Namen der Assembly an, wie er im globalen Assemblycache angezeigt wird.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`assemblyBinding`|Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Aufrufen der <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> mit partiellen Assemblynamen Methode bewirkt, dass die common Language Runtime für die Assembly nur im Basisverzeichnis Anwendung gesucht werden soll. Verwenden der  **\<QualifyAssembly >** Element in der Konfigurationsdatei der Anwendung geben Sie die vollständige Assemblyinformationen (Name, Version, öffentliches Schlüsseltoken und Kultur) und dazu führen, dass die common Language Runtime, gesucht werden soll für die Assembly im globalen Assemblycache.  
  
 Die **FullName** Attribut muss vier Felder der Assemblyidentität enthalten: Name, Version, öffentliches Schlüsseltoken und Kultur. Die **PartialName** Attribut muss teilweise auf eine Assembly verweisen. Geben Sie mindestens den Namen der Assembly Text (die am häufigsten vorkommen), aber Sie können auch die Version, Token des öffentlichen Schlüssels oder Kultur (oder eine beliebige Kombination aus den vier, aber nicht alle vier) einschließen. Die **PartialName** muss die im Aufruf angegebenen Namen übereinstimmen. Angenommen, Sie können nicht angeben, `"math"` als die **PartialName** Attribut in der Konfigurationsdatei und der Aufruf `Assembly.Load("math, Version=3.3.3.3")` im Code.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird logisch der Aufruf `Assembly.Load("math")` in `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"   
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [So sucht Common Language Runtime nach Assemblys](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [NIB: Partielle Assemblyverweise](http://msdn.microsoft.com/en-us/ec90f07a-398c-4306-9401-0fc5ff9cb59f)
