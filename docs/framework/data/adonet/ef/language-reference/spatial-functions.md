---
title: "Räumliche Funktionen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: c482c2f79c6416a4e748599c896280b426d31ce2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="spatial-functions"></a>Räumliche Funktionen
Es gibt kein Literalformat für räumliche Typen. Sie können jedoch kanonische Entity Framework-Funktionen verwenden, die Sie mit Zeichenfolgen im WKT (Well-Known Text)-Format aufrufen. Beispielsweise wird durch den folgenden Funktionsaufruf ein Geometriepunkt erstellt:  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 Die [SpatialEdmFunctions-Methoden](http://msdn.microsoft.com/library/hh749531.aspx) Seite listet aller räumliche kanonische Entity Framework-Methoden. Klicken Sie auf die gewünschte Methode, um herauszufinden, welche Parameter an eine Funktion übergeben werden sollten.
