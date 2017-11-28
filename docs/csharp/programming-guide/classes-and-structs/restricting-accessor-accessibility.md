---
title: "Einschränken des Zugriffsmethodenzugriffs (C#-Programmierhandbuch)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- read-only properties [C#]
- read-only indexers [C#]
- accessors [C#]
- properties [C#], read-only
- asymmetric accessor accesibility [C#]
- indexers [C#], read-only
ms.assetid: 6e655798-e112-4301-a680-6310a6e012e1
caps.latest.revision: "26"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a4905885323f59d8b8b2654a5331e02054334398
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="restricting-accessor-accessibility-c-programming-guide"></a>Einschränken des Zugriffsmethodenzugriffs (C#-Programmierhandbuch)
Die [Get](../../../csharp/language-reference/keywords/get.md)- und [Set](../../../csharp/language-reference/keywords/set.md)-Teile einer Eigenschaft oder eines Indexers werden *Zugriffsmethoden* oder Accessoren genannt. Standardmäßig weisen diese Zugriffsmethoden dieselbe Sichtbarkeit oder Zugriffsebene auf: nämlich die der Eigenschaft oder des Indexers, zu dem sie gehören. Weitere Informationen finden Sie unter [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md). Allerdings ist es manchmal sinnvoll, den Zugriff auf eine der beiden Zugriffsmethoden einzuschränken. Dies bedeutet in der Regel, dass der Zugriff auf den `set`-Accessor eingeschränkt wird, während der `get`-Accessor öffentlich zugänglich bleibt. Zum Beispiel:  
  
 [!code-csharp[csProgGuideIndexers#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_1.cs)]  
  
 In diesem Beispiel definiert die Eigenschaft `Name` einen `get`- und einen `set`-Accessor. Der `get`-Accessor erhält die Zugriffsebene der Eigenschaft selbst, in diesem Fall `public`. Der `set`-Accessor wird jedoch explizit durch Anwenden des [Protected](../../../csharp/language-reference/keywords/protected.md)-Zugriffsmodifizierers auf den Accessor selbst eingeschränkt.  
  
## <a name="restrictions-on-access-modifiers-on-accessors"></a>Einschränkungen für Zugriffsmodifizierer für Accessoren  
 Bei der Verwendung von Accessormodifizierern auf Eigenschaften oder Indexer muss Folgendes beachtet werden:  
  
-   Accessormodifizierer können nicht bei einer Schnittstelle oder einer expliziten [Schnittstellen](../../../csharp/language-reference/keywords/interface.md)-Member-Implementierung verwendet werden.  
  
-   Accessormodifizierer können nur verwendet werden, wenn die Eigenschaft oder der Indexer sowohl einen `set`- als auch einen `get`-Accessor besitzt. In diesem Fall ist der Modifizierer nur für einen der beiden Accessoren zulässig.  
  
-   Besitzt die Eigenschaft oder der Indexer einen [Override](../../../csharp/language-reference/keywords/override.md)-Modifizierer, muss der Accessormodifizierer mit dem eventuell vorhandenen Accessor des überschriebenen Accessors übereinstimmen.  
  
-   Die Zugriffsebene des Accessors muss restriktiver sein als die Zugriffsebene der Eigenschaft oder des Indexers selbst.  
  
## <a name="access-modifiers-on-overriding-accessors"></a>Zugriffsmodifizierer für Override-Accessoren  
 Beim Überschreiben einer Eigenschaft oder eines Indexers müssen die überschriebenen Accessoren für den überschreibenden Code zugänglich sein. Außerdem müssen die Zugriffsebenen der Eigenschaft/des Indexers als auch der Accessoren mit der entsprechenden überschriebenen Eigenschaft/dem Indexer und den Accessoren übereinstimmen. Zum Beispiel:  
  
 [!code-csharp[csProgGuideIndexers#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_2.cs)]  
  
## <a name="implementing-interfaces"></a>Implementieren von Schnittsellen  
 Bei der Verwendung eines Accessors zur Implementierung einer Schnittstelle darf der Accessor keinen Zugriffsmodifizierer besitzen. Wird jedoch zur Implementierung der Schnittstelle nur ein Accessor verwendet, z.B. `get`, kann der andere Accessor einen Zugriffsmodifizierer besitzen. Hier ein Beispiel:  
  
 [!code-csharp[csProgGuideIndexers#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_3.cs)]  
  
## <a name="accessor-accessibility-domain"></a>Zugriffsdomäne des Accessors  
 Bei Verwendung eines Zugriffsmodifizierers für den Accessor wird die [Zugriffsdomäne](../../../csharp/language-reference/keywords/accessibility-domain.md) des Accessors durch diesen Modifizierer bestimmt.  
  
 Andernfalls wird die Zugriffsdomäne des Accessors durch die Zugriffsebene der Eigenschaft oder des Indexers bestimmt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel enthält drei Klassen: `BaseClass`, `DerivedClass` und `MainClass`. Für `BaseClass` gibt es zwei Eigenschaften, `Name` und `Id` für beide Klassen. Das Beispiel veranschaulicht, wie die Eigenschaft `Id` in `DerivedClass` durch die Eigenschaft `Id` in `BaseClass` ausgeblendet werden kann, wenn ein restriktiver Zugriffsmodifizierer, wie z.B. [protected](../../../csharp/language-reference/keywords/protected.md) oder [private](../../../csharp/language-reference/keywords/private.md), verwendet wird. Daher wird beim Zuweisen von Werten zu dieser Eigenschaft stattdessen die Eigenschaft für die Klasse `BaseClass` aufgerufen. Wird der Zugriffsmodifizierer durch [public](../../../csharp/language-reference/keywords/public.md) ersetzt, kann auf die Eigenschaft zugegriffen werden.  
  
 Das Beispiel zeigt auch, dass die Verwendung eines restriktiven Zugriffsmodifizierers, wie z.B. `private` oder `protected`, auf den `set`-Accessor der Eigenschaft `Name` in `DerivedClass` den Zugriff auf den Accessor verhindert. Mit dem Zuweisen zu dem Accessor wird ein Fehler generiert.  
  
 [!code-csharp[csProgGuideIndexers#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_4.cs)]  
  
## <a name="comments"></a>Kommentare  
 Beachten Sie, dass beim Ersetzen der Deklaration `new private string Id` durch `new public string Id` Folgendes ausgegeben wird:  
  
 `Name and ID in the base class: Name-BaseClass, ID-BaseClass`  
  
 `Name and ID in the derived class: John, John123`  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [Indexer](../../../csharp/programming-guide/indexers/index.md)  
 [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)
