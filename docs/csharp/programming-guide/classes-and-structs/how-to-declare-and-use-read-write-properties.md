---
title: 'Gewusst wie: Deklarieren und Verwenden von Lese-/Schreibeigenschaften – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- get accessor [C#], declaring properties
- set accessor [C#]
- properties [C#], declaring
- read/write properties [C#]
- accessors [C#], declaring properties with
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
ms.openlocfilehash: 2865feb74692e7075c92a9ee2b5cd2a7735a8e62
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971015"
---
# <a name="how-to-declare-and-use-read-write-properties-c-programming-guide"></a>Gewusst wie: Deklarieren und Verwenden von Lese-/Schreibeigenschaften (C#-Programmierhandbuch)
Eigenschaften stellen die Vorteile von öffentlichen Datenmembern bereit, ohne die mit dem ungeschützten, nicht kontrollierten und nicht geprüften Zugriff auf die Daten eines Objekts verknüpften Risiken aufzuweisen. Dies wird durch *Accessoren* erreicht: Dies sind besondere Methoden, die den zugrunde liegenden Datenmembern Werte zuweisen bzw. diese Werte abrufen. Der [set](../../language-reference/keywords/set.md)-Accessor ermöglicht das Zuweisen von Datenmembern, und der [get](../../language-reference/keywords/get.md)-Accessor ruft Datenmemberwerte ab.  
  
 In diesem Beispiel wird eine `Person`-Klasse mit zwei Eigenschaften dargestellt: `Name` (Zeichenfolge) und `Age` (ganze Zahl). Beide Eigenschaften stellen einen `get`- und einen `set`-Accessor bereit, es handelt sich also um Lese- bzw. Schreibeigenschaften.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideObjects#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#33)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Im vorherigen Beispiel sind die `Name`- und `Age`-Eigenschaften [public (öffentlich)](../../language-reference/keywords/public.md) und besitzen jeweils einen `get`- und einen `set`-Accessor. Auf diese Weise können diese Eigenschaften von allen Objekten gelesen und überschrieben werden. Manchmal ist es jedoch wünschenswert, einen der Accessoren auszuschließen. Indem Sie den `set`-Accessor auslassen, wandeln Sie die Eigenschaft beispielsweise in eine schreibgeschützte Eigenschaft um:  
  
 [!code-csharp[csProgGuideObjects#87](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#87)]  
  
 Alternativ können Sie einen Accessor öffentlich verfügbar machen, während der andere als privat oder geschützt festgelegt wird. Weitere Informationen finden Sie unter [Asymmetric Accessor Accessibility (Asymmetrischer Accessorzugriff)](./restricting-accessor-accessibility.md).  
  
 Nachdem die Eigenschaften deklariert wurden, können Sie genauso wie Felder der Klasse verwendet werden. Daher kann sowohl beim Abrufen als auch beim Festlegen von Eigenschaftswerten eine relativ natürliche Syntax verwendet werden. Siehe dazu folgende Anweisungen:  
  
 [!code-csharp[csProgGuideObjects#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#35)]  
  
 Beachten Sie, dass in der `set`-Methode einer Eigenschaft eine spezielle `value`-Variable verfügbar ist. Diese Variable enthält den vom Benutzer angegebenen Wert. Beispiel:  
  
 [!code-csharp[csProgGuideObjects#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#36)]  
  
 Beachten Sie die einfache Syntax zum Erhöhen des `Age`-Eigenschaftswerts eines `Person`-Objekts:  
  
 [!code-csharp[csProgGuideObjects#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#37)]  
  
 Wenn getrennte `set`- und `get`-Methoden verwendet wurden, um Eigenschaften zu modellieren, könnte der entsprechende Code folgendermaßen aussehen:  
  
```csharp  
person.SetAge(person.GetAge() + 1);   
```  
  
 Die `ToString`-Methode wird in diesem Beispiel überschrieben:  
  
 [!code-csharp[csProgGuideObjects#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#38)]  
  
 Beachten Sie, dass `ToString` im Programm nicht explizit verwendet wird. Es wird standardmäßig durch die `WriteLine`-Aufrufe aufgerufen.  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Eigenschaften](./properties.md)
- [Klassen und Strukturen](./index.md)
