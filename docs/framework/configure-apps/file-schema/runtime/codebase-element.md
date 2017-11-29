---
title: '&lt;codeBase&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: c5b30f1dc3ccade3028c31c57ffdab521802f086
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltcodebasegt-element"></a>&lt;codeBase&gt; Element
Gibt an, in dem die common Language Runtime eine Assembly finden kann.  
  
 \<configuration>  
\<Common Language Runtime >  
\<AssemblyBinding >  
\<DependentAssembly >  
\<codeBase >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
   <codeBase    
version="Assembly version"  
href="URL of assembly"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`href`|Erforderliches Attribut.<br /><br /> Gibt die URL, wo die Laufzeit die angegebene Version der Assembly finden kann.|  
|`version`|Erforderliches Attribut.<br /><br /> Gibt die Version der Assembly, der die Codebasis gilt. Das Format der Versionsnummer einer Assembly ist *"Hauptversion.Nebenversion.Build.Revision" vorliegen*.|  
  
## <a name="version-attribute"></a>Version-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Gültige Werte für jeden Teil der Versionsnummer sind 0 bis 65535.|Nicht zutreffend.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`buildproviders`|Definiert eine Auflistung von Buildanbietern, die zum Kompilieren benutzerdefinierter Ressourcendateien verwendet werden. Sie können eine beliebige Anzahl von Buildanbietern verwenden.|  
|`compilation`|Konfiguriert die kompilierungseinstellungen, die ASP.NET verwendet.|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`System.web`|Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.|  
  
## <a name="remarks"></a>Hinweise  
 Für die Laufzeit die  **\<codeBase >** in einer Konfigurationsdatei des Computers oder der Herausgeberrichtliniendatei festlegen, die Datei muss auch der Assemblyversionen umleiten. Anwendungskonfigurationsdateien können eine Codebase-Einstellung aufweisen, ohne die Version der Assembly umleiten. Nachdem die zu verwendende Assemblyversion ermittelt wurde, gilt die Common Language Runtime die Codebase-Einstellung aus der Datei, die die Version bestimmt. Wenn keine Codebase angegeben ist, sucht die Runtime für die Assembly, auf die übliche Weise.  
  
 Wenn die Assembly einen starken Namen besitzt, kann die CodeBase an einer beliebigen Stelle im lokalen Intranet oder Internet sein. Wenn die Assembly eine private Assembly handelt, muss die Codebase-Einstellung ein Pfad relativ zum Verzeichnis der Anwendung.  
  
 Für Assemblys ohne starken Namen, Version ignoriert und das Ladeprogramm verwendet die erste Darstellung der \<codebase > innerhalb \<DependentAssembly >. Wenn ein Eintrag in der Anwendungskonfigurationsdatei, die Bindung an eine andere Assembly umleitet vorhanden ist, wird die Umleitung Vorrang hat, auch wenn die Version der Assembly nicht mit die bindungsanforderung übereinstimmt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die anzugeben, wo die Common Language Runtime eine Assembly finden kann.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Festlegen des Speicherortes einer Assembly](../../../../../docs/framework/configure-apps/specify-assembly-location.md)  
 [So sucht Common Language Runtime nach Assemblys](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
