---
title: Zurückgeben einer Abfrage aus einer Methode
description: Vorgehensweise zum Zurückgeben einer Abfrage aus einer Methode.
ms.date: 11/30/2016
ms.assetid: db220f79-c35b-41f2-886c-cd068672d42d
ms.openlocfilehash: 1df533770f76301432b104d6f8398f1687750cce
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73972513"
---
# <a name="how-to-return-a-query-from-a-method-c-programming-guide"></a>Gewusst wie: Zurückgeben einer Abfrage aus einer Methode (C#-Programmierhandbuch)
In diesem Beispiel wird gezeigt, wie Sie eine Abfrage aus einer Methode als Rückgabewert oder `out`-Parameter zurückgeben.  
  
 Abfrageobjekte sind zusammensetzbar, das bedeutet, dass Sie eine Abfrage aus einer Methode zurückgeben können. Objekte, die Abfragen darstellen, speichern nicht die resultierende Auflistung, sondern bei Bedarf die Schritte zum Erzeugen der Ergebnisse. Der Vorteil des Zurückgebens von Abfrageobjekten aus Methoden ist, dass diese weiter zusammengesetzt oder geändert werden können. Daher muss ein Rückgabewert oder ein `out`-Parameter einer Methode, die eine Abfrage zurückgibt, über diesen Typ verfügen. Wenn eine Methode eine Abfrage in einen konkreten <xref:System.Collections.Generic.List%601>- oder <xref:System.Array>-Typ materialisiert, wird sie als Methode betrachtet, die die Abfrageergebnisse zurückgibt, nicht die Abfrage selbst. Eine Abfragevariable, die aus einer Methode zurückgegeben wird, kann noch zusammengesetzt oder geändert werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel gibt die erste Methode eine Abfrage als Rückgabewert zurück. Die zweite Methode gibt eine Abfrage als `out`-Parameter zurück. Beachten Sie, dass es sich in beiden Fällen um eine Abfrage handelt, die zurückgegeben wird, nicht um Abfrageergebnisse.  
  
 [!code-csharp[csProgGuideLINQ#80](~/samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]  

## <a name="see-also"></a>Siehe auch

- [Language-Integrated Query (LINQ)](index.md)
