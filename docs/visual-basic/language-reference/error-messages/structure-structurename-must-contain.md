---
title: Die Struktur "<structurename>" muss mindestens eine Instanzmembervariable oder Instanzereignisdeklaration enthalten, die nicht als "Custom" markiert ist.
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: a350940cf052aa8fbee4a1e3c61cbeaa4e37408a
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870583"
---
# <a name="structure-structurename-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-custom"></a>Die Struktur "\<structurename>" muss mindestens eine Instanzmembervariable oder Instanzereignisdeklaration enthalten, die nicht als "Custom" markiert ist.

Eine Struktur Definition enthält keine nicht freigegebenen Variablen oder nicht freigegebene Nichtbenutzer definierte Ereignisse.  
  
 Jede Struktur muss entweder über eine Variable oder ein Ereignis verfügen, das für jede spezifische Instanz (nicht freigegeben) gilt, anstatt für alle Instanzen Kollektiv (frei[gegeben](../modifiers/shared.md)). Nicht freigegebene Konstanten, Eigenschaften und Prozeduren erfüllen diese Anforderung nicht. Wenn keine nicht freigegebenen Variablen und nur ein nicht frei gegebenes Ereignis vorhanden sind, kann dieses Ereignis nicht als `Custom` Ereignis verwendet werden.  
  
 **Fehler-ID:** BC30941  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Definieren Sie mindestens eine Variable oder ein Ereignis, das nicht ist `Shared` . Wenn Sie nur ein Ereignis definieren, darf es Nichtbenutzer definiert und nicht freigegeben sein.  
  
## <a name="see-also"></a>Weitere Informationen

- [Strukturen](../../programming-guide/language-features/data-types/structures.md)
- [Vorgehensweise: Deklarieren einer Struktur](../../programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Structure Statement](../statements/structure-statement.md)
