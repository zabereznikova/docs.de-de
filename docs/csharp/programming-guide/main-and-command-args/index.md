---
title: Main() und Befehlszeilenargumente (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- CS5001
- main_CSharpKeyword
- Main
dev_langs:
- CSharp
helpviewer_keywords:
- Main method [C#]
- C# language, command-line arguments
- arguments [C#], command-line
- command line [C#], arguments
- command-line arguments [C#], Main method
ms.assetid: 73a17231-cf96-44ea-aa8a-54807c6fb1f4
caps.latest.revision: 30
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
ms.openlocfilehash: 1b2950f7718cda66b545935229a64850449850d0
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="main-and-command-line-arguments-c-programming-guide"></a>Main() und Befehlszeilenargumente (C#-Programmierhandbuch)
Die `Main`-Methode ist der Einstiegspunkt einer C#-Konsolenanwendung oder einer Windows-Anwendung. (Bibliotheken und Dienste erfordern keine `Main`-Methode als Einstiegspunkt.) Wenn die Anwendung gestartet wird, ist die `Main`-Methode die erste Methode, die aufgerufen wird.  
  
 In einem C#-Programm kann nur ein Einstiegspunkt vorhanden sein. Wenn Sie mehr als eine Klasse mit einer `Main`-Methode aufweisen, müssen Sie das Programm mit der **/main**-Compileroption kompilieren, um anzugeben, welche `Main`-Methode als Einstiegspunkt verwendet wird. Weitere Informationen hierzu finden Sie unter [/main (C# Compiler Options)](../../../csharp/language-reference/compiler-options/main-compiler-option.md).  
  
 [!code-cs[csProgGuideMain#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-and-command-line-arguments_1.cs)]  
  
## <a name="overview"></a>Übersicht  
  
-   Die `Main`-Methode ist der Einstiegspunkt eines EXE-Programms, in dem die Programmsteuerung beginnt und endet.  
  
-   `Main` wird innerhalb einer Klasse oder Struktur deklariert. `Main` muss [statisch](../../../csharp/language-reference/keywords/static.md) sein und sollte nicht [öffentlich](../../../csharp/language-reference/keywords/public.md) sein. (Im Beispiel oben erhält es den Standardzugriff [private](../../../csharp/language-reference/keywords/private.md).) Die einschließende Klasse oder Struktur muss nicht statisch sein.  
  
-   `Main` kann den Rückgabetyp `void` oder `int` aufweisen.  
  
-   Die `Main`-Methode kann mit oder ohne `string[]`-Parameter deklariert werden, der die Befehlszeilenargumente enthält. Bei Verwendung von [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] zum Erstellen der Windows Forms-Anwendung können Sie den Parameter manuell hinzufügen oder die <xref:System.Environment>-Klasse anderweitig verwenden, um die Befehlszeilenargumente abzurufen. Parameter werden als mit Null indizierte Befehlszeilenargumente gelesen. Im Gegensatz zu C und C++ wird der Name des Programms nicht als erstes Befehlszeilenargument behandelt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
-   [Befehlszeilenargumente](../../../csharp/programming-guide/main-and-command-args/command-line-arguments.md)  
  
-   [Gewusst wie: Anzeigen von Befehlszeilenargumenten](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
  
-   [Gewusst wie: Zugreifen auf Befehlszeilenargumente mithilfe von foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)  
  
-   [Main()-Rückgabewerte](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen über die Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [Einblicke in ein C#-Programm](../../../csharp/programming-guide/inside-a-program/index.md)   
 [\<paveover>Beispielanwendungen für C#](http://msdn.microsoft.com/en-us/9a9d7aaa-51d3-4224-b564-95409b0f3e15)

