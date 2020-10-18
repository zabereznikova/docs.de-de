---
title: Die Struktur "<structurename>" muss mindestens eine Instanzmembervariable oder Instanzereignisdeklaration enthalten, die nicht als "Custom" markiert ist.
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: 4e7ef82659c43be08ee444eaf3f4df663f7aaa53
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159650"
---
# <a name="bc30941-structure-structurename-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-custom"></a>BC30941: die Struktur " \<structurename> " muss mindestens eine Instanzmember-Variable oder mindestens eine Instanzereignisdeklaration enthalten, die nicht als "Custom" gekennzeichnet ist.

Eine Struktur Definition enthält keine nicht freigegebenen Variablen oder nicht freigegebene Nichtbenutzer definierte Ereignisse.

 Jede Struktur muss entweder über eine Variable oder ein Ereignis verfügen, das für jede spezifische Instanz (nicht freigegeben) gilt, anstatt für alle Instanzen Kollektiv (frei[gegeben](../modifiers/shared.md)). Nicht freigegebene Konstanten, Eigenschaften und Prozeduren erfüllen diese Anforderung nicht. Wenn keine nicht freigegebenen Variablen und nur ein nicht frei gegebenes Ereignis vorhanden sind, kann dieses Ereignis nicht als `Custom` Ereignis verwendet werden.

 **Fehler-ID:** BC30941

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Definieren Sie mindestens eine Variable oder ein Ereignis, das nicht ist `Shared` . Wenn Sie nur ein Ereignis definieren, darf es Nichtbenutzer definiert und nicht freigegeben sein.

## <a name="see-also"></a>Siehe auch

- [Strukturen](../../programming-guide/language-features/data-types/structures.md)
- [Vorgehensweise: Deklarieren einer Struktur](../../programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Structure Statement](../statements/structure-statement.md)
