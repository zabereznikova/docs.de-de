---
title: . (Memberzugriff) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
ms.openlocfilehash: 82cd2f17b2b5ea484a8202b50619047b428fe94a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192151"
---
# <a name="-member-access-entity-sql"></a>. (Memberzugriff) (Entity SQL)

Der Punkt Operator (.) ist der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Member Access-Operator. Mit dem Operator für den Memberzugriff kann auf den Wert einer Eigenschaft oder eines Felds der Instanz eines strukturellen konzeptionellen Modelltyps zugegriffen werden.  
  
## <a name="syntax"></a>Syntax  
  
```sql  
expression.identifier  
```  
  
## <a name="arguments"></a>Argumente  

 `expression`  
 Eine Instanz eines strukturellen konzeptionellen Modelltyps.  
  
 `identifier`  
 Eine Eigenschaft oder ein Feld einer Objektinstanz.  
  
## <a name="remarks"></a>Bemerkungen  

 Mit dem Punktoperator (.) können Sie Felder eines Datensatzes extrahieren, ähnlich wie beim Extrahieren der Eigenschaften eines komplexen Typs oder Entitätstyps. Wenn z. B. "n" vom Typ "Name" ein Member des Typs "Person" ist und "p" eine Instanz des Typs "Person" ist, ist "p.n" ein zulässiger Memberzugriffsausdruck, der einen Wert des Typs "Name" zurückgibt.  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## <a name="see-also"></a>Weitere Informationen

- [Entity SQL-Referenz](entity-sql-reference.md)
