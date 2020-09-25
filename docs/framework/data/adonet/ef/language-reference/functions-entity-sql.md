---
title: Funktionen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 52b3d776-5acc-4f69-b614-5a43ce56ef9f
ms.openlocfilehash: bef959ae6a835b5d1d696162528a8f904c59e8e5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201069"
---
# <a name="functions-entity-sql"></a>Funktionen (Entity SQL)

Entity SQL unterstützt benutzerdefinierte Funktionen sowie kanonische und anbieterspezifische Funktionen. Benutzerdefinierte Funktionen werden im konzeptionellen Modell oder inline in der Abfrage angegeben. Weitere Informationen finden Sie unter [benutzerdefinierte Funktionen](user-defined-functions-entity-sql.md).  
  
 Kanonische Funktionen sind im Entity Framework vordefiniert und müssen von Datenanbietern unterstützt werden. Entity SQL-Befehle schlagen fehl, wenn ein Benutzer eine Funktion aufruft, die von einem Anbieter nicht unterstützt wird. Deshalb werden kanonische Funktionen im Allgemeinen speicherspezifischen Funktionen vorgezogen, die sich in einem anbieterspezifischen Namespace befinden. Weitere Informationen finden Sie unter [kanonische Funktionen](canonical-functions.md).  
  
 Der verwaltete Anbieter des Microsoft SQL Client stellt eine Reihe anbieterspezifischer Funktionen bereit. Weitere Informationen finden Sie unter [SqlClient für Entity Framework Funktionen](../sqlclient-for-ef-functions.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Benutzerdefinierte Funktionen](user-defined-functions-entity-sql.md)  
  
 [Auflösung von Funktionsüberladungen](function-overload-resolution-entity-sql.md)  
  
 [Aggregatfunktionen](../aggregate-functions-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Entity SQL](entity-sql-overview.md)
