---
title: Festlegen des Speicherortes einer Assembly
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: ead69d1e850050214c15295134c06ff6f66e9760
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646034"
---
# <a name="specifying-an-assemblys-location"></a>Festlegen des Speicherortes einer Assembly
Es gibt zwei Möglichkeiten, den Speicherort einer Assembly anzugeben:  
  
- Verwenden des [ \<codeBase>-Elements.](./file-schema/runtime/codebase-element.md)  
  
- Verwenden [ \<](./file-schema/runtime/probing-element.md) des>Elements.  
  
 Sie können auch das [.NET Framework Configuration Tool (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) verwenden, um Assemblyspeicherorte anzugeben oder Speicherorte für die Common Language Runtime anzugeben, die für Assemblys untersucht werden soll.  
  
## <a name="using-the-codebase-element"></a>Verwenden \<des codeBase>-Elements  
 Sie können das ** \<codeBase>-Element** nur in Computerkonfigurations- oder Herausgeberrichtliniendateien verwenden, die auch die Assemblyversion umleiten. Wenn die Laufzeit bestimmt, welche Assemblyversion verwendet werden soll, wendet sie die Codebasiseinstellung aus der Datei an, die die Version bestimmt. Wenn keine Codebasis angegeben ist, werden die Laufzeittests für die Assembly auf die normale Weise angezeigt. Weitere Informationen finden Sie unter [So findet die Laufzeit Assemblys](../deployment/how-the-runtime-locates-assemblies.md).  
  
 Das folgende Beispiel zeigt, wie der Speicherort einer Assembly angegeben wird.  
  
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
  
 Das **Versionsattribut** ist für alle Assemblys mit starkem Namen erforderlich, sollte jedoch für Assemblys weggelassen werden, die keinen starken Namen haben. Das ** \<codeBase>-Element** erfordert das **href-Attribut.** Sie können keine Versionsbereiche im ** \<codeBase>-Element** angeben.  
  
> [!NOTE]
> Wenn Sie einen Codebasishinweis für eine Assembly angeben, die keinen starken Namen hat, muss der Hinweis auf die Anwendungsbasis oder ein Unterverzeichnis des Anwendungsbasisverzeichnisses verweisen.  
  
## <a name="using-the-probing-element"></a>Verwenden \<des> Elements  
 Die Laufzeit sucht Assemblys, die keine Codebasis haben, indem sie untersucht wird. Weitere Informationen zum Thema Sondierung finden Sie unter [So findet die Laufzeit Assemblys](../deployment/how-the-runtime-locates-assemblies.md).  
  
 Sie können [ \<](./file-schema/runtime/probing-element.md) das>-Element in der Anwendungskonfigurationsdatei verwenden, um Unterverzeichnisse anzugeben, die die Laufzeit beim Suchen einer Assembly suchen soll. Das folgende Beispiel zeigt, wie Verzeichnisse angegeben werden, die die Laufzeit durchsuchen soll.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Das **privatePath-Attribut** enthält die Verzeichnisse, die die Laufzeit nach Assemblys durchsuchen soll. Wenn sich die Anwendung unter C:-Programmdateien und MyApp befindet, sucht die Laufzeit nach Assemblys, die keine Codebasis in C:-Programmdateien, "MyApp"-Bin, "C:-Programmdateien" und """"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""" Bei den in **privatePath** angegebenen Verzeichnissen müssen es sich um Unterverzeichnisse des Anwendungsbasisverzeichnisses befinden.  
  
## <a name="see-also"></a>Siehe auch

- [Assemblys in .NET](../../standard/assembly/index.md)
- [Programmieren mit Assemblys](../../standard/assembly/index.md)
- [So sucht die Laufzeit Assemblys](../deployment/how-the-runtime-locates-assemblies.md)
- [Konfigurieren von Apps mithilfe von Konfigurationsdateien](index.md)
