---
title: "Erstellen von Assemblys | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Assemblys [.NET Framework], Erstellen"
  - "Assemblys [.NET Framework], Mehrfachdatei"
  - "Mehrfachdateiassemblys"
  - "Einzeldateiassemblys"
ms.assetid: 54832ee9-dca8-4c8b-913c-c0b9d265e9a4
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Erstellen von Assemblys
Sie können Einfach\- oder Mehrfachdateiassemblys mithilfe einer IDE, wie [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], oder mit den von [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] zur Verfügung gestellten Compilern und Tools erstellen.  Das einfachste Beispiel für eine Assembly ist eine einzelne Datei mit einem einfachen Namen, die in eine einzelne Anwendungsdomäne geladen wird.  Andere Assemblys außerhalb des Anwendungsverzeichnisses können nicht auf diese Assembly verweisen; sie wird auch keiner Versionsüberprüfung unterzogen.  Um die aus der Assembly bestehende Anwendung zu deinstallieren, löschen Sie einfach das Verzeichnis, in dem sie sich befindet.  Viele Entwickler benötigen zur Bereitstellung einer Anwendung lediglich eine Assembly mit diesen Features.  
  
 Sie können eine Mehrfachdateiassembly aus mehreren Codemodulen und Ressourcendateien erstellen.  Es ist außerdem möglich, Assemblys zu erstellen, die gemeinsam von mehreren Anwendungen genutzt werden.  Eine solche freigegebene Assembly muss einen starken Namen haben und kann im globalen Assemblycache bereitgestellt werden.  
  
 Sie haben bei der Gruppierung von Codemodulen und Ressourcen in Assemblys verschiedene Auswahlmöglichkeiten, abhängig von den folgenden Faktoren:  
  
-   Versionskontrolle  
  
     Gruppenmodule mit identischen Versionsinformationen  
  
-   Bereitstellung  
  
     Gruppencodemodule und Ressourcen, die Ihr Bereitstellungsmodell unterstützen.  
  
-   Wiederverwendung  
  
     Gruppenmodule, falls sie logisch gemeinsam für denselben Zweck verwendet werden können.  Beispielsweise kann eine Assembly, die aus Typen und Klassen besteht, mit denen in unregelmäßigen Abständen das Programm gewartet wird, in derselben Assembly platziert werden.  Des Weiteren sollten Typen, die Sie für mehrere Anwendungen freigeben möchten, in einer Assembly zusammengefasst werden; diese Assembly sollte mit einem starken Namen signiert werden.  
  
-   Sicherheit  
  
     Gruppenmodule, die Typen mit denselben erforderlichen Sicherheitsberechtigungen enthalten.  
  
-   Scoping  
  
     Gruppenmodule, die Typen enthalten, deren Sichtbarkeit auf dieselbe Assembly beschränkt sein soll.  
  
 Spezielle Vorkehrungen müssen getroffen werden, wenn Common Language Runtime\-Assemblys für nicht verwaltete COM\-Anwendungen verfügbar gemacht werden sollen.  Weitere Informationen über das Arbeiten mit nicht verwaltetem Code finden Sie unter [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md).  
  
## Siehe auch  
 [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)   
 [Assemblyversionen](../../../docs/framework/app-domains/assembly-versioning.md)   
 [Gewusst wie: Erstellen einer Einzeldateiassembly](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)   
 [Gewusst wie: Erstellen einer Mehrfachdateiassembly](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)   
 [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [Mehrfachdateiassemblys](../../../docs/framework/app-domains/multifile-assemblies.md)