---
title: Nicht unterstützte Funktionalität
ms.date: 03/30/2017
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
ms.openlocfilehash: 18a1a8f33a9360b4299648bcd329f4c5f2e7de88
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097872"
---
# <a name="unsupported-functionality"></a>Nicht unterstützte Funktionalität
In LINQ to SQL können die folgenden SQL-Funktionen nicht durch Übersetzung von vorhandenen CLR- und .NET Framework-Konstrukten genutzt werden:  
  
-   `STDDEV`  
  
-   `LIKE`  
  
     Obwohl `LIKE` nicht durch direkte Übersetzung unterstützt wird, ist eine ähnliche Funktionalität in der <xref:System.Data.Linq.SqlClient.SqlMethods>-Klasse vorhanden. Weitere Informationen finden Sie unter <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.  
  
-   `DATEDIFF`  
  
     LINQ to SQL unterstützt `DATEDIFF` nur eingeschränkt. Ähnliche Funktionalität ist in der <xref:System.Data.Linq.SqlClient.SqlMethods>-Klasse vorhanden.  
  
-   `ROUND`  
  
     LINQ to SQL unterstützt `ROUND` nur eingeschränkt. Weitere Informationen finden Sie unter [System.Math-Methoden](system-math-methods.md).  
  
## <a name="see-also"></a>Siehe auch

- [Datentypen und Funktionen](data-types-and-functions.md)
