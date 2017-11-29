---
title: "&lt;Nachricht&gt; dieser Fehler ist möglicherweise auch aufgrund eines Dateiverweises mit einem Projektverweis auf Assembly &#39;&lt; AssemblyName&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords: BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a30e5d5aca09e7b74e16dd05cdc0c5c361c1657d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltmessagegt-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-39ltassemblynamegt39"></a>&lt;Nachricht&gt; dieser Fehler ist möglicherweise auch aufgrund eines Dateiverweises mit einem Projektverweis auf Assembly &#39;&lt; AssemblyName&gt;&#39;
\<Meldung > Dieser Fehler ist möglicherweise auch aufgrund eines Dateiverweises mit einem Projektverweis auf Assembly '\<Assemblyname >. In diesem Fall versuchen Sie es, und Ersetzen Sie dabei den Dateiverweis auf "\<Assemblydateiname >" in Projekt "\<projektname1 >" mit einem Projektverweis auf "\<projektname2 >".  
  
 Code in Ihrem Projekt greift auf einen Member eines anderen Projekts zu, aufgrund der Konfiguration Ihrer Projektmappe kann der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] -Compiler den Verweis aber nicht auflösen.  
  
 Für den Zugriff auf einen Typ in einer anderen Assembly benötigt der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] -Compiler einen Verweis auf diese Assembly. Dabei muss es sich um einen einzelnen, eindeutigen Verweis handeln, der keine Zirkelverweise in Projekten verursacht.  
  
 **Fehler-ID:** BC30971  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Bestimmen Sie, welches Projekt die Assembly erzeugt, auf die Ihr Projekt am besten verweisen kann. Für diese Entscheidung können Sie Kriterien wie den einfachen Zugriff auf Dateien und die Häufigkeit von Updates verwenden.  
  
2.  Fügen Sie in den Projekteigenschaften einen Verweis auf das Projekt mit der Assembly hinzu, die den von Ihnen verwendeten Typ definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project)  
 [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [NIB: Gewusst wie: Hinzufügen oder Entfernen von Verweisen mithilfe des Dialogfelds "Verweis hinzufügen"](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)  
 [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)  
 [Problembehandlung bei fehlerhaften Verweisen](/visualstudio/ide/troubleshooting-broken-references)
