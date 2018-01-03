---
title: NULL-Semantik
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 6786c7ea4441b1a753d6f0b4213f40fa64dcb4ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="null-semantics"></a>NULL-Semantik
Die folgende Tabelle enthält Links zu verschiedenen Teilen der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] -Dokumentation, in denen es um `null` -Probleme geht (bzw. um`Nothing` -Probleme in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]).  
  
|Thema|Beschreibung|  
|-----------|-----------------|  
|[SQL-CLR-Typenkonflikte](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)|Der Abschnitt "NULL-Semantik" dieses Themas umfasst Informationen zum dreistufigen SQL-Boolean und zum zweistufigen Common Language Runtime (CLR)- <xref:System.Boolean>, zum `Nothing` -Literal ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) und zum `null` -Literal (C#) sowie zu ähnliche Aspekten.|  
|[Übersetzen von Standardabfrageoperatoren](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)|Im Abschnitt "NULL-Semantik" dieses Themas wird die NULL-Vergleichssemantik in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]beschrieben.|  
|[System.String-Methoden](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md)|Der Abschnitt "Unterschiede zu .NET" dieses Themas erläutert, warum der Rückgabewert 0 von <xref:System.String.LastIndexOf%2A> auf eine NULL-Zeichenfolge oder auf die gefundene Position 0 hinweisen kann.|  
|[Berechnen der Summe von Werten in einer numerischen Sequenz](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)|Erläutert, wie der <xref:System.Linq.Enumerable.Sum%2A> -Operator bei einer Sequenz, die nur aus Nullen besteht, bzw. bei einer leeren Sequenz zu `null` (`Nothing` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) und nicht zu 0 führt.|  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypen und Funktionen](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
