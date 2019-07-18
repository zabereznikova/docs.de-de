---
title: Im Modell deklarierte Funktion
ms.date: 03/30/2017
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
ms.openlocfilehash: a0bea36693122c77d9c1abdf4484ee8e68627a0c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645877"
---
# <a name="model-declared-function"></a>Im Modell deklarierte Funktion
Ein *im Modell deklarierte Funktion* ist eine Funktion, die in einem konzeptionellen Modell deklariert ist, aber nicht in diesem konzeptionellen Modell definiert ist. Die Funktion kann in der Hosting- oder Speicherumgebung definiert werden. Eine im Modell deklarierte Funktion kann z. B. einer in einer Datenbank definierten Funktion zugeordnet werden, sodass die serverseitige Funktionalität im konzeptionellen Modell verfügbar gemacht wird.  
  
 Die Deklaration einer im Modell deklarierten Funktion enthält die folgenden Informationen:  
  
- Der Name der Funktion. (erforderlich)  
  
- Den Typ des Rückgabewerts. (Optional)  
  
    > [!NOTE]
    >  Wenn kein Rückgabewert angegeben wird, ist der Rückgabetyp leer.  
  
- Parameterinformationen, einschließlich Parametername und -typ. (Optional)  
  
## <a name="example"></a>Beispiel  
 Die [ADO.NET Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), konzeptionelle Modelle zu definieren. In CSDL ist eine Implementierung einer im Modell deklarierte Funktion eines Funktionsimports (mithilfe der [FunctionImport-Element](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)). Die folgende CSDL definiert einen Entitätscontainer mit einer Funktionsimportdefinition. Beachten Sie, dass der Rückgabetyp für die Funktion leer ist, da kein Rückgabetyp angegeben wird.  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
