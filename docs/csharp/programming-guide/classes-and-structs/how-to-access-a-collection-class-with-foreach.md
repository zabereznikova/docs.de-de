---
title: 'Gewusst wie: Zugreifen auf Auflistungsklassen mit foreach (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- collection classes [C#], foreach statement
ms.assetid: a6b9cf5c-6c8d-4223-b12c-288949434493
caps.latest.revision: 21
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
ms.openlocfilehash: 2ad81ab699b079f4aabb04a886211e94a937335d
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-access-a-collection-class-with-foreach-c-programming-guide"></a>Gewusst wie: Zugreifen auf Auflistungsklassen mit foreach (C#-Programmierhandbuch)
Das folgende Codebeispiel zeigt, wie Sie eine nicht generische Auflistungsklasse schreiben, die mit [foreach](../../../csharp/language-reference/keywords/foreach-in.md) verwendet werden kann. Das Beispiel definiert eine Zeichenfolgen-Tokenisierungsklasse.  
  
> [!NOTE]
>  Das Beispiel stellt nur die empfohlene Vorgehensweise dar, wenn Sie keine generische Auflistungsklasse verwenden können. Ein Beispiel wie eine typsichere generische Auflistungsklasse implementiert wird, die <xref:System.Collections.Generic.IEnumerable%601> unterstützt, finden Sie unter [Iterators (Iteratoren)](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).  
  
 Im Beispiel verwendet das folgende Codesegment die `Tokens`-Klasse, um den Satz „Dies ist ein Beispielsatz“. in Token aufzuteilen, indem „ “ und „-“ als Trennzeichen verwendet werden. Der Code zeigt anschließend diese Tokens mithilfe einer `foreach`-Anweisung an.  
  
 [!code-cs[csProgGuideCollections#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_1.cs)]  
  
## <a name="example"></a>Beispiel  
 Die `Tokens`-Klasse verwendet intern ein Array, um die Token zu speichern. Da Arrays <xref:System.Collections.IEnumerator> und <xref:System.Collections.IEnumerable> implementieren, hätte das Codebeispiel die Enumerationsmethoden des Arrays (<xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A> und <xref:System.Collections.IEnumerator.Current%2A>) verwenden können, anstatt sie in der Klasse `Tokens` zu definieren. Die Methodendefinitionen sind im Beispiel enthalten, um zu verdeutlichen, wie sie definiert sind und was jede Definition tut.  
  
 [!code-cs[csProgGuideCollections#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_2.cs)]  
  
 In C# muss eine Auflistungsklasse nicht <xref:System.Collections.IEnumerable> und <xref:System.Collections.IEnumerator> implementieren, um mit `foreach` kompatibel zu sein. Wenn die Klasse über die erforderlichen Elemente <xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A> und <xref:System.Collections.IEnumerator.Current%2A> verfügt, wird sie mit `foreach` arbeiten. Das Auslassen der Schnittstellen hat den Vorteil, dass Sie einen Rückgabetyp für `Current` definieren können, der spezifischer als <xref:System.Object> ist. Dadurch wird Typsicherheit bereitgestellt.  
  
 Ändern Sie z.B. die folgenden Zeilen im vorherigen Beispiel.  
  
```csharp  
// Change the Tokens class so that it no longer implements IEnumerable.  
public class Tokens  
{  
    // . . .  
  
    // Change the return type for the GetEnumerator method.  
    public TokenEnumerator GetEnumerator()  
    {   }  
  
    // Change TokenEnumerator so that it no longer implements IEnumerator.  
    public class TokenEnumerator  
    {  
        // . . .  
  
        // Change the return type of method Current to string.  
        public string Current  
        {   }  
    }  
 }  
```  
  
 Da `Current` eine Zeichenfolge zurückgibt, kann der Compiler erkennen, wenn ein nicht kompatibler Typ in einer `foreach`-Anweisung verwendet wird, so wie in folgendem Code dargestellt.  
  
```csharp  
// Error: Cannot convert type string to int.  
foreach (int item in f)    
```  
  
 Wenn <xref:System.Collections.IEnumerator> und `foreach` ausgelassen werden, besteht der Nachteil darin, dass die Auflistungsklasse nicht länger mit den <xref:System.Collections.IEnumerable>-Anweisungen oder entsprechenden Anweisungen anderer Common Language Runtime-Sprachen interoperabel ist.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Collections.Generic>   
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Arrays](../../../csharp/programming-guide/arrays/index.md)   
 [Sammlungen](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)

