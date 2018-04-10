---
title: Frühes und spätes Binden (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- early binding [Visual Basic]
- objects [Visual Basic], late-bound
- objects [Visual Basic], early-bound
- objects [Visual Basic], late bound
- early binding [Visual Basic], Visual Basic compiler
- binding [Visual Basic], late and early
- objects [Visual Basic], early bound
- Visual Basic compiler, early and late binding
- late binding [Visual Basic]
- late binding [Visual Basic], Visual Basic compiler
ms.assetid: d6ff7f1e-b94f-4205-ab8d-5cfa91758724
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aceffe59fb6043b3089621b9a3f95b0425f9a522
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="early-and-late-binding-visual-basic"></a>Frühes und spätes Binden (Visual Basic)
Der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]-Compiler führt einen als `binding` bezeichneten Vorgang aus, wenn ein Objekt einer Objektvariablen zugewiesen wird. Objekt wird *früh gebunden*, wenn es einer Variablen zugeordnet wird, für die ein spezifischer Objekttyp deklariert wurde. Früh gebundene Objekte ermöglichen es dem Compiler, die Speicherbelegung und andere Optimierungen vor der Ausführung einer Anwendung durchzuführen. Das folgende Codefragment deklariert beispielsweise eine Variable des Typs <xref:System.IO.FileStream>:  
  
 [!code-vb[VbVbalrOOP#90](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_1.vb)]  
  
 Da <xref:System.IO.FileStream> ein spezifischer Objekttyp ist, handelt es sich bei der Zuweisung der Instanz zu `FS` um eine frühe Bindung.  
  
 Im Gegensatz dazu wird ein Objekt *spät gebunden*, wenn es einer Variablen zugeordnet wird, für die der Typ `Object` deklariert wurde. Objekte dieses Typs können Verweise zu beliebigen Objekten enthalten, jedoch gehen einige der Vorteile früh gebundener Objekte verloren. Das folgende Codefragment deklariert beispielsweise eine Objektvariable, die ein von der `CreateObject`-Funktion zurückgegebenes Objekt enthalten soll:  
  
 [!code-vb[VbVbalrOOP#91](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_2.vb)]  
  
## <a name="advantages-of-early-binding"></a>Vorteile der frühen Bindung  
 Sie sollten soweit möglich früh gebundene Objekte verwenden, da diese dem Compiler wichtige Optimierungen ermöglichen, die zu effizienteren Anwendungen führen. Früh gebundene Objekte sind bedeutend schneller als spät gebundene Objekte, verbessern die Lesbarkeit des Codes und erleichtern dessen Verwaltung, weil sie die Art der verwendeten Objekte genau angeben. Ein weiterer Vorteil der frühen Bindung besteht darin, dass sie nützliche Funktionen verfügbar macht, wie z.B. die automatische Codevervollständigung und die dynamische Hilfe, da die integrierte Entwicklungsumgebung (Integrated Development Environment, IDE) von [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] genau ermitteln kann, welchen Objekttyp Sie während der Bearbeitung des Codes verwenden. Die frühe Bindung reduziert die Anzahl und den Schweregrad von Laufzeitfehlern, da sie dem Compiler die Ausgabe von Fehlern während der Programmkompilierung ermöglicht.  
  
> [!NOTE]
>  Die späte Bindung kann nur für den Zugriff auf als `Public` deklarierte Typmember verwendet werden. Der Zugriff auf als `Friend` oder `Protected Friend` deklarierte Member führt zu Laufzeitfehlern.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>  
 [Objektlebensdauer: Erstellen und Zerstören von Objekten](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md)
