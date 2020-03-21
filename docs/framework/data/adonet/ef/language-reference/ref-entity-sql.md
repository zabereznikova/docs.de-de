---
title: REF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
ms.openlocfilehash: 40a5afd7eb99dba7cae8fe14ed0a45213fda94a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149946"
---
# <a name="ref-entity-sql"></a>REF (Entity SQL)
Gibt einen Verweis auf eine Entitätsinstanz zurück.  
  
## <a name="syntax"></a>Syntax  
  
```sql  
REF( expression )
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Gültige Ausdrücke, die eine Instanz eines Entitätstyps zurückgeben.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf die angegebene Entitätsinstanz.  
  
## <a name="remarks"></a>Bemerkungen  
 Ein Entitätsverweis besteht aus dem Entitätsschlüssel und einem Entitätenmengennamen. Da unterschiedliche Entitätenmengen auf demselben Typ basieren können, kann ein bestimmter Entitätsschlüssel in mehreren Entitätenmengen erscheinen. Ein Entitätsverweis ist jedoch stets eindeutig. Wenn der Eingabeausdruck eine permanente Entität darstellt, wird ein Verweis auf diese Entität zurückgegeben. Wenn der Eingabeausdruck keine permanente Entität ist, wird ein NULL-Verweis zurückgegeben.  
  
 Wird der Eigenschaftsextraktionsoperator (.) für den Zugriff auf eine Eigenschaft verwendet, wird der Verweis automatisch dereferenziert.  
  
## <a name="example"></a>Beispiel  
 Die folgende Entity SQL-Abfrage verwendet den REF-Operator, um den Verweis für ein Eingabeentitätsargument zurückzugeben. Dieselbe Abfrage dereferenziert den Verweis, da ein Eigenschaftsextraktionsoperator (.) für den Zugriff auf eine Eigenschaft der "Product"-Entität verwendet wird. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Gehen Sie wie folgt unter [Gewusst wie: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt.](../how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:  
  
 [!code-sql[DP EntityServices Concepts#REF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#ref)]  
  
## <a name="see-also"></a>Weitere Informationen

- [DEREF](deref-entity-sql.md)
- [CREATEREF](createref-entity-sql.md)
- [Schlüssel](key-entity-sql.md)
- [Entity SQL-Referenz](entity-sql-reference.md)
- [Typdefinitionen](type-definitions-entity-sql.md)
