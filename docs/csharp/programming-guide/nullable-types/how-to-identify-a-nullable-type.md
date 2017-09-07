---
title: "Gewusst wie: Identifizieren eines Typs, der NULL-Werte zulässt (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- nullable types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
caps.latest.revision: 7
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
ms.openlocfilehash: c9e05bfe8be45e5b71a8db06ce4f2502c5397fd4
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-identify-a-nullable-type-c-programming-guide"></a>Gewusst wie: Identifizieren eines Typs, der NULL-Werte zulässt (C#-Programmierhandbuch)
Sie können den C#-Operator [typeof](../../../csharp/language-reference/keywords/typeof.md) zum Erstellen eines <xref:System.Type>-Objekts verwenden, der einen Nullable-Typ darstellt:  
  
```  
System.Type type = typeof(int?);  
```  
  
 Sie können auch die Klassen und Methoden des <xref:System.Reflection>-Namespace verwenden, um <xref:System.Type>-Objekte zu generieren, die Nullable-Typen darstellen. Wenn Sie jedoch versuchen, Typinformationen von Nullable-Variablen zur Laufzeit abzurufen, indem Sie die <xref:System.Object.GetType%2A>-Methode oder den `is`-Operator verwenden, ist das Ergebnis ein <xref:System.Type>-Objekt, das den zugrunde liegenden Typ und nicht den Nullable-Typ selbst darstellt.  
  
 Das Aufrufen von `GetType` auf einem Nullable-Typ führt dazu, dass ein Boxing-Vorgang ausgeführt wird, wenn der Typ impliziert in <xref:System.Object> konvertiert wird. Aus diesem Grund gibt <xref:System.Object.GetType%2A> immer ein <xref:System.Type>-Objekt zurück, das den zugrunde liegenden Typ und nicht einen Nullable-Typ darstellt.  
  
```  
int? i = 5;  
Type t = i.GetType();  
Console.WriteLine(t.FullName); //"System.Int32"  
```  
  
 Der C#-Operator [is](../../../csharp/language-reference/keywords/is.md) wird auch auf dem zugrunde liegenden Nullable-Typen betrieben. Aus diesem Grund können Sie `is` nicht verwenden, um zu bestimmen, ob eine Variable ein Nullable-Typ ist. Das folgende Beispiel zeigt, dass der `is`-Operator eine Nullable-Variable \<int> als „int“ behandelt.  
  
```  
static void Main(string[] args)  
{  
  int? i = 5;  
  if (i is int) // true  
    //…  
}  
```  
  
## <a name="example"></a>Beispiel  
 Verwenden Sie den folgenden Code, um zu bestimmen, ob ein <xref:System.Type>-Objekt einen Nullable-Typ darstellt. Denken Sie daran, dass dieser Code immer FALSE zurückgibt, wenn das `Type`-Objekt von einem Aufruf auf <xref:System.Object.GetType%2A> zurückgegeben wurde, so wie zuvor in diesem Thema beschrieben wurde.  
  
```  
if (type.IsGenericType && type.GetGenericTypeDefinition() == typeof(Nullable<>)) {…}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Typen, die NULL-Werte zulassen](../../../csharp/programming-guide/nullable-types/index.md)   
 [Boxing von Typen mit Nullwerten](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)

