---
title: Schnittstelleneigenschaften – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: cdd425970442e284d6fd6488bbb13394c12e939a
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69596453"
---
# <a name="interface-properties-c-programming-guide"></a>Schnittstelleneigenschaften (C#-Programmierhandbuch)
Eigenschaften können für eine [Schnittstelle](../../language-reference/keywords/interface.md) deklariert werden. Das folgende Beispiel zeigt den Accessor einer Schnittstelleneigenschaft:  
  
 [!code-csharp[csProgGuideProperties#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#14)]  
  
 Der Accessor einer Schnittstelleneigenschaft enthält keinen Text. Der Zweck eines Accessors besteht darin anzugeben, ob die Eigenschaft gleichzeitig Lese- und Schreibzugriff, nur Lesezugriff oder nur Schreibzugriff besitzt.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel besitzt die Schnittstelle `IEmployee` eine Lese-/Schreibzugriff-Eigenschaft `Name` und eine Lesezugriff-Eigenschaft `Counter`. Die Klasse `Employee` implementiert die Schnittstelle `IEmployee` und verwendet diese beiden Eigenschaften. Der Name eines neuen Mitarbeiters und die aktuelle Anzahl der Mitarbeiter werden vom Programm gelesen, und der Mitarbeitername sowie die berechnete Mitarbeiteranzahl werden angezeigt.  
  
 Sie können den vollqualifizierten Namen der Eigenschaft verwenden, der auf die Schnittstelle verweist, in der der Member deklariert wird. Beispiel:  
  
 [!code-csharp[csProgGuideProperties#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#16)]  
  
 Dies wird [Explizite Schnittstellenimplementierung](../interfaces/explicit-interface-implementation.md) genannt. Wenn z.B. die Klasse `Employee` die beiden Schnittstellen `ICitizen` und `IEmployee` implementiert und beide Schnittstellen die Eigenschaft `Name` besitzen, ist die explizite Implementierung des Schnittstellenmembers erforderlich. Das bedeutet, dass die folgende Eigenschaftendeklaration:  
  
 [!code-csharp[csProgGuideProperties#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#16)]  
  
 die Eigenschaft `Name` für die Schnittstelle `IEmployee` implementiert. Dahingegen implementiert die folgende Deklaration:  
  
 [!code-csharp[csProgGuideProperties#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#17)]  
  
 die Eigenschaft `Name` für die Schnittstelle `ICitizen`.  
  
 [!code-csharp[csProgGuideProperties#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#15)]  
  
  **`210 Hazem Abolrous`**    
## <a name="sample-output"></a>Beispielausgabe  
 `Enter number of employees: 210`  
  
 `Enter the name of the new employee: Hazem Abolrous`  
  
 `The employee information:`  
  
 `Employee number: 211`  
  
 `Employee name: Hazem Abolrous`  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Eigenschaften](./properties.md)
- [Verwenden von Eigenschaften](./using-properties.md)
- [Vergleich zwischen Eigenschaften und Indexern](../indexers/comparison-between-properties-and-indexers.md)
- [Indexer](../indexers/index.md)
- [Schnittstellen](../interfaces/index.md)
