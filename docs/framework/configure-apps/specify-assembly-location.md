---
title: Angeben einer Assemblys&#39;s-Speicherort
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 65bd075115e33486e86e8081b01b96db665e9da5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758268"
---
# <a name="specifying-an-assembly39s-location"></a>Angeben einer Assemblys&#39;s-Speicherort
Es gibt zwei Möglichkeiten zum Angeben des Speicherortes einer Assembly:  
  
-   Mithilfe der [ \<codeBase >](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) Element.  
  
-   Mithilfe der [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) Element.  
  
 Sie können auch die [.NET Framework-Konfigurationstool (Mscorcfg.msc)](http://msdn.microsoft.com/library/a7106c52-68da-490e-b129-971b2c743764) Speicherorte von Assemblys angeben, oder geben Sie Speicherorte für die common Language Runtime nach Assemblys suchen.  
  
## <a name="using-the-codebase-element"></a>Mithilfe der \<codeBase >-Element  
 Sie können die  **\<codeBase >** Element nur im Computer-Konfiguration oder Verleger Richtliniendateien, die auch die Version der Assembly umleiten. Wenn die Runtime die zu verwendende Assemblyversion ermittelt wird, gilt die CodeBase-Einstellung aus der Datei, die die Version bestimmt. Wenn keine CodeBase angegeben ist, sucht die Runtime für die Assembly, auf die übliche Weise. Weitere Informationen finden Sie unter [so sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 Im folgende Beispiel wird das Festlegen des Speicherortes einer Assembly veranschaulicht.  
  
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
  
 Die **Version** Attribut ist für alle Assemblys mit starkem Namen erforderlich, sollte für Assemblys, die keinen starken Namen weggelassen werden. Die  **\<codeBase >** Element erfordert die **Href** Attribut. Sie können keine Versionsbereiche im Angeben der  **\<codeBase >** Element.  
  
> [!NOTE]
>  Wenn Sie einen CodeBase-Hinweis für eine Assembly, die nicht mit starkem Namen handelt bereitstellen, muss der Hinweis auf die Anwendungsbasis oder in einem Unterverzeichnis des Basisverzeichnisses der Anwendung verweisen.  
  
## <a name="using-the-probing-element"></a>Mithilfe der \<probing >-Element  
 Die Laufzeit sucht, Assemblys, die nicht über eine Codebasis Überprüfung verfügen. Weitere Informationen dazu finden Sie unter [so sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 Sie können die [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) Element in der Anwendungskonfigurationsdatei Unterverzeichnisse angeben, die Common Language Runtime durchsucht werden sollen, um die Assembly zu ermitteln. Im folgende Beispiel zeigt, wie die Verzeichnisse an, die die Common Language Runtime suchen soll.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Die **PrivatePath** Attribut enthält, die Verzeichnisse, die die Common Language Runtime nach Assemblys suchen soll. Wenn die Anwendung auf C:\Program Files\MyApp befindet, sucht die Common Language Runtime nach Assemblys, die keine Codebasis in c:\Programme\Microsoft Files\MyApp\Bin c:\Programme\Microsoft Files\MyApp\Bin2\Subbin und c:\Programme\Microsoft Files\MyApp\Bin3 angeben. Die Verzeichnisse im angegebenen **PrivatePath** müssen Unterverzeichnisse des Basisverzeichnisses der Anwendung sein.  
  
## <a name="see-also"></a>Siehe auch  
 [Assemblys in der Common Language Runtime (CLR)](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Konfigurieren von .NET Framework-Apps](http://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
