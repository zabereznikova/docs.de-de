---
title: "Verwenden von Serviced Components mit dem globalen Assemblycache | Microsoft Docs"
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
  - "Assemblys [.NET Framework], Globaler Assemblycache"
  - "GAC (Globaler Assembly-Cache), Serviced Components"
  - "Globaler Assemblycache, Serviced Components"
  - "Serviced Components, Globaler Assemblycache"
ms.assetid: 3423e5d9-234c-4571-8161-e35f6d130128
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Verwenden von Serviced Components mit dem globalen Assemblycache
Die Serviced Components \(COM\+\-Komponenten mit verwaltetem Code\) sollten im globalen Assemblycache abgelegt werden.  Nur in bestimmten Szenarien können die Common Language Runtime und die COM\+\-Dienste mit Serviced Components umgehen, die sich nicht im globalen Assemblycache befinden.  Folgende Beispielszenarien verdeutlichen dies:  
  
-   Für Serviced Components in einer COM\+\-Serveranwendung muss sich die Assembly, die die Komponenten enthält, im globalen Assemblycache befinden. Der Grund dafür ist, dass Dllhost.exe nicht in dem Verzeichnis ausgeführt werden kann, das die Serviced Components enthält.  
  
-   Bei Serviced Components in einer COM\+\-Bibliotheksanwendung können die Common Language Runtime und die COM\+\-Dienste durch Durchsuchen des aktuellen Verzeichnisses den Verweis auf die Assembly auflösen.  Demzufolge muss sich in diesem Fall die Assembly nicht unbedingt im globalen Assemblycache befinden.  
  
-   Bei Serviced Components in einer ASP.NET\-Anwendung stellt sich die Situation anders dar.  Wenn Sie die Assembly, die Serviced Components enthält, im bin\-Verzeichnis des Anwendungsstamms ablegen und bedarfsabhängige Registrierung verwenden, wird die Assembly mittels Spiegelung in den Downloadcache kopiert, da ASP.NET die Spiegelungsfunktionen der Common Language Runtime verwendet.  
  
## Siehe auch  
 [How to: Create a Serviced Component](http://msdn.microsoft.com/de-de/7ec0b488-e5fc-46f2-a48d-1278ea4e301d)   
 [Arbeiten mit Assemblys und dem globalen Assemblychache](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)   
 [Gacutil.exe \(Global Assembly Cache Tool\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)   
 [Assembly Cache Viewer \(Shfusion.dll\)](http://msdn.microsoft.com/de-de/0d9464cf-ddba-4ca9-bbec-f678fb58f380)