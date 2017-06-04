---
title: "Gewusst wie: Erstellen von in Modell- und Zuordnungsdateien eingebetteten Ressourcen | Microsoft Docs"
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
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Gewusst wie: Erstellen von in Modell- und Zuordnungsdateien eingebetteten Ressourcen
Mit [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] können Modell\- und Zuordnungsdatendateien als in eine Anwendung eingebettete Ressourcen bereitgestellt werden.  Die Assembly mit den eingebetteten Modell\- und Zuordnungsdatendateien muss in derselben Anwendungsdomäne geladen werden wie die Entitätsverbindung.  Weitere Informationen finden Sie unter [Verbindungszeichenfolgen](../../../../../docs/framework/data/adonet/ef/connection-strings.md).  Die [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)]\-Tools betten standardmäßig die Modell\- und Zuordnungsdateien ein. Wenn Sie die Modell\- und Zuordnungsdateien manuell definieren, verwenden Sie diese Prozedur, um sicherzustellen, dass die Dateien als eingebettete Ressourcen zusammen mit einer [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]\-Anwendung bereitgestellt werden.  
  
> [!NOTE]
>  Wiederholen Sie diese Prozedur, wenn Modell\- und Zuordnungsdateien geändert werden, um eingebettete Ressourcen beizubehalten.  
  
### So betten Sie Modell\- und Zuordnungsdateien ein  
  
1.  Wählen Sie im **Projektmappen\-Explorer** die konzeptionelle \(CSDL\) Datei aus.  
  
2.  Legen Sie im Bereich **Eigenschaften** die Option **Buildvorgang** auf **Eingebettete Ressource** fest.  
  
3.  Wiederholen Sie die Schritte 1 und 2 für die SSDL\-Speicherdatei und die MSL\-Zuordnungsdatei.  
  
4.  Doppelklicken Sie im **Projektmappen\-Explorer** auf die Datei **App.config**, und ändern Sie anschließend den `Metadata`\-Parameter des `connectionString`\-Attributs unter Verwendung eines der folgenden Formate:  
  
    -   `Metadata=` `res://<assemblyFullName>/<resourceName>;`  
  
    -   `Metadata=` `res://*/<resourceName>;`  
  
    -   `Metadata=res://*;`  
  
     Weitere Informationen finden Sie unter [Verbindungszeichenfolgen](../../../../../docs/framework/data/adonet/ef/connection-strings.md).  
  
## Beispiel  
 Die folgende Verbindungszeichenfolge verweist auf eingebettete Modell\- und Zuordnungsdateien für das [AdventureWorks Sales\-Modell](http://msdn.microsoft.com/de-de/f16cd988-673f-4376-b034-129ca93c7832).  Diese Verbindungszeichenfolge wird in der Datei **App.config** des Projekts gespeichert.  
  
  
  
## Siehe auch  
 [Modellieren und Zuordnen](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)   
 [Vorgehensweise: Definieren der Verbindungszeichenfolge](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)   
 [Gewusst wie: Erstellen einer EntityConnection\-Verbindungszeichenfolge](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)   
 [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/de-de/91076853-0881-421b-837a-f582f36be527)