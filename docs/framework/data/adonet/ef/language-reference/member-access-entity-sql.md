---
title: . (Memberzugriff) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
ms.openlocfilehash: 1db6be632da90eaa7a761bb213e395182ae42347
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250296"
---
# <a name="-member-access-entity-sql"></a>. (Memberzugriff) (Entity SQL)
Der Punkt Operator (.) ist der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Member Access-Operator. Mit dem Operator für den Memberzugriff kann auf den Wert einer Eigenschaft oder eines Felds der Instanz eines strukturellen konzeptionellen Modelltyps zugegriffen werden.  
  
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

- [Entity SQL-Referenz](entity-sql-reference.md)
