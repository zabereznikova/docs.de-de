---
title: "Vorgehensweise: Aktivieren der Serialisierbarkeit von Entit&#228;ten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Vorgehensweise: Aktivieren der Serialisierbarkeit von Entit&#228;ten
Sie können die Serialisierbarkeit von Entitäten aktivieren, wenn Sie den Code generieren.  Entitätsklassen werden mit dem <xref:System.Runtime.Serialization.DataContractAttribute>\-Attribut und Spalten mit dem <xref:System.Runtime.Serialization.DataMemberAttribute>\-Attribut ergänzt.  
  
 Entwickler, die mit [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] arbeiten, können für diesen Zweck den [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] verwenden.  
  
 Wenn Sie mit dem SQLMetal\-Befehlszeilentool arbeiten, verwenden Sie die **\/serialization**\-Option mit dem `unidirectional`\-Argument.  Weitere Informationen finden Sie unter [SqlMetal.exe \(Tool zur Codegenerierung\)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## Beispiel  
 Die folgenden SQLMetal\-Befehlszeilen erzeugen Dateien, die serialisierbare Entitäten aufweisen.  
  
```  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## Siehe auch  
 [Serialisierung](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md)   
 [Erstellen des Objektmodells](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)