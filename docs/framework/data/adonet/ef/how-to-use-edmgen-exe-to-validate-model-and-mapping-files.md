---
title: "Gewusst wie: &#220;berpr&#252;fen von Modell- und Zuordnungsdateien mithilfe von EdmGen.exe | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "ESQL"
  - "jsharp"
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Gewusst wie: &#220;berpr&#252;fen von Modell- und Zuordnungsdateien mithilfe von EdmGen.exe
In diesem Thema wird dargestellt, wie das Tool [EDM Generator \(EdmGen.exe\)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) zum Validieren der Modell\- und Zuordnungsdateien verwendet wird.  Weitere Informationen finden Sie unter [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).  
  
### So validieren Sie das Modell 'School' mit 'EdmGen.exe'  
  
1.  Erstellen der Datenbank "School".  Weitere Informationen finden Sie unter [Creating the School Sample Database](http://msdn.microsoft.com/de-de/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Erstellen des Modells "School"  Weitere Informationen finden Sie unter [Vorgehensweise: Generieren von Modell\- und Zuordnungsdateien mithilfe von EdmGen.exe](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3.  Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```scr  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## Siehe auch  
 [How to: Manually Configure an Entity Framework Project](http://msdn.microsoft.com/de-de/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)   
 [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/de-de/91076853-0881-421b-837a-f582f36be527)   
 [How to: Pre\-Generate Views to Improve Query Performance](http://msdn.microsoft.com/de-de/b18a9d16-e10b-4043-ba91-b632f85a2579)   
 [Gewusst wie: Verwenden von 'EdmGen.exe' zum Generieren von Objektebenencode](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)