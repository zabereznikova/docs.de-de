---
title: + (Zeichen folgen Verkettung) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
ms.openlocfilehash: 9c078e193eeecd4d331c5e3c04c66dee2c4a1daa
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319316"
---
# <a name="-string-concatenation-entity-sql"></a>+ (Zeichenfolgenverkettung) (Entity SQL)
Verkettet zwei Zeichenfolgen.  
  
## <a name="syntax"></a>Syntax  
  
```sql  
expression + expression  
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Jeder gültige Ausdruck des Datentyps EDM.String. Beide Ausdrücke müssen denselben Datentyp aufweisen, oder ein Ausdruck muss implizit in den Datentyp des anderen Ausdrucks konvertiert werden können.  
  
## <a name="result-types"></a>Ergebnistypen  
 Der Datentyp, der sich aus der impliziten Datentyphöherstufung der zwei Argumente ergibt. Weitere Informationen zur impliziten herauf Stufung von Typen finden Sie unter [Type System (Typsystem](type-system-entity-sql.md)).  
  
## <a name="example"></a>Beispiel  
 Die folgende Entity SQL-Abfrage verwendet den Operator "+", um zwei Zeichenfolgen zu verketten. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Befolgen Sie das Verfahren unter Gewusst [wie: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:  
  
 [!code-sql[DP EntityServices Concepts#CONCAT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#concat)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](entity-sql-reference.md)
- [Konzeptionelle Modelltypen (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
