---
title: Checked und Unchecked – C#-Referenz
ms.custom: seodec18
ms.date: 05/15/2018
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
ms.openlocfilehash: ba4ddd7fa87eb200de0de3aea6f0bc056a40f0e5
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235802"
---
# <a name="checked-and-unchecked-c-reference"></a>Checked und Unchecked (C#-Referenz)
C#-Anweisungen könnten entweder in einem geprüften oder nicht geprüften Kontext (checked oder unchecked) ausgeführt werden. In einem überprüften Kontext löst der arithmetische Überlauf eine Ausnahme aus. In einem nicht aktivierten Kontext wird der arithmetische Überlauf ignoriert und das Ergebnis gekürzt, indem alle höherwertigen Bits verworfen werden, die nicht in den Zieltyp passen.  
  
-   [checked](checked.md) Gibt einen geprüften Kontext an.  
  
-   [unchecked](unchecked.md) Gibt einen ungeprüften Kontext an.  
  
 Die folgenden Vorgänge sind von der Überlaufüberprüfung betroffen:  
  
-   Ausdrücke, die die folgenden vordefinierten Operatoren für ganzzahlige Typen verwenden:  
  
     `++`, `--`, unäres `-`, `+`, `-`, `*`, `/`  
  
-   Explizite numerische Konvertierungen zwischen ganzzahligen Typen oder von `float` oder `double` in einen integralen Typ.  
  
 Wenn weder `checked` noch `unchecked` festgelegt ist, wird der Standardkontext für nicht konstante Ausdrücke (Ausdrücke, die zur Laufzeit ausgewertet werden) vom Wert der Compileroption [-checked](../compiler-options/checked-compiler-option.md) definiert. Standardmäßig ist der Wert dieser Option nicht festgelegt, und arithmetische Operationen werden in einem nicht geprüften Kontext ausgeführt.
 
 Für konstante Ausdrücke (Ausdrücke, die zur Kompilierzeit vollständig ausgewertet werden können) ist der Standardkontext immer geprüft. Überläufe, die während der Auswertung des Ausdrucks zur Kompilierzeit auftreten, führen zu Kompilierzeitfehlern, wenn der konstante Ausdruck nicht explizit in einen ungeprüften Kontext gebracht wird.
  
## <a name="see-also"></a>Siehe auch  

- [C#-Referenz](../index.md)  
- [C#-Programmierhandbuch](../../programming-guide/index.md)  
- [C#-Schlüsselwörter](index.md)  
- [Anweisungsschlüsselwörter](statement-keywords.md)
