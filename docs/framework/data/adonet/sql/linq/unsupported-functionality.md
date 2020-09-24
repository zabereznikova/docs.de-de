---
title: Nicht unterstützte Funktionalität
ms.date: 03/30/2017
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
ms.openlocfilehash: d4fe3d91b80197d962989cd2d3bc9bb2df6e3ffe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164154"
---
# <a name="unsupported-functionality"></a>Nicht unterstützte Funktionalität

In LINQ to SQL können die folgenden SQL-Funktionen nicht durch Übersetzung von vorhandenen CLR- und .NET Framework-Konstrukten genutzt werden:  
  
- `STDDEV`  
  
- `LIKE`  
  
     Obwohl `LIKE` nicht durch direkte Übersetzung unterstützt wird, ist eine ähnliche Funktionalität in der <xref:System.Data.Linq.SqlClient.SqlMethods>-Klasse vorhanden. Weitere Informationen finden Sie unter <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.  
  
- `DATEDIFF`  
  
     LINQ to SQL unterstützt `DATEDIFF` nur eingeschränkt. Ähnliche Funktionalität ist in der <xref:System.Data.Linq.SqlClient.SqlMethods>-Klasse vorhanden.  
  
- `ROUND`  
  
     LINQ to SQL unterstützt `ROUND` nur eingeschränkt. Weitere Informationen finden Sie unter [System. Math-Methoden](system-math-methods.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Datentypen und Funktionen](data-types-and-functions.md)
