---
title: "Anpassen von Operationen durch Verwenden gespeicherter Prozeduren | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aedbecc1-c33c-4fb4-8861-fdf7e1dc6b8a
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Anpassen von Operationen durch Verwenden gespeicherter Prozeduren
Gespeicherte Prozeduren stellen einen allgemeinen Ansatz zum Überschreiben des Standardverhaltens dar.  Die Beispiele in diesem Absatz zeigen, wie Sie erzeugte Methoden für gespeicherte Prozeduren verwenden und wie Sie gespeicherte Prozeduren direkt aufrufen können.  
  
 Wenn Sie [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] verwenden, können Sie mit dem [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] gespeicherte Prozeduren zuweisen, um Daten einzufügen, zu aktualisieren und zu löschen.  
  
> [!NOTE]
>  Um datenbankgenerierte Werte einzulesen, verwenden Sie Ausgabeparameter in den gespeicherten Prozeduren.  Wenn Sie keine Ausgabeparameter verwenden können, schreiben Sie eine partielle Methodenimplementierung, anstatt sich auf den von [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] erzeugten Code zu verlassen.  Member, die datenbankgenerierten Werten zugeordnet sind, müssen auf die entsprechenden Werte festgelegt werden, nach dem die `INSERT`\-Operation oder die `UPDATE`\-Operation erfolgreich abgeschlossen wurde.  Weitere Informationen finden Sie unter [Aufgaben des Entwicklers beim Überschreiben des Standardverhaltens](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md).  
  
## Beispiel  
  
### Beschreibung  
 Nehmen Sie im folgenden Beispiel an, dass die `Northwind`\-Klasse zwei Methoden zum Aufruf gespeicherter Prozeduren enthält, die für Überschreibungen in einer abgeleiteten Klasse verwendet werden.  
  
### Code  
 [!code-csharp[DLinqOverrideDefaultSproc#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefaultSproc#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#1)]  
  
## Beispiel  
  
### Beschreibung  
 Die folgende Klasse verwendet diese Methoden für die Überschreibung.  
  
### Code  
 [!code-csharp[DLinqOverrideDefaultSproc#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefaultSproc#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#2)]  
  
## Beispiel  
  
### Beschreibung  
 Sie können `NorthwindThroughSprocs` genau so wie `Northwnd` verwenden.  
  
### Code  
 [!code-csharp[DLinqOverrideDefaultSproc#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefaultSproc#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#3)]  
  
## Siehe auch  
 [Aufgaben des Entwicklers beim Überschreiben des Standardverhaltens](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)