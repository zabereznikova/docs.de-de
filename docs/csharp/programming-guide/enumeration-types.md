---
title: Enumerationstypen (C#-Programmierhandbuch) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- enumerations [C#]
- enums [C#]
- C# Language, enums
- bit flags [C#]
ms.assetid: 64a9b731-9e3c-4336-8a09-018db2aa10b7
caps.latest.revision: 17
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 7e33ed084c560470a486ebbb25035a59ddc18565
ms.openlocfilehash: 2014047f17f766023ba4db4981aad6e6d4902381
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="enumeration-types-c-programming-guide"></a>Enumerationstypen (C#-Programmierhandbuch)
Ein Enumerationstyp (auch Enumeration oder enum genannt) bietet eine effiziente Möglichkeit zum Definieren von benannten ganzzahligen Konstanten, die einer Variablen zugewiesen werden können. Nehmen wir beispielsweise an, Sie müssen eine Variable definieren, deren Wert einen Tag der Woche darstellt. Es gibt nur sieben sinnvolle Werte, die diese Variable speichern kann. Sie können einen Enumerationstyp verwenden, der mithilfe des [enum](../../csharp/language-reference/keywords/enum.md)-Schlüsselworts deklariert wurde, um diese Werte zu definieren.  
  
 [!code-cs[csProgGuideEnums#1](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_1.cs)]  
  
 Standardmäßig ist [int](../../csharp/language-reference/keywords/int.md) der zugrunde liegende Typ jedes Elements in enum. Sie können mithilfe eines Doppelpunktes einen anderen ganzzahligen numerischen Typ angeben, wie im vorherigen Beispiel gezeigt. Eine vollständige Liste der möglichen Typen finden Sie unter [enum (C#-Referenz)](../../csharp/language-reference/keywords/enum.md).  
  
 Sie können die zugrunde liegenden numerischen Werte durch Umwandeln in den zugrunde liegenden Typ, wie im folgenden Beispiel gezeigt, überprüfen.  
  
```csharp  
Days today = Days.Monday;  
int dayNumber =(int)today;  
Console.WriteLine("{0} is day number #{1}.", today, dayNumber);  
  
Months thisMonth = Months.Dec;  
byte monthNumber = (byte)thisMonth;  
Console.WriteLine("{0} is month number #{1}.", thisMonth, monthNumber);  
  
// Output:  
// Monday is day number #1.  
// Dec is month number #11.  
```  
  
 Im Folgenden werden die Vorteile der Verwendung eines enum anstelle eines numerischen Typs gezeigt:  
  
-   Sie geben für Clientcode eindeutig die Werte an, die für die Variable gültig sind.  
  
-   In [!INCLUDE[vsprvs](../../csharp/includes/vsprvs_md.md)] listet IntelliSense die definierten Werte auf.  
  
 Wenn Sie keine Werte für die Elemente in der Enumeratorliste angeben, werden die Werte automatisch um 1 erhöht. Im vorherigen Beispiel hat `Days.Sunday` den Wert 0, `Days.Monday` hat den Wert 1 und so weiter. Beim Erstellen eines neuen `Days`-Objekt, wird es den Standardwert `Days.Sunday` (0) aufweisen, wenn Sie nicht explizit einen Wert zuweisen. Wenn Sie ein enum erstellen, wählen Sie den logischen Standardwert aus und weisen Sie ihm einen Wert von Null zu. Dadurch werden alle Enumerationen über diesen Standardwert verfügen, wenn sie nicht explizit einen Wert zugewiesen bekommen, wenn sie erstellt werden.  
  
 Wenn die Variable `meetingDay` vom Typ `Days` ist, dann können Sie (ohne eine explizite Umwandlung) für sie nur einen der durch `Days` definierten Werte zuweisen. Und wenn sich der Sitzungstag ändert, können Sie einen neuen Wert von `Days` auf `meetingDay` zuweisen:  
  
 [!code-cs[csProgGuideEnums#4](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_2.cs)]  
  
> [!NOTE]
>  Es ist möglich, einen beliebigen ganzzahligen Wert an `meetingDay` zuzuweisen. Diese Codezeile ergibt z.B. keinen Fehler: `meetingDay = (Days) 42`. Allerdings sollten Sie dies nicht tun, da implizit erwartet wird, dass eine Enumerationensvariable nur einen der von enum definierten Werte enthält. Einen beliebigen Wert einer Variablen eines Enumerationstyps zuzuweisen bedeutet, ein hohes Fehlerrisiko einzuführen.  
  
 Sie können den Elementen in der Enumeratorliste eines Enumerationstyps Werte zuweisen, und Sie können auch berechnete Werte verwenden:  
  
 [!code-cs[csProgGuideEnums#3](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_3.cs)]  
  
## <a name="enumeration-types-as-bit-flags"></a>Enumerationstypen als Bitflags  
 Sie können einen Enumerationstyp zum Definieren von Bitflags verwenden. Dadurch kann eine Instanz des Enumerationstyps eine beliebige Kombination der Werte speichern, die in der Enumeratorliste definiert sind. (Natürlich können einige Kombinationen nicht sinnvoll oder in Ihrem Programmcode nicht zulässig sein.)  
  
 Sie erstellen ein Bitflags-Enum durch Anwenden des Attribut <xref:System.FlagsAttribute?displayProperty=fullName>, und definieren die Werte entsprechend, damit die bitweisen Operationen `AND`, `OR`, `NOT` und `XOR` ausgeführt werden können. In einem Bitflag-Enum ist eine benannte Konstante mit dem Wert Null enthalten, das bedeutet, dass „keine Flags festgelegt sind“. Geben Sie einem Flag keinen Wert Null, wenn es nicht bedeutet, dass „keine Flags festgelegt sind“.  
  
 Im folgenden Beispiel ist eine andere Version der `Days`-Enum mit dem Namen `Days2` definiert. `Days2` verfügt über das `Flags`-Attribut, und jedem Wert wird die nächste höhere Potenz von 2 zugewiesen. Dies ermöglicht Ihnen die Erstellung einer `Days2`-Variable, deren Wert `Days2.Tuesday` und `Days2.Thursday` ist.  
  
 [!code-cs[csProgGuideEnums#2](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_4.cs)]  
  
 Um ein Flag für einen enum festzulegen, verwenden Sie den bitweisen `OR` Operator, wie im folgenden Beispiel gezeigt:  
  
 [!code-cs[csProgGuideEnums#6](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_5.cs)]  
  
 Verwenden Sie einen bitweisen `AND`-Vorgang, wie im folgenden Beispiel gezeigt, um zu bestimmen, ob ein bestimmtes Flag festgelegt ist:  
  
 [!code-cs[csProgGuideEnums#7](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_6.cs)]  
  
 Weitere Informationen darüber, was Sie beim Definieren von Enumerationstypen mit dem Attribut <xref:System.FlagsAttribute?displayProperty=fullName> berücksichtigen müssen, finden Sie unter <xref:System.Enum?displayProperty=fullName>.  
  
## <a name="using-the-systemenum-methods-to-discover-and-manipulate-enum-values"></a>Verwenden der Methoden System.Enum zum Ermitteln und Bearbeiten der Enumerationswerte  
 Alle Enumerationen sind Instanzen des Typs <xref:System.Enum?displayProperty=fullName>. Sie können keine neuen Klassen von <xref:System.Enum?displayProperty=fullName> ableiten, aber Sie können seine Methoden verwenden, um Informationen zu ermitteln und Werte in einer enum-Instanz zu bearbeiten.  
  
 [!code-cs[csProgGuideEnums#5](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_7.cs)]  
  
 Weitere Informationen finden Sie unter <xref:System.Enum?displayProperty=fullName>.  
  
 Sie können auch mithilfe einer Erweiterungsmethode eine neue Methode für ein enum erstellen. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen einer neuen Methode für eine Enumeration (C#-Programmierhandbuch)](../../csharp/programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).  

## <a name="see-also"></a>Siehe auch  
 <xref:System.Enum?displayProperty=fullName>   
 [C#-Programmierhandbuch](../../csharp/programming-guide/index.md)   
 [enum](../../csharp/language-reference/keywords/enum.md)
