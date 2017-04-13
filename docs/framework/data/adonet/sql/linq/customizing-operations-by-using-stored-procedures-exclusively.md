---
title: "Anpassen von Operationen durch ausschlie&#223;liche Verwendung von gespeicherten Prozeduren | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Anpassen von Operationen durch ausschlie&#223;liche Verwendung von gespeicherten Prozeduren
Der Zugriff auf Daten nur mit gespeicherten Prozeduren ist ein gängiges Szenario.  
  
## Beispiel  
  
### Beschreibung  
 Sie können das Beispiel in [Anpassen von Operationen durch Verwenden gespeicherter Prozeduren](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md) modifizieren, indem Sie die erste Abfrage \(die zu einer Ausführung von dynamischem SQL führt\) durch einen Methodenaufruf ersetzen, der eine gespeicherte Prozedur umschließt.  
  
 Gehen Sie wie im folgenden Beispiel von der `CustomersByCity`\-Methode aus.  
  
### Code  
 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 Der folgende Code wird ohne jedes dynamische SQL ausgeführt.  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## Siehe auch  
 [Aufgaben des Entwicklers beim Überschreiben des Standardverhaltens](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)