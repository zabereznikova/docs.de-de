---
title: Es ist ein Verweis auf die Assembly '<assemblyidentity>' erforderlich, die den Typ '<typename>' enthält, aber aufgrund der Mehrdeutigkeit der Projekte '<projectname1>' und '<projectname2>' wurde kein geeigneter Verweis gefunden
ms.date: 07/20/2015
f1_keywords:
- bc30969
- vbc30969
helpviewer_keywords:
- BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
ms.openlocfilehash: 4b9f74f0627268752b0ba3c3816fe9d4cc8a231b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404822"
---
# <a name="reference-required-to-assembly-assemblyidentity-containing-type-typename-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-projectname1-and-projectname2"></a>Es ist ein Verweis auf die Assembly '\<assemblyidentity>' erforderlich, die den Typ '\<typename>' enthält, aber aufgrund der Mehrdeutigkeit der Projekte '\<projectname1>' und '\<projectname2>' wurde kein geeigneter Verweis gefunden
Ein Ausdruck verwendet einen Typ (z. B. eine Klasse, eine Struktur, eine Schnittstelle, eine Enumeration oder einen Delegaten), der außerhalb des Projekts definiert ist. Sie haben jedoch Projektverweise auf mehr als eine Assembly, die diesen Typ definiert.  
  
 Die genannten Projekte erzeugen Assemblys mit demselben Namen. Daher kann der Compiler nicht bestimmen, welche Assembly für den Typ, auf den Sie zugreifen, verwendet werden soll.  
  
 Für den Zugriff auf einen Typ, der in einer anderen Assembly definiert ist, muss der Visual Basic-Compiler über einen Verweis auf diese Assembly verfügen. Dabei muss es sich um einen einzelnen, eindeutigen Verweis handeln, der keine Zirkelverweise in Projekten verursacht.  
  
 **Fehler-ID:** BC30969  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Bestimmen Sie, welches Projekt die Assembly erzeugt, auf die Ihr Projekt am besten verweisen kann. Für diese Entscheidung können Sie Kriterien wie den einfachen Zugriff auf Dateien und die Häufigkeit von Updates verwenden.  
  
2. Fügen Sie in den Projekteigenschaften einen Verweis auf die Datei mit der Assembly hinzu, die den von Ihnen verwendeten Typ definiert.  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project)
- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
- [Problembehandlung bei fehlerhaften Verweisen](/visualstudio/ide/troubleshooting-broken-references)
