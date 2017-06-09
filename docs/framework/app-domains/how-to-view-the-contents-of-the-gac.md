---
title: "Gewusst wie: Anzeigen der Inhalte des globalen Assemblycaches | Microsoft Docs"
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
  - "GAC (Globaler Assembly-Cache), Anzeigen des Inhalts"
  - "Gacutil.exe"
  - "Globaler Assemblycache (Tool)"
  - "Globaler Assemblycache, Anzeigen des Inhalts"
  - "Liste der Assemblys im globalen Assemblycache"
  - "Assemblys mit starken Namen, Globaler Assemblycache"
  - "Anzeigen von Assemblys im globalen Assemblycache"
ms.assetid: c5f786a0-969b-4f14-9f02-e77c3384d9af
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Anzeigen der Inhalte des globalen Assemblycaches
Verwenden Sie das [Global Assembly Cache\-Tool \(Gacutil.exe\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md), um den Inhalt des globalen Assemblycaches anzuzeigen.  
  
### So zeigen Sie eine Liste der Assemblys im globalen Assemblycache an  
  
1.  Geben Sie an der [Visual Studio\-Eingabeaufforderung](../../../docs/framework/tools/developer-command-prompt-for-vs.md) den folgenden Befehl ein:  
  
     **gacutil \-l**   
     \- oder \-                
     **gacutil \/l**  
  
 In früheren Versionen von .NET Framework ermöglichte die Windows Shell\-Erweiterung [Shfusion.dll](http://msdn.microsoft.com/de-de/0d9464cf-ddba-4ca9-bbec-f678fb58f380) das Anzeigen des globalen Assemblycaches im Datei\-Explorer.  Ab [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] ist Shfusion.dll veraltet.  
  
## Siehe auch  
 [Arbeiten mit Assemblys und dem globalen Assemblychache](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)   
 [Gacutil.exe \(Global Assembly Cache Tool\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)