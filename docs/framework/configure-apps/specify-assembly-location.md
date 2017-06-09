---
title: "Festlegen des Speicherortes einer Assembly | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Anwendungskonfiguration [.NET Framework]"
  - "Assemblys [.NET Framework], Festlegen des Orts"
  - "Konfiguration [.NET Framework], Anwendungen"
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Festlegen des Speicherortes einer Assembly
Es gibt zwei Möglichkeiten, den Speicherort einer Assembly anzugeben:  
  
-   Verwenden des [\<CodeBase\>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)\-Elements.  
  
-   Verwenden des [\<Überprüfen\>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)\-Elements.  
  
 Sie können auch das [.NET Framework Configuration\-Tool \(Mscorcfg.msc\)](http://msdn.microsoft.com/de-de/a7106c52-68da-490e-b129-971b2c743764) verwenden, um Speicherorte von Assemblys oder Verzeichnisse anzugeben, in denen die Common Language Runtime nach Assemblys suchen soll.  
  
## Verwenden des \<CodeBase\>\-Elements  
 Sie können das **\<codeBase\>**\-Element nur in Computerkonfigurations\- oder Herausgeberrichtliniendateien verwenden, die auch die Assemblyversion umleiten.  Die Common Language Runtime wendet zur Bestimmung der zu verwendenden Assemblyversion die CodeBase\-Einstellung der Datei an, die die Version festlegt.  Wenn keine CodeBase angegeben ist, wird auf normalem Wege nach der Assembly gesucht.  Weitere Informationen finden Sie unter [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 Im folgenden Beispiel wird gezeigt, wie der Speicherort einer Assembly festgelegt wird.  
  
```  
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
  
 Das **version**\-Attribut ist für alle Assemblys mit starkem Namen erforderlich, sollte jedoch bei Assemblys ohne starken Namen ausgelassen werden.  Das **\<codeBase\>**\-Element erfordert das **href**\-Attribut.  Sie können im **\<codeBase\>**\-Element keine Versionsbereiche angeben.  
  
> [!NOTE]
>  Wenn Sie einen CodeBase\-Hinweis für eine Assembly ohne starken Namen zur Verfügung stellen, muss der Hinweis auf die Anwendungsbasis oder eines ihrer Unterverzeichnisse zeigen.  
  
## Verwenden des \<prüfenden\>\-Elements  
 Assemblys ohne CodeBase werden von der Common Language Runtime durch Suchen ermittelt.  Weitere Informationen dazu finden Sie unter [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 Sie können das [\<Überprüfen\>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)\-Element in der Anwendungskonfigurationsdatei verwenden, um anzugeben Unterverzeichnissen, die die Laufzeit suchen soll, wenn die Assembly zu ermitteln.  Das folgende Beispiel veranschaulicht, wie zu durchsuchende Verzeichnisse festgelegt werden.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Das **privatePath**\-Attribut enthält die Verzeichnisse, in denen die Common Language Runtime nach Assemblys suchen soll.  Wenn sich die Anwendung unter C:\\Programme\\MyApp befindet, wird nach Assemblys ohne CodeBase unter C:\\Programme\\MyApp\\Bin, C:\\Programme\\MyApp\\Bin2\\Subbin und C:\\Programme\\MyApp\\Bin3 gesucht.  Die in **privatePath** angegebenen Verzeichnisse müssen Unterverzeichnisse der Anwendungsbasis sein.  
  
## Siehe auch  
 [Assemblys in der Common Language Runtime \(CLR\)](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)   
 [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)   
 [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [Configuring .NET Framework Apps](http://msdn.microsoft.com/de-de/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)