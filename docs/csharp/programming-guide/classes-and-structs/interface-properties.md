---
title: Schnittstelleneigenschaften (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: 619b9167b9b96be2908d833403379e4c2fe78ba5
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43746917"
---
# <a name="interface-properties-c-programming-guide"></a>Schnittstelleneigenschaften (C#-Programmierhandbuch)
Eigenschaften können für eine [Schnittstelle](../../../csharp/language-reference/keywords/interface.md) deklariert werden. Das folgende Beispiel zeigt den Accessor einer Schnittstelleneigenschaft:  
  
 [!code-csharp[csProgGuideProperties#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_1.cs)]  
  
 Der Accessor einer Schnittstelleneigenschaft enthält keinen Text. Der Zweck eines Accessors besteht darin anzugeben, ob die Eigenschaft gleichzeitig Lese- und Schreibzugriff, nur Lesezugriff oder nur Schreibzugriff besitzt.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel besitzt die Schnittstelle `IEmployee` eine Lese-/Schreibzugriff-Eigenschaft `Name` und eine Lesezugriff-Eigenschaft `Counter`. Die Klasse `Employee` implementiert die Schnittstelle `IEmployee` und verwendet diese beiden Eigenschaften. Der Name eines neuen Mitarbeiters und die aktuelle Anzahl der Mitarbeiter werden vom Programm gelesen, und der Mitarbeitername sowie die berechnete Mitarbeiteranzahl werden angezeigt.  
  
 Sie können den vollqualifizierten Namen der Eigenschaft verwenden, der auf die Schnittstelle verweist, in der der Member deklariert wird. Zum Beispiel:  
  
 [!code-csharp[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]  
  
 Dies wird [Explizite Schnittstellenimplementierung](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md) genannt. Wenn z.B. die Klasse `Employee` die beiden Schnittstellen `ICitizen` und `IEmployee` implementiert und beide Schnittstellen die Eigenschaft `Name` besitzen, ist die explizite Implementierung des Schnittstellenmembers erforderlich. Das bedeutet, dass die folgende Eigenschaftendeklaration:  
  
 [!code-csharp[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]  
  
 die Eigenschaft `Name` für die Schnittstelle `IEmployee` implementiert. Dahingegen implementiert die folgende Deklaration:  
  
 [!code-csharp[csProgGuideProperties#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_3.cs)]  
  
 die Eigenschaft `Name` für die Schnittstelle `ICitizen`.  
  
 [!code-csharp[csProgGuideProperties#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_4.cs)]  
  
  **`210 Hazem Abolrous`**    
## <a name="sample-output"></a>Beispielausgabe  
 `Enter number of employees: 210`  
  
 `Enter the name of the new employee: Hazem Abolrous`  
  
 `The employee information:`  
  
 `Employee number: 211`  
  
 `Employee name: Hazem Abolrous`  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md)  
- [Verwenden von Eigenschaften](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
- [Vergleich zwischen Eigenschaften und Indexern](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
- [Indexer](../../../csharp/programming-guide/indexers/index.md)  
- [Schnittstellen](../../../csharp/programming-guide/interfaces/index.md)
