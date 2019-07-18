---
title: 'Vorgehensweise: Explizites Implementieren von Schnittstellenmembern – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: 8cef6c840bf6afff8ccbf7d02012990e11d47991
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64595372"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a>Vorgehensweise: Explizites Implementieren von Schnittstellenmembern (C#-Programmierhandbuch)
Dieses Beispiel deklariert eine [Schnittstelle](../../../csharp/language-reference/keywords/interface.md), `IDimensions`, und eine Klasse, `Box`, die explizit die Schnittstellenmember `getLength` und `getWidth` implementiert. Die Member werden über eine Schnittstelleninstanz, `dimensions`, erreicht.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideInheritance#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#8)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
  
- Beachten Sie, dass die folgenden Zeilen in der `Main`-Methode auskommentiert werden, da sie Kompilierungsfehler verursachen würden. Auf ein Schnittstellenmember, das explizit implementiert wird, kann nicht von einer [class](../../../csharp/language-reference/keywords/class.md)-Instanz zugegriffen werden.  
  
     [!code-csharp[csProgGuideInheritance#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#45)]  
  
- Beachten Sie auch, dass die folgenden Zeilen in der `Main`-Methode erfolgreich die Dimensionen des Felds ausdrucken, da die Methoden von einer Instanz der Schnittstelle aufgerufen werden:  
  
     [!code-csharp[csProgGuideInheritance#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#46)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)
- [Schnittstellen](../../../csharp/programming-guide/interfaces/index.md)
- [Vorgehensweise: Explizites Implementieren von Membern zweier Schnittstellen](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md)
