---
title: "Klasse unterstützt keine Automatisierung oder unterstützt die erwartete Schnittstelle nicht"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID430
ms.assetid: d985bb7e-e48e-443e-86f2-ddb86758757c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6528ceabeb7fb7a1cdc0beff2fd362632a0a0c9a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="class-does-not-support-automation-or-does-not-support-expected-interface"></a>Klasse unterstützt keine Automatisierung oder unterstützt die erwartete Schnittstelle nicht
Entweder macht die im Funktionsaufruf `GetObject` oder `CreateObject` angegebene Klasse eine Programmierschnittstelle nicht verfügbar, oder Sie haben ein Projekt von .dll in .exe oder umgekehrt konvertiert.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Lesen Sie die Dokumentation zur Anwendung, mit der das Objekt erstellt wurde, um Beschränkungen hinsichtlich des Einsatzes von Automatisierung bei dieser Objektklasse herauszufinden.  
  
2.  Wenn Sie ein Projekt von .dll in .exe oder umgekehrt geändert haben, müssen Sie die Registrierung der alten .dll oder .exe manuell aufheben.  
  
## <a name="see-also"></a>Siehe auch  
 [Fehlertypen](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [Sprechen Sie mit uns](/visualstudio/ide/talk-to-us)
