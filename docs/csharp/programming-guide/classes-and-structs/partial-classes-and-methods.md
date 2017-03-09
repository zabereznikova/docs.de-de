---
title: "Partielle Klassen und Methoden (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C#-Sprache, Partielle Klassen und Methoden"
  - "Partielle Klassen [C#]"
  - "Partielle Methoden [C#]"
ms.assetid: 804cecb7-62db-4f97-a99f-60975bd59fa1
caps.latest.revision: 35
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 35
---
# Partielle Klassen und Methoden (C#-Programmierhandbuch)
Sie können die Definition einer [Klasse](../../../csharp/language-reference/keywords/class.md) oder einer [Struktur](../../../csharp/language-reference/keywords/struct.md), einer [Schnittstelle](../../../csharp/language-reference/keywords/interface.md) oder einer Methode auf zwei oder mehr Quelldateien aufteilen.  Jede Quelldatei enthält einen Abschnitt der Typ\- oder Methodendefinition, und alle Teile werden bei der Kompilierung der Anwendung miteinander kombiniert.  
  
## Teilklassen  
 Es gibt mehrere Situationen, in denen das Teilen einer Klassendefinition von Vorteil sein kann:  
  
-   Beim Arbeiten an großen Projekten ermöglicht das Aufteilen einer Klasse auf verschiedene Dateien mehreren Programmierern, gleichzeitig daran zu arbeiten.  
  
-   Beim Arbeiten mit einer automatisch generierten Quelle kann der Klasse Code hinzugefügt werden, ohne die Quelldatei neu erstellen zu müssen.  Visual Studio verwendet diesen Ansatz beim Erstellen von Windows Forms, Webdienst\-Wrappercode usw.  Dadurch können Sie Code erstellen, der diese Klassen verwendet, ohne die von Visual Studio erstellte Datei ändern zu müssen.  
  
-   Um eine Klassendefinition aufzuteilen, verwenden Sie den Modifizierer des [partial](../../../csharp/language-reference/keywords/partial-type.md)\-Schlüsselworts, wie im folgenden Beispiel gezeigt:  
  
 [!code-cs[csProgGuideObjects#26](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/partial-classes-and-meth_1.cs)]  
  
 Das `partial`\-Schlüsselwort gibt an, dass weitere Teile der Klasse, Struktur oder Schnittstelle im Namespace definiert werden können.  Alle Teile müssen das `partial`\-Schlüsselwort verwenden.  Alle Teile müssen beim Kompilieren verfügbar sein, um den Gesamttyp zu bilden.  Alle Teile müssen die gleiche Zugriffsebene haben, z. B. `public`, `private` usw.  
  
 Wenn ein Teil als abstract deklariert ist, dann wird der ganze Typ als abstract betrachtet.  Wenn ein Teil als sealed deklariert ist, dann wird der ganze Typ als sealed betrachtet.  Wenn ein Teil einen Basistyp deklariert, dann erbt der ganze Typ diese Klasse.  
  
 Alle Teile, die eine Basisklasse angeben, müssen übereinstimmen. Auch Teile, die eine Basisklasse weglassen, erben den Basistyp.  Teile können unterschiedliche Basisschnittstellen angeben. Der Gesamttyp implementiert alle durch die Teildeklarationen aufgelisteten Schnittstellen.  Alle Klassen\-, Struktur\- oder Schnittstellenmember, die in einer partiellen Definition deklariert sind, stehen allen anderen Teilen zur Verfügung.  Der Gesamttyp ist die Kombination aller Teile zur Kompilierzeit.  
  
> [!NOTE]
>  Der `partial`\-Modifizierer ist für Delegat\- oder Enumerationsdeklarationen nicht verfügbar.  
  
 Das folgende Beispiel zeigt, dass geschachtelte Typen partiell sein können, auch wenn der Typ, in dem sie geschachtelt sind, selbst nicht partiell ist.  
  
 [!code-cs[csProgGuideObjects#25](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/partial-classes-and-meth_2.cs)]  
  
 Zur Kompilierzeit werden die Attribute der partiellen Typdefinitionen zusammengeführt.  Betrachten Sie beispielsweise die folgenden Deklarationen:  
  
 [!code-cs[csProgGuideObjects#23](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/partial-classes-and-meth_3.cs)]  
  
 Sie entsprechen den folgenden Deklarationen:  
  
 [!code-cs[csProgGuideObjects#24](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/partial-classes-and-meth_4.cs)]  
  
 Folgende Elemente werden aus allen Definitionen des partiellen Typs zusammengeführt:  
  
-   XML\-Kommentare  
  
-   interfaces  
  
-   Generische Typparameterattribute  
  
-   Klassenattribute  
  
-   Member  
  
 Betrachten Sie beispielsweise die folgenden Deklarationen:  
  
 [!code-cs[csProgGuideObjects#21](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/partial-classes-and-meth_5.cs)]  
  
 Sie entsprechen den folgenden Deklarationen:  
  
 [!code-cs[csProgGuideObjects#22](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/partial-classes-and-meth_6.cs)]  
  
### Beschränkungen  
 Beim Arbeiten mit partiellen Klassendefinitionen sind mehrere Regeln zu beachten:  
  
-   Alle partiellen Typdefinitionen, die als Teile des gleichen Typs vorgesehen sind, müssen mit `partial` bearbeitet werden.  Durch folgende Klassendeklarationen wird z. B. ein Fehler verursacht:  
  
     [!code-cs[csProgGuideObjects#20](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/partial-classes-and-meth_7.cs)]  
  
-   Der `partial`\-Modifizierer kann nur unmittelbar vor den Schlüsselwörtern `class`, `struct` oder `interface` stehen.  
  
-   Geschachtelte partielle Typen sind in Definitionen des partiellen Typs zulässig, wie im folgenden Beispiel veranschaulicht:  
  
     [!code-cs[csProgGuideObjects#19](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/partial-classes-and-meth_8.cs)]  
  
-   Alle partiellen Typdefinitionen, die als Teile desselben Typs vorgesehen sind, müssen in derselben Assembly und demselben Modul \(EXE\- oder DLL\-Datei\) definiert sein.  Partielle Definitionen können sich nicht über mehrere Module erstrecken.  
  
-   Der Klassenname und die generischen Typparameter müssen in allen partiellen Typdefinitionen übereinstimmen.  Generische Typen können partiell sein.  Jede partielle Deklaration muss die gleichen Parameternamen in der gleichen Reihenfolge verwenden.  
  
-   Folgende Schlüsselwörter sind in Definitionen für partielle Typen optional. Falls sie aber in einer der partiellen Typdefinitionen vorhanden sind, dürfen sie nicht in Konflikt mit Schlüsselwörtern stehen, die in einer anderen partiellen Definition für denselben Typ angegeben sind:  
  
    -   [public](../../../csharp/language-reference/keywords/public.md)  
  
    -   [private](../../../csharp/language-reference/keywords/private.md)  
  
    -   [protected](../../../csharp/language-reference/keywords/protected.md)  
  
    -   [internal](../../../csharp/language-reference/keywords/internal.md)  
  
    -   [abstract](../../../csharp/language-reference/keywords/abstract.md)  
  
    -   [sealed](../../../csharp/language-reference/keywords/sealed.md)  
  
    -   Basisklasse  
  
    -   [new](../../../csharp/language-reference/keywords/new.md)\-Modifizierer \(geschachtelte Teile\)  
  
    -   Generische Einschränkungen  
  
         Weitere Informationen finden Sie unter [Einschränkungen für Typparameter](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).  
  
## Beispiel 1  
  
### Beschreibung  
 Im folgenden Beispiel sind die Felder und der Konstruktor der Klasse, `CoOrds`, in einer partiellen Klassendefinition deklariert, und der `PrintCoOrds`\-Member ist in einer anderen partiellen Klassendefinition deklariert.  
  
### Code  
 [!code-cs[csProgGuideObjects#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/partial-classes-and-meth_9.cs)]  
  
## Beispiel 2  
  
### Beschreibung  
 Das folgende Beispiel zeigt, dass auch partielle Strukturen und Schnittstellen entwickelt werden können.  
  
### Code  
 [!code-cs[csProgGuideObjects#18](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/partial-classes-and-meth_10.cs)]  
  
## Partielle Methoden  
 Eine partielle Klasse oder Struktur kann eine partielle Methode enthalten.  Ein Teil der Klasse enthält die Signatur der Methode.  Eine optionale Implementierung kann im selben oder einem anderen Teil definiert sein.  Ist keine Implementierung angegeben, werden die Methode und alle Aufrufe der Methode beim Kompilieren entfernt.  
  
 Mit partiellen Methoden kann der Implementierer eines Teils einer Klasse eine Methode definieren, ähnlich wie ein Ereignis.  Der Implementierer des anderen Teils der Klasse kann entscheiden, ob die Methode implementiert werden soll oder nicht.  Wird die Methode nicht implementiert, entfernt der Compiler die Methodensignatur und alle Aufrufe der Methode.  Die Aufrufe der Methode, einschließlich aller Ergebnisse, die bei der Auswertung von Argumenten in Aufrufen auftreten würden, haben keine Auswirkungen während der Laufzeit.  So kann jeder Code in der partiellen Klasse eine partielle Methode verwenden, auch wenn die Implementierung nicht bereitgestellt wurde.  Es treten weder Kompilier\- noch Laufzeitfehler auf, wenn die Methode aufgerufen wird, ohne implementiert zu sein.  
  
 Partielle Methoden sind besonders hilfreich, wenn es darum geht, generierten Code anzupassen.  Sie ermöglichen das Reservieren eines Methodennamens und einer Signatur, sodass der generierte Code die Methode aufrufen kann und dem Entwickler die Entscheidung überlassen bleibt, die Methode zu implementieren.  Ähnlich wie partielle Klassen ermöglichen partielle Methoden, dass vom Code\-Generator erstellter Code und vom Entwickler erstellter Code zusammen verwendet werden können, ohne dass Laufzeitkosten entstehen.  
  
 Die Deklaration einer partiellen Methode besteht aus zwei Teilen: Definition und Implementierung.  Diese können sich in getrennten Teilen einer partiellen Klasse oder im selben Teil befinden.  Ohne Implementierungsdeklaration optimiert und entfernt der Compiler sowohl die definierende Deklaration als auch alle Aufrufe der Methode.  
  
```  
// Definition in file1.cs  
partial void onNameChanged();  
  
// Implementation in file2.cs  
partial void onNameChanged()  
{  
  // method body  
}  
```  
  
-   Die Deklarationen partieller Methoden müssen mit dem kontextbezogenen Schlüsselwort [partial](../../../csharp/language-reference/keywords/partial-type.md) beginnen, und die Methode muss [void](../../../csharp/language-reference/keywords/void.md) zurückgeben.  
  
-   Partielle Methoden dürfen [ref](../../../csharp/language-reference/keywords/ref.md)\-Parameter, aber keine [out](../../../csharp/language-reference/keywords/out.md)\-Parameter aufweisen.  
  
-   Partielle Methoden sind implizit [private](../../../csharp/language-reference/keywords/private.md), können also nicht [virtual](../../../csharp/language-reference/keywords/virtual.md) sein.  
  
-   Partielle Methoden dürfen nicht [extern](../../../csharp/language-reference/keywords/extern.md) sein, da durch das Vorhandensein von Text festgelegt ist, ob sie definierend oder implementierend sind.  
  
-   Partielle Methoden können über Modifizierer vom Typ [static](../../../csharp/language-reference/keywords/static.md) und [unsafe](../../../csharp/language-reference/keywords/unsafe.md) verfügen.  
  
-   Partielle Methoden können generisch sein.  Für die definierende Deklaration einer partiellen Methode gelten Einschränkungen, die optional für die implementierende Deklaration wiederholt werden können.  Die Namen von Parametern und Typparametern müssen in der implementierenden und definierenden Deklaration nicht übereinstimmen.  
  
-   Sie können einen [Delegaten](../../../csharp/language-reference/keywords/delegate.md) zu einer partiellen Methode machen, die definiert wurde und implementiert wurde, nicht jedoch zu einer partiellen Methode, die nur definiert wurde.  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Klassen](../../../csharp/programming-guide/classes-and-structs/classes.md)   
 [Strukturen](../../../csharp/programming-guide/classes-and-structs/structs.md)   
 [Schnittstellen](../../../csharp/programming-guide/interfaces/index.md)   
 [partial \(Typ\)](../../../csharp/language-reference/keywords/partial-type.md)