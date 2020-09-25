---
title: Räumliche Funktionen
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: 7d0979b5166c847244cbeec97acf4fa4f745a259
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169582"
---
# <a name="spatial-functions"></a>Räumliche Funktionen

Es gibt kein Literalformat für räumliche Typen. Sie können jedoch kanonische Entity Framework-Funktionen verwenden, die Sie mit Zeichenfolgen im WKT (Well-Known Text)-Format aufrufen. Beispielsweise wird durch den folgenden Funktionsaufruf ein Geometriepunkt erstellt:  
  
```sql  
GeometryFromText('POINT (43 -73)')  
```  
  
 Die- <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> Methoden verfügen über alle räumlichen kanonischen Entity Framework-Methoden. Klicken Sie auf die gewünschte Methode, um herauszufinden, welche Parameter an eine Funktion übergeben werden sollten.
