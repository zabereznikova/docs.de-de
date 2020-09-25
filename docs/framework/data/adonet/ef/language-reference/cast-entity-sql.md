---
title: CAST (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 07b6d750-dfd4-48a9-b86c-3badcbba6f70
ms.openlocfilehash: 5591f1947963dde45d34ad2342485af476765709
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198014"
---
# <a name="cast-entity-sql"></a>CAST (Entity SQL)

Konvertiert einen Ausdruck von einem Datentyp in einen anderen.  
  
## <a name="syntax"></a>Syntax  
  
```csharp
CAST ( expression AS data_type )  
```  
  
## <a name="arguments"></a>Argumente  

 `expression`  
 Ein gültiger Ausdruck, der zu `data_type`konvertierbar ist.  
  
 `data_type`  
 Der vom Zielsystem bereitgestellte Datentyp. Dabei muss es sich um einen primitiven (skalaren) Typ handeln. Der verwendete `data_type` hängt von der Abfrageumgebung ab. Wird eine Abfrage mit dem <xref:System.Data.EntityClient.EntityCommand>ausgeführt, ist der Datentyp ein im konzeptionellen Modell definierter Typ. Weitere Informationen finden Sie unter [CSDL Specification](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec). Wenn eine Abfrage mit <xref:System.Data.Objects.ObjectQuery%601>ausgeführt wird, ist der Datentyp ein CLR-Typ.  
  
## <a name="return-value"></a>Rückgabewert  

 Gibt denselben Wert zurück wie `data_type`.  
  
## <a name="remarks"></a>Bemerkungen  

 Der Umwandlungs Ausdruck hat eine ähnliche Semantik wie der Transact-SQL-Konvertierungs Ausdruck. Der CAST-Ausdruck wird zum Konvertieren eines Werts von einem Typ in einen Wert von einem anderen Typ verwendet.  
  
```csharp
CAST( e as T )  
```  
  
 Wenn "e" vom Typ "S" ist und "S" zu "T" konvertierbar ist, ist der obige Ausdruck ein gültiger Umwandlungsausdruck. "T" muss dabei ein primitiver (skalarer) Typ sein.  
  
 Beim Umwandeln in `Edm.Decimal`können Werte für die Facets der Genauigkeit und der Dezimalstellenanzahl bereitgestellt werden. Werden keine expliziten Angaben gemacht, sind die Standardwerte für Genauigkeit und Dezimalstellenanzahl 18 bzw. 0. Insbesondere werden folgende Überladungen von `Decimal`unterstützt:  
  
- `CAST( d as Edm.Decimal );`  
  
- `CAST( d as Edm.Decimal(precision) );`  
  
- `CAST( d as Edm.Decimal(precision, scale) );`  
  
 Die Verwendung eines Umwandlungsausdrucks wird als explizite Konvertierung aufgefasst. Explizite Konvertierungen können Daten abschneiden oder zu Genauigkeitsverlust führen.  
  
> [!NOTE]
> CAST wird nur für primitive Typen und Enumerationsmembertypen unterstützt.  
  
## <a name="example"></a>Beispiel  

 In der folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage wird der CAST-Operator zum Umwandeln des Datentyps eines Ausdrucks in einen anderen verwendet. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Befolgen Sie das Verfahren unter Gewusst [wie: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#CAST](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#cast)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Entity SQL-Referenz](entity-sql-reference.md)
