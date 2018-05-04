---
title: REF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
ms.openlocfilehash: fdad27e52f3cdc366415ed585d4bd80542a6915f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ref-entity-sql"></a>REF (Entity SQL)
Gibt einen Verweis auf eine Entitätsinstanz zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
REF( expression )   
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Gültige Ausdrücke, die eine Instanz eines Entitätstyps zurückgeben.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf die angegebene Entitätsinstanz.  
  
## <a name="remarks"></a>Hinweise  
 Ein Entitätsverweis besteht aus dem Entitätsschlüssel und einem Entitätenmengennamen. Da unterschiedliche Entitätenmengen auf demselben Typ basieren können, kann ein bestimmter Entitätsschlüssel in mehreren Entitätenmengen erscheinen. Ein Entitätsverweis ist jedoch stets eindeutig. Wenn der Eingabeausdruck eine permanente Entität darstellt, wird ein Verweis auf diese Entität zurückgegeben. Wenn der Eingabeausdruck keine permanente Entität ist, wird ein NULL-Verweis zurückgegeben.  
  
 Wird der Eigenschaftsextraktionsoperator (.) für den Zugriff auf eine Eigenschaft verwendet, wird der Verweis automatisch dereferenziert.  
  
## <a name="example"></a>Beispiel  
 Die folgende Entity SQL-Abfrage verwendet den REF-Operator, um den Verweis für ein Eingabeentitätsargument zurückzugeben. Dieselbe Abfrage dereferenziert den Verweis, da ein Eigenschaftsextraktionsoperator (.) für den Zugriff auf eine Eigenschaft der "Product"-Entität verwendet wird. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Verwenden Sie das Verfahren in [Vorgehensweise: Ausführen einer Abfrage, gibt PrimitiveType-Ergebnisse](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#REF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref)]  
  
## <a name="see-also"></a>Siehe auch  
 [DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)  
 [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
 [KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Typdefinitionen](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)
