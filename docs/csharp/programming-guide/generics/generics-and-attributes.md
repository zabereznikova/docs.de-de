---
title: "Generische Typen und Attribute (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "Attribute [C#], Mit Generika"
  - "Generika [C#], Attribute"
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Generische Typen und Attribute (C#-Programmierhandbuch)
Das Anwenden von Attributen auf generische Typen erfolgt in derselben Weise wie auf nicht generische Typen.  Weitere Informationen zum Anwenden von Attributen finden Sie unter [Attribute](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Benutzerdefinierte Attribute dürfen nur auf offene generische Typen \(generische Typen, für die keine Typargumente bereitgestellt werden\) und auf geschlossene konstruierte generische Typen \(generische Typen, die Argumente für alle Typparameter bereitstellen\) verweisen.  
  
 In den folgenden Beispielen wird dieses benutzerdefinierte Attribut verwendet:  
  
 [!code-cs[csProgGuideGenerics#48](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_1.cs)]  
  
 Ein Attribut kann auf einen offenen generischen Typ verweisen:  
  
 [!code-cs[csProgGuideGenerics#49](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_2.cs)]  
  
 Geben Sie mehrere Typparameter mit der entsprechenden Anzahl von Kommas an.  In diesem Beispiel verfügt `GenericClass2` über zwei Typparameter:  
  
 [!code-cs[csProgGuideGenerics#50](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_3.cs)]  
  
 Ein Attribut kann auf einen geschlossenen, konstruierten generischen Typ verweisen:  
  
 [!code-cs[csProgGuideGenerics#51](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_4.cs)]  
  
 Ein Attribut, das auf einen generischen Typparameter verweist, verursacht einen Kompilierungsfehler:  
  
 [!code-cs[csProgGuideGenerics#52](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_5.cs)]  
  
 Ein generischer Typ kann nicht von <xref:System.Attribute> erben:  
  
 [!code-cs[csProgGuideGenerics#53](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_6.cs)]  
  
 Um zur Laufzeit Informationen zu einem generischen Typ oder Typparameter abzurufen, können Sie die Methoden von <xref:System.Reflection> verwenden.  Weitere Informationen finden Sie unter [Generische Typen und Reflektion](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Generika](../../../csharp/programming-guide/generics/index.md)   
 [Attribute](../Topic/Extending%20Metadata%20Using%20Attributes.md)