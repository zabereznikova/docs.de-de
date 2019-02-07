---
title: Festlegen des Speicherortes einer Assembly
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: 328fe08872a2b57d0bdf87ea9be9224795ca9ad9
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825406"
---
# <a name="specifying-an-assemblys-location"></a>Festlegen des Speicherortes einer Assembly
Es gibt zwei Möglichkeiten zum Angeben des Speicherortes einer Assembly:  
  
-   Mithilfe der [ \<codeBase >](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) Element.  
  
-   Mithilfe der [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) Element.  
  
 Sie können auch die [.NET Framework-Konfigurationstool (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) Speicherorte von Assemblys oder Speicherorte für die common Language Runtime nach Assemblys suchen angeben.  
  
## <a name="using-the-codebase-element"></a>Mithilfe der \<codeBase >-Element  
 Sie können die  **\<codeBase >** Element nur im Computer-Konfiguration oder Verleger Richtliniendateien, die auch die Version der Assembly umleiten. Wenn die Runtime die zu verwendende Assemblyversion ermittelt wird, gilt es die CodeBase-Einstellung aus der Datei, die die Version bestimmt. Wenn keine Codebasis angegeben ist, durchsucht die Runtime für die Assembly, auf die übliche Weise. Weitere Informationen finden Sie unter [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 Das folgende Beispiel zeigt, wie Sie des Speicherortes einer Assembly angeben.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <codeBase version="2.0.0.0"  
                   href="http://www.litwareinc.com/myAssembly.dll"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Die **Version** Attribut ist für alle Assemblys mit starkem Namen erforderlich, aber für Assemblys ohne starken Namen weggelassen werden soll. Die  **\<codeBase >** Element ist erforderlich. die **Href** Attribut. Kann nicht angegeben werden versionsbereichen in die  **\<codeBase >** Element.  
  
> [!NOTE]
>  Wenn Sie einen CodeBase-Hinweis für eine Assembly, die nicht mit starkem Namen handelt angeben, muss der Hinweis auf der Basis der Anwendung oder einem Unterverzeichnis des Basisverzeichnisses der Anwendung verweisen.  
  
## <a name="using-the-probing-element"></a>Mithilfe der \<probing >-Element  
 Die Laufzeit sucht Assemblys, die nicht über eine Codebasis von-Tests verfügen. Weitere Informationen dazu finden Sie unter [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 Können Sie die [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) Element in der Konfigurationsdatei der Anwendung an Unterverzeichnisse, die Common Language Runtime durchsucht werden sollen, um die Assembly zu ermitteln. Das folgende Beispiel zeigt, wie Sie die Verzeichnisse angeben, die die Common Language Runtime suchen soll.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Die **PrivatePath** Attribut enthält die Verzeichnisse, die die Common Language Runtime nach Assemblys suchen soll. Wenn die Anwendung unter C:\Program Files\MyApp befindet, sucht die Runtime nach Assemblys, die keine Codebasis in c:\Programme\Microsoft Files\MyApp\Bin, c:\Programme\Microsoft Files\MyApp\Bin2\Subbin und c:\Programme\Microsoft Files\MyApp\Bin3 angeben. Die Verzeichnisse im angegebenen **PrivatePath** müssen Unterverzeichnisse des Basisverzeichnisses der Anwendung sein.  
  
## <a name="see-also"></a>Siehe auch
- [Assemblys in der Common Language Runtime (CLR)](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
- [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)
- [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [Konfigurieren von Apps mithilfe von Konfigurationsdateien](index.md)
