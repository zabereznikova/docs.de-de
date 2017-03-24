---
title: "Automatisch implementierte Eigenschaften (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Automatisch implementierte Eigenschaften [C#]"
  - "Eigenschaften [C#], Automatisch implementiert"
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
caps.latest.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 23
---
# Automatisch implementierte Eigenschaften (C#-Programmierhandbuch)
In C\# 3.0 und höher werden Eigenschaftsdeklarationen durch automatisch implementierte Eigenschaften präziser, wenn in den Eigenschaftenaccessoren keine zusätzliche Logik erforderlich ist.  Sie können damit auch Clientcode aktivieren, um Objekte zu erstellen.  Wenn Sie eine Eigenschaft wie im folgenden Beispiel gezeigt deklarieren, erstellt der Compiler ein privates, anonymes, dahinter liegendes Feld, auf das nur über `get` und `set`\-Accessoren zugegriffen werden kann.  
  
## Beispiel  
 Das folgende Beispiel zeigt eine einfache Klasse, die über einige automatisch implementierte Eigenschaften verfügt:  
  
 [!code-cs[csProgGuideLINQ#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/auto-implemented-properties_1.cs)]  
  
 In C\#\-6 und höher können Sie automatisch implementierte Eigenschaften entsprechend auf Felder initialisieren:  
  
```c#  
public string FirstName { get; set; } = "Jane";  
```  
  
 Die im vorherigen Beispiel gezeigte Klasse kann geändert werden.  Clientcode kann die Werte in Objekten ändern, nachdem sie erstellt wurden.  In komplexen Klassen mit signifikantem Verhalten \(Methoden\) sowie Daten, ist es oft notwendig, öffentliche Eigenschaften zu haben.  Bei kleinen Klassen oder Strukturen, die nur einen Satz von Werten \(Daten\) kapseln und nur wenig oder kein Verhalten besitzen, deshalb sollten Sie Objekte entweder durch Deklarieren des Set\-Accessors als [private](../../../csharp/language-reference/keywords/private.md) \(unveränderliche für Consumer\) unveränderlich machen oder nur durch Deklarieren eines Get\-Accessor \(unveränderlich überall außer im Konstruktor\).  Weitere Informationen finden Sie unter [Gewusst wie: Implementieren einer einfachen Klasse mit automatisch implementierten Eigenschaften](../../../csharp/programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).  
  
 Attribute sind für automatisch implementierte Eigenschaften, jedoch offensichtlich nicht für die dahinter liegenden Felder zulässig, da diese nicht aus dem Quellcode zugänglich sind.  Wenn Sie ein Attribut auf das dahinter liegende Feld einer Eigenschaft verwenden müssen, erstellen Sie einfach eine reguläre Eigenschaft.  
  
## Siehe auch  
 [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)