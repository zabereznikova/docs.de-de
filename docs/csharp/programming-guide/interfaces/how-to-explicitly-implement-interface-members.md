---
title: 'Gewusst wie: Explizites Implementieren von Schnittstellenmembern (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: 5f7ae6bae46cdf6596b206abbdeeb94b5c21a13f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a>Gewusst wie: Explizites Implementieren von Schnittstellenmembern (C#-Programmierhandbuch)
Dieses Beispiel deklariert eine [Schnittstelle](../../../csharp/language-reference/keywords/interface.md), `IDimensions`, und eine Klasse, `Box`, die explizit die Schnittstellenmember `getLength` und `getWidth` implementiert. Die Member werden über eine Schnittstelleninstanz, `dimensions`, erreicht.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideInheritance#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_1.cs)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
  
-   Beachten Sie, dass die folgenden Zeilen in der `Main`-Methode auskommentiert werden, da sie Kompilierungsfehler verursachen würden. Auf ein Schnittstellenmember, das explizit implementiert wird, kann nicht von einer [class](../../../csharp/language-reference/keywords/class.md)-Instanz zugegriffen werden.  
  
     [!code-csharp[csProgGuideInheritance#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_2.cs)]  
  
-   Beachten Sie auch, dass die folgenden Zeilen in der `Main`-Methode erfolgreich die Dimensionen des Felds ausdrucken, da die Methoden von einer Instanz der Schnittstelle aufgerufen werden:  
  
     [!code-csharp[csProgGuideInheritance#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_3.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Schnittstellen](../../../csharp/programming-guide/interfaces/index.md)  
 [Gewusst wie: Explizites Implementieren von Membern zweier Schnittstellen](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md)
