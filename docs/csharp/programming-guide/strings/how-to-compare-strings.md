---
title: 'Vorgehensweise: Vergleichen von Zeichenfolgen (C#-Programmierhandbuch) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- strings [C#], comparison
- comparing strings [C#]
ms.assetid: e1268e28-ee98-4695-98e9-92280f1c33c0
caps.latest.revision: 23
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 164d84a1e241572a1545c6fc2d3d1e9f0821cfcb
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-compare-strings-c-programming-guide"></a>Gewusst wie: Vergleichen von Zeichenfolgen (C#-Programmierhandbuch)
Wenn Sie Zeichenfolgen vergleichen, erzeugen Sie ein Ergebnis, das besagt, dass eine Zeichenfolge größer oder kleiner als eine andere ist oder dass die beiden Zeichenfolgen gleich sind. Die Regeln, nach denen das Ergebnis bestimmt wird, unterscheiden sich abhängig davon, ob Sie einen *Ordinalvergleich* oder einen *kulturabhängigen Vergleich* durchführen. Es ist wichtig, die richtige Art von Vergleich für eine bestimmte Aufgabe zu verwenden.  
  
 Verwenden Sie grundlegende Ordinalvergleiche, wenn Sie die Werte zweier Zeichenfolgen vergleichen oder sortieren, ohne linguistische Konventionen zu berücksichtigen. Ein grundlegender ordinaler Vergleich (`System.StringComparison.Ordinal`) unterscheidet zwischen Groß- und Kleinschreibung, was bedeutet, dass die beiden Zeichenfolgen Zeichen für Zeichen übereinstimmen müssen: „and“ ist nicht gleich „And“ oder „AND“. Eine häufig verwendete Variante ist `System.StringComparison.OrdinalIgnoreCase`, bei der „and“, „And“ und „AND“ nicht unterschieden werden. `StringComparison.OrdinalIgnoreCase` wird häufig verwendet, um Dateinamen, Pfadnamen, Netzwerkpfade und jede andere Zeichenfolge, deren Wert basierend auf dem Gebietsschema des Computers des Benutzers nicht geändert wird, zu vergleichen. Weitere Informationen finden Sie unter <xref:System.StringComparison?displayProperty=fullName>.  
  
 Kulturabhängige Vergleiche werden normalerweise verwendet, um Zeichenfolgen zu vergleichen und zu sortieren, die von Endbenutzern eingegeben werden, da die Zeichen und Sortierungskonventionen dieser Zeichenfolgen je nach Gebietsschema des Computers des Benutzers variieren können. Sogar Zeichenfolgen, die identische Zeichen enthalten, sortieren je nach Kultur des aktuellen Threads möglicherweise unterschiedlich.  
  
> [!NOTE]
>  Wenn Sie Zeichenfolgen vergleichen, sollten Sie die Methoden verwenden, die explizit angeben, welche Art von Vergleich Sie durchführen möchten. Dadurch kann der Code viel besser verwaltet und gelesen werden. Verwenden Sie nach Möglichkeit die Überladungen der Methoden der <xref:System.String?displayProperty=fullName>- und <xref:System.Array?displayProperty=fullName>-Klassen, die einen <xref:System.StringComparison>-Enumerationsparameter akzeptieren, damit Sie angeben können, welcher Typ von Vergleich ausgeführt werden soll. Es empfiehlt sich, beim Vergleichen von Zeichenfolgen die Operatoren `==` und `!=` zu vermeiden. Vermeiden Sie es auch, die <xref:System.String.CompareTo%2A?displayProperty=fullName>-Instanzmethoden zu verwenden, da keine Überladung <xref:System.StringComparison> akzeptiert.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Zeichenfolgen, deren Werte sich basierend auf dem Gebietsschema des Computers des Benutzers nicht ändern, ordnungsgemäß verglichen werden. Darüber hinaus wird die Funktion von C# zur *Internalisierung von Zeichenfolgen* gezeigt. Wenn ein Programm zwei oder mehr identische Zeichenfolgenvariablen deklariert, speichert der Compiler alle am selben Speicherort. Durch Aufrufen der <xref:System.Object.ReferenceEquals%2A>-Methode können Sie sehen, dass die beiden Zeichenfolgen tatsächlich auf das gleiche Objekt im Arbeitsspeicher verweisen. Verwenden Sie die <xref:System.String.Copy%2A?displayProperty=fullName>-Methode, um eine Internalisierung zu vermeiden, wie im Beispiel gezeigt.  
  
 [!code-cs[csProgGuideStrings#11](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-compare-strings_1.cs)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Zeichenfolgen bevorzugt verglichen werden, indem die <xref:System.String?displayProperty=fullName>-Methoden verwendet werden, die eine <xref:System.StringComparison>-Enumeration akzeptieren. Beachten Sie, dass die <xref:System.String.CompareTo%2A?displayProperty=fullName>-Instanzmethoden hier nicht verwendet werden, da keine Überladung <xref:System.StringComparison> akzeptiert.  
  
 [!code-cs[csProgGuideStrings#31](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-compare-strings_2.cs)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie Zeichenfolgen in einem Array auf kulturabhängige Weise mithilfe der statischen <xref:System.Array>-Methoden, die einen <xref:System.StringComparer?displayProperty=fullName>-Parameter akzeptieren, sortieren und danach suchen.  
  
 [!code-cs[csProgGuideStrings#32](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-compare-strings_3.cs)]  
  
 Auflistungsklassen wie z.B. <xref:System.Collections.Hashtable?displayProperty=fullName>, <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> und <xref:System.Collections.Generic.List%601?displayProperty=fullName> verfügen über Konstruktoren, die einen <xref:System.StringComparer?displayProperty=fullName>-Parameter akzeptieren, wenn der Typ der Elemente oder Schlüssel `string` ist. Im Allgemeinen sollten Sie nach Möglichkeit diese Konstruktoren verwenden und entweder `Ordinal` oder `OrdinalIgnoreCase` angeben.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Globalization.CultureInfo?displayProperty=fullName>   
 <xref:System.StringComparer?displayProperty=fullName>   
 [Zeichenfolgen](../../../csharp/programming-guide/strings/index.md)   
 [Vergleichen von Zeichenfolgen](http://msdn.microsoft.com/library/977dc094-fe19-4955-98ec-d2294d04a4ba)   
 [Globalisieren und Lokalisieren von Anwendungen](https://docs.microsoft.com/visualstudio/ide/globalizing-and-localizing-applications)
