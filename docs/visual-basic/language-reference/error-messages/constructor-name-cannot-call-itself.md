---
title: 'Der Konstruktor "<name>" kann sich nicht selbst aufrufen:'
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: dce98a4deef8fbb0e8bc024244b815e23d51c790
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874571"
---
# <a name="constructor-name-cannot-call-itself"></a>Der Konstruktor "\<name>" kann sich nicht selbst aufrufen:

Eine `Sub New` Prozedur in einer Klasse oder Struktur ruft sich selbst auf.  
  
 Der Zweck eines Konstruktors besteht darin, eine Instanz einer Klasse oder Struktur zu initialisieren, wenn Sie erstmalig erstellt wird. Eine Klasse oder Struktur kann mehrere Konstruktoren aufweisen, vorausgesetzt, Sie verfügen über unterschiedliche Parameterlisten. Ein Konstruktor ist berechtigt, einen anderen Konstruktor aufzurufen, um seine Funktionalität zusätzlich zu seiner eigenen Funktionalität auszuführen. Es ist jedoch nicht bedeutungslos, dass sich ein Konstruktor selbst aufruft, und es würde tatsächlich zu einer unendlichen Rekursion kommen, wenn dies zulässig ist.  
  
 **Fehler-ID:** BC30298  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Überprüfen Sie die Parameterliste des aufgerufenen Konstruktors. Er sollte sich von dem des aufzurufenden Konstruktors unterscheiden.  
  
2. Wenn Sie nicht beabsichtigen, einen anderen Konstruktor aufzurufen, entfernen Sie den-Befehl `Sub New` vollständig.  
  
## <a name="see-also"></a>Weitere Informationen

- [Objektlebensdauer: Erstellen und Zerstören von Objekten](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
