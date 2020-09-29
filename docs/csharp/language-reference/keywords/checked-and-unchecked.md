---
description: Checked und Unchecked – C#-Referenz
title: Checked und Unchecked – C#-Referenz
ms.date: 05/15/2018
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
ms.openlocfilehash: 0ab30eb238a4db21233da612d132dfcbdb9e8895
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91160514"
---
# <a name="checked-and-unchecked-c-reference"></a>Checked und Unchecked (C#-Referenz)

C#-Anweisungen könnten entweder in einem geprüften oder nicht geprüften Kontext (checked oder unchecked) ausgeführt werden. In einem überprüften Kontext löst der arithmetische Überlauf eine Ausnahme aus. In einem nicht aktivierten Kontext wird der arithmetische Überlauf ignoriert und das Ergebnis gekürzt, indem alle höherwertigen Bits verworfen werden, die nicht in den Zieltyp passen.  
  
- [checked](checked.md) Gibt einen geprüften Kontext an.  
  
- [unchecked](unchecked.md) Gibt einen ungeprüften Kontext an.  
  
 Die folgenden Vorgänge sind von der Überlaufüberprüfung betroffen:  
  
- Ausdrücke, die die folgenden vordefinierten Operatoren für ganzzahlige Typen verwenden:  
  
     `++`, `--`, unäres `-`, `+`, `-`, `*`, `/`  
  
- Explizite numerische Konvertierungen zwischen ganzzahligen Typen oder von `float` oder `double` in einen integralen Typ.  
  
 Wenn weder `checked` noch `unchecked` festgelegt ist, wird der Standardkontext für nicht konstante Ausdrücke (Ausdrücke, die zur Laufzeit ausgewertet werden) vom Wert der Compileroption [-checked](../compiler-options/checked-compiler-option.md) definiert. Standardmäßig ist der Wert dieser Option nicht festgelegt, und arithmetische Operationen werden in einem nicht geprüften Kontext ausgeführt.

 Für konstante Ausdrücke (Ausdrücke, die zur Kompilierzeit vollständig ausgewertet werden können) ist der Standardkontext immer geprüft. Überläufe, die während der Auswertung des Ausdrucks zur Kompilierzeit auftreten, führen zu Kompilierzeitfehlern, wenn der konstante Ausdruck nicht explizit in einen ungeprüften Kontext gebracht wird.
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Anweisungsschlüsselwörter](statement-keywords.md)
