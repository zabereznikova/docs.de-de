---
title: sein. (Memberzugriff) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
ms.openlocfilehash: fdcd026d245b3f6d6ecaccc0f828f3d77fd6ce1a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
