---
title: Einschränken des Zugriffsmethodenzugriffs – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- read-only properties [C#]
- read-only indexers [C#]
- accessors [C#]
- properties [C#], read-only
- asymmetric accessor accessibility [C#]
- indexers [C#], read-only
ms.assetid: 6e655798-e112-4301-a680-6310a6e012e1
ms.openlocfilehash: a332fef814f0c81914eb7b8c308de68f719fbaac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714693"
---
# <a name="restricting-accessor-accessibility-c-programming-guide"></a>Einschränken des Accessorzugriffs (C#-Programmierhandbuch)
Die [Get](../../language-reference/keywords/get.md)- und [Set](../../language-reference/keywords/set.md)-Teile einer Eigenschaft oder eines Indexers werden *Zugriffsmethoden* oder Accessoren genannt. Standardmäßig weisen diese Zugriffsmethoden dieselbe Sichtbarkeit oder Zugriffsebene auf: nämlich die der Eigenschaft oder des Indexers, zu dem sie gehören. Weitere Informationen finden Sie unter [Zugriffsebenen](../../language-reference/keywords/accessibility-levels.md). Allerdings ist es manchmal sinnvoll, den Zugriff auf eine der beiden Zugriffsmethoden einzuschränken. Dies bedeutet in der Regel, dass der Zugriff auf den `set`-Accessor eingeschränkt wird, während der `get`-Accessor öffentlich zugänglich bleibt. Beispiel:  
  
 [!code-csharp[csProgGuideIndexers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#6)]  
  
 In diesem Beispiel definiert die Eigenschaft `Name` einen `get`- und einen `set`-Accessor. Der `get`-Accessor erhält die Zugriffsebene der Eigenschaft selbst, in diesem Fall `public`. Der `set`-Accessor wird jedoch explizit durch Anwenden des [Protected](../../language-reference/keywords/protected.md)-Zugriffsmodifizierers auf den Accessor selbst eingeschränkt.  
  
## <a name="restrictions-on-access-modifiers-on-accessors"></a>Einschränkungen für Zugriffsmodifizierer für Accessoren  
 Bei der Verwendung von Accessormodifizierern auf Eigenschaften oder Indexer muss Folgendes beachtet werden:  
  
- Accessormodifizierer können nicht bei einer Schnittstelle oder einer expliziten [Schnittstellen](../../language-reference/keywords/interface.md)-Member-Implementierung verwendet werden.  
  
- Accessormodifizierer können nur verwendet werden, wenn die Eigenschaft oder der Indexer sowohl einen `set`- als auch einen `get`-Accessor besitzt. In diesem Fall ist der Modifizierer nur für einen der beiden Accessoren zulässig.  
  
- Besitzt die Eigenschaft oder der Indexer einen [Override](../../language-reference/keywords/override.md)-Modifizierer, muss der Accessormodifizierer mit dem eventuell vorhandenen Accessor des überschriebenen Accessors übereinstimmen.  
  
- Die Zugriffsebene des Accessors muss restriktiver sein als die Zugriffsebene der Eigenschaft oder des Indexers selbst.  
  
## <a name="access-modifiers-on-overriding-accessors"></a>Zugriffsmodifizierer für Override-Accessoren  
 Beim Überschreiben einer Eigenschaft oder eines Indexers müssen die überschriebenen Accessoren für den überschreibenden Code zugänglich sein. Außerdem müssen der Zugriff der Eigenschaft/des Indexers als auch der Accessoren mit der entsprechenden überschriebenen Eigenschaft/dem Indexer und den Accessoren übereinstimmen. Beispiel:  
  
 [!code-csharp[csProgGuideIndexers#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#7)]  
  
## <a name="implementing-interfaces"></a>Implementieren von Schnittstellen  
 Bei der Verwendung eines Accessors zur Implementierung einer Schnittstelle darf der Accessor keinen Zugriffsmodifizierer besitzen. Wird jedoch zur Implementierung der Schnittstelle nur ein Accessor verwendet, z.B. `get`, kann der andere Accessor einen Zugriffsmodifizierer besitzen. Hier ein Beispiel:  
  
 [!code-csharp[csProgGuideIndexers#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#8)]  
  
## <a name="accessor-accessibility-domain"></a>Zugriffsdomäne des Accessors  
 Bei Verwendung eines Zugriffsmodifizierers für den Accessor wird die [Zugriffsdomäne](../../language-reference/keywords/accessibility-domain.md) des Accessors durch diesen Modifizierer bestimmt.  
  
 Andernfalls wird die Zugriffsdomäne des Accessors durch die Zugriffsebene der Eigenschaft oder des Indexers bestimmt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel enthält drei Klassen: `BaseClass`, `DerivedClass` und `MainClass`. Für `BaseClass` gibt es zwei Eigenschaften, `Name` und `Id` für beide Klassen. Das Beispiel veranschaulicht, wie die Eigenschaft `Id` in `DerivedClass` durch die Eigenschaft `Id` in `BaseClass` ausgeblendet werden kann, wenn ein restriktiver Zugriffsmodifizierer, wie z.B. [protected](../../language-reference/keywords/protected.md) oder [private](../../language-reference/keywords/private.md), verwendet wird. Daher wird beim Zuweisen von Werten zu dieser Eigenschaft stattdessen die Eigenschaft für die Klasse `BaseClass` aufgerufen. Wird der Zugriffsmodifizierer durch [public](../../language-reference/keywords/public.md) ersetzt, kann auf die Eigenschaft zugegriffen werden.  
  
 Das Beispiel zeigt auch, dass die Verwendung eines restriktiven Zugriffsmodifizierers, wie z.B. `private` oder `protected`, auf den `set`-Accessor der Eigenschaft `Name` in `DerivedClass` den Zugriff auf den Accessor verhindert. Mit dem Zuweisen zu dem Accessor wird ein Fehler generiert.  
  
 [!code-csharp[csProgGuideIndexers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#5)]  
  
## <a name="comments"></a>Kommentare  
 Beachten Sie, dass beim Ersetzen der Deklaration `new private string Id` durch `new public string Id` Folgendes ausgegeben wird:  
  
 `Name and ID in the base class: Name-BaseClass, ID-BaseClass`  
  
 `Name and ID in the derived class: John, John123`  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../index.md)
- [Eigenschaften](./properties.md)
- [Indexer](../indexers/index.md)
- [Zugriffsmodifizierer](./access-modifiers.md)
