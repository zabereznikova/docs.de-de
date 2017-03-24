---
title: "Klassen (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Klassen [C#]"
  - "C#-Sprache, Klassen"
ms.assetid: e8848524-7273-429f-8aba-c658d5eff5ad
caps.latest.revision: 40
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 40
---
# Klassen (C#-Programmierhandbuch)
Eine *Klasse* ist ein Konstrukt, mit dem benutzerdefinierte Typen erstellt werden können, indem Variablen anderer Typen, Methoden und Ereignisse zusammengefasst werden.  Eine Klasse ist mit einem Entwurf vergleichbar.  Sie definiert die Daten und das Verhalten eines Typs.  Wenn die Klasse nicht als statisch deklariert ist, kann Clientcode sie durch das Erstellen von *Objekten* oder *Instanzen* verwenden, die einer Variablen zugewiesen werden.  Die Variable verbleibt im Arbeitsspeicher, bis alle Verweise darauf den Bereich verlassen.  Zu diesem Zeitpunkt markiert die CLR sie als für die Garbage Collection freigegeben.  Wenn die Klasse als [statisch](../../../csharp/language-reference/keywords/static.md) deklariert ist, ist nur eine Kopie im Speicher vorhanden, und Clientcode kann darauf nur über die Klasse selbst und nicht über eine *Instanzvariable* zugreifen.  Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
 Im Gegensatz zu Strukturen unterstützen Klassen *Vererbung*. Dies ist ein wesentlicher Aspekt der objektorientierten Programmierung.  Weitere Informationen finden Sie unter [Vererbung](../../../csharp/programming-guide/classes-and-structs/inheritance.md).  
  
## Deklarieren von Klassen  
 Wie im folgenden Beispiel dargestellt, werden Klassen mit dem [class](../../../csharp/language-reference/keywords/class.md)\-Schlüsselwort deklariert:  
  
 [!code-cs[csProgGuideObjects#79](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_1.cs)]  
  
 Dem `class`\-Schlüsselwort wird die Zugriffsebene vorangestellt.  Da in diesem Fall [public](../../../csharp/language-reference/keywords/public.md) verwendet wird, können alle Benutzer Objekte von dieser Klasse erstellen.  Der Name der Klasse folgt auf das `class`\-Schlüsselwort.  Der Rest der Definition ist der Klassentext, in dem das Verhalten und die Daten definiert werden.  Die Felder, Eigenschaften, Methoden und Ereignisse für eine Klasse werden zusammen als *Klassenmember* bezeichnet.  
  
## Erstellen von Objekten  
 Obwohl die Begriffe manchmal als Synonyme verwendet werden, sind Klassen und Objekte voneinander zu unterscheiden.  Eine Klasse definiert einen Objekttyp, ist aber selbst kein Objekt.  Ein Objekt ist eine konkrete Entität, die auf einer Klasse basiert und manchmal als Instanz einer Klasse bezeichnet wird.  
  
 Objekte können mit dem [new](../../../csharp/language-reference/keywords/new.md)\-Schlüsselwort erstellt werden, an das der Name der Klasse angehängt wird, auf dem das Objekt basiert. Beispiel:  
  
 [!code-cs[csProgGuideObjects#80](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_2.cs)]  
  
 Beim Erstellen einer Klasseninstanz wird ein Verweis auf das Objekt an den Programmierer zurückgegeben.  Im vorherigen Beispiel ist `object1` ein Verweis auf ein Objekt, das auf `Customer` basiert.  Dieser Verweis verweist auf das neue Objekt, er enthält aber nicht die Objektdaten selbst.  In der Tat können Sie einen Objektverweis erstellen, ohne dabei ein Objekt zu erstellen:  
  
 [!code-cs[csProgGuideObjects#81](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_3.cs)]  
  
 Es wird davon abgeraten, Objektverweise wie diesen zu erstellen, der nicht auf ein Objekt verweist, da beim Zugriff auf ein Objekt über einen solchen Verweis zur Laufzeit ein Fehler auftritt.  Sie können einen solchen Verweis jedoch erstellen, um auf ein Objekt zu verweisen, indem Sie entweder ein neues Objekt erstellen oder es einem vorhandenen Objekt zuweisen. Beispiel:  
  
 [!code-cs[csProgGuideObjects#82](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_4.cs)]  
  
 In diesem Code werden zwei Objektverweise erstellt, die beide auf dasselbe Objekt verweisen.  Daher wirken sich durch `object3` am Objekt vorgenommene Änderungen auf nachfolgende Verwendungen von `object4` aus.  Da auf Objekte, die auf Klassen basieren, mit Verweisen verwiesen wird, werden Klassen auch als Referenztypen bezeichnet.  
  
## Klassenvererbung  
 Vererbung wird mithilfe einer *Ableitung* erreicht. Dies bedeutet, dass eine Klasse mit einer *Basisklasse* deklariert wird, von der sie Daten und Verhalten erbt.  Eine Basisklasse wird angegeben, indem wie im folgenden Beispiel ein Punkt und der Name der Basisklasse sowie der Name der abgeleiteten Klasse angehängt werden:  
  
 [!code-cs[csProgGuideObjects#83](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_5.cs)]  
  
 Wenn eine Klasse eine Basisklasse deklariert, erbt sie sämtliche Member der Basisklasse mit Ausnahme der Konstruktoren.  
  
 Anders als in C\+\+ kann eine Klasse in C\# nur von einer Basisklasse direkt erben.  Da eine Basisklasse jedoch selbst von einer anderen Klasse erben kann, kann eine Klasse indirekt von mehreren Basisklassen erben.  Außerdem kann eine Klasse mehrere Schnittstellen direkt implementieren.  Weitere Informationen finden Sie unter [Schnittstellen](../../../csharp/programming-guide/interfaces/index.md).  
  
 Eine Klasse kann als [abstrakt](../../../csharp/language-reference/keywords/abstract.md) deklariert werden.  Eine abstrakte Klasse enthält abstrakte Methoden, die über eine Signaturdefinition, jedoch nicht über eine Implementierung verfügen.  Abstrakte Klassen können nicht instanziiert werden.  Sie können nur mithilfe von abgeleiteten Klassen verwendet werden, die die abstrakten Methoden implementieren.  Im Gegensatz dazu können von [versiegelten](../../../csharp/language-reference/keywords/sealed.md) Klassen keine anderen Klassen abgeleitet werden.  Weitere Informationen finden Sie unter [Abstrakte und versiegelte Klassen und Klassenmember](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).  
  
 Klassendefinitionen können auf verschiedene Quelldateien verteilt sein.  Weitere Informationen finden Sie unter [Partielle Klassen und Methoden](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).  
  
## Beschreibung  
 Im folgenden Beispiel wird eine öffentliche Klasse definiert, die ein einzelnes Feld, eine Methode und eine spezielle, als Konstruktor bezeichnete Methode enthält.  Weitere Informationen finden Sie unter [Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md).  Die Klasse wird dann mit dem `new`\-Schlüsselwort instanziiert.  
  
## Beispiel  
 [!code-cs[csProgGuideObjects#84](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_6.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Objektorientiertes Programmieren](../Topic/Object-Oriented%20Programming%20\(C%23%20and%20Visual%20Basic\).md)   
 [Polymorphismus](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)   
 [Member](../../../csharp/programming-guide/classes-and-structs/members.md)   
 [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [Destruktoren](../../../csharp/programming-guide/classes-and-structs/destructors.md)   
 [Objekte](../../../csharp/programming-guide/classes-and-structs/objects.md)