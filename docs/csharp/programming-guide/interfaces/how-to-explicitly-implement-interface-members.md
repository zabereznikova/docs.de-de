---
title: 'Vorgehensweise: Explizites Implementieren von Schnittstellenmembern (C#-Programmierleitfaden)'
description: In diesem C#-Beispiel erfahren Sie, wie Sie Schnittstellenmember explizit implementieren. Der Zugriff auf die Member erfolgt über eine Schnittstelleninstanz.
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: a9c019cdcf6e229199d980a2d1913df7c72a2169
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157394"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a>Vorgehensweise: Explizites Implementieren von Schnittstellenmembern (C#-Programmierleitfaden)

Dieses Beispiel deklariert eine [Schnittstelle](../../language-reference/keywords/interface.md), `IDimensions`, und eine Klasse, `Box`, die explizit die Schnittstellenmember `GetLength` und `GetWidth` implementiert. Die Member werden über eine Schnittstelleninstanz, `dimensions`, erreicht.  
  
## <a name="example"></a>Beispiel  

 [!code-csharp[csProgGuideInheritance#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#8)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
  
- Beachten Sie, dass die folgenden Zeilen in der `Main`-Methode auskommentiert werden, da sie Kompilierungsfehler verursachen würden. Auf ein Schnittstellenmember, das explizit implementiert wird, kann nicht von einer [class](../../language-reference/keywords/class.md)-Instanz zugegriffen werden.  
  
     [!code-csharp[csProgGuideInheritance#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#45)]  
  
- Beachten Sie auch, dass die folgenden Zeilen in der `Main`-Methode erfolgreich die Dimensionen des Felds ausdrucken, da die Methoden von einer Instanz der Schnittstelle aufgerufen werden:  
  
     [!code-csharp[csProgGuideInheritance#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#46)]  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../index.md)
- [Klassen und Strukturen](../classes-and-structs/index.md)
- [Schnittstellen](./index.md)
- [Explizites Implementieren von Membern zweier Schnittstellen](./how-to-explicitly-implement-members-of-two-interfaces.md)
