---
title: Funktionen (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52b3d776-5acc-4f69-b614-5a43ce56ef9f
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: fb55fecc7c876fda5918418e353eaf327ce6c034
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="functions-entity-sql"></a>Funktionen (Entity SQL)
Entity SQL unterstützt benutzerdefinierte Funktionen sowie kanonische und anbieterspezifische Funktionen. Benutzerdefinierte Funktionen werden im konzeptionellen Modell oder inline in der Abfrage angegeben. Weitere Informationen finden Sie unter [benutzerdefinierte Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md).  
  
 Kanonische Funktionen sind im Entity Framework vordefiniert und müssen von Datenanbietern unterstützt werden. Entity SQL-Befehle schlagen fehl, wenn ein Benutzer eine Funktion aufruft, die von einem Anbieter nicht unterstützt wird. Deshalb werden kanonische Funktionen im Allgemeinen speicherspezifischen Funktionen vorgezogen, die sich in einem anbieterspezifischen Namespace befinden. Weitere Informationen finden Sie unter [kanonische Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).  
  
 Der verwaltete Anbieter des Microsoft SQL Client stellt eine Reihe anbieterspezifischer Funktionen bereit. Weitere Informationen finden Sie unter [SqlClient für Entity Framework-Funktionen](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Benutzerdefinierte Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md)  
  
 [Auflösung von Funktionsüberladungen](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md)  
  
 [Aggregatfunktionen](../../../../../../docs/framework/data/adonet/ef/aggregate-functions-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
