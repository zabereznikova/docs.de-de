---
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: 8dd0e34a6669b2147052befb17b8f4ff8395aabc
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248488"
---
# <a name="where-entity-sql"></a>WHERE (Entity SQL)
Die WHERE-Klausel wird direkt nach der [from](from-entity-sql.md) -Klausel angewendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Ein boolescher Typ.  
  
## <a name="remarks"></a>Hinweise  
 Die WHERE-Klausel verfügt über die gleiche Semantik wie für Transact-SQL. Sie beschränkt die vom Abfrageausdruck zurückgegebenen Objekte, indem die Elemente der Quellauflistung auf diejenigen Elemente eingeschränkt werden, die die Bedingung erfüllen.  
  
```  
select c from cs as c where e  
```  
  
 Der Ausdruck `e` muss einen booleschen Wert haben.  
  
 Die WHERE-Klausel wird direkt nach der FROM-Klausel und vor der Ausführung von Gruppierungs-, Sortierungs- oder Projektionsvorgängen angewendet. Alle in der FROM-Klausel definierten Elementnamen sind für den Ausdruck der WHERE-Klausel sichtbar.  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](entity-sql-reference.md)
- [Abfrageausdrücke](query-expressions-entity-sql.md)
