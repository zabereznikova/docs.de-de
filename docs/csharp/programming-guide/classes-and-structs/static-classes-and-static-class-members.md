---
title: Statische Klassen und statische Klassenmember (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, static members
- static members [C#]
- static classes [C#]
- C# language, static classes
- static class members [C#]
ms.assetid: 235614b5-1371-4dbd-9abd-b406a8b0298b
caps.latest.revision: 49
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
ms.openlocfilehash: 63f46f9ae35b3c699744f7bf61cad3b08b796509
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="static-classes-and-static-class-members-c-programming-guide"></a>Statische Klassen und statische Klassenmember (C#-Programmierhandbuch)
Eine [statische](../../../csharp/language-reference/keywords/static.md) Klasse ist im Grunde identisch mit einer nicht statischen Klasse, aber es gibt einen Unterschied: Eine statische Klasse kann nicht instanziiert werden. Das heißt, Sie können das Schlüsselwort [new](../../../csharp/language-reference/keywords/new.md) nicht verwenden, um eine Variable des Klassentyps zu erstellen. Da keine Instanzvariable vorhanden ist, greifen Sie auf die Member einer statischen Klasse mit dem Klassennamen selbst zu. Wenn Sie z.B: eine statische Klasse haben, die `UtilityClass` heißt, die eine öffentliche Methode mit dem Namen `MethodA` besitzt, rufen Sie die Methode auf, wie im folgenden Beispiel gezeigt wird:  
  
```csharp  
UtilityClass.MethodA();  
```  
  
 Eine statische Klasse kann als geeigneter Container für Reihen von Methoden verwendet werden, die nur Eingabeparameter verarbeiten und keine internen Instanzfelder haben oder festlegen müssen. In der .NET Framework-Klassenbibliothek enthält z.B. die statische Klasse <xref:System.Math?displayProperty=fullName> Methoden, die mathematische Vorgänge ausführen, ohne dass es notwendig ist, Daten zu speichern oder abzurufen, die in einer bestimmten Instanz der Klasse <xref:System.Math> einzigartig sind. Sie wenden also die Member der Klasse an, indem der Klassen- und Methodennamen angegeben wird, wie im folgenden Beispiel gezeigt wird.  
  
```csharp  
double dub = -3.14;  
Console.WriteLine(Math.Abs(dub));  
Console.WriteLine(Math.Floor(dub));  
Console.WriteLine(Math.Round(Math.Abs(dub)));  
  
// Output:  
// 3.14  
// -4  
// 3  
```  
  
 Wie auch bei allen Klassentypen werden die Typinformationen für eine statische Klasse von der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Common Language Runtime (CLR) geladen, wenn das Programm, das auf die Klasse verweist, geladen wird. Das Programm kann nicht genau angeben, wann die Klasse geladen wird. Jedoch wird sichergestellt, dass es geladen wird, und dass seine Felder initialisiert sowie seine statischen Konstruktoren aufgerufen sind, bevor zum ersten Mal auf die Klasse in Ihrem Programm verwiesen wird. Ein statischer Konstruktor wird nur einmal aufgerufen, und eine statische Klasse verbleibt im Speicher für die Lebensdauer der Anwendungsdomäne, in der sich das Programm befindet.  
  
> [!NOTE]
>  Wie Sie eine nicht statische Klasse erstellen, die es erlaubt, dass nur eine Instanz von ihr selbst erstellt wird, finden Sie unter [Implementierung von Singleton in C#](http://go.microsoft.com/fwlink/?LinkID=100567).  
  
 Die folgende Liste stellt die Haupteigenschaften einer statischen Klasse dar:  
  
-   Enthält nur statische Member  
  
-   Kann nicht instanziiert werden  
  
-   Ist versiegelt  
  
-   Darf keine [Instanzkonstruktoren](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md) enthalten  
  
 Daher ist das Erstellen einer statischen Klasse grundsätzlich dasselbe wie das Erstellen einer Klasse, die nur statische Member und einen privaten Konstruktor enthält. Ein privater Konstruktor verhindert, dass die Klasse instanziiert wird. Der Vorteil bei der Verwendung einer statischen Klasse ist, dass der Compiler überprüfen und dadurch sicherstellen kann, dass keine Instanzmember versehentlich hinzugefügt werden. Der Compiler garantiert, dass Instanzen dieser Klasse nicht erstellt werden können.  
  
 Statische Klassen sind versiegelt und können nicht vererbt werden. Sie können nur von der Klasse <xref:System.Object> erben. Statische Klassen können keinen Instanzkonstruktor enthalten. Allerdings können sie einen statischen Konstruktor enthalten. Nicht statische Klassen sollten auch einen statischen Konstruktor definieren, wenn die Klasse statische Member enthält, die eine nicht triviale Initialisierung erfordern. Weitere Informationen finden Sie unter [Statische Konstruktoren](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).  
  
## <a name="example"></a>Beispiel  
 Dies ist ein Beispiel für eine statische Klasse, die zwei Methoden enthält, die die Temperatur von Grad Celsius in Fahrenheit und umgekehrt konvertieren:  
  
 [!code-cs[csProgGuideObjects#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_1.cs)]  
  
## <a name="static-members"></a>Statische Member  
 Eine nicht statische Klasse kann statische Methoden, Felder, Eigenschaften oder Ereignisse enthalten. Der statische Member ist für eine Klasse aufrufbar, selbst wenn keine Instanz der Klasse erstellt wurde. Auf den statischen Member wird immer vom Klassennamen, nicht vom Namen der Instanz, zugegriffen. Es ist nur eine Kopie eines statischen Members vorhanden, unabhängig davon, wie viele Instanzen der Klasse erstellt werden. Statische Methoden und Eigenschaften können nicht auf nicht statische Felder und Ereignisse in ihrem enthaltenden Typ zugreifen, und sie können nicht auf eine Instanzvariable für ein beliebiges Objekt zugreifen, außer es wird ausdrücklich an einen Methodenparameter übergeben.  
  
 Es ist üblicher, eine nicht statische Klasse mit einigen statischen Membern zu deklarieren, statt eine ganze Klasse als statisch zu deklarieren. Zwei häufige Verwendungen von statischen Feldern bestehen daraus, dass die Anzahl von instanziierten Objekten mitgezählt wird, oder dass ein Wert gespeichert wird, der für alle Instanzen freigegeben werden muss.  
  
 Statische Methoden können überladen, aber nicht überschrieben werden, da sie zu der Klasse gehören und nicht zu einer Instanz der Klasse.  
  
 Obwohl ein Feld nicht als `static const` deklariert werden kann, ist ein [const](../../../csharp/language-reference/keywords/const.md)-Feld in seinem Verhalten grundsätzlich statisch. Es gehört zum Typ und nicht zu Instanzen des Typs. Daher kann auf const-Felder mithilfe der gleichen Notation `ClassName.MemberName` zugegriffen werden, die für statische Felder verwendet wird. Es wird keine Objektinstanz benötigt.  
  
 C# unterstützt keine statischen lokalen Variablen (Variablen, die im Methodenbereich deklariert werden).  
  
 Deklarieren Sie statische Klassenmember mithilfe des Schlüsselworts `static` vor dem Rückgabetyp des Members, wie im folgenden Beispiel gezeigt wird:  
  
 [!code-cs[csProgGuideObjects#29](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_2.cs)]  
  
 Statische Member werden initialisiert, bevor auf die statischen Member zum ersten Mal zugegriffen wird, und bevor der statische Konstruktor, sofern vorhanden, aufgerufen wird. Verwenden Sie zum Angeben des Speicherorts des Members den Namen der Klasse anstelle des Variablennamens, um auf einen statischen Klassenmember zuzugreifen, wie im folgenden Beispiel gezeigt wird:  
  
 [!code-cs[csProgGuideObjects#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_3.cs)]  
  
 Wenn Ihre Klasse statische Felder enthält, stellen Sie einen statischen Konstruktor bereit, der sie beim Laden der Klasse initialisiert.  
  
 Ein Aufruf einer statischen Methode erzeugt eine Aufrufanweisung in Microsoft Intermediate Language (MSIL), während ein Aufruf einer Instanzmethode eine Anweisung `callvirt` erzeugt, die auch auf Verweise auf ein NULL-Objekt überprüft. Jedoch ist in den meisten Fällen der Leistungsunterschied zwischen den beiden nicht bedeutend genug.  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [static](../../../csharp/language-reference/keywords/static.md)   
 [Klassen](../../../csharp/programming-guide/classes-and-structs/classes.md)   
 [Klasse](../../../csharp/language-reference/keywords/class.md)   
 [Statische Konstruktoren](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)   
 [Instanzkonstruktoren](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)

