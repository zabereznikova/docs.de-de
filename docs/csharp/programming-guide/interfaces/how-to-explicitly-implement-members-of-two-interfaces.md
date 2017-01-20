---
title: "Gewusst wie: Explizites Implementieren von Membern zweier Schnittstellen (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Vererbung [C#], Explizites Implementieren von Schnittstellenmembern"
  - "Schnittstellen [C#], Explizites Implementieren mit Vererbung"
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Explizites Implementieren von Membern zweier Schnittstellen (C#-Programmierhandbuch)
Bei der expliziten [Schnittstellen](../../../csharp/language-reference/keywords/interface.md)\-Implementierung haben Programmierer außerdem die Möglichkeit, zwei Schnittstellen zu implementieren, die über identische Membernamen verfügen, und jeden Schnittstellenmember getrennt zu implementieren.  In diesem Beispiel werden die Abmessungen eines Felds sowohl in metrischen als auch in englischen Maßeinheiten ausgegeben.  Die Box\-[Klasse](../../../csharp/language-reference/keywords/class.md) implementiert die beiden Schnittstellen IEnglishDimensions und IMetricDimensions, die die unterschiedlichen Maßsysteme darstellen.  Beide Schnittstellen verfügen über die identischen Membernamen Length und Width.  
  
## Beispiel  
 [!code-cs[csProgGuideInheritance#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implem_0_1.cs)]  
  
## Robuste Programmierung  
 Wenn die englischen Maßeinheiten standardmäßig verwendet werden sollen, implementieren Sie die Length\-Methode und die Width\-Methode auf normale Weise und die Length\-Methode und Width\-Methode der IMetricDimensions\-Schnittstelle explizit:  
  
 [!code-cs[csProgGuideInheritance#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implem_0_2.cs)]  
  
 In diesem Fall kann über die Klasseninstanz auf die englischen Maßeinheiten und über die Schnittstelleninstanz auf die metrischen Einheiten zugegriffen werden:  
  
 [!code-cs[csProgGuideInheritance#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implem_0_3.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Schnittstellen](../../../csharp/programming-guide/interfaces/index.md)   
 [Gewusst wie: Explizites Implementieren von Schnittstellenmembern](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-interface-members.md)