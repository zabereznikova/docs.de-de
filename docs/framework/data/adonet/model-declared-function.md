---
title: Im Modell deklarierte Funktion
ms.date: 03/30/2017
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
ms.openlocfilehash: fb30dd86c29d6a7fff6f2c71d5fd892326e1fda4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147852"
---
# <a name="model-declared-function"></a>Im Modell deklarierte Funktion

Eine *Modell deklarierte Funktion* ist eine Funktion, die in einem konzeptionellen Modell deklariert ist, aber nicht in diesem konzeptionellen Modell definiert ist. Die Funktion kann in der Hosting- oder Speicherumgebung definiert werden. Eine im Modell deklarierte Funktion kann z. B. einer in einer Datenbank definierten Funktion zugeordnet werden, sodass die serverseitige Funktionalität im konzeptionellen Modell verfügbar gemacht wird.  
  
 Die Deklaration einer im Modell deklarierten Funktion enthält die folgenden Informationen:  
  
- Der Name der Funktion. (Erforderlich)  
  
- Den Typ des Rückgabewerts. (Optional)  
  
    > [!NOTE]
    > Wenn kein Rückgabewert angegeben wird, ist der Rückgabetyp leer.  
  
- Parameterinformationen, einschließlich Parametername und -typ. (Optional)  
  
## <a name="example"></a>Beispiel  

 Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren. In CSDL ist eine Implementierung einer Modell deklarierten Funktion ein Funktions Import (mithilfe des [FunctionImport-Elements](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)). Die folgende CSDL definiert einen Entitätscontainer mit einer Funktionsimportdefinition. Beachten Sie, dass der Rückgabetyp für die Funktion leer ist, da kein Rückgabetyp angegeben wird.  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Schlüsselkonzepte im Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
