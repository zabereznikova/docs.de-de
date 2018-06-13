---
title: Klasse unterstützt keine Automatisierung oder unterstützt die erwartete Schnittstelle nicht
ms.date: 07/20/2015
f1_keywords:
- vbrID430
ms.assetid: d985bb7e-e48e-443e-86f2-ddb86758757c
ms.openlocfilehash: 860c472794495ef2be37aea7c7d8305c237dfd13
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585669"
---
# <a name="class-does-not-support-automation-or-does-not-support-expected-interface"></a>Klasse unterstützt keine Automatisierung oder unterstützt die erwartete Schnittstelle nicht
Entweder macht die im Funktionsaufruf `GetObject` oder `CreateObject` angegebene Klasse eine Programmierschnittstelle nicht verfügbar, oder Sie haben ein Projekt von .dll in .exe oder umgekehrt konvertiert.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Lesen Sie die Dokumentation zur Anwendung, mit der das Objekt erstellt wurde, um Beschränkungen hinsichtlich des Einsatzes von Automatisierung bei dieser Objektklasse herauszufinden.  
  
2.  Wenn Sie ein Projekt von .dll in .exe oder umgekehrt geändert haben, müssen Sie die Registrierung der alten .dll oder .exe manuell aufheben.  
  
## <a name="see-also"></a>Siehe auch  
 [Fehlertypen](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [Sprechen Sie mit uns](/visualstudio/ide/talk-to-us)
