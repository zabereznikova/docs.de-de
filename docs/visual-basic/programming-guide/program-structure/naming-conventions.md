---
title: Namenskonventionen
ms.date: 07/20/2015
helpviewer_keywords:
- names [Visual Basic], Visual Basic rules
- naming conventions
- naming conventions [Visual Basic], Visual Basic
- Visual Basic code, naming conventions
- conventions [Visual Basic], Visual Basic coding
- names [Visual Basic], naming conventions
- naming conventions [Visual Basic], classes
ms.assetid: 164949a4-2a7c-4736-9d82-9c3078e2e56c
ms.openlocfilehash: 20531e379ddf9b93a278795e9b3c0eb91b47e077
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398343"
---
# <a name="visual-basic-naming-conventions"></a>Benennungskonventionen in Visual Basic
Wenn Sie ein Element in der Visual Basic Anwendung benennen, muss das erste Zeichen dieses Namens ein alphabetisches Zeichen oder ein Unterstrich sein. Beachten Sie jedoch, dass Namen, die mit einem Unterstrich beginnen, nicht mit der [Sprachunabhängigkeit und sprachunabhängigen Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) kompatibel sind.  
  
 Die folgenden Vorschläge gelten für die Benennung.  
  
- Beginnen Sie jedes einzelne Wort in einem Namen mit einem Großbuchstaben, wie in `FindLastRecord` und `RedrawMyForm` .  
  
- Beginnen Sie Funktions-und Methodennamen mit einem Verb, wie in `InitNameArray` oder `CloseDialog` .  
  
- Beginnen Sie Klassen-, Struktur-, Modul-und Eigenschaftsnamen mit einem Substantiv, wie in `EmployeeName` oder `CarAccessory` .  
  
- Starten Sie Schnittstellennamen mit dem Präfix "I", gefolgt von einem Substantiv oder einem Substantiv-Ausdruck, wie `IComponent` , oder mit einem Adjektiv, das das Verhalten der Schnittstelle beschreibt, `IPersistable` z.b.. Verwenden Sie den Unterstrich nicht, und verwenden Sie Abkürzungen sparsam, da Abkürzungen Verwirrung verursachen können.  
  
- Beginnen Sie die Namen von Ereignis Handlern mit einem Substantiv, das den Ereignistyp, gefolgt vom `EventHandler` Suffix "", beschreibt, wie in " `MouseEventHandler` ".  
  
- Fügen Sie in Namen von Ereignis Argument Klassen das `EventArgs` Suffix "" ein.  
  
- Wenn ein Ereignis über das Konzept "Before" oder "After" verfügt, verwenden Sie ein Suffix in der Vergangenheit oder Vergangenheits Darstellung, wie in " `ControlAdd` " oder " `ControlAdded` ".  
  
- Verwenden Sie für lange oder häufig verwendete Begriffe Abkürzungen, um die namens Längen angemessen zu halten, z. b. "HTML" anstelle von "Hypertext Markup Language". Im Allgemeinen ist es schwierig, Variablennamen mit mehr als 32 Zeichen auf einem Monitor zu lesen, der auf eine niedrige Auflösung festgelegt ist. Stellen Sie außerdem sicher, dass die Abkürzungen in der gesamten Anwendung einheitlich sind. Das zufällige wechseln in ein Projekt zwischen "HTML" und "Hypertext Markup Language" kann zu Verwirrung führen.  
  
- Vermeiden Sie die Verwendung von Namen in einem inneren Gültigkeitsbereich, die mit Namen in einem äußeren Gültigkeitsbereich identisch sind. Fehler können auftreten, wenn auf die falsche Variable zugegriffen wird. Wenn zwischen einer Variablen und dem Schlüsselwort mit demselben Namen ein Konflikt auftritt, müssen Sie das Schlüsselwort identifizieren, indem Sie es der entsprechenden Typbibliothek vorangestellt haben. Wenn Sie z. b. eine Variable namens haben `Date` , können Sie die intrinsische `Date` Funktion nur durch Aufrufen von verwenden <xref:System.DateTime.Date%2A?displayProperty=nameWithType> .  
  
## <a name="see-also"></a>Weitere Informationen

- [Schlüsselwörter als Elementnamen in Code](keywords-as-element-names-in-code.md)
- [Me, My, MyBase und MyClass](me-my-mybase-and-myclass.md)
- [Declared Element Names](../language-features/declared-elements/declared-element-names.md)
- [Programmstruktur und Codekonventionen](program-structure-and-code-conventions.md)
- [Sprachreferenz zu Visual Basic](../../language-reference/index.md)
