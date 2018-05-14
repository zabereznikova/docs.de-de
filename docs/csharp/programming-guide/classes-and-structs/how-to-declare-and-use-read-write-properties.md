---
title: 'Gewusst wie: Deklarieren und Verwenden von Lese-/Schreibeigenschaften (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- get accessor [C#], declaring properties
- set accessor [C#]
- properties [C#], declaring
- read/write properties [C#]
- accessors [C#], declaring properties with
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
ms.openlocfilehash: 1930d6c50c176ae1765bdb41af2c7484fb908328
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-declare-and-use-read-write-properties-c-programming-guide"></a>Gewusst wie: Deklarieren und Verwenden von Lese-/Schreibeigenschaften (C#-Programmierhandbuch)
Eigenschaften stellen die Vorteile von öffentlichen Datenmembern bereit, ohne die mit dem ungeschützten, nicht kontrollierten und nicht geprüften Zugriff auf die Daten eines Objekts verknüpften Risiken aufzuweisen. Dies wird durch *Accessoren* erreicht: Dies sind besondere Methoden, die den zugrunde liegenden Datenmembern Werte zuweisen bzw. diese Werte abrufen. Der [set](../../../csharp/language-reference/keywords/set.md)-Accessor ermöglicht das Zuweisen von Datenmembern, und der [get](../../../csharp/language-reference/keywords/get.md)-Accessor ruft Datenmemberwerte ab.  
  
 In diesem Beispiel wird eine `Person`-Klasse mit zwei Eigenschaften dargestellt: `Name` (Zeichenfolge) und `Age` (ganze Zahl). Beide Eigenschaften stellen einen `get`- und einen `set`-Accessor bereit, es handelt sich also um Lese- bzw. Schreibeigenschaften.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideObjects#33](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_1.cs)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Im vorherigen Beispiel sind die `Name`- und `Age`-Eigenschaften [public (öffentlich)](../../../csharp/language-reference/keywords/public.md) und besitzen jeweils einen `get`- und einen `set`-Accessor. Auf diese Weise können diese Eigenschaften von allen Objekten gelesen und überschrieben werden. Manchmal ist es jedoch wünschenswert, einen der Accessoren auszuschließen. Indem Sie den `set`-Accessor auslassen, wandeln Sie die Eigenschaft beispielsweise in eine schreibgeschützte Eigenschaft um:  
  
 [!code-csharp[csProgGuideObjects#87](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_2.cs)]  
  
 Alternativ können Sie einen Accessor öffentlich verfügbar machen, während der andere als privat oder geschützt festgelegt wird. Weitere Informationen finden Sie unter [Asymmetric Accessor Accessibility (Asymmetrischer Accessorzugriff)](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).  
  
 Nachdem die Eigenschaften deklariert wurden, können Sie genauso wie Felder der Klasse verwendet werden. Daher kann sowohl beim Abrufen als auch beim Festlegen von Eigenschaftswerten eine relativ natürliche Syntax verwendet werden. Siehe dazu folgende Anweisungen:  
  
 [!code-csharp[csProgGuideObjects#35](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_3.cs)]  
  
 Beachten Sie, dass in der `set`-Methode einer Eigenschaft eine spezielle `value`-Variable verfügbar ist. Diese Variable enthält den vom Benutzer angegebenen Wert. Beispiel:  
  
 [!code-csharp[csProgGuideObjects#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_4.cs)]  
  
 Beachten Sie die einfache Syntax zum Erhöhen des `Age`-Eigenschaftswerts eines `Person`-Objekts:  
  
 [!code-csharp[csProgGuideObjects#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_5.cs)]  
  
 Wenn getrennte `set`- und `get`-Methoden verwendet wurden, um Eigenschaften zu modellieren, könnte der entsprechende Code folgendermaßen aussehen:  
  
```  
person.SetAge(person.GetAge() + 1);   
```  
  
 Die `ToString`-Methode wird in diesem Beispiel überschrieben:  
  
 [!code-csharp[csProgGuideObjects#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_6.cs)]  
  
 Beachten Sie, dass `ToString` im Programm nicht explizit verwendet wird. Es wird standardmäßig durch die `WriteLine`-Aufrufe aufgerufen.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)
