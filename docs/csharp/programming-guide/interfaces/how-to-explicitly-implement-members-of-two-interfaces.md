---
title: 'Vorgehensweise: Explizites Implementieren von Membern zweier Schnittstellen (C#-Programmierleitfaden)'
description: In diesem C#-Beispiel erfahren Sie, wie Sie explizit zwei Schnittstellen implementieren, die über dieselben Membernamen verfügen, und wie Sie für jeden Schnittstellenmember eine separate Implementierung einrichten.
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: 18b1f9cfb1690d35c0bca0a3c79c1b80ae5dd44d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205086"
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a>Vorgehensweise: Explizites Implementieren von Membern zweier Schnittstellen (C#-Programmierleitfaden)

Die explizite [Schnittstellenimplementierung](../../language-reference/keywords/interface.md) erlaubt dem Programmierer auch, zwei Schnittstellen zu implementieren, die über die gleichen Membernamen verfügen, sowie jedem Schnittstellenmember eine separate Implementierung zu geben. Dieses Beispiel zeigt die Dimensionen eines Felds in jeweils der metrischen und der englischen Einheit. Das Feld [class](../../language-reference/keywords/class.md) implementiert zwei Schnittstellen, „IEnglishDimensions“ und „IMetricDimensions“, die die unterschiedlichen Messsysteme darstellen. Beide Schnittstellen verfügen über identische Elementnamen, sowie unterschiedliche Länge und Breite.  
  
## <a name="example"></a>Beispiel  

 [!code-csharp[csProgGuideInheritance#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#9)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  

 Wenn Sie die Standardmessungen in englischen Einheiten durchführen möchten, implementieren Sie die Methoden Länge und Breite normal, und implementieren Sie explizit die Methoden Länge und Breite aus der „IMetricDimensions“-Schnittstelle.  
  
 [!code-csharp[csProgGuideInheritance#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#10)]  
  
 In diesem Fall können Sie auf die englischen Einheiten von der Klasseninstanz aus zugreifen und auf die metrischen Einheiten von der Schnittstelleninstanz aus.  
  
 [!code-csharp[csProgGuideInheritance#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#11)]  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../index.md)
- [Klassen und Strukturen](../classes-and-structs/index.md)
- [Schnittstellen](./index.md)
- [Explizites Implementieren von Schnittstellenmembern](./how-to-explicitly-implement-interface-members.md)
