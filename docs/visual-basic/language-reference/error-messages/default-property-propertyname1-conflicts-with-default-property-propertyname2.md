---
title: Die "<propertyname1>"-Standardeigenschaft verursacht einen Konflikt mit der "<propertyname2>"-Standardeigenschaft in "<classname>" und sollte daher als "Shadows" deklariert werden.
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: 290971a3173c59f08fbd279b6fffe3bcb618cb72
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160606"
---
# <a name="bc40007-default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a>BC40007: die Default-Eigenschaft "" verursacht einen \<propertyname1> Konflikt mit der Standard Eigenschaft " \<propertyname2> " in "" \<classname> und sollte daher als "Shadows" deklariert werden.

Eine Eigenschaft wird mit dem gleichen Namen wie eine Eigenschaft deklariert, die in der Basisklasse definiert ist. In dieser Situation sollte die-Eigenschaft in dieser Klasse den Schatten der Basisklassen Eigenschaft überschatten.

 Diese Meldung ist eine Warnung. `Shadows` wird standardmäßig angenommen. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Fehler-ID:** BC40007

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Fügen Sie das- `Shadows` Schlüsselwort zur Deklaration hinzu, oder ändern Sie den Namen der Eigenschaft, die deklariert wird.

## <a name="see-also"></a>Siehe auch

- [Schatten](../modifiers/shadows.md)
- [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)
