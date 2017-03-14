---
title: "Namespace or type specified in the project-level Imports &#39;&lt;qualifiedelementname&gt;&#39; doesn&#39;t contain any public member or cannot be found | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc40057"
  - "bc40057"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40057"
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Namespace or type specified in the project-level Imports &#39;&lt;qualifiedelementname&gt;&#39; doesn&#39;t contain any public member or cannot be found
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Der in Imports '\<QualifizierterElementname\>' auf Projektebene angegebene Namespace oder Typ enthält keine öffentlichen Member oder kann nicht gefunden werden.Stellen Sie sicher, dass der Namespace oder der Typ definiert ist und mindestens einen öffentlichen Member enthält.Stellen Sie weiterhin sicher, dass der Aliasname keine weiteren Aliase enthält.  
  
 In einer Importeigenschaft eines Projekts ist ein enthaltendes Element angegeben, das entweder nicht gefunden werden kann oder keine `Public`\-Member definiert.  
  
 Ein *enthaltendes Element* kann ein Namespace, eine Klasse, eine Struktur, ein Modul, eine Schnittstelle oder eine Enumeration sein.  Das enthaltende Element enthält Member, z. B. Variablen, Prozeduren oder andere enthaltende Elemente.  
  
 Der Sinn des Importierens besteht darin, im Code den Zugriff auf Namespaces oder Typmember zu ermöglichen, ohne diese vollständig bezeichnen zu müssen.  Unter Umständen ist es für das Projekt auch erforderlich, einen Verweis auf den Namespace oder den Typ hinzuzufügen.  Weitere Informationen finden Sie unter [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) in "Importieren von enthaltenden Elementen".  
  
 Wenn der Compiler das angegebene enthaltende Element nicht finden kann, ist er nicht in der Lage, Verweise aufzulösen, in denen dieses Element verwendet wird.  Wenn das Element gefunden wird, dieses jedoch keine `Public`\-Member bereitstellt, schlägt jeder Zugriff über einen Verweis fehl.  In beiden Fällen ist es sinnlos, das Element zu importieren.  
  
 Die zu importierenden Elemente werden mithilfe des **Projekt\-Designers** angegeben.  Dazu wird der Abschnitt **Importierte Namespaces** der Seite **Verweise** verwendet.  Sie erreichen den **Projekt\-Designer**, indem Sie im **Projektmappen\-Explorer** auf das Symbol **Mein Projekt** doppelklicken.  
  
 **Fehler\-ID:** BC40057  
  
### So beheben Sie diesen Fehler  
  
1.  Öffnen Sie den **Projekt\-Designer**, und wechseln Sie zur Seite **Verweise**.  
  
2.  Stellen Sie im Abschnitt **Importierte Namespaces** sicher, dass der Zugriff auf das enthaltende Element vom Projekt aus möglich ist.  
  
3.  Stellen Sie sicher, dass das enthaltende Element mindestens einen `Public`\-Member bereitstellt.  
  
## Siehe auch  
 [Seite "Verweise", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Public](../../../visual-basic/language-reference/modifiers/public.md)   
 [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)