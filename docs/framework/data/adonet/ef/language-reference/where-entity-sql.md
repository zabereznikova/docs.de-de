---
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: 43c038e9ff0acfdeff88492aa2ca34fbf4ada94a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="where-entity-sql"></a>WHERE (Entity SQL)
Die WHERE-Klausel direkt nach dem gilt die [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) Klausel.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Ein boolescher Typ.  
  
## <a name="remarks"></a>Hinweise  
 Die WHERE[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]-Klausel hat die für  beschriebene Semantik. Sie beschränkt die vom Abfrageausdruck zurückgegebenen Objekte, indem die Elemente der Quellauflistung auf diejenigen Elemente eingeschränkt werden, die die Bedingung erfüllen.  
  
```  
select c from cs as c where e  
```  
  
 Der Ausdruck `e` muss einen booleschen Wert haben.  
  
 Die WHERE-Klausel wird direkt nach der FROM-Klausel und vor der Ausführung von Gruppierungs-, Sortierungs- oder Projektionsvorgängen angewendet. Alle in der FROM-Klausel definierten Elementnamen sind für den Ausdruck der WHERE-Klausel sichtbar.  
  
## <a name="see-also"></a>Siehe auch  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Abfrageausdrücke](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
