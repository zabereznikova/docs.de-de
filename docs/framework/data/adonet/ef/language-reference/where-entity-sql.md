---
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: 939d4c0ec2c30bc71b22fb65ab36644e063f97de
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489849"
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
 Die WHERE-Klausel weist dieselbe Semantik wie für Transact-SQL beschrieben. Sie beschränkt die vom Abfrageausdruck zurückgegebenen Objekte, indem die Elemente der Quellauflistung auf diejenigen Elemente eingeschränkt werden, die die Bedingung erfüllen.  
  
```  
select c from cs as c where e  
```  
  
 Der Ausdruck `e` muss einen booleschen Wert haben.  
  
 Die WHERE-Klausel wird direkt nach der FROM-Klausel und vor der Ausführung von Gruppierungs-, Sortierungs- oder Projektionsvorgängen angewendet. Alle in der FROM-Klausel definierten Elementnamen sind für den Ausdruck der WHERE-Klausel sichtbar.  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Abfrageausdrücke](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
