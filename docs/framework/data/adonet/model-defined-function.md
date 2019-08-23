---
title: Modelldefinierte Funktion
ms.date: 03/30/2017
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
ms.openlocfilehash: 05a44e86a118b649490cde849c8ca2c2bb0d2f15
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934521"
---
# <a name="model-defined-function"></a>Modelldefinierte Funktion
Eine *Modell definierte Funktion* ist eine Funktion, die in einem konzeptionellen Modell definiert ist. Der Text einer Modell definierten Funktion wird in [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)ausgedrückt, wodurch die Funktion unabhängig von Regeln oder Sprachen ausgedrückt werden kann, die in der Datenquelle unterstützt werden.  
  
 Eine Definition für eine modelldefinierte Funktion enthält die folgenden Informationen:  
  
- Einen Funktionsnamen. (erforderlich)  
  
- Den Typ des Rückgabewerts. (Optional)  
  
    > [!NOTE]
    > Wenn kein Rückgabetyp angegeben wird, ist der Rückgabewert leer.  
  
- Parameterinformationen. (Optional)  
  
- Ein [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md) Ausdruck, der den Hauptteil der Funktion definiert.  
  
 Beachten Sie, dass modelldefinierte Funktionen keine Ausgabeparameter unterstützen. Diese Einschränkung ist vorhanden, damit modelldefinierte Funktionen verfasst werden können.  
  
## <a name="example"></a>Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`.  
  
 ![Screenshot, der ein Modell mit veröffentlichtem Datum anzeigt.](./media/model-defined-function/model-published-date-three-entity-types.gif)  
  
 Der [ADO.NET-Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)), um konzeptionelle Modelle zu definieren. Die folgende CSDL definiert eine Funktion im konzeptionellen Modell, das die Anzahl der Jahre zurückgibt, seit eine Instanz eines `Book` (in der Abbildung oben) veröffentlicht wurde.  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
- [Entity Data Model: Primitive Datentypen](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)
