---
title: using-Direktive (C#-Referenz) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
caps.latest.revision: 31
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
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e91cc4fea9fbe57b257e17915cd28b3b82f12f6e
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="using-directive-c-reference"></a>using-Anweisung (C#-Referenz)
Die `using`-Direktive hat drei Verwendungszwecke:  
  
-   Sie ermöglicht die Verwendung von Typen in einem Namespace, sodass Sie die Verwendung eines Typs in diesem Namespace nicht qualifizieren müssen:  
  
    ```csharp  
    using System.Text;  
    ```  
  
-   Ermöglicht den Zugriff auf statische Member eines Typs, ohne den Zugriff mit dem Typnamen zu qualifizieren. 
  
    ```csharp  
    using static System.Math;  
    ```  
     
    Weitere Informationen finden Sie unter [using static-Direktive (C#-Referenz)](using-static.md).

-   Erstellen eines Alias für einen Namespace oder Typ. Dies wird als *using-Aliasdirektive* bezeichnet.  
  
    ```csharp  
    using Project = PC.MyCompany.Project;  
    ```  
  
 Das Schlüsselwort `using` wird auch zum Erstellen von *using-Anweisungen* verwendet, mit denen sichergestellt wird, dass <xref:System.IDisposable>-Objekte wie Dateien und Schriftarten richtig verarbeitet werden. Weitere Informationen finden Sie unter [using-Anweisung](../../../csharp/language-reference/keywords/using-statement.md).  
  
## <a name="using-static-type"></a>Verwenden statischer Typen  
 Sie können auf statische Member eines Typs zugreifen, ohne den Zugriff mit dem Typnamen zu qualifizieren:  
  
```csharp  
using static System.Console;   
using static System.Math;  
class Program   
{   
    static void Main()   
    {   
        WriteLine(Sqrt(3*3 + 4*4));   
    }   
}  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Bereich einer `using`-Direktive ist auf die Datei beschränkt, in der er enthalten ist.  
  
 Erstellen Sie einen `using`-Alias, um das Qualifizieren eines Bezeichners in einen Namespace oder Typ zu vereinfachen. Der rechten Seite einer using-Aliasdirektive muss immer ein vollqualifizierter Typ sein, unabhängig von den using-Direktiven davor.  
  
 Erstellen Sie eine `using`-Direktive, um die Typen in einem Namespace zu verwenden, ohne den Namespace angeben zu müssen. Eine `using`-Direktive ermöglicht Ihnen nicht den Zugriff auf Namespaces, die im angegebenen Namespace geschachtelt sind.  
  
 Gibt zwei Kategorien von Namespaces: benutzerdefinierte und systemdefinierte Namespaces. Benutzerdefinierte Namespaces sind Namespaces, die im Code definiert sind. Eine Liste der systemdefinierten Namespaces finden Sie unter [.NET Framework-Klassenbibliothek](http://go.microsoft.com/fwlink/?LinkID=227195).  
  
 Beispiele für das Verweisen auf Methoden in anderen Assemblys finden Sie unter [Erstellen und Verwenden von C#-DLLs](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4).  
  
## <a name="example-1"></a>Beispiel 1  
  
 Das folgende Beispiel zeigt, wie Sie einen `using`-Alias für einen Namespace definieren und verwenden:  
  
 [!code-cs[csrefKeywordsNamespace#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_1.cs)]  
  
 Eine using-Aliasanweisung kann auf der rechten Seite nicht über einen offenen generischen Typen verfügen. Sie können zum Beispiel keinen using-Alias für „List\<T>“ erstellen, jedoch für „List\<int>“.  
  
## <a name="example-2"></a>Beispiel 2  
  
 Das folgende Beispiel zeigt, wie Sie eine `using`-Direktive und einen `using`-Alias für eine Klasse definieren:  
  
 [!code-cs[csrefKeywordsNamespace#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_2.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Using-Namespaces](../../../csharp/programming-guide/namespaces/using-namespaces.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Namespace Keywords (Schlüsselwörter des Namespace)](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [Namespaces](../../../csharp/programming-guide/namespaces/index.md)   
 [Using-Anweisung](../../../csharp/language-reference/keywords/using-statement.md)

