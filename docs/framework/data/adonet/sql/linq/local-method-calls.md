---
title: "Aufrufe einer lokalen Methode | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c34b5012-aee9-4994-9364-1d99d12b7463
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Aufrufe einer lokalen Methode
Ein Aufruf einer lokalen Methode wird innerhalb des Objektmodells ausgeführt.  Ein Remotemethodenaufruf wird von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in SQL übersetzt und zur Ausführung an das Datenbankmodul übergeben.  Aufrufe einer lokalen Methode werden benötigt, wenn [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] den Aufruf nicht in SQL übersetzen kann.  Andernfalls wird eine <xref:System.InvalidOperationException> ausgelöst.  
  
## Beispiel 1  
 Im folgenden Beispiel wird veranschaulicht, wie eine `Order`\-Klasse der Tabelle Bestellungen in der Datenbank Northwind zugewiesen wird.  Eine lokale Instanzmethode wurde der Klasse hinzugefügt.  
  
 In Abfrage 1 wird der Konstruktor für die `Order`\-Klasse lokal ausgeführt.  Hat [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in Abfrage 2 versucht, `LocalInstanceMethod()` in SQL zu übersetzen, würde der Versuch fehlschlagen, und eine <xref:System.InvalidOperationException>\-Ausnahme würde ausgelöst. Aber da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Aufrufe einer lokalen Methode unterstützt, löst Abfrage 2 keine Ausnahme aus.  
  
 [!code-csharp[DlinqLocalMethodCall#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/Program.cs#1)]
 [!code-vb[DlinqLocalMethodCall#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/Module1.vb#1)]  
  
 [!code-csharp[DlinqLocalMethodCall#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/northwind.cs#2)]
 [!code-vb[DlinqLocalMethodCall#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/northwind.vb#2)]  
  
## Siehe auch  
 [Hintergrundinformationen](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)