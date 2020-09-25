---
title: -- (Kommentar) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 9ad6e38726d0802c3bc2090a4e6f11f008828ee5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197897"
---
# <a name="---comment-entity-sql"></a>-- (Kommentar) (Entity SQL)

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfragen können Kommentare enthalten. Zwei Bindestriche (`--`) zeigen den Beginn einer Kommentarzeile an.  
  
## <a name="syntax"></a>Syntax  
  
```csharp  
-- text_of_comment  
```  
  
## <a name="arguments"></a>Argumente  

 `text_of_comment`  
 Die Zeichenfolge mit dem Kommentartext.  
  
## <a name="example"></a>Beispiel  

 In der folgenden Entity SQL-Abfrage wird die Verwendung von Kommentaren veranschaulicht. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Entity SQL](entity-sql-overview.md)
- [Entity SQL-Referenz](entity-sql-reference.md)
