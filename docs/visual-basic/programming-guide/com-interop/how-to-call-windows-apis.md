---
title: "How to: Call Windows APIs (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "API calls"
  - "Windows API, calling"
  - "API calls, platform invoke"
  - "calls, stored procedures"
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# How to: Call Windows APIs (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Dieses Beispiel definiert die `MessageBox`\-Funktion in der Datei "user32.dll", ruft sie auf und fügt ihr anschließend eine Zeichenfolge hinzu.  
  
## Beispiel  
 [!code-vb[VbVbalrInterop#1](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-call-windows-apis_1.vb)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein Verweis auf den <xref:System>\-Namespace.  
  
## Robuste Programmierung  
 Unter den folgenden Bedingungen kann eine Ausnahme ausgelöst werden:  
  
-   Die Methode ist entweder nicht statisch, abstrakt oder wurde zuvor definiert.  Beim übergeordneten Typ handelt es sich um eine Schnittstelle, die Länge von *Name*, oder es gilt *dllName* \= 0 \(null\).  \(<xref:System.ArgumentException>\)  
  
-   *Name* oder *dllName* ist `Nothing`.  \(<xref:System.ArgumentNullException>\)  
  
-   Der enthaltende Typ wurde zuvor mithilfe von `CreateType` erstellt.  \(<xref:System.InvalidOperationException>\)  
  
## Siehe auch  
 [A Closer Look at Platform Invoke](http://msdn.microsoft.com/de-de/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)   
 [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md)   
 [Consuming Unmanaged DLL Functions](../Topic/Consuming%20Unmanaged%20DLL%20Functions.md)   
 [Defining a Method with Reflection Emit](http://msdn.microsoft.com/de-de/84fd3bf6-628f-41aa-83d9-b990cf926e81)   
 [Walkthrough: Calling Windows APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)   
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)