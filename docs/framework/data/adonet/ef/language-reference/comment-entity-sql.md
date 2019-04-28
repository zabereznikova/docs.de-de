---
title: -- (Kommentar) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: c10b17931c6024e2a9e947083747435d8aa54fa2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61605989"
---
# <a name="---comment-entity-sql"></a>-- (Kommentar) (Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfragen können Kommentare enthalten. Zwei Bindestriche (`--`) zeigen den Beginn einer Kommentarzeile an.  
  
## <a name="syntax"></a>Syntax  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a>Argumente  
 `text_of_comment`  
 Ist die Zeichenfolge mit dem Kommentartext.  
  
## <a name="example"></a>Beispiel  
 In der folgenden Entity SQL-Abfrage wird die Verwendung von Kommentaren veranschaulicht. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
