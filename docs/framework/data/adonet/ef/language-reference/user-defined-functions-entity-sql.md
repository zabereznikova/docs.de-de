---
title: "Benutzerdefinierte Funktionen (Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Benutzerdefinierte Funktionen (Entity SQL)
Entity SQL unterstützt das Aufrufen von benutzerdefinierten Funktionen in einer Abfrage.  Sie können diese Funktionen mit der Abfrage \(siehe [How to: Call a User\-Defined Function](http://msdn.microsoft.com/de-de/ad131b86-8b4e-4747-8605-d4fc64fb9d02)\) oder als Teil des konzeptionellen Modells \(siehe [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/de-de/0dad7b8b-58f6-4271-b238-f34810d68e5f)\) inline definieren.  Konzeptionelle Modellfunktionen werden als ein Entity SQL\-Befehl im [DefiningExpression](http://msdn.microsoft.com/de-de/d3da8d8b-a048-47ee-8d81-0c2ea3acdd3e)\-Element eines [Function](http://msdn.microsoft.com/de-de/dc3beca7-55cf-4977-8db0-5064cdbab134)\-Elements im konzeptionellen Modell definiert.  
  
 Entity SQL ermöglicht Ihnen, Funktionen im Abfragebefehl selbst zu definieren.  Der [FUNCTION](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md)\-Operator definiert Inlinefunktionen.  Sie können mehrere Funktionen in einem einzelnen Befehl definieren. Diese Funktionen können den gleichen Funktionsnamen aufweisen, solange die Funktionssignaturen eindeutig sind.  Weitere Informationen finden Sie unter [Auflösung von Funktionsüberladungen](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).  
  
## Siehe auch  
 [Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)