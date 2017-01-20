---
title: "Explizite Schnittstellenimplementierung (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "Explizite Schnittstellen [C#]"
  - "Schnittstellen [C#], explizit"
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Explizite Schnittstellenimplementierung (C#-Programmierhandbuch)
Wenn eine [Klasse](../../../csharp/language-reference/keywords/class.md) zwei Schnittstellen erbt, die einen Member mit derselben Signatur enthalten, bewirkt die Implementierung dieses Members in der Klasse, dass beide Schnittstellen diesen Member als ihre Implementierung verwenden.  Im folgenden Beispiel rufen alle Aufrufe `Paint` dieselbe Methode auf.  
  
 [!code-cs[csProgGuideInheritance#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implemen_1.cs)]  
  
 Falls die beiden [Schnittstellen](../../../csharp/language-reference/keywords/interface.md)\-Member jedoch nicht dieselbe Funktion erfüllen, kann dies zu einer falschen Implementierung von einer oder beiden Schnittstellen führen.  Es ist möglich, einen Schnittstellenmember explizit zu implementieren – also einen Klassenmember zu erstellen, der nur über die Schnittstelle aufgerufen wird und für diese Schnittstelle spezifisch ist.  Dazu benennt man den Klassenmember mit dem Namen der Schnittstelle und einem Punkt.  Beispiel:  
  
 [!code-cs[csProgGuideInheritance#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implemen_2.cs)]  
  
 Der `IControl.Paint`\-Klassenmember ist nur über die `IControl`\-Schnittstelle verfügbar, und `ISurface.Paint` ist nur über `ISurface` verfügbar.  Beide Methodenimplementierungen sind getrennt, und keine ist direkt in der Klasse verfügbar.  Beispiel:  
  
 [!code-cs[csProgGuideInheritance#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implemen_3.cs)]  
  
 Explizite Implementierung wird auch zum Lösen von Konflikten verwendet, bei denen zwei Schnittstellen verschiedene Member mit demselben Namen deklarieren, z. B. eine Eigenschaft und eine Methode:  
  
 [!code-cs[csProgGuideInheritance#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implemen_4.cs)]  
  
 Um beide Schnittstellen zu implementieren, muss eine Klasse zur Vermeidung eines Compilerfehlers die explizite Implementierung entweder für Eigenschaft P, für Methode P oder für beide verwenden.  Beispiel:  
  
 [!code-cs[csProgGuideInheritance#43](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implemen_5.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Schnittstellen](../../../csharp/programming-guide/interfaces/index.md)   
 [Vererbung](../../../csharp/programming-guide/classes-and-structs/inheritance.md)