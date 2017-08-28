---
title: "default-Schlüsselwort in generischem Code (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.assetid: b9daf449-4e64-496e-8592-6ed2c8875a98
caps.latest.revision: 22
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
ms.openlocfilehash: b5f5995b720d377717a5fff8a5e7e6e2196c612c
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="default-keyword-in-generic-code-c-programming-guide"></a>default-Schlüsselwort in generischem Code (C#-Programmierhandbuch)
Das Zuweisen eines Standardwerts zu einem parametrisierten Typ T wird bei generischen Klassen und Methoden erschwert, wenn folgende Punkte im Voraus noch unklar sind:  
  
-   Ob T ein Referenztyp oder ein Werttyp ist.  
  
-   Wenn T ein Werttyp ist, ob es ein numerischer Wert oder eine Struktur ist.  
  
 Wenn ein parametrisierter Typ T eine Variable t hat, ist die Anweisung t = NULL nur dann gültig, wenn T ein Referenztyp ist. Außerdem funktioniert t = 0 nur für numerische Werttypen, nicht aber für Strukturen. Die Lösung für dieses Problem besteht in der Verwendung des Schlüsselworts `default`, das NULL für Referenztypen und 0 (null) für numerische Werttypen zurückgibt. Bei Strukturen werden die einzelnen Member der Struktur auf 0 (null) oder auf NULL initialisiert zurückgegeben, je nachdem, ob es sich um Werttypen oder Referenztypen handelt. Bei auf NULL festlegbaren Werttypen wird standardmäßig <xref:System.Nullable%601?displayProperty=fullName> zurückgegeben, die Initialisierung erfolgt analog zu allen anderen Strukturen.  
  
 Das folgende Beispiel aus der Klasse `GenericList<T>` demonstriert die Verwendung des Schlüsselworts `default`. Weitere Informationen finden Sie unter [Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md).  
  
 [!code-cs[csProgGuideGenerics#41](../../../csharp/programming-guide/generics/codesnippet/CSharp/default-keyword-in-generic-code_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Collections.Generic>   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Generika](../../../csharp/programming-guide/generics/index.md)   
 [Generische Methoden](../../../csharp/programming-guide/generics/generic-methods.md)   
 [Generika](~/docs/standard/generics/index.md)

