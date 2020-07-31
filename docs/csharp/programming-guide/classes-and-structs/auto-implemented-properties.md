---
title: Automatisch implementierte Eigenschaften – C#-Programmierhandbuch
description: Für eine automatisch implementierte Eigenschaft in C# erstellt der Compiler eine private, anonyme Unterstützungsvariable, auf die nur über Zugriffsmethoden „get“ und „set“ der Eigenschaft zugegriffen werden kann.
ms.date: 01/31/2020
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: f58f9a23f26bde7e80d834528d94e38af1231e7b
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474474"
---
# <a name="auto-implemented-properties-c-programming-guide"></a>Automatisch implementierte Eigenschaften (C#-Programmierhandbuch)

In C# 3.0 und höher werden Eigenschaftsdeklarationen durch automatisch implementierte Eigenschaften präziser, wenn in den Eigenschaftenzugriffsmethoden keine zusätzliche Logik erforderlich ist. Zudem ermöglichen sie Clientcode das Erstellen von Objekten. Wenn Sie eine Eigenschaft wie im folgenden Beispiel gezeigt deklarieren, erstellt der Compiler ein privates, anonymes, dahinter liegendes Feld, auf das nur über `get` und `set`-Accessoren zugegriffen werden kann.
  
## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt eine einfache Klasse, die über einige automatisch implementierte Eigenschaften verfügt:  

[!code-csharp[csProgGuideLINQ#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#28)]  

Sie können keine automatisch implementierten Eigenschaften in Schnittstellen deklarieren. Automatisch implementierte Eigenschaften deklarieren ein Unterstützungsfeld für die private Instanz. Schnittstellen deklarieren möglicherweise keine Instanzfelder. Beim Deklarieren einer Eigenschaft in einer Schnittstelle, ohne einen Text zu definieren, wird eine Eigenschaft mit Zugriffsmethoden deklariert, die von allen Typen implementiert werden muss, die die Schnittstelle implementieren.

Ab C# 6 können Sie automatisch implementierte Eigenschaften ähnlich wie Felder initialisieren:  

```csharp  
public string FirstName { get; set; } = "Jane";  
```  

Die im vorherigen Beispiel gezeigte Klasse kann geändert werden. Der Clientcode kann die Werte in Objekten nach der Erstellung ändern. In komplexen Klassen mit signifikantem Verhalten (Methoden) sowie Daten, ist es oft notwendig, öffentliche Eigenschaften zu haben. Bei kleinen Klassen oder Strukturen, die nur einen Satz von Werten (Daten) kapseln und nur wenig oder kein Verhalten besitzen, sollten Sie deshalb Objekte unveränderlich machen, entweder durch Deklarieren der Set-Zugriffsmethode [privat](../../language-reference/keywords/private.md) (unveränderlich für Consumer) machen oder nur durch Deklarieren einer Get-Zugriffsmethode (unveränderlich überall außer im Konstruktor).  Weitere Informationen finden Sie unter [Vorgehensweise: Implementieren einer einfachen Klasse mit automatisch implementierten Eigenschaften](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).

## <a name="see-also"></a>Siehe auch

- [Eigenschaften](./properties.md)
- [Modifizierer](/dotnet/csharp/language-reference/keywords)
