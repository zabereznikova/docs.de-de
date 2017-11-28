---
title: Member (C#-Programmierhandbuch)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- types [C#], nested types
- C# language, type members
ms.assetid: 4a30a4ab-d690-4936-9124-92ce9448665a
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 184d4f2976b8594c308efeb113a0490499e3460e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="members-c-programming-guide"></a>Member (C#-Programmierhandbuch)
Klassen und Strukturen verfügen über Member, die ihre Daten und ihr Verhalten darstellen. Die Member einer Klasse umfassen alle Member, die in dieser Klasse deklariert sind, sowie alle Member (mit Ausnahme von Konstruktoren und Finalizer), die in den Klassen der Vererbungshierarchie deklariert sind. Private Member in Basisklassen werden geerbt. Aus abgeleiteten Klassen kann jedoch nicht darauf zugegriffen werden.  
  
 In der folgenden Tabelle sind die Arten von Membern aufgeführt, die in einer Klasse oder Struktur enthalten sein können:  
  
|Member|Beschreibung|  
|------------|-----------------|  
|[Felder](../../../csharp/programming-guide/classes-and-structs/fields.md)|Felder sind im Gültigkeitsbereich einer Klasse deklarierte Variablen. Ein Feld kann ein integrierter numerischer Typ oder eine Instanz einer anderen Klasse sein. So kann zum Beispiel eine Kalenderklasse über ein Feld verfügen, das das aktuelle Datum enthält.|  
|[Konstanten](../../../csharp/programming-guide/classes-and-structs/constants.md)|Konstanten sind Felder oder Eigenschaften, deren Wert bei der Kompilierung festgelegt wird und nicht geändert werden kann.|  
|[Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md)|Eigenschaften sind Methoden einer Klasse, auf die zugegriffen wird, als ob sie Felder dieser Klasse wären. Eine Eigenschaft kann ein Klassenfeld davor schützen, ohne das Wissen des Objekts geändert zu werden.|  
|[Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md)|Methoden definieren die Aktionen, die von einer Klasse ausgeführt werden können. Methoden können Parameter entgegennehmen, die Eingabedaten bereitstellen, und mithilfe von Parametern Ausgabedaten zurückgeben. Methoden können auch direkt einen Wert zurückgeben, ohne einen Parameter zu verwenden.|  
|[Ereignisse](../../../csharp/programming-guide/events/index.md)|Ereignisse stellen für andere Objekte Benachrichtigungen darüber bereit, dass bestimmte Vorgänge (z. B. das Klicken auf eine Schaltfläche oder die erfolgreiche Beendigung einer Methode) eingetreten sind. Ereignisse werden mithilfe von Delegaten definiert und ausgelöst.|  
|[Operatoren](../../../csharp/programming-guide/statements-expressions-operators/operators.md)|Überladene Operatoren werden als Klassenmember betrachtet. Wenn Sie einen Operator überladen, definieren Sie diesen in einer Klasse als öffentliche statische Methode. Die vordefinierten Operatoren (`+`, `*`, `<` usw.) werden nicht als Member betrachtet. Weitere Informationen finden Sie unter [Überladbare Operatoren](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md).|  
|[Indexer](../../../csharp/programming-guide/indexers/index.md)|Indexer ermöglichen es einem Objekt, ähnlich wie ein Array indiziert zu werden.|  
|[Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md)|Konstruktoren sind Methoden, die beim ersten Erstellen von Objekten aufgerufen werden. Sie werden häufig verwendet, um die Daten der Objekte zu initialisieren.|  
|[Finalizer](../../../csharp/programming-guide/classes-and-structs/destructors.md)|Finalizer werden in C# sehr selten verwendet. Bei Destruktoren handelt es sich um Methoden, die vom Ausführungsmodul der Laufzeit aufgerufen werden, wenn das Objekt aus dem Speicher entfernt werden soll. In der Regel werden sie verwendet, um sicherzustellen, dass Ressourcen, die freigegeben werden müssen, angemessen verarbeitet werden.|  
|[Geschachtelte Typen](../../../csharp/programming-guide/classes-and-structs/nested-types.md)|Geschachtelte Typen sind Typen, die in einem anderen Typ deklariert sind. Geschachtelte Typen werden häufig verwendet, um Objekte zu beschreiben, die nur von den Typen verwendet werden, in denen sie enthalten sind.|  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Klassen](../../../csharp/programming-guide/classes-and-structs/classes.md)  
 [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md)  
 [Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [Finalizer](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
 [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [Felder](../../../csharp/programming-guide/classes-and-structs/fields.md)  
 [Indexer](../../../csharp/programming-guide/indexers/index.md)  
 [Ereignisse](../../../csharp/programming-guide/events/index.md)  
 [Geschachtelte Typen](../../../csharp/programming-guide/classes-and-structs/nested-types.md)  
 [Operatoren](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
 [Überladbare Operatoren](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)
