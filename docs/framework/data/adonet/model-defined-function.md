---
title: Modelldefinierte Funktion
ms.date: 03/30/2017
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
ms.openlocfilehash: 371af3ae090e37cfd425a9e9d5946bb0751dc527
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54538881"
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
  
 ![Modell mit Veröffentlichungsdatum](../../../../docs/framework/data/adonet/media/modelwithpublisheddate.gif "ModelWithPublishedDate")  
  
 Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)), konzeptionelle Modelle zu definieren. Die folgende CSDL definiert eine Funktion im konzeptionellen Modell, das die Anzahl der Jahre zurückgibt, seit eine Instanz eines `Book` (in der Abbildung oben) veröffentlicht wurde.  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a>Siehe auch
- [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
- [Entity Data Model: Primitive Datentypen](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)
