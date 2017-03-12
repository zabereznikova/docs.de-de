---
title: "Einschr&#228;nken des Accessorzugriffs (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Accessoren [C#]"
  - "Asymmetrischer Accessorzugriff [C#]"
  - "Indexer [C#], Schreibgeschützt"
  - "Eigenschaften [C#], Schreibgeschützt"
  - "Schreibgeschützte Indexer [C#]"
  - "Schreibschutzeigenschaften [C#]"
ms.assetid: 6e655798-e112-4301-a680-6310a6e012e1
caps.latest.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 26
---
# Einschr&#228;nken des Accessorzugriffs (C#-Programmierhandbuch)
Die Abschnitte [get](../../../csharp/language-reference/keywords/get.md) und [set](../../../csharp/language-reference/keywords/set.md) einer Eigenschaft oder eines Indexers werden als *Accessoren* bezeichnet.  Diese Accessoren weisen standardmäßig dieselbe Sichtbarkeits\- bzw. Zugriffsebene auf, und zwar diejenige der Eigenschaft oder des Indexers, der bzw. dem sie angehören.  Weitere Informationen finden Sie unter [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md).  In bestimmten Fällen ist es jedoch nützlich, den Zugriff auf einen der beiden Accessoren einzuschränken.  Normalerweise wird der Zugriff auf den `set`\-Accessor eingeschränkt, während auf den `get`\-Accessor weiterhin öffentlich zugegriffen werden kann.  Beispiele:  
  
 [!code-cs[csProgGuideIndexers#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/restricting-accessor-acc_1.cs)]  
  
 In diesem Beispiel definiert die Eigenschaft `Name` einen `set`\-Accessor und einen `get`\-Accessor.  Dem `get`\-Accessor wird die Zugriffsebene der Eigenschaft selbst zugewiesen, `public` in diesem Fall, während der `set`\-Accessor explizit eingeschränkt wird, indem der [protected](../../../csharp/language-reference/keywords/protected.md)\-Zugriffsmodifizierer auf den Accessor selbst angewendet wird.  
  
## Einschränkungen für Zugriffsmodifizierer bei Accessoren  
 Die Anwendung von Accessormodifizierern auf Eigenschaften oder Indexer unterliegt den folgenden Bedingungen:  
  
-   Sie können Accessormodifizierer nicht für eine [Schnittstelle](../../../csharp/language-reference/keywords/interface.md) oder eine explizite Implementierung eines Schnittstellenmembers verwenden.  
  
-   Sie können nur Accessormodifizierer verwenden, wenn die Eigenschaft oder der Indexer sowohl über einen `set`\-Accessor als auch über einen `get`\-Accessor verfügt.  In diesem Fall ist der Modifizierer nur auf einem der beiden Accessoren erlaubt.  
  
-   Wenn die Eigenschaft oder der Indexer einen [override](../../../csharp/language-reference/keywords/override.md)\-Modifizierer besitzt, muss der Accessormodifizierer dem Accessor des überschriebenen Accessors \(falls vorhanden\) entsprechen.  
  
-   Die Zugriffsebene für den Accessor muss restriktiver sein als die Zugriffsebene für die Eigenschaft oder den Indexer.  
  
## Zugriffsmodifizierer auf überschreibenden Accessoren  
 Wenn Sie eine Eigenschaft oder einen Indexer überschreiben, müssen die überschriebenen Accessoren für den überschreibenden Code zugänglich sein.  Außerdem muss die Zugriffsebene sowohl von Eigenschaft\/Indexer als auch der Accessoren mit den überschriebenen Entsprechungen von Eigenschaft\/Indexer und der Accessoren übereinstimmen.  Beispiele:  
  
 [!code-cs[csProgGuideIndexers#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/restricting-accessor-acc_2.cs)]  
  
## Implementieren von Schnittstellen  
 Wenn Sie einen Accessor verwenden, um eine Schnittstelle zu implementieren, ist es möglich, dass der Accessor keinen Zugriffsmodifizierer hat.  Wenn Sie die Schnittstelle mit einem Accessor implementieren, z. B. mit `get`, kann der andere Accessor einen Zugriffsmodifizierer haben. Beispiel:  
  
 [!code-cs[csProgGuideIndexers#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/restricting-accessor-acc_3.cs)]  
  
## Accessorzugriffsdomäne  
 Wenn Sie auf dem Accessor einen Zugriffsmodifizierer verwenden, wird die [Zugriffsdomäne](../../../csharp/language-reference/keywords/accessibility-domain.md) des Accessors von diesem Modifizierer bestimmt.  
  
 Wenn Sie auf dem Accessor keinen Zugriffsmodifizierer verwendet haben, wird die Zugriffsdomäne des Accessors von der Zugriffsebene der Eigenschaft bzw. des Indexers bestimmt.  
  
## Beispiel  
 Das folgende Beispiel enthält drei Klassen: `BaseClass`, `DerivedClass` und `MainClass`.  Es gibt zwei Eigenschaften auf der `BaseClass`, `Name` und `Id` auf beiden Klassen.  Im Beispiel wird veranschaulicht, wie die `Id`\-Eigenschaft für `DerivedClass` durch die `Id`\-Eigenschaft für `BaseClass` ausgeblendet wird, wenn ein restriktiver Zugriffsmodifizierer wie [protected](../../../csharp/language-reference/keywords/protected.md) oder [private](../../../csharp/language-reference/keywords/private.md) verwendet wird.  Wenn Sie dieser Eigenschaft Werte zuweisen, wird daher stattdessen die Eigenschaft auf der `BaseClass`\-Klasse aufgerufen.  Indem Sie den Zugriffsmodifizierer durch [public](../../../csharp/language-reference/keywords/public.md) ersetzen, kann auf die Eigenschaft zugegriffen werden.  
  
 Das Beispiel zeigt auch, dass ein restriktiver Zugriffsmodifizierer \(z. B. `private` oder `protected`\) auf dem `set`\-Accessor der `Name`\-Eigenschaft in `DerivedClass` den Zugriff auf den Accessor verhindert und einen Fehler generiert, sobald Sie darauf verweisen.  
  
 [!code-cs[csProgGuideIndexers#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/restricting-accessor-acc_4.cs)]  
  
## Kommentare  
 Beachten Sie, dass Sie beim Ersetzen der Deklaration `new private string Id` durch `new public string Id` die folgende Ausgabe erhalten:  
  
 `Name and ID in the base class: Name-BaseClass, ID-BaseClass`  
  
 `Name and ID in the derived class: John, John123`  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Indexer](../../../csharp/programming-guide/indexers/index.md)   
 [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)