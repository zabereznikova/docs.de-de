---
title: sein. (Memberzugriff) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
ms.openlocfilehash: 6ebedd2b381d035d199e151f64632acf7d502ff5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139710"
---
# <a name="-member-access-entity-sql"></a>sein. (Memberzugriff) (Entity SQL)
Der Punktoperator (.) wird die [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Memberzugriffsoperator. Mit dem Operator für den Memberzugriff kann auf den Wert einer Eigenschaft oder eines Felds der Instanz eines strukturellen konzeptionellen Modelltyps zugegriffen werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
expression.identifier  
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Eine Instanz eines strukturellen konzeptionellen Modelltyps.  
  
 `identifier`  
 Eine Eigenschaft oder ein Feld einer Objektinstanz.  
  
## <a name="remarks"></a>Hinweise  
 Mit dem Punktoperator (.) können Sie Felder eines Datensatzes extrahieren, ähnlich wie beim Extrahieren der Eigenschaften eines komplexen Typs oder Entitätstyps. Wenn z. B. "n" vom Typ "Name" ein Member des Typs "Person" ist und "p" eine Instanz des Typs "Person" ist, ist "p.n" ein zulässiger Memberzugriffsausdruck, der einen Wert des Typs "Name" zurückgibt.  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
