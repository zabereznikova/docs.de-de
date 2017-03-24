---
title: "using-Direktive (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "using-Direktive [C#]"
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
caps.latest.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 31
---
# using-Direktive (C#-Referenz)
Die `using`\-Direktive hat drei Verwendungszwecke:  
  
-   Sie ermöglicht die Verwendung von Typen in einem Namespace, sodass Sie die Verwendung eines Typs in diesem Namespace nicht qualifizieren müssen:  
  
    ```c#  
    using System.Text;  
    ```  
  
-   Ermöglichen des Zugriffs auf statische Member eines Typs, ohne den Zugriff mit dem Typnamen zu qualifizieren:  
  
    ```c#  
    using static System.Math;  
    ```  
  
-   Erstellen eines Alias für einen Namespace oder Typ.  Dies wird als *Verwenden einer Aliasdirektive* bezeichnet.  
  
    ```c#  
    using Project = PC.MyCompany.Project;  
    ```  
  
 Das `using`\-Schlüsselwort wird auch zum Erstellen von *using\-Anweisungen* verwendet, mit denen sichergestellt wird, dass <xref:System.IDisposable>\-Objekte wie Dateien und Schriftarten richtig verarbeitet werden.  Weitere Informationen finden Sie unter [using\-Anweisung](../../../csharp/language-reference/keywords/using-statement.md).  
  
## Verwenden statischer Typen  
 Sie können auf statische Member eines Typs zugreifen, ohne den Zugriff mit dem Typnamen zu qualifizieren:  
  
```c#  
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
  
 `Using static` importiert nur zugängliche statische Member und geschachtelte Typen, die im angegebenen Typ deklariert sind.  Geerbte Member werden nicht importiert.  Sie können aus jedem benannten Typen mit einer statischen using\-Direktive importieren, einschließlich Visual Basic\-Module.  Wenn F\#\-Funktionen der obersten Ebene in den Metadaten als statische Member eines benannten Typs angezeigt werden, dessen Name ein gültiger C\#\-Bezeichner ist, können die F\#\-Funktionen importiert werden.  
  
 `Using static` macht Erweiterungsmethoden, die im angegebenen Typ deklariert sind, für die Erweiterungsmethodensuche verfügbar.  Die Namen der Erweiterungsmethoden werden jedoch bei nicht referenzierten Verweisen im Code nicht in den Bereich importiert.  
  
 Methoden mit dem gleichen Namen, die aus verschiedenen Typen von verschiedenen statischen using\-Direktiven in der gleichen Kompilierungseinheit oder dem gleichen Namespace importiert wurden, bilden eine Methodengruppe.  Die Überladungsauflösung innerhalb dieser Methodengruppen folgt den normalen C\#\-Regeln.  
  
## Hinweise  
 Der Bereich einer `using`\-Direktive ist auf die Datei beschränkt, in der er enthalten ist.  
  
 Erstellen Sie einen `using`\-Alias, um das Qualifizieren eines Bezeichners in einen Namespace oder Typ zu vereinfachen.  Der rechten Seite einer using\-Aliasdirektive muss immer ein vollqualifizierter Typ sein, unabhängig von den using\-Direktiven davor.  
  
 Erstellen Sie eine `using`\-Direktive, um die Typen in einem Namespace zu verwenden, ohne den Namespace angeben zu müssen.  Eine `using`\-Direktive ermöglicht Ihnen nicht den Zugriff auf Namespaces, die im angegebenen Namespace geschachtelt sind.  
  
 Gibt zwei Kategorien von Namespaces: benutzerdefinierte und systemdefinierte Namespaces.  Benutzerdefinierte Namespaces sind Namespaces, die im Code definiert sind.  Eine Liste der systemdefinierten Namespaces finden Sie unter [.NET Framework\-Klassenbibliothek](http://go.microsoft.com/fwlink/?LinkID=227195).  
  
 Beispiele für das Verweisen auf Methoden in anderen Assemblys finden Sie unter [Erstellen und Verwenden von C\#\-DLLs](../Topic/How%20to:%20Create%20and%20Use%20Assemblies%20Using%20the%20Command%20Line%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Beispiel 1  
  
### Beschreibung  
 Das folgende Beispiel zeigt, wie Sie einen `using`\-Alias für einen Namespace definieren und verwenden:  
  
### Code  
 [!code-cs[csrefKeywordsNamespace#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_1.cs)]  
  
### Kommentare  
 Eine using\-Aliasdirektive kann auf der rechten Seite nicht über einen offenen generischen Typen verfügen.  Sie können zum Beispiel keinen using\-Alias für „List\<T\>“ erstellen, jedoch für „List\<int\>“.  
  
## Beispiel 2  
  
### Beschreibung  
 Das folgende Beispiel zeigt, wie Sie eine `using`\-Direktive und einen `using`\-Alias für eine Klasse definieren:  
  
### Code  
 [!code-cs[csrefKeywordsNamespace#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_2.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Verwenden von Namespaces](../../../csharp/programming-guide/namespaces/using-namespaces.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Namespaceschlüsselwörter](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [Namespaces](../../../csharp/programming-guide/namespaces/index.md)   
 [using\-Anweisung](../../../csharp/language-reference/keywords/using-statement.md)