---
title: Ein Verweis auf Assembly erforderlich &#39; &lt;Assemblyidentity&gt; &#39; enthaltenden Typ &#39; &lt;Typename&gt;&#39;, aber kein geeigneter Verweis konnte aufgrund der Mehrdeutigkeit nicht gefunden werden Projekte &#39; &lt;projektname1&gt; &#39; und &#39; &lt;projektname2&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30969
- vbc30969
helpviewer_keywords:
- BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
ms.openlocfilehash: 1a0c2a2fd235026729901153a0c0c300f914a78f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54553008"
---
# <a name="reference-required-to-assembly-39ltassemblyidentitygt39-containing-type-39lttypenamegt39-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-39ltprojectname1gt39-and-39ltprojectname2gt39"></a>Ein Verweis auf Assembly erforderlich &#39; &lt;Assemblyidentity&gt; &#39; enthaltenden Typ &#39; &lt;Typename&gt;&#39;, aber kein geeigneter Verweis konnte aufgrund der Mehrdeutigkeit nicht gefunden werden Projekte &#39; &lt;projektname1&gt; &#39; und &#39; &lt;projektname2&gt;&#39;
Ein Ausdruck verwendet einen Typ (z. B. eine Klasse, eine Struktur, eine Schnittstelle, eine Enumeration oder einen Delegaten), der außerhalb des Projekts definiert ist. Sie haben jedoch Projektverweise auf mehr als eine Assembly, die diesen Typ definiert.  
  
 Die genannten Projekte erzeugen Assemblys mit demselben Namen. Daher kann der Compiler nicht bestimmen, welche Assembly für den Typ, auf den Sie zugreifen, verwendet werden soll.  
  
 Zugriff auf einen Typ in einer anderen Assembly definiert, müssen die Visual Basic-Compiler einen Verweis auf diese Assembly. Dabei muss es sich um einen einzelnen, eindeutigen Verweis handeln, der keine Zirkelverweise in Projekten verursacht.  
  
 **Fehler-ID:** BC30969  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Bestimmen Sie, welches Projekt die Assembly erzeugt, auf die Ihr Projekt am besten verweisen kann. Für diese Entscheidung können Sie Kriterien wie den einfachen Zugriff auf Dateien und die Häufigkeit von Updates verwenden.  
  
2.  Fügen Sie in den Projekteigenschaften einen Verweis auf die Datei mit der Assembly hinzu, die den von Ihnen verwendeten Typ definiert.  
  
## <a name="see-also"></a>Siehe auch
- [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project)
- [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
- [Problembehandlung bei fehlerhaften Verweisen](/visualstudio/ide/troubleshooting-broken-references)
