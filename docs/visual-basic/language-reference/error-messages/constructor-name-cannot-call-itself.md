---
title: 'Der Konstruktor "<name>" kann sich nicht selbst aufrufen:'
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: f40319cde8388b17e27cfaec2117ebd519ebd4ff
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160944"
---
# <a name="bc30298-constructor-name-cannot-call-itself"></a>BC30298: der Konstruktor " \<name> " kann sich nicht selbst anrufen.

Eine `Sub New` Prozedur in einer Klasse oder Struktur ruft sich selbst auf.

 Der Zweck eines Konstruktors besteht darin, eine Instanz einer Klasse oder Struktur zu initialisieren, wenn Sie erstmalig erstellt wird. Eine Klasse oder Struktur kann mehrere Konstruktoren aufweisen, vorausgesetzt, Sie verfügen über unterschiedliche Parameterlisten. Ein Konstruktor ist berechtigt, einen anderen Konstruktor aufzurufen, um seine Funktionalität zusätzlich zu seiner eigenen Funktionalität auszuführen. Es ist jedoch nicht bedeutungslos, dass sich ein Konstruktor selbst aufruft, und es würde tatsächlich zu einer unendlichen Rekursion kommen, wenn dies zulässig ist.

 **Fehler-ID:** BC30298

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Überprüfen Sie die Parameterliste des aufgerufenen Konstruktors. Er sollte sich von dem des aufzurufenden Konstruktors unterscheiden.

2. Wenn Sie nicht beabsichtigen, einen anderen Konstruktor aufzurufen, entfernen Sie den-Befehl `Sub New` vollständig.

## <a name="see-also"></a>Siehe auch

- [Objektlebensdauer: Erstellen und Zerstören von Objekten](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
