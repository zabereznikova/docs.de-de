---
title: CAST (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 07b6d750-dfd4-48a9-b86c-3badcbba6f70
ms.openlocfilehash: 51de041a4b06d5da31071ea2b3cb31c86feff137
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61606163"
---
# <a name="cast-entity-sql"></a>CAST (Entity SQL)
Konvertiert einen Ausdruck von einem Datentyp in einen anderen.  
  
## <a name="syntax"></a>Syntax  
  
```  
CAST ( expression AS data_type )  
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Ein gültiger Ausdruck, der zu `data_type`konvertierbar ist.  
  
 `data_type`  
 Der vom Zielsystem bereitgestellte Datentyp. Dabei muss es sich um einen primitiven (skalaren) Typ handeln. Der verwendete `data_type` hängt von der Abfrageumgebung ab. Wird eine Abfrage mit dem <xref:System.Data.EntityClient.EntityCommand>ausgeführt, ist der Datentyp ein im konzeptionellen Modell definierter Typ. Weitere Informationen finden Sie unter [CSDL Specification](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md). Wenn eine Abfrage mit <xref:System.Data.Objects.ObjectQuery%601>ausgeführt wird, ist der Datentyp ein CLR-Typ.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt denselben Wert zurück wie `data_type`.  
  
## <a name="remarks"></a>Hinweise  
 Der CAST-Ausdruck verfügt über eine ähnliche Semantik wie der CONVERT-Ausdruck von [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] . Der CAST-Ausdruck wird zum Konvertieren eines Werts von einem Typ in einen Wert von einem anderen Typ verwendet.  
  
```  
CAST( e as T )  
```  
  
 Wenn "e" vom Typ "S" ist und "S" zu "T" konvertierbar ist, ist der obige Ausdruck ein gültiger Umwandlungsausdruck. "T" muss dabei ein primitiver (skalarer) Typ sein.  
  
 Beim Umwandeln in `Edm.Decimal`können Werte für die Facets der Genauigkeit und der Dezimalstellenanzahl bereitgestellt werden. Werden keine expliziten Angaben gemacht, sind die Standardwerte für Genauigkeit und Dezimalstellenanzahl 18 bzw. 0. Insbesondere werden folgende Überladungen von `Decimal`unterstützt:  
  
- `CAST( d as Edm.Decimal );`  
  
- `CAST( d as Edm.Decimal(precision) );`  
  
- `CAST( d as Edm.Decimal(precision, scale) );`  
  
 Die Verwendung eines Umwandlungsausdrucks wird als explizite Konvertierung aufgefasst. Explizite Konvertierungen können Daten abschneiden oder zu Genauigkeitsverlust führen.  
  
> [!NOTE]
>  CAST wird nur für primitive Typen und Enumerationsmembertypen unterstützt.  
  
## <a name="example"></a>Beispiel  
 In der folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage wird der CAST-Operator zum Umwandeln des Datentyps eines Ausdrucks in einen anderen verwendet. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#CAST](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#cast)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
