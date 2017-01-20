---
title: "Walkthrough: Validating That Passwords Are Complex (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "String data type, validation"
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Walkthrough: Validating That Passwords Are Complex (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Diese Methode überprüft einige Merkmale sicherer Kennwörter und aktualisiert einen Zeichenfolgenparameter mit den Informationen über die fehlgeschlagenen Kennwortüberprüfungen.  
  
 Kennwörter können in einem sicheren System zum Autorisieren eines Benutzers verwendet werden.  Die Kennwörter müssen jedoch für unbefugte Benutzer schwierig zu erraten sein.  Angreifer können ein Programm für *Wörterbuchangriffe* verwenden, das alle Wörter in einem Wörterbuch durchläuft \(oder mehrere Wörterbücher in verschiedenen Sprachen\) und überprüft, ob eines der Wörter als Kennwort eines Benutzers fungiert.  Unsichere Kennwörter, z. B. "Hertha" oder "Mustang", können schnell erraten werden.  Sicherere Kennwörter, z. B "?Me1NkeNnWoRtIStGEh@im\!", sind viel schwieriger zu erraten.  Ein kennwortgeschütztes System sollte sicherstellen, dass Benutzer sichere Kennwörter auswählen.  
  
 Ein sicheres Kennwort ist komplex \(mit einer Mischung aus Großbuchstaben, Kleinbuchstaben, numerischen Zeichen und Sonderzeichen\) und kein lexikalisches Wort.  In diesem Beispiel wird veranschaulicht, wie Komplexität überprüft wird.  
  
## Beispiel  
  
### Code  
 [!code-vb[VbVbcnRegEx#1](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that_1.vb)]  
  
## Kompilieren des Codes  
 Rufen Sie diese Methode auf, indem Sie die Zeichenfolge übergeben, die dieses Kennwort enthält.  
  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Zugriff auf die Member des <xref:System.Text.RegularExpressions>\-Namespaces.  Fügen Sie eine `Imports`\-Anweisung hinzu, wenn der Code keine vollqualifizierten Membernamen enthält.  Weitere Informationen finden Sie unter [Imports Statement \(.NET Namespace and Type\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## Sicherheit  
 Wenn Sie das Kennwort im Netzwerk übertragen, müssen Sie eine sichere Methode für die Datenübertragung verwenden.  Weitere Informationen finden Sie unter [ASP.NET Web Application Security](../Topic/ASP.NET%20Web%20Application%20Security.md).  
  
 Sie können die Präzision der `ValidatePassword`\-Funktion erhöhen, indem Sie zusätzliche Komplexitätsüberprüfungen hinzufügen:  
  
-   Vergleichen Sie das Kennwort und seine Teilzeichenfolgen mit dem Namen des Benutzers, der Benutzer\-ID und einem anwendungsdefinierten Wörterbuch.  Behandeln Sie darüber hinaus optisch ähnliche Zeichen als gleiche Zeichen, wenn Sie die Vergleiche ausführen.  Behandeln Sie z. B. die Buchstaben "I" und "e" als Entsprechungen der Zahlen "1" und "3".  
  
-   Wenn nur ein Großbuchstabe vorhanden ist, stellen Sie sicher, dass er nicht das erste Zeichen des Kennworts ist.  
  
-   Stellen Sie sicher, dass die letzten beiden Zeichen des Kennworts Buchstaben sind.  
  
-   Lassen Sie keine Kennwörter zu, für die sämtliche Zeichen auf der obersten Reihe der Tastatur eingegeben werden.  
  
## Siehe auch  
 <xref:System.Text.RegularExpressions.Regex>   
 [ASP.NET Web Application Security](../Topic/ASP.NET%20Web%20Application%20Security.md)