---
title: Räumliche Funktionen
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: eba384e77389f82006479f165178e80fcac244b1
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319303"
---
# <a name="spatial-functions"></a>Räumliche Funktionen
Es gibt kein Literalformat für räumliche Typen. Sie können jedoch kanonische Entity Framework-Funktionen verwenden, die Sie mit Zeichenfolgen im WKT (Well-Known Text)-Format aufrufen. Beispielsweise wird durch den folgenden Funktionsaufruf ein Geometriepunkt erstellt:  
  
```sql  
GeometryFromText('POINT (43 -73)')  
```  
  
 Die <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions>-Methoden verfügen über alle räumlichen kanonischen Entity Framework-Methoden. Klicken Sie auf die gewünschte Methode, um herauszufinden, welche Parameter an eine Funktion übergeben werden sollten.
