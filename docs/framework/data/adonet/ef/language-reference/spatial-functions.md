---
title: Räumliche Funktionen
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: ad6b722e84aae40354e30434b107752d02352645
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2018
ms.locfileid: "46580680"
---
# <a name="spatial-functions"></a>Räumliche Funktionen
Es gibt kein Literalformat für räumliche Typen. Sie können jedoch kanonische Entity Framework-Funktionen verwenden, die Sie mit Zeichenfolgen im WKT (Well-Known Text)-Format aufrufen. Beispielsweise wird durch den folgenden Funktionsaufruf ein Geometriepunkt erstellt:  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 Die [SpatialEdmFunctions-Methoden](https://msdn.microsoft.com/library/hh749531.aspx) Seite listet aller räumliche kanonische Entity Framework-Methoden. Klicken Sie auf die gewünschte Methode, um herauszufinden, welche Parameter an eine Funktion übergeben werden sollten.
