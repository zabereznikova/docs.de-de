---
title: CASE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 26a47873-e87d-4ba2-9e2c-3787c21efe89
ms.openlocfilehash: 65d038564683e0a97939cabc7081be3341f4542d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162801"
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
 Ist der zurückgegebene Ausdruck, wenn `Boolean_expression` den Wert `true`ergibt. `result expression` Kann jeder gültige Ausdruck.  
  
 ELSE `else_result_expression`  
 Der Ausdruck, der zurückgegeben wird, wenn keine Vergleichsoperation `true`ergibt. Wenn dieses Argument nicht angegeben wird und keine Vergleichsoperation `true`ergibt, gibt die CASE-Funktion null zurück. `else_result_expression` Kann jeder gültige Ausdruck. Die Datentypen von `else_result_expression` und allen `result_expression` -Ausdrücken müssen gleich sein, oder es muss eine implizite Konvertierung vorliegen.  
  
 WHEN `Boolean_expression`  
 Der `Boolean` -Ausdruck, der ausgewertet wird, wenn das gesuchte CASE-Format verwendet wird. `Boolean_expression` bezeichnet jeden gültigen `Boolean` Ausdruck.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt den Typ mit der höchsten Priorität in `result_expression` und im optionalen `else_result_expression`zurück.  
  
## <a name="remarks"></a>Hinweise  
 Der CASE-Ausdruck von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ähnelt dem CASE-Ausdruck von [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] . Mit dem CASE-Ausdruck wird eine Reihe von Bedingungen geprüft, um zu ermitteln, welcher Ausdruck das passende Ergebnis ergibt. Diese Form des CASE-Ausdrucks ist für einen oder eine Reihe von `Boolean` -Ausdrücken geeignet, um den korrekten Ergebnisausdruck zu ermitteln.  
  
 Die CASE-Funktion wertet `Boolean_expression` für jede WHEN-Klausel in der angegebenen Reihenfolge aus und gibt `result_expression` des ersten `Boolean_expression` zurück, der `true`ergibt. Die übrigen Ausdrücke werden nicht ausgewertet. Ergibt kein `Boolean_expression` den Wert `true`, gibt die Datenbank-Engine den `else_result_expression` -Ausdruck zurück, sofern eine ELSE-Klausel angegeben wurde, oder einen NULL-Wert, wenn keine ELSE-Klausel angegeben wurde.  
  
 Eine CASE-Anweisung kann keinen multiset-Wert zurückgeben.  
  
## <a name="example"></a>Beispiel  
 In der folgenden Entity SQL-Abfrage wird der CASE-Ausdruck zur Auswertung eines Satzes von `Boolean` -Ausdrücken verwendet, um das Ergebnis zu bestimmen. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a>Siehe auch

- [THEN](../../../../../../docs/framework/data/adonet/ef/language-reference/then-entity-sql.md)
- [SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)
- [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
