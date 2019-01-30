---
title: <codeBase>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
ms.openlocfilehash: ebf7e2624cc36fb6a758afef38e2054669061dff
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269652"
---
# <a name="codebase-element"></a>\<codeBase >-Element
Gibt an, in dem die common Language Runtime eine Assembly finden kann.  
  
 \<configuration>  
\<runtime>  
\<assemblyBinding>  
\<dependentAssembly>  
\<codeBase>  
  
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
|`href`|Erforderliches Attribut.<br /><br /> Gibt die URL, in dem die Runtime die angegebene Version der Assembly finden kann.|  
|`version`|Erforderliches Attribut.<br /><br /> Gibt die Version der Assembly, die, der auf die Codebasis angewendet wird. Hat das Format einer Assemblyversionsnummer *"Hauptversion.Nebenversion.Build.Revision"*.|  
  
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
|`compilation`|Konfiguriert alle kompilierungseinstellungen, mit denen ASP.NET an.|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`System.web`|Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.|  
  
## <a name="remarks"></a>Hinweise  
 Für die Laufzeit die  **\<codeBase >** in einer Konfigurationsdatei des Computers oder der Herausgeberrichtliniendatei festlegen, die Datei muss auch umleiten, die Version der Assembly. Anwendungskonfigurationsdateien haben eine Codebase-Einstellung, ohne die Version der Assembly umleiten. Nachdem die zu verwendende Assemblyversion ermittelt wurde, gilt die Runtime die Codebase-Einstellung aus der Datei, die die Version bestimmt. Wenn keine Codebase angegeben, durchsucht die Runtime für die Assembly, auf die übliche Weise.  
  
 Wenn die Assembly einen starken Namen aufweist, kann die Codebase-Einstellung an eine beliebige Stelle im lokalen Intranet oder Internet sein. Wenn die Assembly über eine private Assembly handelt, muss die Codebase-Einstellung auf einen Pfad relativ zum Verzeichnis der Anwendung sein.  
  
 Für Assemblys ohne starken Namen, Version ignoriert, und das Ladeprogramm verwendet das erste Vorkommen von \<codebase > in \<DependentAssembly >. Wenn ein Eintrag vorhanden, in der Konfigurationsdatei der Anwendung, die Bindung an eine andere Assembly umleitet ist, hat die Umleitung Vorrang, selbst wenn die Version der Assembly nicht mit der bindungsanforderung übereinstimmt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie angeben, in dem die Runtime eine Assembly finden kann.  
  
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
- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Festlegen des Speicherortes einer Assembly](../../../../../docs/framework/configure-apps/specify-assembly-location.md)
- [So sucht Common Language Runtime nach Assemblys](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
