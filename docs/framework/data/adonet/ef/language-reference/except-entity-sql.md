---
title: EXCEPT (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 69cc23e5-3f8f-4b49-b20e-2f84ff11c80d
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: de4455e997e0fc644fdc5bbef8ff52f84735d133
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="except-entity-sql"></a>EXCEPT (Entity SQL)
Gibt eine Auflistung der vom Abfrageausdruck auf der linken Seite des EXCEPT-Operanden zurückgegebenen und unterschiedlichen Werte zurück, die nicht zusätzlich vom Abfrageausdruck auf der rechten Seite des EXCEPT-Operanden zurückgegeben werden. Alle Ausdrücke müssen vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ sein wie `expression`.  
  
## <a name="syntax"></a>Syntax  
  
```  
expression EXCEPT expression  
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Ein beliebiger gültiger Ausdruck, der eine Auflistung für den Vergleich mit einer von einem anderen Abfrageausdruck zurückgegebenen Auflistung zurückgibt.  
  
## <a name="return-value"></a>Rückgabewert  
 Eine Auflistung vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ wie `expression`.  
  
## <a name="remarks"></a>Hinweise  
 EXCEPT ist einer der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren. Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren werden von links nach rechts ausgewertet. In der folgenden Tabelle wird die Rangfolge der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren dargestellt.  
  
|Rangfolge|Operatoren|  
|----------------|---------------|  
|Höchste|INTERSECT|  
||UNION<br /><br /> UNION ALL|  
||EXCEPT|  
|Niedrigste|EXISTS<br /><br /> OVERLAPS<br /><br /> FLATTEN<br /><br /> SET|  
  
## <a name="example"></a>Beispiel  
 In der folgenden Entity SQL-Abfrage wird ein EXCEPT-Operator verwendet, um eine Auflistung aller unterschiedlicher Werte von zwei Abfrageausdrücken zurückzugeben. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#EXCEPT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#except)]  
  
## <a name="see-also"></a>Siehe auch  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
