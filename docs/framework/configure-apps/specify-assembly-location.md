---
title: Festlegen des Speicherortes einer Assembly
description: Weitere Informationen finden Sie unter Angeben des Speicher Orts einer Assembly in .net mit dem CodeBase-Element oder dem probingelement in einer XML-Konfigurationsdatei.
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: 6f9e41584ca36fcead06b73a485cb879c45705fa
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166884"
---
# <a name="specifying-an-assemblys-location"></a>Festlegen des Speicherortes einer Assembly

Es gibt zwei Möglichkeiten, den Speicherort einer Assembly anzugeben:  
  
- Verwenden des- [\<codeBase>](./file-schema/runtime/codebase-element.md) Elements.  
  
- Verwenden des- [\<probing>](./file-schema/runtime/probing-element.md) Elements.  
  
 Sie können auch das [.NET Framework-Konfigurations Tool (Mscorcfg. msc)](/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) verwenden, um Assemblyspeicher Orte anzugeben oder Speicherorte anzugeben, an denen die Common Language Runtime nach Assemblys suchen soll.  
  
## <a name="using-the-codebase-element"></a>Verwenden des- \<codeBase> Elements  

 Sie können das- **\<codeBase>** Element nur in der Computerkonfiguration oder in Herausgeber Richtlinien Dateien verwenden, die auch die Assemblyversion umleiten Wenn die Laufzeit bestimmt, welche Assemblyversion verwendet werden soll, wendet Sie die Codebasis Einstellung aus der Datei an, die die Version bestimmt. Wenn keine Codebasis angegeben wird, testet die Runtime die Assembly auf die normale Weise. Weitere Informationen finden Sie unter so sucht Common Language [Runtime](../deployment/how-the-runtime-locates-assemblies.md)nach Assemblys.  
  
 Im folgenden Beispiel wird gezeigt, wie der Speicherort einer Assembly angegeben wird.  
  
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
  
 Das **Versions** Attribut ist für alle Assemblys mit starkem Namen erforderlich, sollte jedoch nicht für Assemblys mit starkem Namen ausgelassen werden. Das- **\<codeBase>** Element benötigt das **href** -Attribut. Sie können keine Versions Bereiche im- **\<codeBase>** Element angeben.  
  
> [!NOTE]
> Wenn Sie einen Code Basis Hinweis für eine Assembly bereitstellen, die nicht mit starkem Namen benannt ist, muss der Hinweis auf die Anwendungs Basis oder auf ein Unterverzeichnis des Anwendungs Basisverzeichnisses zeigen.  
  
## <a name="using-the-probing-element"></a>Verwenden des- \<probing> Elements  

 Die Common Language Runtime sucht Assemblys, für die keine Codebasis vorhanden ist. Weitere Informationen zur Überprüfung finden Sie unter [so](../deployment/how-the-runtime-locates-assemblies.md)sucht Common Language Runtime nach Assemblys.  
  
 Sie können das- [\<probing>](./file-schema/runtime/probing-element.md) Element in der Anwendungs Konfigurationsdatei verwenden, um Unterverzeichnisse anzugeben, die die Common Language Runtime beim Suchen einer Assembly durchsuchen soll. Im folgenden Beispiel wird gezeigt, wie Sie die Verzeichnisse angeben, die die Laufzeit durchsuchen soll.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Das **privatePath** -Attribut enthält die Verzeichnisse, die von der Laufzeit nach Assemblys durchsucht werden sollen. Wenn sich die Anwendung unter c:\Programme\MyApp befindet, sucht die Runtime nach Assemblys, die keine Codebasis in c:\Programme\MyApp\Bin, c:\Programme\MyApp\Bin2\Subbin und c:\Programme\MyApp\Bin3. angeben. Die in **privatePath** angegebenen Verzeichnisse müssen Unterverzeichnisse des Basisverzeichnisses der Anwendung sein.  
  
## <a name="see-also"></a>Siehe auch

- [Assemblys in .NET](../../standard/assembly/index.md)
- [Programmieren mit Assemblys](../../standard/assembly/index.md)
- [So sucht Common Language Runtime nach Assemblys](../deployment/how-the-runtime-locates-assemblies.md)
- [Konfigurieren von Apps mithilfe von Konfigurationsdateien](index.md)
