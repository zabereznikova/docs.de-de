---
title: + (Hinzufügen)
ms.date: 03/30/2017
ms.assetid: 51769b02-a8f7-4177-9e99-bbd10e77092c
ms.openlocfilehash: 62bb4782f135309eed8efa7e182fd8b75f92e126
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040289"
---
# <a name="-add"></a>+ (Addition)
Addiert zwei Zahlen.  
  
## <a name="syntax"></a>Syntax  
  
```csharp  
expression + expression  
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Jeder gültige Ausdruck mit einem numerischen Datentyp.  
  
## <a name="result-types"></a>Ergebnistypen  
 Der Datentyp, der sich aus der impliziten Datentyphöherstufung der zwei Argumente ergibt. Weitere Informationen zur impliziten herauf Stufung von Typen finden Sie unter [Type System (Typsystem](type-system-entity-sql.md)).  
  
## <a name="remarks"></a>Hinweise  
 Für EDM.String-Typen wird Addition als Verkettung durchgeführt.  
  
## <a name="example"></a>Beispiel  
 Die folgende Entity SQL-Abfrage verwendet den arithmetischen Operator +, um zwei Zahlen zu addieren. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#ADD](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#add)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](entity-sql-reference.md)
- [Konzeptionelle Modelltypen (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
