---
title: "Nicht unterstützte Funktionalität"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6dd8ccebd278fdc36c536c49f7f1d4262b2de8c1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="unsupported-functionality"></a>Nicht unterstützte Funktionalität
In LINQ to SQL können die folgenden SQL-Funktionen nicht durch Übersetzung von vorhandenen CLR- und .NET Framework-Konstrukten genutzt werden:  
  
-   `STDDEV`  
  
-   `LIKE`  
  
     Obwohl `LIKE` nicht durch direkte Übersetzung unterstützt wird, ist eine ähnliche Funktionalität in der <xref:System.Data.Linq.SqlClient.SqlMethods>-Klasse vorhanden. Weitere Informationen finden Sie unter <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.  
  
-   `DATEDIFF`  
  
     LINQ to SQL unterstützt `DATEDIFF` nur eingeschränkt. Ähnliche Funktionalität ist in der <xref:System.Data.Linq.SqlClient.SqlMethods>-Klasse vorhanden.  
  
-   `ROUND`  
  
     LINQ to SQL unterstützt `ROUND` nur eingeschränkt. Weitere Informationen finden Sie unter ["System.Math" Methoden](system-math-methods.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypen und Funktionen](data-types-and-functions.md)
