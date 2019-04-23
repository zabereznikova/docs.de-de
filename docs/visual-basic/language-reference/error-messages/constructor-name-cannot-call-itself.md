---
title: 'Der Konstruktor "<name>" kann sich nicht selbst aufrufen:'
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: 8459ee7fec6d761161a721c88ccdc88e513fc95f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59324382"
---
# <a name="constructor-name-cannot-call-itself"></a>Konstruktor '\<Name >' kann nicht selbst aufrufen
Ein `Sub New` Prozedur in einer Klasse oder Struktur ruft sich selbst.  
  
 Gibt einen Überblick einen Konstruktor zum Initialisieren einer Instanz einer Klasse oder Struktur bei erstellt. Eine Klasse oder Struktur haben mehrere Konstruktoren, sofern diese unterschiedlichen Parameterlisten aufweisen. Ein Konstruktor ist zulässig, einen anderen Konstruktor, um ihre Funktionalität zusätzlich zu seiner eigenen auszuführen aufrufen. Aber es ist ohne Bedeutung für einen Konstruktor selbst aufrufen, und in der Tat hätte dies Endlosschleife, wenn zulässig.  
  
 **Fehler-ID:** BC30298  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Überprüfen Sie die Parameterliste des Konstruktors aufgerufen wird. Es sollte sich von der Konstruktor den Aufruf sein.  
  
2. Wenn Sie nicht beabsichtigen, einen anderen Konstruktor aufrufen, entfernen Sie die `Sub New` ganz aufgerufen.  
  
## <a name="see-also"></a>Siehe auch

- [Objektlebensdauer: Wie die Objekte erstellt und zerstört werden](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
