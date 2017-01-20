---
title: "Namespace or type specified in the Imports &#39;&lt;qualifiedelementname&gt;&#39; doesn&#39;t contain any public member or cannot be found | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc40056"
  - "vbc40056"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40056"
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Namespace or type specified in the Imports &#39;&lt;qualifiedelementname&gt;&#39; doesn&#39;t contain any public member or cannot be found
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Der in Imports '\<QualifizierterElementname\>' angegebene Namespace oder Typ enthält keine öffentlichen Member oder kann nicht gefunden werden.Stellen Sie sicher, dass der Namespace oder der Typ definiert ist und mindestens einen öffentlichen Member enthält.Stellen Sie weiterhin sicher, dass der Aliasname keine weiteren Aliase enthält.  
  
 In einer `Imports`\-Anweisung ist ein enthaltendes Element angegeben, das entweder nicht gefunden werden kann oder keine `Public`\-Member definiert.  
  
 Ein *enthaltendes Element* kann ein Namespace, eine Klasse, eine Struktur, ein Modul, eine Schnittstelle oder eine Enumeration sein.  Das enthaltende Element enthält Member, z. B. Variablen, Prozeduren oder andere enthaltende Elemente.  
  
 Der Sinn des Importierens besteht darin, im Code den Zugriff auf Namespaces oder Typmember zu ermöglichen, ohne diese vollständig bezeichnen zu müssen.  Unter Umständen ist es für das Projekt auch erforderlich, einen Verweis auf den Namespace oder den Typ hinzuzufügen.  Weitere Informationen finden Sie unter [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) in "Importieren von enthaltenden Elementen".  
  
 Wenn der Compiler das angegebene enthaltende Element nicht finden kann, ist er nicht in der Lage, Verweise aufzulösen, in denen dieses Element verwendet wird.  Wenn das Element gefunden wird, dieses jedoch keine `Public`\-Member bereitstellt, schlägt jeder Zugriff über einen Verweis fehl.  In beiden Fällen ist es sinnlos, das Element zu importieren.  
  
 Beachten Sie, dass Sie nach dem Importieren eines enthaltenden Elements und der Zuweisung eines Importalias zu diesem Element den Importalias nicht mehr verwenden können, um ein weiteres Element zu importieren.  Im folgenden Code wird ein Compilerfehler generiert.  
  
 `Imports`   `winfrm`   `= System.Windows.Forms`  
  
 `' The following statement is`   `INVALID`   `because it reuses an import alias.`  
  
 `Imports behav =`   `winfrm`  `.Design.Behavior`  
  
 **Fehler\-ID:** BC40056  
  
### So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass vom Projekt aus der Zugriff auf das enthaltende Element möglich ist.  
  
2.  Stellen Sie sicher, dass die Spezifikation des enthaltenden Elements keinen Importalias eines anderen Imports enthält.  
  
3.  Stellen Sie sicher, dass das enthaltende Element mindestens einen `Public`\-Member bereitstellt.  
  
## Siehe auch  
 [Imports Statement \(.NET Namespace and Type\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Public](../../../visual-basic/language-reference/modifiers/public.md)   
 [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)