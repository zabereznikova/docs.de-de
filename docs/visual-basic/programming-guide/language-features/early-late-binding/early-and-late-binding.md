---
title: "Early and Late Binding (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "02/25/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "early binding"
  - "objects [Visual Basic], late-bound"
  - "objects [Visual Basic], early-bound"
  - "objects [Visual Basic], late bound"
  - "early binding, Visual Basic compiler"
  - "binding, late and early"
  - "objects [Visual Basic], early bound"
  - "Visual Basic compiler, early and late binding"
  - "late binding"
  - "late binding, Visual Basic compiler"
ms.assetid: d6ff7f1e-b94f-4205-ab8d-5cfa91758724
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Early and Late Binding (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Compiler führt einen als `binding` bezeichneten Vorgang aus, wenn ein Objekt einer Objektvariablen zugewiesen wird.  Ein Objekt wird *früh gebunden*, wenn es einer Variablen zugeordnet wird, für die ein spezifischer Objekttyp deklariert wurde.  Früh gebundene Objekte ermöglichen es dem Compiler, die Speicherbelegung und andere Optimierungen vor der Ausführung einer Anwendung durchzuführen.  Im folgenden Codefragment wird beispielsweise eine Variable des Typs <xref:System.IO.FileStream> deklariert:  
  
 [!code-vb[VbVbalrOOP#90](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#90)]  
  
 Da <xref:System.IO.FileStream> ein spezifischer Objekttyp ist, handelt es sich bei der Zuweisung der Instanz zu `FS` um eine frühe Bindung.  
  
 Im Gegensatz dazu wird ein Objekt *spät gebunden*, wenn es einer Variablen zugeordnet wird, für die der Typ `Object` deklariert wurde.  Objekte dieses Typs können Verweise zu allen Objekten beinhalten, jedoch gehen einige der Vorteile früh gebundener Objekte verloren.  Das folgende Codefragment deklariert beispielsweise eine Objektvariable, die ein von der `CreateObject`\-Funktion zurückgegebenes Objekt aufnimmt:  
  
 [!code-vb[VbVbalrOOP#91](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/LateBinding.vb#91)]  
  
## Vorteile der frühen Bindung  
 Sie sollten soweit möglich früh gebundene Objekte verwenden, da diese dem Compiler wichtige Optimierungen ermöglichen, die zu effizienteren Anwendungen führen.  Früh gebundene Objekte sind bedeutend schneller als spät gebundene Objekte, verbessern die Lesbarkeit des Codes und erleichtern dessen Verwaltung, weil sie die Art der verwendeten Objekte genau angeben.  Ein weiterer Vorteil der frühen Bindung besteht in der Aktivierung nützlicher Funktionen, z. B. der automatischen Codevervollständigung und der dynamischen Hilfe, da die integrierte Entwicklungsumgebung \(Integrated Development Environment, IDE\) von [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs-md.md)] genau ermitteln kann, welchen Objekttyp Sie während der Bearbeitung des Codes verwenden.  Die frühe Bindung reduziert die Anzahl und den Schweregrad der Laufzeitfehler, da sie dem Compiler die Ausgabe von Fehlern während der Programmkompilierung ermöglicht.  
  
> [!NOTE]
>  Die späte Bindung kann nur für den Zugriff auf als `Public` deklarierte Typmember verwendet werden.  Der Zugriff auf als `Friend` oder `Protected Friend` deklarierte Member führt zu Laufzeitfehlern.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>   
 [Object Lifetime: How Objects Are Created and Destroyed](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)   
 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)