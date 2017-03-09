---
title: "COM-Beispielklasse (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "COM, Verfügbarmachen von Visual C#-Objekten für"
  - "Beispiele [C#], COM-Klassen"
ms.assetid: 6504dea9-ad1c-4993-a794-830fec5270af
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# COM-Beispielklasse (C#-Programmierhandbuch)
Folgendes ist ein Beispiel einer Klasse, die Sie als COM\-Objekt verfügbar machen würden.  Nachdem dieser Code in eine CS\-Datei eingefügt und dem Projekt hinzugefügt wurde, setzen Sie die Eigenschaft **Für COM\-Interop registrieren** auf **True**.  Weitere Informationen finden Sie unter [NIB: How to: Register a Component for COM Interop](http://msdn.microsoft.com/de-de/4de7d474-56e8-4027-994d-d47ca4725c5e).  
  
 Das Verfügbarmachen von Visual C\#\-Objekten für COM erfordert die Deklaration einer Klassenschnittstelle, einer Ereignisschnittstelle \(falls erforderlich\) und der Klasse selbst.  Folgende Regeln gelten für die Klassenmember, damit sie für COM sichtbar sind:  
  
-   Es muss sich um eine öffentliche Klasse handeln.  
  
-   Eigenschaften, Methoden und Ereignisse müssen öffentlich sein.  
  
-   Eigenschaften und Methoden müssen auf der Klassenschnittstelle deklariert werden.  
  
-   Ereignisse müssen auf der Ereignisschnittstelle deklariert werden.  
  
 Andere öffentliche Klassenmember, die nicht auf diesen Schnittstellen deklariert werden, sind für COM nicht sichtbar. Für andere .NET Framework\-Objekte sind sie jedoch sichtbar.  
  
 Um Eigenschaften und Methoden für COM verfügbar zu machen, müssen Sie diese auf der Klassenschnittstelle deklarieren und mit einem `DispId`\-Attribut markieren. Anschließend müssen Sie sie in der Klasse implementieren.  Die Reihenfolge, in der die Member auf der Schnittstelle deklariert werden, entspricht der für die COM\-vtable verwendeten Reihenfolge.  
  
 Um Ereignisse aus Ihrer Klasse verfügbar zu machen, müssen Sie diese auf der Ereignisschnittstelle deklarieren und mit einem `DispId`\-Attribut markieren.  Die Klasse sollte diese Schnittstelle nicht implementieren.  
  
 Die Klasse implementiert die Klassenschnittstelle; sie kann mehr als eine Schnittstelle implementieren, zuerst wird jedoch die standardmäßige Klassenschnittstelle implementiert.  Implementieren Sie hier die für COM verfügbar gemachten Methoden und Eigenschaften.  Sie müssen als öffentlich markiert sein und den Deklarationen in der Klassenschnittstelle entsprechen.  Deklarieren Sie hier darüber hinaus die durch die Klasse ausgelösten Ereignisse.  Sie müssen als öffentlich markiert sein und den Deklarationen in der Ereignisschnittstelle entsprechen.  
  
## Beispiel  
 [!code-cs[csProgGuideInterop#8](../../../csharp/programming-guide/interop/codesnippet/csharp/example-com-class_1.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Interoperabilität](../../../csharp/programming-guide/interop/interoperability.md)   
 [Seite "Erstellen", Projekt\-Designer \(C\#\)](/visual-studio/ide/reference/build-page-project-designer-csharp)