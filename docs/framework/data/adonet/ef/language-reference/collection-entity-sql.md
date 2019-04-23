---
title: COLLECTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
ms.openlocfilehash: 8cd440571726796ee3d2c91e0d2f6b50571e8e27
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59217756"
---
# <a name="collection-entity-sql"></a>COLLECTION (Entity SQL)
Das COLLECTION-Schlüsselwort wird nur in der Definition einer Inlinefunktion verwendet. Auflistungsfunktionen sind Funktionen, die sich auf eine Reihe von Werten auswirken und eine Skalarausgabe erzeugen.  
  
## <a name="syntax"></a>Syntax  
  
```  
COLLECTION(type_definition)   
```  
  
## <a name="arguments"></a>Argumente  
 `type_definition`  
 Ein Ausdruck, der eine Auflistung von unterstützten Typen, Zeilen oder Verweisen zurückgibt.  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zum COLLECTION-Schlüsselwort finden Sie unter [Type Definitions](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie mit dem COLLECTION-Schlüsselwort eine Auflistung von Dezimalziffern als Argument für eine Inlineabfragefunktion deklariert wird.  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
