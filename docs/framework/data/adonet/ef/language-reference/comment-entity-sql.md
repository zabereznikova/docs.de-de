---
title: -- (Kommentar) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 4b3c801999d520a775c1a7026c945c027145b59d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32764163"
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
  
1.  Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
