---
title: Verweis auf die Assembly erforderlich &quot;&lt;Assemblyidentity&gt;&quot;mit Typ&quot;&lt;Typename&gt;&quot;, aber kein geeigneter Verweis konnte nicht gefunden werden, aufgrund der Mehrdeutigkeit der Projekte&lt;projectname1&gt;&quot;und&quot;&lt;projectname2&gt;&quot; | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30969
- vbc30969
dev_langs:
- VB
helpviewer_keywords:
- BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
caps.latest.revision: 11
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 38f016b9d0de053c9a95a6d4a4d810d55af903e9
ms.lasthandoff: 03/13/2017

---
# <a name="reference-required-to-assembly-39ltassemblyidentitygt39-containing-type-39lttypenamegt39-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-39ltprojectname1gt39-and-39ltprojectname2gt39"></a>Verweis auf die Assembly erforderlich '&lt;Assemblyidentity&gt;'mit Typ'&lt;Typename&gt;', aber kein geeigneter Verweis konnte nicht gefunden werden, aufgrund der Mehrdeutigkeit der Projekte&lt;projectname1&gt;"und"&lt;projectname2&gt;'
Ein Ausdruck verwendet einen Typ (z. B. eine Klasse, eine Struktur, eine Schnittstelle, eine Enumeration oder einen Delegaten), der außerhalb des Projekts definiert ist. Sie haben jedoch Projektverweise auf mehr als eine Assembly, die diesen Typ definiert.  
  
 Die genannten Projekte erzeugen Assemblys mit demselben Namen. Daher kann der Compiler nicht bestimmen, welche Assembly für den Typ, auf den Sie zugreifen, verwendet werden soll.  
  
 Auf einen Typ in einer anderen Assembly definiert die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler benötigen einen Verweis auf diese Assembly. Dabei muss es sich um einen einzelnen, eindeutigen Verweis handeln, der keine Zirkelverweise in Projekten verursacht.  
  
 **Fehler-ID:** BC30969  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Bestimmen Sie, welches Projekt die Assembly erzeugt, auf die Ihr Projekt am besten verweisen kann. Für diese Entscheidung können Sie Kriterien wie den einfachen Zugriff auf Dateien und die Häufigkeit von Updates verwenden.  
  
2.  Fügen Sie in den Projekteigenschaften einen Verweis auf die Datei mit der Assembly hinzu, die den von Ihnen verwendeten Typ definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwalten von Verweise in einem Projekt](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)   
 [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [NIB: Vorgehensweise: Hinzufügen oder Entfernen von Verweisen mithilfe des Dialogfelds „Verweis hinzufügen“](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [NIB Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Problembehandlung bei fehlerhaften Verweisen](https://docs.microsoft.com/visualstudio/ide/troubleshooting-broken-references)
