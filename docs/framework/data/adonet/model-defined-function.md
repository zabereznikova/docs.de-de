---
title: Modelldefinierte Funktion
ms.date: 03/30/2017
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
ms.openlocfilehash: 77152e8f37b009cbc3e72f053ead867914768d3d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226637"
---
# <a name="model-defined-function"></a>Modelldefinierte Funktion
Ein *modelldefinierte Funktion* ist eine Funktion, die in einem konzeptionellen Modell definiert ist. Der Text einer modelldefinierten Funktion, ausgedrückt in [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md), wodurch für die Funktion unabhängig von ausgedrückt werden Regeln oder Sprachen, die in der Datenquelle unterstützt.  
  
 Eine Definition für eine modelldefinierte Funktion enthält die folgenden Informationen:  
  
-   Einen Funktionsnamen. (erforderlich)  
  
-   Den Typ des Rückgabewerts. (Optional)  
  
    > [!NOTE]
    >  Wenn kein Rückgabetyp angegeben wird, ist der Rückgabewert leer.  
  
-   Parameterinformationen. (Optional)  
  
-   Ein [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md) Ausdruck, der den Textkörper der Funktion definiert.  
  
 Beachten Sie, dass modelldefinierte Funktionen keine Ausgabeparameter unterstützen. Diese Einschränkung ist vorhanden, damit modelldefinierte Funktionen verfasst werden können.  
  
## <a name="example"></a>Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`.  
  
 ![Screenshot mit einem Modell mit Veröffentlichungsdatum.](./media/model-defined-function/model-published-date-three-entity-types.gif)  
  
 Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)), konzeptionelle Modelle zu definieren. Die folgende CSDL definiert eine Funktion im konzeptionellen Modell, das die Anzahl der Jahre zurückgibt, seit eine Instanz eines `Book` (in der Abbildung oben) veröffentlicht wurde.  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
- [Entity Data Model: primitive Datentypen](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)
