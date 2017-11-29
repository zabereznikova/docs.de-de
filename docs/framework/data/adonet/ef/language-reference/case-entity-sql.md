---
title: CASE (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26a47873-e87d-4ba2-9e2c-3787c21efe89
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f4e92d9a7c66d176357499bc831f07c56f36c90d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="case-entity-sql"></a>CASE (Entity SQL)
Wertet eine Reihe von `Boolean` -Ausdrücken aus, um das Ergebnis zu bestimmen.  
  
## <a name="syntax"></a>Syntax  
  
```  
CASE  
     WHEN Boolean_expression THEN result_expression   
    [ ...n ]   
     [   
    ELSE else_result_expression   
     ]   
END  
```  
  
## <a name="arguments"></a>Argumente  
 `n`  
 Ist ein Platzhalter, der angibt, dass mehrere WHEN `Boolean_expression` THEN `result_expression` -Klauseln verwendet werden können.  
  
 THEN `result_expression`  
 Ist der zurückgegebene Ausdruck, wenn `Boolean_expression` den Wert `true`ergibt. `result expression` ist ein beliebiger gültiger Ausdruck.  
  
 ELSE `else_result_expression`  
 Der Ausdruck, der zurückgegeben wird, wenn keine Vergleichsoperation `true`ergibt. Wenn dieses Argument nicht angegeben wird und keine Vergleichsoperation `true`ergibt, gibt die CASE-Funktion null zurück. `else_result_expression` ist ein beliebiger gültiger Ausdruck. Die Datentypen von `else_result_expression` und allen `result_expression` -Ausdrücken müssen gleich sein, oder es muss eine implizite Konvertierung vorliegen.  
  
 WHEN `Boolean_expression`  
 Der `Boolean` -Ausdruck, der ausgewertet wird, wenn das gesuchte CASE-Format verwendet wird. `Boolean_expression` ist ein beliebiger gültiger `Boolean` -Ausdruck.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt den Typ mit der höchsten Priorität in `result_expression` und im optionalen `else_result_expression`zurück.  
  
## <a name="remarks"></a>Hinweise  
 Der CASE-Ausdruck von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ähnelt dem CASE-Ausdruck von [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] . Mit dem CASE-Ausdruck wird eine Reihe von Bedingungen geprüft, um zu ermitteln, welcher Ausdruck das passende Ergebnis ergibt. Diese Form des CASE-Ausdrucks ist für einen oder eine Reihe von `Boolean` -Ausdrücken geeignet, um den korrekten Ergebnisausdruck zu ermitteln.  
  
 Die CASE-Funktion wertet `Boolean_expression` für jede WHEN-Klausel in der angegebenen Reihenfolge aus und gibt `result_expression` des ersten `Boolean_expression` zurück, der `true`ergibt. Die übrigen Ausdrücke werden nicht ausgewertet. Ergibt kein `Boolean_expression` den Wert `true`, gibt das Datenbankmodul den `else_result_expression` -Ausdruck zurück, sofern eine ELSE-Klausel angegeben wurde, oder einen NULL-Wert, wenn keine ELSE-Klausel angegeben wurde.  
  
 Eine CASE-Anweisung kann keinen multiset-Wert zurückgeben.  
  
## <a name="example"></a>Beispiel  
 In der folgenden Entity SQL-Abfrage wird der CASE-Ausdruck zur Auswertung eines Satzes von `Boolean` -Ausdrücken verwendet, um das Ergebnis zu bestimmen. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Verwenden Sie das Verfahren in [Vorgehensweise: Ausführen einer Abfrage, gibt PrimitiveType-Ergebnisse](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a>Siehe auch  
 [KLICKEN SIE DANN](../../../../../../docs/framework/data/adonet/ef/language-reference/then-entity-sql.md)  
 [WÄHLEN SIE](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
