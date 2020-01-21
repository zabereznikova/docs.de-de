---
title: Statische Konstruktoren – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- static constructors [C#]
- constructors [C#], static
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
ms.openlocfilehash: 7b8171e75bbd27a1079f2c6cc1b7aef6400d7419
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76115763"
---
# <a name="static-constructors-c-programming-guide"></a>Statische Konstruktoren (C#-Programmierhandbuch)
Ein statischer Konstruktor wird verwendet, um [static](../../language-reference/keywords/static.md)-Daten zu initialisieren oder um eine bestimmte Aktion auszuführen, die nur einmal ausgeführt werden muss. Er wird automatisch aufgerufen, bevor die erste Instanz erstellt oder auf irgendwelche statischen Member verwiesen wird.  
  
 [!code-csharp[csProgGuideObjects#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#14)]  
 
## <a name="remarks"></a>Hinweise
Statische Konstruktoren verfügen über folgende Eigenschaften:  
  
- Ein statischer Konstruktor kann nicht über Zugriffsmodifizierer oder Parameter verfügen.  

- Eine Klasse oder Struktur kann nur einen statischen Konstruktor besitzen.

- Statische Konstruktoren können nicht vererbt oder überladen werden.

- Ein statischer Konstruktor kann nicht direkt aufgerufen werden und ist nur für den Aufruf durch die Common Language Runtime (CLR) gedacht. Er wird automatisch aufgerufen.

- Der Benutzer hat keine Kontrolle, wenn der statische Konstruktor im Programm ausgeführt wird.
  
- Ein statischer Konstruktor wird automatisch zum Initialisieren von [class](../../language-reference/keywords/class.md) aufgerufen, bevor die erste Instanz erzeugt wird oder auf irgendwelche statischen Member verwiesen wird. Ein statischer Konstruktor wird vor einem Instanzkonstruktor ausgeführt. Der statische Konstruktor eines Typs wird aufgerufen, wenn eine statische Methode, die einem Ereignis oder Delegaten zugewiesen ist, aufgerufen wird. Dies erfolgt nicht während der Zuweisung. Wenn Variableninitialisierer für statische Felder in der Klasse des statischen Konstruktors vorhanden sind, werden sie direkt vor Ausführung des statischen Konstruktors in der Textreihenfolge ausgeführt, in der sie in der Klassendeklaration vorhanden sind.

- Wenn Sie keinen statischen Konstruktor zum Initialisieren von statischen Feldern angeben, werden alle statischen Felder mit ihrem Standardwert initialisiert, wie unter [Standardwerte für C#-Typen](../../language-reference/builtin-types/default-values.md) aufgeführt.
  
- Wenn ein statischer Konstruktor eine Ausnahme auslöst, wird die Laufzeit ihn kein zweites Mal aufrufen, und der Typ bleibt für die Lebensdauer der Anwendungsdomäne, in der das Programm ausgeführt wird, nicht initialisiert. Eine <xref:System.TypeInitializationException>-Ausnahme wird in aller Regel ausgelöst, wenn ein statischer Konstruktor keinen Typ instanziieren kann oder wenn in einem statischen Konstruktor ein Ausnahmefehler auftritt. Bei impliziten statischen Konstruktoren, die im Quellcode nicht explizit definiert sind, ist zur Problembehandlung möglicherweise eine Prüfung des IL-Codes (Intermediate Language, Zwischensprache) erforderlich.

- Die Existenz eines statischen Konstruktors verhindert die Hinzufügung des <xref:System.Reflection.TypeAttributes.BeforeFieldInit>-Typattributs. Dadurch wird die Laufzeitoptimierung eingeschränkt.

- Ein als `static readonly` deklariertes Feld darf nur als Teil der Deklaration oder in einem statischen Konstruktor zugewiesen werden. Wenn ein expliziter statischer Konstruktor nicht erforderlich ist, initialisieren Sie statische Felder in der Deklaration anstatt über einen statischen Konstruktor, um die Laufzeitoptimierung zu verbessern.

> [!Note]
> Auch wenn auf einen expliziten statischen Konstruktor nicht direkt zugegriffen werden kann, sollte seine Existenz dennoch dokumentiert werden, um bei der Fehlerbehebung von Initialisierungsausnahmen zu helfen.

### <a name="usage"></a>Verwendung

- Eine typische Verwendung statischer Konstruktoren besteht darin, wenn die Klasse eine Protokolldatei verwendet und der Konstruktor verwendet wird, um Einträge in dieser Datei zu schreiben.  
- Statische Konstruktoren sind auch beim Erstellen von Wrapperklassen für nicht verwalteten Code nützlich, wenn der Konstruktor die `LoadLibrary`-Methode aufrufen kann.  

- Statische Konstruktoren sind auch eine praktische Möglichkeit, Laufzeitüberprüfungen des Typparameters über Einschränkungen (Typparametereinschränkungen) zu erzwingen, der zur Kompilierzeit nicht überprüft werden kann.

## <a name="example"></a>Beispiel
 In diesem Beispiel verfügt die Klasse `Bus` über einen statischen Konstruktor. Wenn die erste Instanz von `Bus` erstellt wird (`bus1`), wird der statische Konstruktor zur Initialisierung der Klasse aufgerufen. Die Beispielausgabe überprüft, ob der statische Konstruktor nur einmal ausgeführt wird, obwohl zwei Instanzen von `Bus` erstellt werden, und dass er vor dem Ausführen des Instanzkonstruktors ausgeführt wird.  
  
 [!code-csharp[csProgGuideObjects#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#15)]
 
## <a name="c-language-specification"></a>C#-Sprachspezifikation
Weitere Informationen finden Sie im Abschnitt [Statische Konstruktoren](~/_csharplang/spec/classes.md#static-constructors) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Klassen und Strukturen](./index.md)
- [Konstruktoren](./constructors.md)
- [Statische Klassen und statische Klassenmember](./static-classes-and-static-class-members.md)
- [Finalizer](./destructors.md)
- [Entwurfsrichtlinien für Konstruktoren](../../../standard/design-guidelines/constructor.md#type-constructor-guidelines)
- [Sicherheitswarnung – CA2121: Statische Konstruktoren sollten privat sein.](https://docs.microsoft.com/visualstudio/code-quality/ca2121-static-constructors-should-be-private)
