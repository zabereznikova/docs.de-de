---
title: COLLECTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
ms.openlocfilehash: 5a1af1aab8a084b19e48fbdbb159d7ddd8a8dd7c
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039911"
---
# <a name="collection-entity-sql"></a>COLLECTION (Entity SQL)
Das COLLECTION-Schlüsselwort wird nur in der Definition einer Inlinefunktion verwendet. Auflistungsfunktionen sind Funktionen, die sich auf eine Reihe von Werten auswirken und eine Skalarausgabe erzeugen.  
  
## <a name="syntax"></a>Syntax  
  
```csharp  
COLLECTION(type_definition)
```  
  
## <a name="arguments"></a>Argumente  
 `type_definition`  
 Ein Ausdruck, der eine Auflistung von unterstützten Typen, Zeilen oder Verweisen zurückgibt.  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zum COLLECTION-Schlüsselwort finden Sie unter [Type Definitions](type-definitions-entity-sql.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie mit dem COLLECTION-Schlüsselwort eine Auflistung von Dezimalziffern als Argument für eine Inlineabfragefunktion deklariert wird.  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](entity-sql-reference.md)
