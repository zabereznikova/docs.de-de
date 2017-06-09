---
title: "Gewusst wie: Verwenden von &#39;EdmGen.exe&#39; zum Generieren von Objektebenencode | Microsoft Docs"
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
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Gewusst wie: Verwenden von &#39;EdmGen.exe&#39; zum Generieren von Objektebenencode
In diesem Thema wird gezeigt, wie der [EDM\-Generator \(EdmGen.exe\)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) verwendet wird, um Objektebenencode auf der Grundlage der CSDL\-Datei zu generieren.  
  
### So generieren Sie mithilfe von EdmGen.exe den Objektebenencode für das Modell "School" für ein Visual Basic\-Projekt  
  
1.  Erstellen der Datenbank "School".  Weitere Informationen finden Sie unter [Creating the School Sample Database](http://msdn.microsoft.com/de-de/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Generieren Sie das Modell "School", oder verwenden Sie die Datei **School.csdl**.  Weitere Informationen finden Sie unter [Vorgehensweise: Generieren von Modell\- und Zuordnungsdateien mithilfe von EdmGen.exe](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3.  Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### So generieren Sie mithilfe von EdmGen.exe den Objektebenencode für das Modell "School" für ein C\#\-Projekt  
  
1.  Erstellen der Datenbank "School".  Weitere Informationen finden Sie unter [Creating the School Sample Database](http://msdn.microsoft.com/de-de/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Generieren Sie das Modell "School", oder verwenden Sie die Datei **School.csdl**.  Weitere Informationen finden Sie unter [Vorgehensweise: Generieren von Modell\- und Zuordnungsdateien mithilfe von EdmGen.exe](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3.  Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## Siehe auch  
 [Modellieren und Zuordnen](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)   
 [How to: Manually Configure an Entity Framework Project](http://msdn.microsoft.com/de-de/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)   
 [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/de-de/91076853-0881-421b-837a-f582f36be527)   
 [How to: Pre\-Generate Views to Improve Query Performance](http://msdn.microsoft.com/de-de/b18a9d16-e10b-4043-ba91-b632f85a2579)   
 [Vorgehensweise: Generieren von Modell\- und Zuordnungsdateien mithilfe von EdmGen.exe](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)