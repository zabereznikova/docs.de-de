---
title: <message> Dieser Fehler könnte auch auf das Mischen eines Dateiverweises mit einem Projektverweis auf Assembly "<assemblyname>" zurückzuführen sein.
ms.date: 07/20/2015
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
ms.openlocfilehash: 9340c5c58c0cdb70c517534a339f57eb9ec1f906
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162426"
---
# <a name="bc30971-message-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-assemblyname"></a>BC30971: \<message> dieser Fehler kann auch auf das Mischen eines Datei Verweises mit einem Projekt Verweis auf die Assembly "" zurückzuführen sein. \<assemblyname>

\<message> Dieser Fehler kann auch auf das Mischen eines Datei Verweises mit einem Projekt Verweis auf die Assembly "" zurückzuführen sein \<assemblyname> . Ersetzen Sie in diesem Fall den Datei Verweis auf " \<assemblyfilename> " im Projekt "" \<projectname1> durch einen Projekt Verweis auf " \<projectname2> ".

 Der Code in Ihrem Projekt greift auf einen Member eines anderen Projekts zu, aber die Konfiguration der Projekt Mappe lässt nicht zu, dass der Visual Basic Compiler den Verweis auflösen kann.

 Für den Zugriff auf einen Typ, der in einer anderen Assembly definiert ist, muss der Visual Basic-Compiler über einen Verweis auf diese Assembly verfügen. Dabei muss es sich um einen einzelnen, eindeutigen Verweis handeln, der keine Zirkelverweise in Projekten verursacht.

 **Fehler-ID:** BC30971

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Bestimmen Sie, welches Projekt die Assembly erzeugt, auf die Ihr Projekt am besten verweisen kann. Für diese Entscheidung können Sie Kriterien wie den einfachen Zugriff auf Dateien und die Häufigkeit von Updates verwenden.

2. Fügen Sie in den Projekteigenschaften einen Verweis auf das Projekt mit der Assembly hinzu, die den von Ihnen verwendeten Typ definiert.

## <a name="see-also"></a>Siehe auch

- [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project)
- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
- [Problembehandlung bei fehlerhaften Verweisen](/visualstudio/ide/troubleshooting-broken-references)
