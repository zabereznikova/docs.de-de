---
title: Modelldefinierte Funktion
ms.date: 03/30/2017
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
ms.openlocfilehash: 973d7ff9f7b76650782d62dcdcab60c8cedde18f
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735581"
---
# <a name="model-defined-function"></a>Modelldefinierte Funktion
Eine *Modell definierte Funktion* ist eine Funktion, die in einem konzeptionellen Modell definiert ist. Der Text einer Modell definierten Funktion wird in [Entity SQL](./ef/language-reference/entity-sql-language.md)ausgedrückt, wodurch die Funktion unabhängig von Regeln oder Sprachen ausgedrückt werden kann, die in der Datenquelle unterstützt werden.  
  
 Eine Definition für eine modelldefinierte Funktion enthält die folgenden Informationen:  
  
- Einen Funktionsnamen. (erforderlich)  
  
- Den Typ des Rückgabewerts. (Optional)  
  
    > [!NOTE]
    > Wenn kein Rückgabetyp angegeben wird, ist der Rückgabewert leer.  
  
- Parameterinformationen. (Optional)  
  
- Ein [Entity SQL](./ef/language-reference/entity-sql-language.md) Ausdruck, der den Hauptteil der Funktion definiert.  
  
 Beachten Sie, dass modelldefinierte Funktionen keine Ausgabeparameter unterstützen. Diese Einschränkung ist vorhanden, damit modelldefinierte Funktionen verfasst werden können.  
  
## <a name="example"></a>Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`.  
  
 ![Screenshot, der ein Modell mit veröffentlichtem Datum anzeigt.](./media/model-defined-function/model-published-date-three-entity-types.gif)  
  
 Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren. Die folgende CSDL definiert eine Funktion im konzeptionellen Modell, das die Anzahl der Jahre zurückgibt, seit eine Instanz eines `Book` (in der Abbildung oben) veröffentlicht wurde.  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselkonzepte im Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
- [Entity Data Model: Primitive Datentypen](entity-data-model-primitive-data-types.md)
