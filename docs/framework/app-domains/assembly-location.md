---
title: "Assemblyspeicherort | Microsoft Docs"
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
  - "Assemblys [.NET Framework], Speicherort"
  - "Suchen von Assemblys"
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Assemblyspeicherort
Der Speicherort einer Assembly bestimmt, ob sie, wenn auf sie verwiesen wird, von der Common Language Runtime gefunden wird und ob die Freigabe zusammen mit anderen Assemblys möglich ist.  Sie können Assemblys an folgenden Speicherorten bereitstellen:  
  
-   Im Anwendungsverzeichnis oder dessen Unterverzeichnissen.  
  
     Dies ist der gebräuchlichste Ort für die Bereitstellung einer Assembly.  Die Unterverzeichnisse des Stammverzeichnisses einer Anwendung können z. B. auf Sprache oder Kultur basieren.  Enthält eine Assembly Informationen im Kulturattribut, muss sie sich in einem Unterverzeichnis des Anwendungsverzeichnisses befinden, das den Namen dieser Kultur trägt.  
  
-   Im globalen Assemblycache.  
  
     Dies ist ein computerweiter Codecache, der immer zusammen mit der Common Language Runtime installiert wird.  Wenn eine Assembly von mehreren Anwendungen gemeinsam genutzt werden soll, ist es in den meisten Fällen empfehlenswert, sie im globalen Assemblycache bereitzustellen.  
  
-   Auf einem HTTP\-Server.  
  
     Eine auf einem HTTP\-Server bereitgestellte Assembly muss einen starken Namen haben. Der Verweis auf die Assembly erfolgt im CodeBase\-Abschnitt der Konfigurationsdatei der Anwendung.  
  
## Siehe auch  
 [Erstellen von Assemblys](../../../docs/framework/app-domains/create-assemblies.md)   
 [Globaler Assemblycache](../../../docs/framework/app-domains/gac.md)   
 [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)