---
title: "Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39; (Multiple file references) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30961"
  - "bc30961"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30961"
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39; (Multiple file references)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Der Wert vom Typ '\<Typname1\>' kann nicht in '\<Typname2\>' konvertiert werden.Der Typenkonflikt könnte auf die Kombination eines Dateiverweises auf '\<Dateiname1\>' in Projekt '\<Projektname1\>' mit einem Dateiverweis auf '\<Dateiname2\>' in Projekt '\<Projektname2\>' zurückzuführen sein.Wenn die beiden Assemblys identisch sind, ersetzen Sie die beiden Verweise durch Verweise vom gleichen Speicherort.  
  
 Wenn ein Projekt mehr als einen Dateiverweis auf eine Assembly enthält, kann der Compiler die Konvertierung zwischen den Typen nicht gewährleisten.  
  
 Jeder Dateiverweis gibt einen Dateipfad und einen Namen für die Ausgabedatei eines Projekts an \(in der Regel eine DLL\-Datei\).  Der Compiler kann nicht garantieren, dass die Ausgabedateien aus derselben Quelle erzeugt wurden oder dass sie dieselbe Version einer Assembly darstellen.  Daher kann der Compiler nicht garantieren, dass die Typen in den verschiedenen Verweisen identisch sind, oder dass ein Typ in den anderen konvertiert werden kann.  
  
 Sie können einen einzigen Dateiverweis verwenden, wenn Sie sicher sind, dass die Assemblys, auf die verwiesen wird, über ein und dieselbe Assemblyidentität verfügen.  Die *Assemblyidentität* umfasst den Namen, die Version, ggf. den öffentlichen Schlüssel und die Kultur der Assembly.  Anhand dieser Informationen wird die Assembly eindeutig bezeichnet.  
  
 **Fehler\-ID:** BC30961  
  
### So beheben Sie diesen Fehler  
  
-   Wenn die Assemblys, auf die verwiesen wird, über dieselbe Assemblyidentität verfügen, entfernen oder ersetzen Sie einen der Dateiverweise, sodass nur noch ein einziger Dateiverweis vorhanden ist.  
  
-   Wenn die Assemblys, auf die verwiesen wird, nicht über dieselbe Assemblyidentität verfügen, ändern Sie den Code dahingehend, dass keine Konvertierung eines Typs aus einer Assembly in einen Typ aus der anderen Assembly erfolgt.  
  
## Siehe auch  
 [Type Conversions in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Verwalten von Verweisen in einem Projekt](/visual-studio/ide/managing-references-in-a-project)   
 [Gewusst wie: Hinzufügen oder Entfernen von Verweisen mithilfe des Dialogfelds "Verweise hinzufügen"](http://msdn.microsoft.com/de-de/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)