---
title: "Statische Klassen und statische Klassenmember (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C#-Sprache, Statische Klassen"
  - "C#-Sprache, Statische Member"
  - "Statische Klassenmember [C#]"
  - "Statische Klassen [C#]"
  - "Statische Member [C#]"
ms.assetid: 235614b5-1371-4dbd-9abd-b406a8b0298b
caps.latest.revision: 49
caps.handback.revision: 49
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Statische Klassen und statische Klassenmember (C#-Programmierhandbuch)
Eine [statische](../../../csharp/language-reference/keywords/static.md) Klasse gleicht im Grunde einer nicht statischen Klasse, mit einem Unterschied: eine statische Klasse kann nicht instanziiert werden.  In anderen Worten, Sie können das [new](../../../csharp/language-reference/keywords/new.md)\-Schlüsselwort nicht verwenden, um eine Variable des Klassentyps zu erstellen.  Da keine Instanzvariable vorhanden ist, greifen Sie auf die Member einer statischen Klasse mit dem Klassennamen selbst zu.  Wenn Sie beispielsweise eine statische Klasse mit dem Namen `UtilityClass` haben, die über eine öffentliche Methode mit dem Namen `MethodA` verfügt, rufen Sie die Methode wie im folgenden Beispiel dargestellt auf:  
  
```c#  
UtilityClass.MethodA();  
```  
  
 Eine statische Klasse kann als geeigneter Container für Sätze von Methoden verwendet werden, die nur mit Eingabeparametern arbeiten und die keine internen Instanzfelder abrufen oder festlegen müssen.  In der .NET Framework\-Klassenbibliothek enthält die statische <xref:System.Math?displayProperty=fullName>\-Klasse beispielsweise Methoden zur Durchführung mathematischer Operationen, ohne die Erfordernis zum Speichern oder Abrufen von Daten, die spezifisch für eine bestimmte Instanz der <xref:System.Math>\-Klasse sind.  Das heißt, Sie wenden die Member der Klasse an, indem Sie den Klassennamen und den Methodennamen wie im folgenden Beispiel angeben.  
  
```  
double dub = -3.14;  
Console.WriteLine(Math.Abs(dub));  
Console.WriteLine(Math.Floor(dub));  
Console.WriteLine(Math.Round(Math.Abs(dub)));  
  
// Output:  
// 3.14  
// -4  
// 3  
  
```  
  
 Wie bei allen Klassentypen werden die Typinformationen für eine statische Klasse von der CLR \(Common Language Runtime\) von [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] geladen, wenn das Programm, das auf die Klasse verweist, geladen wird. Das Programm kann nicht genau festlegen, wann die Klasse geladen wird.  Mit Bestimmtheit wird sie jedoch geladen, die zugehörigen Felder werden initialisiert und der statische Konstruktor wird aufgerufen, bevor im Programm zum ersten Mal auf die Klasse verwiesen wird.  Ein statischer Konstruktor wird nur einmal aufgerufen, und eine statische Klasse verbleibt im Speicher für die Lebensdauer der Anwendungsdomäne, in der sich das Programm befindet.  
  
> [!NOTE]
>  Informationen zum Erstellen einer nicht statischen Klasse, die nur die Erstellung einer einzigen Instanz von sich selbst zulässt, finden Sie unter [Implementing Singleton in C\#](http://go.microsoft.com/fwlink/?LinkID=100567).  
  
 Die folgende Liste enthält die Hauptmerkmale einer statischen Klasse:  
  
-   Enthält nur statische Member.  
  
-   Kann nicht instanziiert werden.  
  
-   Ist versiegelt.  
  
-   Kann keine [Instanzkonstruktoren](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md) enthalten.  
  
 Das Erstellen einer statischen Klasse entspricht daher im Wesentlichen dem Erstellen einer Klasse, die nur statische Member und einen privaten Konstruktor enthält.  Ein privater Konstruktor verhindert, dass die Klasse instanziiert wird.  Der Vorteil der Verwendung von statischen Klassen besteht darin, dass der Compiler eine Überprüfung ausführen und sicherstellen kann, dass nicht versehentlich Instanzmember hinzugefügt werden.  Der Compiler garantiert, dass keine Instanzen dieser Klasse erstellt werden können.  
  
 Statische Klassen sind versiegelt und deshalb nicht vererbbar.  Sie können von keiner Klasse erben, außer von <xref:System.Object>.  Statische Klassen können keinen Instanzkonstruktor enthalten, stattdessen jedoch einen statischen Konstruktor.  Nicht statische Klassen sollten auch einen statischen Konstruktor definieren, wenn die Klasse statische Member enthält, die eine nicht triviale Initialisierung erfordern.  Weitere Informationen finden Sie unter [Statische Konstruktoren](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).  
  
## Beispiel  
 Das folgende Beispiel einer statischen Klasse enthält zwei Methoden, die die Temperatur von Grad Celsius in Grad Fahrenheit und umgekehrt umwandeln:  
  
 [!code-cs[csProgGuideObjects#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-c_1.cs)]  
  
## Statische Member  
 Eine nicht statische Klasse kann statische Methoden, Felder, Eigenschaften oder Ereignisse enthalten.  Der statische Member ist in einer Klasse auch dann aufrufbar, wenn keine Instanz der Klasse erstellt wurde.  Auf den statischen Member wird immer anhand des Klassennamens anstelle des Instanznamens zugegriffen.  Von einem statischen Member existiert nur eine Kopie, unabhängig davon, wie viele Instanzen der Klasse erstellt werden.  Statische Methoden und Eigenschaften haben in ihrem enthaltenden Typ keinen Zugriff auf nicht statische Felder und Ereignisse, und sie können auf eine Instanzvariable eines Objekts nur zugreifen, wenn diese explizit in einem Methodenparameter übergeben wird.  
  
 Es kommt es häufiger vor, dass eine nicht statische Klasse mit ein paar statischen Membern deklariert wird, als dass eine gesamte Klasse als statisch deklariert wird.  Das Zählen der Anzahl instanziierter Objekte oder das Speichern eines Werts, der für alle Instanzen freigegeben werden muss, sind zwei allgemeine Verwendungsweisen für statische Felder.  
  
 Statische Methoden können überladen, jedoch nicht überschrieben werden, da sie zur Klasse und nicht zu einer Instanz der Klasse gehören.  
  
 Obwohl ein Feld nicht als `static const` deklariert werden kann, ist ein [const](../../../csharp/language-reference/keywords/const.md)\-Feld in seinem Verhalten im Wesentlichen statisch.  Es gehört zum Typ und nicht zu Instanzen des Typs.  Daher kann auf const\-Felder mithilfe der gleichen `ClassName.MemberName`\-Notation wie bei statischen Feldern zugegriffen werden.  Eine Objektinstanz ist nicht erforderlich.  
  
 C\# unterstützt keine statischen lokalen Variablen \(Variablen, die im Methodenbereich deklariert werden\).  
  
 Statische Klassenmember werden mit dem `static`\-Schlüsselwort vor dem Rückgabetyp des Members deklariert, wie im folgenden Beispiel erläutert:  
  
 [!code-cs[csProgGuideObjects#29](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-c_2.cs)]  
  
 Statische Member werden vor dem ersten Zugriff auf den statischen Member und vor dem Aufruf des statischen Konstruktors, soweit vorhanden, initialisiert.  Sie können auf einen statischen Klassenmember zugreifen, indem Sie anstelle eines Variablennamens den Klassennamen verwenden, um den Speicherort des Members anzugeben, wie im folgenden Beispiel erläutert:  
  
 [!code-cs[csProgGuideObjects#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-c_3.cs)]  
  
 Wenn die Klasse statische Felder enthält, geben Sie einen statischen Konstruktur an, der diese Felder beim Laden der Klasse initialisiert.  
  
 Ein Aufruf einer statischen Methode generiert in Microsoft Intermediate Language \(MSIL\) eine Aufrufanweisung, während ein Aufruf einer Instanzmethode eine `callvirt`\-Anweisung generiert, bei der auch eine Überprüfung auf NULL\-Objektverweise durchgeführt wird.  Meistens ist der Leistungsunterschied zwischen beiden jedoch nicht spürbar.  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Statische](../../../csharp/language-reference/keywords/static.md)   
 [Klassen](../../../csharp/programming-guide/classes-and-structs/classes.md)   
 [Klasse](../../../csharp/language-reference/keywords/class.md)   
 [Statische Konstruktoren](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)   
 [Instanzkonstruktoren](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)