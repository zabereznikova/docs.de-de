---
title: Fehlermeldungen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- errors [Visual Basic]
- error messages
- trappable errors
- errors [Visual Basic], trappable
ms.assetid: f2dda05b-baef-41f5-8bb1-598bd7cf239f
ms.openlocfilehash: 822c0f266e7dd68f063043d98a9f4af308ae93fd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013815"
---
# <a name="error-messages-visual-basic"></a>Fehlermeldungen (Visual Basic)
Wenn Sie eine Visual Basic-Anwendung schreiben, kompilieren oder ausführen, können die folgenden Arten von Fehlern auftreten:  
  
1. Entwurfszeitfehler, die auftreten, wenn Sie eine Anwendung in Visual Studio schreiben.  
  
2. Kompilierzeitfehler, die auftreten, wenn Sie eine Anwendung in Visual Studio oder an einer Eingabeaufforderung kompilieren.  
  
3. Laufzeitfehler, die auftreten, wenn Sie eine Anwendung in Visual Studio oder als eigenständige ausführbare Daten ausführen.  
  
 Informationen zur Behebung bestimmter Fehler finden Sie unter [Zusätzliche Ressourcen für Visual Basic-Programmierer](../../../visual-basic/getting-started/additional-resources.md).  
  
## <a name="run-time-errors"></a>Laufzeitfehler  
 Wenn eine Visual Basic-Anwendung versucht, eine Aktion auszuführen, die das System nicht ausgeführt werden kann, ein Laufzeitfehler tritt auf, und Visual Basic löst eine `Exception` Objekt. Visual Basic können benutzerdefinierte Fehler jeden Datentyps generieren eingeben, einschließlich `Exception` Objekte, mit der `Throw` Anweisung. Eine Anwendung kann den Fehler durch Anzeige der Fehlernummer und -meldung einer abgefangenen Ausnahme identifizieren. Wenn ein Fehler nicht abgefangen wird, wird die Anwendung beendet.  
  
 Der Code kann Laufzeitfehler auffangen und untersuchen. Wenn Sie den Code, der den Fehler erzeugt, in einem `Try`-Block einschließen, können Sie jeden ausgelösten Fehler in einem entsprechenden `Catch`-Block abfangen. Informationen zum Abfangen von Fehlern zur Laufzeit und zum Reagieren auf Fehler im Code finden Sie unter [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="compile-time-errors"></a>Kompilierzeitfehler  
 Wenn der Visual Basic-Compiler ein Problem im Code feststellt, tritt ein Kompilierzeitfehler auf. Im Code-Editor können Sie problemlos ermitteln, welche Codezeile den Fehler verursacht hat, da unter dieser Codezeile eine Wellenlinie angezeigt wird. Die Fehlermeldung wird angezeigt, wenn Sie auf die Wellenlinie zeigen oder die **Fehlerliste** öffnen, die auch weitere Meldungen anzeigt.  
  
 Wenn unter einem Bezeichner eine Wellenlinie und unter dem äußersten rechten Zeichen ein kurzer Unterstrich angezeigt werden, können Sie für die Klasse, den Konstruktor, die Methode, die Eigenschaft, das Feld oder die Enumeration einen Stub generieren. Weitere Informationen finden Sie unter [Generate From Usage](/visualstudio/ide/visual-csharp-intellisense#generate-from-usage).
  
 Indem Sie Warnungen des Visual Basic-Compilers auflösen, können Sie dafür sorgen, dass Ihr Code schneller und fehlerfreier ausgeführt wird. Diese Warnungen identifizieren Code, der Fehler verursachen kann, wenn die Anwendung ausgeführt wird. So gibt der Compiler z.B. eine Warnung aus, wenn Sie versuchen, einen Member einer nicht zugewiesenen Objektvariablen aufzurufen, eine Funktion ohne Angabe eines Rückgabewerts zu beenden oder einen `Try`-Block auszuführen, der Fehler in der Logik zum Abfangen von Ausnahmen enthält. Weitere Informationen zu Warnungen, z.B. zum Aktivieren und Deaktivieren von Warnungen, finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).
