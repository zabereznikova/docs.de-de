---
title: Generics und Attribute – C#-Programmierhandbuch
description: Erfahren Sie mehr über das Anwenden von Attributen auf generische Typen. Hier finden Sie Codebeispiele und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
ms.openlocfilehash: 94378e44782169141314890bf90f050fdb6b5b79
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91184208"
---
# <a name="generics-and-attributes-c-programming-guide"></a>Generics und Attribute (C#-Programmierhandbuch)

Das Anwenden von Attributen auf generische Typen erfolgt in derselben Weise wie auf nicht generische Typen. Weitere Informationen zum Anwenden von Attributen finden Sie unter [Attribute](../concepts/attributes/index.md).  
  
 Benutzerdefinierte Attribute dürfen nur auf offene generische Typen (generische Typen, für die keine Typargumente bereitgestellt werden) und auf geschlossene konstruierte generische Typen (generische Typen, die Argumente für alle Typparameter bereitstellen) verweisen.  
  
 In den folgenden Beispielen wird dieses benutzerdefinierte Attribut verwendet:  
  
 [!code-csharp[csProgGuideGenerics#48](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#48)]  
  
 Ein Attribut kann auf einen offenen generischen Typ verweisen:  
  
 [!code-csharp[csProgGuideGenerics#49](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#49)]  
  
 Geben Sie mehrere Typparameter mit der entsprechenden Anzahl von Kommas an. In diesem Beispiel verfügt `GenericClass2` über zwei Typparameter:  
  
 [!code-csharp[csProgGuideGenerics#50](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#50)]  
  
 Ein Attribut kann auf einen geschlossenen, konstruierten generischen Typ verweisen:  
  
 [!code-csharp[csProgGuideGenerics#51](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#51)]  
  
 Ein Attribut, das auf einen generischen Typparameter verweist, verursacht einen Kompilierungsfehler:  
  
 [!code-csharp[csProgGuideGenerics#52](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#52)]  
  
 Ein generischer Typ kann nicht von <xref:System.Attribute> erben:  
  
 [!code-csharp[csProgGuideGenerics#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#53)]  
  
 Um zur Laufzeit Informationen zu einem generischen Typ oder Typparameter abzurufen, können Sie die Methoden von <xref:System.Reflection> verwenden. Weitere Informationen finden Sie unter [Generics und Reflektion](./generics-and-reflection.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../index.md)
- [Generics](./index.md)
- [Attribute](../../../standard/attributes/index.md)
