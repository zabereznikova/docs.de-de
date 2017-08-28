---
title: into (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- into_CSharpKeyword
- into
dev_langs:
- CSharp
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ef85caf02387432761e5ccbb7e0478b46d32f795
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="into-c-reference"></a>into (C#-Referenz)
Das Kontextschlüsselwort `into` kann zum Erstellen eines temporären Bezeichners verwendet werden, der die Ergebnisse einer [group](../../../csharp/language-reference/keywords/group-clause.md)-, [join](../../../csharp/language-reference/keywords/join-clause.md)- oder [select](../../../csharp/language-reference/keywords/select-clause.md)-Klausel in einem neuen Bezeichner speichert. Dieser Bezeichner kann wiederum ein Generator für zusätzliche Abfragebefehle sein. In einer `group`- oder `select`-Klausel wird die Verwendung des neuen Bezeichners auch als *Fortsetzung* bezeichnet.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Verwendung des Schlüsselworts `into` zur Aktivierung eines temporären Bezeichners `fruitGroup`, der über einen abgeleiteten Typ `IGrouping` verfügt. Mit diesem Bezeichner können Sie die <xref:System.Linq.Enumerable.Count%2A>-Methode für jede Gruppe aufrufen und nur die Gruppen auswählen, die mindestens zwei Wörter enthalten.  
  
 [!code-cs[cscsrefAbfrageSchlüsselwörter#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/into_1.cs)]  
  
 Die Verwendung von `into` in einer `group`-Klausel ist nur erforderlich, wenn Sie zusätzliche Abfragevorgänge für jede Gruppe ausführen möchten. Weitere Informationen finden Sie unter [group-Klausel](../../../csharp/language-reference/keywords/group-clause.md).  
  
 Ein Beispiel für die Verwendung von `into` in einer `join`-Klausel finden Sie unter [join-Klausel](../../../csharp/language-reference/keywords/join-clause.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Abfrageschlüsselwörter (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [LINQ-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [group-Klausel](../../../csharp/language-reference/keywords/group-clause.md)

