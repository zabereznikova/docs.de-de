---
title: 'Vorgehensweise: Explizites Implementieren von Membern zweier Schnittstellen – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: 1d4dd0485be1d859e3e9594ab1558a907b8f1f7a
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589195"
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a>Vorgehensweise: Explizites Implementieren von Membern zweier Schnittstellen (C#-Programmierhandbuch)
Die explizite [Schnittstellenimplementierung](../../language-reference/keywords/interface.md) erlaubt dem Programmierer auch, zwei Schnittstellen zu implementieren, die über die gleichen Membernamen verfügen, sowie jedem Schnittstellenmember eine separate Implementierung zu geben. Dieses Beispiel zeigt die Dimensionen eines Felds in jeweils der metrischen und der englischen Einheit. Das Feld [class](../../language-reference/keywords/class.md) implementiert zwei Schnittstellen, „IEnglishDimensions“ und „IMetricDimensions“, die die unterschiedlichen Messsysteme darstellen. Beide Schnittstellen verfügen über identische Elementnamen, sowie unterschiedliche Länge und Breite.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideInheritance#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#9)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Wenn Sie die Standardmessungen in englischen Einheiten durchführen möchten, implementieren Sie die Methoden Länge und Breite normal, und implementieren Sie explizit die Methoden Länge und Breite aus der „IMetricDimensions“-Schnittstelle.  
  
 [!code-csharp[csProgGuideInheritance#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#10)]  
  
 In diesem Fall können Sie auf die englischen Einheiten von der Klasseninstanz aus zugreifen und auf die metrischen Einheiten von der Schnittstelleninstanz aus.  
  
 [!code-csharp[csProgGuideInheritance#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#11)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Klassen und Strukturen](../classes-and-structs/index.md)
- [Schnittstellen](./index.md)
- [Vorgehensweise: Explizites Implementieren von Schnittstellenmembern](./how-to-explicitly-implement-interface-members.md)
