---
title: "Indexer (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cs.indexers"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C#-Sprache, Indexer"
  - "Indexer [C#]"
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
caps.latest.revision: 29
caps.handback.revision: 29
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Indexer (C#-Programmierhandbuch)
Indexer ermöglichen, dass Instanzen einer Klasse oder Struktur wie Arrays indiziert werden.  Indexer ähneln [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md). Der Unterschied besteht jedoch darin, dass ihre Accessoren Parameter verwenden.  
  
 Im folgenden Beispiel wird eine generische Klasse definiert und mit einfachen [get](../../../csharp/language-reference/keywords/get.md)\- und [set](../../../csharp/language-reference/keywords/set.md)\-Accessormethoden für das Zuweisen und Abrufen von Werten bereitgestellt.  Die `Program`\-Klasse erstellt eine Instanz dieser Klasse für das Speichern von Zeichenfolgen.  
  
 [!code-cs[csProgGuideIndexers#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/index_1.cs)]  
  
> [!NOTE]
>  Links zu den Beispielen finden Sie unter [Verwandte Abschnitte](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).  
  
## Ausdruckstextdefinitionen  
 Es ist üblich, Indexer zu verwenden, die umgehend das Ergebnis des Ausdrucks zurückgeben.  Es ist eine Syntaxabkürzung zur Definition dieser Indexer mithilfe von `=>` verfügbar:  
  
```c#  
public Customer this[long id] => store.LookupCustomer(id);  
  
```  
  
 Der Indexer muss schreibgeschützt sein. Verwenden Sie darüber hinaus nicht das `get`\-Accessorschlüsselwort.  
  
## Übersicht über Indexer  
  
-   Indexer ermöglichen es Objekten, in ähnlicher Weise wie Arrays indiziert zu werden.  
  
-   Ein `get`\-Accessor gibt einen Wert zurück.  Ein `set`\-Accessor weist einen Wert zu.  
  
-   Das [this](../../../csharp/language-reference/keywords/this.md)\-Schlüsselwort wird zum Definieren der Indexer verwendet.  
  
-   Das [value](../../../csharp/language-reference/keywords/value.md)\-Schlüsselwort wird verwendet, um den Wert zu definieren, der vom `set`\-Indexer zugewiesen wird.  
  
-   Indexer müssen nicht durch einen Ganzzahlwert indiziert werden. Sie können entscheiden, wie Sie den spezifischen Suchmechanismus definieren möchten.  
  
-   Indexer können überladen werden.  
  
-   Indexer können mehr als einen formalen Parameter aufweisen, beispielsweise beim Zugreifen auf ein 2D\-Array.  
  
##  <a name="BKMK_RelatedSections"></a> Verwandte Abschnitte  
  
-   [Verwenden von Indexern](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [Indexer in Schnittstellen](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)  
  
-   [Vergleich zwischen Eigenschaften und Indexern](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [Einschränken des Accessorzugriffs](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md)