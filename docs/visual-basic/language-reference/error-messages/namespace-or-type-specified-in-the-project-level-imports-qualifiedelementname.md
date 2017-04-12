---
title: "Namespace oder Typ angegeben werden, in der auf Projektebene Imports&quot;&lt;Qualifiedelementname&gt;&quot; enthält keine öffentlichen Member oder kann nicht gefunden werden | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40057
- bc40057
dev_langs:
- VB
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5dae6f92f573a57d0974c860500bc7420f55a94f
ms.lasthandoff: 03/13/2017

---
# <a name="namespace-or-type-specified-in-the-project-level-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a>Namespace oder Typ angegeben werden, in der auf Projektebene Imports'&lt;Qualifiedelementname&gt;' enthält keine öffentlichen Member oder kann nicht gefunden werden
Namespace oder Typ angegeben werden, in der auf Projektebene Imports'\<Qualifiedelementname >' enthält keine öffentlichen Member oder kann nicht gefunden werden. Stellen Sie sicher, dass der Namespace oder der Typ definiert ist und mindestens einen öffentliches Member enthält. Stellen Sie sicher, dass der Aliasname keine weiteren Aliase enthält.  
  
 Eine Import-Eigenschaft eines Projekts gibt ein Containerelement, das entweder nicht gefunden werden oder ist nicht definiert `Public` Elemente.  
  
 Ein *Element mit* kann ein Namespace, Klasse, Struktur, Modul, Schnittstelle oder Enumeration sein. Das enthaltende Element enthält Member, z. B. Variablen, Prozeduren oder andere enthaltende Elemente.  
  
 Importieren von dient dem Code auf Namespace oder Typ Member zu ermöglichen, ohne sie qualifizieren zu müssen. Das Projekt müssen auch einen Verweis auf den Namespace oder Typ hinzufügen. Weitere Informationen finden Sie unter "Importieren von enthaltenden Elementen" in [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Wenn der Compiler das angegebene enthaltende Element nicht finden kann, dann nicht Verweise aufgelöst werden kann, die es verwenden. Wenn das Element gefunden wird, aber das Element alle macht `Public` Elemente, und klicken Sie dann auf kein Verweis kann erfolgreich sein. In beiden Fällen ist es sinnlos, das Element zu importieren.  
  
 Verwenden Sie die **Projekt-Designer** zu importierenden Elemente angeben. Verwenden der **importierte Namespaces** Teil der **Verweise** Seite. Sie erreichen die **Projekt-Designer** durch Doppelklicken auf die **Mein Projekt** -Symbol in **Projektmappen-Explorer**.  
  
 **Fehler-ID:** BC40057  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Öffnen Sie die **Projekt-Designer** und wechseln Sie in der **Verweis** Seite.  
  
2.  In der **importierte Namespaces** Abschnitt, stellen Sie sicher, dass das enthaltende Element aus dem Projekt zugegriffen werden.  
  
3.  Überprüfen, ob es sich bei das enthaltende Element verfügbar macht, muss mindestens `Public` Member.  
  
## <a name="see-also"></a>Siehe auch  
 [Seite „Verweise“, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)   
 [NIB Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Öffentliche](../../../visual-basic/language-reference/modifiers/public.md)   
 [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
