---
title: "Gewusst wie: Implementieren und Aufrufen einer benutzerdefinierten Erweiterungsmethode (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Erweiterungsmethoden [C#], Implementieren und Aufrufen"
ms.assetid: 7dab2a56-cf8e-4a47-a444-fe610a02772a
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Implementieren und Aufrufen einer benutzerdefinierten Erweiterungsmethode (C#-Programmierhandbuch)
In diesem Thema wird gezeigt, wie für Erweiterungsmethoden implementiert, besitzen entweder eingeben [.NET Framework Class Library](http://go.microsoft.com/fwlink/?LinkID=217856)oder einen anderen .NET\-Typ, den Sie erweitern möchten.  Der Clientcode kann Ihre Erweiterungsmethoden verwenden, indem ein Verweis auf die DLL, die die Methoden enthält, sowie eine [using](../../../csharp/language-reference/keywords/using-directive.md)\-Direktive, die den Namespace festlegt, in der die Erweiterungsmethoden definiert sind, hinzugefügt werden.  
  
### So definieren und die Erweiterungsmethode aufrufen  
  
1.  Definieren Sie eine statische [Klasse](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md), die die Erweiterungsmethode enthalten soll.  
  
     Die Klasse muss für den Clientcode sichtbar sein.  Weitere Informationen über Zugriffsregeln finden Sie unter [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
2.  Implementieren Sie die Erweiterungsmethode als statische Methode mit mindestens den gleichen Sichtbarkeitseinstellungen wie die enthaltende Klasse.  
  
3.  Der erste Parameter der Methode bestimmt den Typ, für den die Methode gilt, und vor dem Parameter steht der [this](../../../csharp/language-reference/keywords/this.md)\-Modifizierer.  
  
4.  Fügen Sie im Aufrufcode eine `using`\-Direktive hinzu, um den [Namespace](../../../csharp/language-reference/keywords/namespace.md) festzulegen, der die Erweiterungsmethodenklasse enthält.  
  
5.  Rufen Sie die Methoden auf, als ob sie Instanzmethoden für den Typ wären.  
  
     Beachten Sie, dass der erste Parameter nicht durch den Aufruf von Code festgelegt wird, da er den Typ darstellt, auf den der Operator angewendet wird, und der Compiler kennt bereits den Typ Ihres Objekts.  Sie müssen nur Argumente für Parameter 2 bis `n` angeben.  
  
## Beispiel  
 Im folgenden Beispiel wird eine Erweiterungsmethode mit dem Namen `WordCount` in der `CustomExtensions.StringExtension`\-Klasse implementiert.  Die Methode gilt für die <xref:System.String>\-Klasse, die als erster Methodenparameter angegeben wird.  Der `CustomExtensions`\-Namespace wird in den Anwendungs\-Namespace importiert, und die Methode wird in der `Main`\-Methode aufgerufen.  
  
 [!code-cs[csProgGuideExtensionMethods#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-and-call-a_1.cs)]  
  
## Kompilieren des Codes  
 Um diesen Code auszuführen, kopieren Sie ihn, und fügen Sie ihn in ein Visual C\#\-Konsolenanwendungsprojekt ein, das in [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)] erstellt wurde.  Dieses Projekt gilt standardmäßig für [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] Version 3.5 und hat einen Verweis auf System.Core.dll sowie eine `using`\-Direktive für System.Linq.  Wenn eine oder mehrere dieser Anforderungen im Projekt fehlen, können Sie sie manuell hinzufügen.  Weitere Informationen hierzu finden Sie unter [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## .NET Framework-Sicherheit  
 Erweiterungsmethoden stellen keine speziellen Sicherheitslücken dar.  Sie können niemals verwendet werden, um als vorhandene Methoden auf einem Typ zu agieren, da alle Namenskonflikte zugunsten der Instanz oder der statischen Methode, die vom Typ selbst definiert wird, gelöst werden.  Erweiterungsmethoden können nicht auf private Daten in der erweiterten Klasse zugreifen.  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Erweiterungsmethoden](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [interne](../../../csharp/language-reference/keywords/internal.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [this](../../../csharp/language-reference/keywords/this.md)   
 [Namespace](../../../csharp/language-reference/keywords/namespace.md)