---
title: Visual Basic von Fehlermeldungen
titleSuffix: ''
ms.date: 10/13/2020
helpviewer_keywords:
- errors [Visual Basic]
- error messages
ms.assetid: f2dda05b-baef-41f5-8bb1-598bd7cf239f
ms.openlocfilehash: 70973b6d34ed1a84a38af3694e144dfcefa61c20
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163375"
---
# <a name="error-messages-in-visual-basic"></a>Fehlermeldungen in Visual Basic

Beim Kompilieren oder Ausführen einer Visual Basic Anwendung können die folgenden Fehlertypen auftreten:

- Kompilierzeitfehler, die auftreten, wenn Sie eine Anwendung kompilieren.

- Laufzeitfehler, die auftreten, wenn eine Anwendung ausgeführt wird.

Informationen zur Behebung bestimmter Fehler finden Sie unter [Zusätzliche Ressourcen für Visual Basic-Programmierer](../../getting-started/additional-resources.md).

## <a name="run-time-errors"></a>Laufzeitfehler

Wenn eine Visual Basic Anwendung versucht, eine Aktion auszuführen, die vom System nicht ausgeführt werden kann, tritt ein Laufzeitfehler auf, und Visual Basic löst ein- <xref:System.Exception> Objekt aus. Visual Basic können benutzerdefinierte Fehler eines beliebigen Datentyps, einschließlich- `Exception` Objekten, mithilfe der- `Throw` Anweisung generieren. Eine Anwendung kann den Fehler durch Anzeige der Fehlernummer und -meldung einer abgefangenen Ausnahme identifizieren. Wenn ein Fehler nicht abgefangen wird, wird die Anwendung beendet.

Der Code kann Laufzeitfehler auffangen und untersuchen. Wenn Sie den Code, der den Fehler erzeugt, in einem `Try`-Block einschließen, können Sie jeden ausgelösten Fehler in einem entsprechenden `Catch`-Block abfangen. Informationen zum Abfangen von Fehlern zur Laufzeit und zum Reagieren auf Fehler im Code finden Sie unter [Try...Catch...Finally-Anweisung](../statements/try-catch-finally-statement.md).

## <a name="compile-time-errors"></a>Kompilierzeitfehler

Wenn der Visual Basic-Compiler ein Problem im Code feststellt, tritt ein Kompilierzeitfehler auf. Im Code-Editor von Visual Studio können Sie leicht feststellen, welche Codezeile den Fehler verursacht hat, da unter dieser Codezeile eine wellenförmige Linie angezeigt wird. Die Fehlermeldung wird angezeigt, wenn Sie auf die Wellenlinie zeigen oder die **Fehlerliste** öffnen, die auch weitere Meldungen anzeigt.

Wenn ein Bezeichner eine wellenförmige Unterstreichung aufweist und unter dem äußersten rechten Zeichen ein kurzer Unterstrich angezeigt wird, können Sie einen Stub für die Klasse, den Konstruktor, die Methode, die Eigenschaft, das Feld oder die Enumeration generieren. Weitere Informationen finden Sie unter [Generate from Usage (Visual Studio)](/visualstudio/ide/visual-csharp-intellisense#generate-from-usage).

Indem Sie Warnungen des Visual Basic-Compilers auflösen, können Sie dafür sorgen, dass Ihr Code schneller und fehlerfreier ausgeführt wird. Diese Warnungen identifizieren Code, der Fehler verursachen kann, wenn die Anwendung ausgeführt wird. So gibt der Compiler z.B. eine Warnung aus, wenn Sie versuchen, einen Member einer nicht zugewiesenen Objektvariablen aufzurufen, eine Funktion ohne Angabe eines Rückgabewerts zu beenden oder einen `Try`-Block auszuführen, der Fehler in der Logik zum Abfangen von Ausnahmen enthält. Weitere Informationen zu Warnungen, z.B. zum Aktivieren und Deaktivieren von Warnungen, finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).
