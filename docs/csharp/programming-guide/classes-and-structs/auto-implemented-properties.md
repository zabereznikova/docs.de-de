---
title: Automatisch implementierte Eigenschaften (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: 0d32dfd626cb8484e935dd0e8608c2e29d3ecbde
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2018
ms.locfileid: "46711206"
---
# <a name="auto-implemented-properties-c-programming-guide"></a>Automatisch implementierte Eigenschaften (C#-Programmierhandbuch)
In C# 3.0 und höher werden Eigenschaftsdeklarationen durch automatisch implementierte Eigenschaften präziser, wenn in den Eigenschaftenzugriffsmethoden keine zusätzliche Logik erforderlich ist. Zudem ermöglichen sie Clientcode das Erstellen von Objekten. Wenn Sie eine Eigenschaft wie im folgenden Beispiel gezeigt deklarieren, erstellt der Compiler ein privates, anonymes, dahinter liegendes Feld, auf das nur über `get` und `set`-Accessoren zugegriffen werden kann.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine einfache Klasse, die über einige automatisch implementierte Eigenschaften verfügt:  
  
 [!code-csharp[csProgGuideLINQ#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/auto-implemented-properties_1.cs)]  
  
 Ab C# 6 können Sie automatisch implementierte Eigenschaften ähnlich wie Felder initialisieren:  
  
```csharp  
public string FirstName { get; set; } = "Jane";  
```  
  
 Die im vorherigen Beispiel gezeigte Klasse kann geändert werden. Clientcode kann die Werte in Objekten ändern, nachdem sie erstellt wurden. In komplexen Klassen mit signifikantem Verhalten (Methoden) sowie Daten, ist es oft notwendig, öffentliche Eigenschaften zu haben. Bei kleinen Klassen oder Strukturen, die nur einen Satz von Werten (Daten) kapseln und nur wenig oder kein Verhalten besitzen, sollten Sie deshalb Objekte unveränderlich machen, entweder durch Deklarieren der Set-Zugriffsmethode [privat](../../../csharp/language-reference/keywords/private.md) (unveränderlich für Consumer) machen oder nur durch Deklarieren einer Get-Zugriffsmethode (unveränderlich überall außer im Konstruktor).  Weitere Informationen finden Sie unter[Vorgehensweise: Implementieren einer einfachen Klasse mit automatisch implementierten Eigenschaften](../../../csharp/programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).  
  
 Attribute sind für automatisch implementierte Eigenschaften, jedoch offensichtlich nicht für die dahinter liegenden Felder zulässig, da diese nicht aus dem Quellcode zugänglich sind. Wenn Sie ein Attribut auf das dahinter liegende Feld einer Eigenschaft verwenden müssen, erstellen Sie einfach eine reguläre Eigenschaft.  
  
## <a name="see-also"></a>Siehe auch

- [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md)  
- [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)
