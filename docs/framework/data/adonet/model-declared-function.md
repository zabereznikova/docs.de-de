---
title: Im Modell deklarierte Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0e47c89524bf149d862ae872c0c5956b7debd818
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="model-declared-function"></a>Im Modell deklarierte Funktion
Ein *im Modell deklarierte Funktion* ist eine Funktion, die in einem konzeptionellen Modell deklariert ist, aber nicht in diesem konzeptionellen Modell definiert ist. Die Funktion kann in der Hosting- oder Speicherumgebung definiert werden. Eine im Modell deklarierte Funktion kann z. B. einer in einer Datenbank definierten Funktion zugeordnet werden, sodass die serverseitige Funktionalität im konzeptionellen Modell verfügbar gemacht wird.  
  
 Die Deklaration einer im Modell deklarierten Funktion enthält die folgenden Informationen:  
  
-   Der Name der Funktion. (erforderlich)  
  
-   Den Typ des Rückgabewerts. (Optional)  
  
    > [!NOTE]
    >  Wenn kein Rückgabewert angegeben wird, ist der Rückgabetyp leer.  
  
-   Parameterinformationen, einschließlich Parametername und -typ. (Optional)  
  
## <a name="example"></a>Beispiel  
 Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) um konzeptionelle Modelle zu definieren. In CSDL ist eine Implementierung einer im Modell deklarierte Funktion ist ein [Funktionsimport](http://msdn.microsoft.com/en-us/125704ae-56c7-4233-80b7-389a10f3a65d). Die folgende CSDL definiert einen Entitätscontainer mit einer Funktionsimportdefinition. Beachten Sie, dass der Rückgabetyp für die Funktion leer ist, da kein Rückgabetyp angegeben wird.  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a>Siehe auch  
 [Schlüsselkonzepte von Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
