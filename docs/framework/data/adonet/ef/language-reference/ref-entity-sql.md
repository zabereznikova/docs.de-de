---
title: REF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
ms.openlocfilehash: 9d35306d1299e91ecaa55a7d2818ee1e2982793f
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249197"
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
  
1. Befolgen Sie das Verfahren [unter Gewusst wie: Führen Sie eine Abfrage aus, die PrimitiveType-Ergebnisse](../how-to-execute-a-query-that-returns-primitivetype-results.md)zurückgibt.  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#REF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref)]  
  
## <a name="see-also"></a>Siehe auch

- [DEREF](deref-entity-sql.md)
- [CREATEREF](createref-entity-sql.md)
- [KEY](key-entity-sql.md)
- [Entity SQL-Referenz](entity-sql-reference.md)
- [Typdefinitionen](type-definitions-entity-sql.md)
