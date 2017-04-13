---
title: "Anpassen von Insert-, Update- und Delete-Operationen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 07eef055-8f6c-414d-850e-d323ff946cd0
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Anpassen von Insert-, Update- und Delete-Operationen
Standardmäßig generiert [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] dynamisches SQL, um Insert\-, Read\-, Update und Delete\-Operationen zu implementieren.  In der Praxis passen Sie die Anwendung i. d. R. an, um die Geschäftsanforderungen zu erfüllen.  
  
> [!NOTE]
>  Wenn Sie [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] verwenden, können Sie mit [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] Einfüge\-, Update\- und Löschvorgänge anpassen.  
  
 Dieser Abschnitt beschreibt die Techniken, die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zur Anpassung von Insert\-, Update\- und Delete\-Operationen in Ihrer Anwendung zur Verfügung stellt.  
  
## In diesem Abschnitt  
 [Anpassen von Operationen: Übersicht](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-overview.md)  
 Beschreibt die verschiedenen Techniken, die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] für das Anpassen von Insert\-, Update\- und Delete\-Operationen zur Verfügung stellt.  
  
 [Insert\-, Update\- und Delete\-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/insert-update-and-delete-operations.md)  
 Beschreibt die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Standardverfahren zum Bearbeiten von Datenbankdaten.  
  
 [Aufgaben des Entwicklers beim Überschreiben des Standardverhaltens](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)  
 Beschreibt die Rolle des Entwicklers bei der Implementierung von Anforderungen, die nicht von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] durchgesetzt wurden.  
  
 [Hinzufügen von Geschäftslogik durch das Verwenden partieller Methoden](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)  
 Beschreibt, wie partielle Methoden verwendet werden, um automatisch generierte Methoden zu überschreiben.