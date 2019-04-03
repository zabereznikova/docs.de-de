---
title: Klasse unterstützt keine Automatisierung oder unterstützt die erwartete Schnittstelle nicht
ms.date: 07/20/2015
f1_keywords:
- vbrID430
ms.assetid: d985bb7e-e48e-443e-86f2-ddb86758757c
ms.openlocfilehash: 28089647e8a67d2da55ddd12288b298bcace66c0
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816186"
---
# <a name="class-does-not-support-automation-or-does-not-support-expected-interface"></a>Klasse unterstützt keine Automatisierung oder unterstützt die erwartete Schnittstelle nicht
Entweder macht die im Funktionsaufruf `GetObject` oder `CreateObject` angegebene Klasse eine Programmierschnittstelle nicht verfügbar, oder Sie haben ein Projekt von .dll in .exe oder umgekehrt konvertiert.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Lesen Sie die Dokumentation zur Anwendung, mit der das Objekt erstellt wurde, um Beschränkungen hinsichtlich des Einsatzes von Automatisierung bei dieser Objektklasse herauszufinden.  
  
2.  Wenn Sie ein Projekt von .dll in .exe oder umgekehrt geändert haben, müssen Sie die Registrierung der alten .dll oder .exe manuell aufheben.  
  
## <a name="see-also"></a>Siehe auch

- [Fehlertypen](../../../visual-basic/programming-guide/language-features/error-types.md)
- [Sprechen Sie mit uns](/visualstudio/ide/talk-to-us)
