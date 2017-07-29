---
title: Partielle Klassen und Methoden (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- partial methods [C#]
- partial classes [C#]
- C# language, partial classes and methods
ms.assetid: 804cecb7-62db-4f97-a99f-60975bd59fa1
caps.latest.revision: 35
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
ms.openlocfilehash: 41b07af83faa6af23695f3719aae29183c35a417
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="partial-classes-and-methods-c-programming-guide"></a>Partielle Klassen und Methoden (C#-Programmierhandbuch)
Es ist möglich, die Definition einer [Klasse](../../../csharp/language-reference/keywords/class.md) oder einer [Struktur](../../../csharp/language-reference/keywords/struct.md), einer [Schnittstelle](../../../csharp/language-reference/keywords/interface.md) oder einer Methode auf zwei oder mehr Quelldateien aufzuteilen. Jede Quelldatei enthält einen Abschnitt der Typ- oder Methodendefinition. Die Teile werden bei der Kompilierung der Anwendung miteinander kombiniert.  
  
## <a name="partial-classes"></a>Teilklassen  
 Es gibt mehrere Situationen, bei denen das Aufteilen einer Klassendefinition wünschenswert ist:  
  
-   Wenn Sie an großen Projekten arbeiten, können durch das Verteilen einer Klasse auf mehrere Dateien mehrere Programmierer gleichzeitig daran arbeiten.  
  
-   Wenn Sie mit automatisch erzeugten Quellen arbeiten, kann Code einer Klasse hinzugefügt werden, ohne die Quelldatei neu zu erstellen. Visual Studio verwendet diesen Ansatz, wenn es Windows Forms, Webdienst-Wrappercode usw. erstellt. Sie können Code erstellen, der diese Klassen verwendet, ohne die von Visual Studio erstellte Datei ändern zu müssen.  
  
-   Um eine Klassendefinition aufzuteilen, verwenden Sie den Schlüsselwortmodifizierer [partial](../../../csharp/language-reference/keywords/partial-type.md), wie hier gezeigt wird:  
  
 [!code-cs[csProgGuideObjects#26](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_1.cs)]  
  
 Das Schlüsselwort `partial` gibt an, dass andere Teile der Klasse, Struktur oder Schnittstelle im Namespace definiert werden können. Alle Teile müssen das Schlüsselwort `partial` verwenden. Alle Teile müssen zur Kompilierzeit verfügbar sein, um den endgültigen Typ zu bilden. Alle Teile müssen die gleiche Zugriffsebene haben, z.B. `public`, `private` usw.  
  
 Wenn ein beliebiger Teil als abstrakt deklariert wird, wird anschließend der ganze Typ als abstrakt betrachtet. Wenn ein beliebiges Teil als versiegelt deklariert wird, wird anschließend der ganze Typ als versiegelt betrachtet. Wenn ein beliebiger Teil einen Basistyp deklariert, erbt der ganze Typ diese Klasse.  
  
 Alle Teile, die eine Basisklasse angeben, müssen übereinstimmen, aber Teile, die eine Basisklasse auslassen, erben weiterhin den Basistyp. Teile können unterschiedliche Basisschnittstellen angeben, und der letzte Typ implementiert alle Schnittstellen, die von allen Teildeklarationen aufgeführt sind. Alle Klassen-, Struktur- und Schnittstellenmember, die in einer Teildefinition deklariert wurden, sind für alle anderen Teile verfügbar. Der endgültige Typ besteht aus allen Teilen zur Kompilierzeit.  
  
> [!NOTE]
>  Der `partial`-Modifizierer ist nicht für Delegat- oder Enumerationsdeklarationen verfügbar.  
  
 Im folgenden Beispiel wird gezeigt, dass geschachtelte Typen eine Teilausführung sein können, selbst wenn der Typ, in dem sie geschachtelt sind, selbst keine ist.  
  
 [!code-cs[csProgGuideObjects#25](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_2.cs)]  
  
 Zur Kompilierzeit werden Attribute von partiellen Typdefinitionen zusammengeführt. Betrachten Sie beispielsweise die folgenden Deklarationen:  
  
 [!code-cs[csProgGuideObjects#23](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_3.cs)]  
  
 Sie entsprechen den folgenden Deklarationen:  
  
 [!code-cs[csProgGuideObjects#24](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_4.cs)]  
  
 Die folgenden werden aus allen partiellen Typdefinitionen zusammengeführt:  
  
-   XML-Kommentare  
  
-   Schnittstellen  
  
-   Generische Parameterattribute  
  
-   Klassenattribute  
  
-   Member  
  
 Betrachten Sie beispielsweise die folgenden Deklarationen:  
  
 [!code-cs[csProgGuideObjects#21](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_5.cs)]  
  
 Sie entsprechen den folgenden Deklarationen:  
  
 [!code-cs[csProgGuideObjects#22](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_6.cs)]  
  
### <a name="restrictions"></a>Beschränkungen  
 Es sind mehrere Regeln zu beachten, wenn Sie partielle Klassendefinitionen verwenden:  
  
-   Alle partiellen Typdefinitionen, die als Teile des gleichen Typs vorgesehen sind, müssen mit `partial` geändert werden. Die folgenden Klassendeklarationen erzeugen z.B. einen Fehler:  
  
     [!code-cs[csProgGuideObjects#20](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_7.cs)]  
  
-   Der `partial`-Modifizierer kann nur unmittelbar vor den Schlüsselwörtern `class`, `struct` oder `interface` erscheinen.  
  
-   Geschachtelte partielle Typen sind in partiellen Typdefinitionen zulässig, wie im folgenden Beispiel dargestellt wird:  
  
     [!code-cs[csProgGuideObjects#19](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_8.cs)]  
  
-   Alle partiellen Typdefinitionen, die als Teile des gleichen Typs vorgesehen sind, müssen in der gleichen Assembly und demselben Modul (EXE- oder DLL-Datei) definiert werden. Partielle Definitionen können nicht mehrere Module umfassen.  
  
-   Der Klassenname und die generischen Typparameter müssen mit allen partiellen Typdefinitionen übereinstimmen. Generische Typen können partiell sein. Jede partielle Definition muss die gleichen Parameternamen in der gleichen Reihenfolge aufweisen.  
  
-   Die nachfolgenden Schlüsselwörter für eine partielle Typdefinition sind optional, wenn sie aber für eine partielle Definition vorhanden sind, können sie nicht mit anderen Schlüsselwörtern in Konflikt treten, die in anderen partiellen Definitionen desselben Typs angegeben wurden:  
  
    -   [public](../../../csharp/language-reference/keywords/public.md)  
  
    -   [private](../../../csharp/language-reference/keywords/private.md)  
  
    -   [protected](../../../csharp/language-reference/keywords/protected.md)  
  
    -   [internal](../../../csharp/language-reference/keywords/internal.md)  
  
    -   [abstract](../../../csharp/language-reference/keywords/abstract.md)  
  
    -   [sealed](../../../csharp/language-reference/keywords/sealed.md)  
  
    -   Basisklasse  
  
    -   [new](../../../csharp/language-reference/keywords/new.md)-Modifizierer (geschachtelte Teile)  
  
    -   Generische Einschränkungen  
  
         Weitere Informationen finden Sie unter [Einschränkungen für Typparameter](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).  
  
## <a name="example-1"></a>Beispiel 1  
  
### <a name="description"></a>Beschreibung  
 Im folgenden Beispiel werden die Felder und der Konstruktor der Klasse (`CoOrds`) in einer partiellen Klassendefinition deklariert, und der Member (`PrintCoOrds`) wird in einer anderen partiellen Klassendefinition deklariert.  
  
### <a name="code"></a>Code  
 [!code-cs[csProgGuideObjects#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_9.cs)]  
  
## <a name="example-2"></a>Beispiel 2  
  
### <a name="description"></a>Beschreibung  
 Im folgenden Beispiel wird gezeigt, dass Sie auch partielle Strukturen und Schnittstellen entwickeln können.  
  
### <a name="code"></a>Code  
 [!code-cs[csProgGuideObjects#18](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_10.cs)]  
  
## <a name="partial-methods"></a>Partielle Methoden  
 Eine partielle Klasse oder Struktur kann eine partielle Methode enthalten. Ein Teil der Klasse enthält die Signatur der Methode. Eine optionale Implementierung kann im gleichen oder in einem anderen Teil definiert werden. Wenn die Implementierung nicht bereitgestellt wird, werden anschließend die Methode sowie alle Aufrufe an die Methode zur Kompilierzeit entfernt.  
  
 Mit partiellen Methoden kann der Implementierer des einen Teils einer Klasse eine Methode definieren, die einem Ereignis ähnelt. Der Implementierer des anderen Teils der Klasse kann entscheiden, ob die Methode implementiert wird. Wenn die Methode nicht implementiert wird, kann der Compiler anschließend die Methodensignatur und alle Aufrufe an die Methode entfernen. Die Aufrufe an die Methode, einschließlich Ergebnissen, die bei der Auswertung eines Arguments im Aufruf auftreten würden, haben zur Laufzeit keine Auswirkung. Deshalb kann jeder Code in der partiellen Klasse eine partielle Methode frei verwenden, selbst wenn die Implementation nicht bereitgestellt wird. Es ergeben sich keine Laufzeit- oder Kompilierzeitfehler, wenn die Methode aufgerufen, aber nicht implementiert wird.  
  
 Partielle Methoden sind besonders nützlich, um generierten Code anzupassen. Sie ermöglichen, dass Methodenname und -signatur reserviert werden können, sodass generierter Code die Methode aufrufen kann, aber der Entwickler über die Implementierung der Methode entscheiden kann. Wie partielle Klassen ermöglichen partielle Methoden, dass Code, der von einem Codegenerator erstellt wurde, zusammen mit Code, der von einem menschlichen Entwickler erstellt wurde, ohne Laufzeitkosten ausgeführt wird.  
  
 Eine partielle Methodendeklaration besteht aus zwei Teilen: der Definition und der Implementierung. Diese können in separaten Teilen einer partiellen Klasse oder im gleichen Teil sein. Wenn es keine Implementierungsdeklaration gibt, optimiert der Compiler anschließend sowohl die definierende Deklaration als auch alle Aufrufe an die Methode.  
  
```  
// Definition in file1.cs  
partial void onNameChanged();  
  
// Implementation in file2.cs  
partial void onNameChanged()  
{  
  // method body  
}  
```  
  
-   Partielle Methodendeklarationen müssen mit dem Kontextschlüsselwort [partial](../../../csharp/language-reference/keywords/partial-type.md) beginnen, und die Methode muss [void](../../../csharp/language-reference/keywords/void.md) zurückgeben.  
  
-   Partielle Methoden können [ref](../../../csharp/language-reference/keywords/ref.md)-Parameter, aber keine [out](../../../csharp/language-reference/keywords/out.md)-Parameter besitzen.  
  
-   Partielle Methoden sind implizit [privat](../../../csharp/language-reference/keywords/private.md) und können daher nicht [virtuell](../../../csharp/language-reference/keywords/virtual.md) sein.  
  
-   Partielle Methoden können nicht [extern](../../../csharp/language-reference/keywords/extern.md) sein, da das Vorhandensein des Texts bestimmt, ob sie definierend oder implementierend sind.  
  
-   Partielle Methoden können [statische](../../../csharp/language-reference/keywords/static.md) und [unsichere](../../../csharp/language-reference/keywords/unsafe.md) Modifizierer besitzen.  
  
-   Partielle Methoden können generisch sein. Einschränkungen gelten für die definierende partielle Methodendeklaration und können optional für die implementierende wiederholt werden. Parameter- und Typparameternamen müssen in der implementierenden und definierenden Deklaration nicht gleich sein.  
  
-   Sie können einen [Delegaten](../../../csharp/language-reference/keywords/delegate.md) für eine partielle Methode erstellen, die definiert und implementiert wurde. Dies geht jedoch nicht für partielle Methoden, die nur definiert wurden.  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Klassen](../../../csharp/programming-guide/classes-and-structs/classes.md)   
 [Strukturen](../../../csharp/programming-guide/classes-and-structs/structs.md)   
 [Schnittstellen](../../../csharp/programming-guide/interfaces/index.md)   
 [partial (Typ)](../../../csharp/language-reference/keywords/partial-type.md)

