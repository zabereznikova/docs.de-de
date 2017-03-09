---
title: "Statische Konstruktoren (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Konstruktoren [C#], Statische"
  - "Statische Konstruktoren [C#]"
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
caps.latest.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 23
---
# Statische Konstruktoren (C#-Programmierhandbuch)
Ein statischer Konstruktor wird verwendet, um [static](../../../csharp/language-reference/keywords/static.md)\-Daten zu initialisieren oder um eine einmalige Handlung auszuführen.  Er wird automatisch aufgerufen, bevor die erste Instanz erstellt oder auf statische Member verwiesen wird.  
  
 [!code-cs[csProgGuideObjects#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/static-constructors_1.cs)]  
  
 Statische Konstruktoren verfügen über die folgenden Eigenschaften:  
  
-   Ein statischer Konstruktor akzeptiert weder Zugriffsmodifizierer, noch besitzt er Parameter.  
  
-   Er wird automatisch zur Initialisierung der [Klasse](../../../csharp/language-reference/keywords/class.md) aufgerufen, bevor die erste Instanz erstellt oder auf beliebige statische Member verwiesen wird.  
  
-   Ein statischer Konstruktor kann nicht direkt aufgerufen werden.  
  
-   Der Benutzer kann nicht steuern, wann der statische Konstruktor im Programm ausgeführt wird.  
  
-   Meistens wird ein statischer Konstruktor verwendet, wenn die Klasse eine Protokolldatei verwendet und mithilfe des Konstruktors Einträge in diese Datei vorgenommen werden.  
  
-   Statische Konstruktoren sind auch beim Erstellen von Wrapperklassen für nicht verwalteten Code nützlich, wenn der Konstruktor die `LoadLibrary`\-Methode aufrufen kann.  
  
-   Wenn ein statischer Konstrukter eine Ausnahme aulöst, wird er zur Laufzeit nicht wieder aufgerufen und der Typ bleibt für die Lebensdauer der Anwendungsdomäne, in der das Programm ausgeführt wird, uninitialisiert.  
  
## Beispiel  
 Die `Bus`\-Klasse in diesem Beispiel verfügt über einen statischen Konstruktor.  Wenn die erste Instanz von `Bus` \(`bus1`\) erstellt wird, wird der statische Konstruktor aufgerufen, um die Klasse zu initialisieren.  Die Beispielausgabe überprüft, ob der statische Konstruktor nur einmal ausgeführt wird, obwohl zwei Instanzen von `Bus` erstellt werden. Ferner wird überprüft, ob der Konstruktor vor dem Instanzenkonstruktor ausgeführt wird.  
  
 [!code-cs[csProgGuideObjects#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/static-constructors_2.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)   
 [Destruktoren](../../../csharp/programming-guide/classes-and-structs/destructors.md)