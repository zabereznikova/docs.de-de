---
title: "Error Statement | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.error"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Error statement, syntax"
  - "Error statement"
  - "Error keyword"
  - "run-time errors, codes"
  - "errors [Visual Basic], simulating"
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Error Statement
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Simuliert das Auftreten eines Fehlers.  
  
## Syntax  
  
```  
Error errornumber  
```  
  
## Teile  
 `errornumber`  
 Erforderlich.  Kann eine beliebige gültige Fehlernummer sein.  
  
## Hinweise  
 Die `Error`\-Anweisung wird aus Gründen der Abwärtskompatibilität unterstützt.  Verwenden Sie bei neuem Code, besonders beim Erstellen von Objekten, die `Raise`\-Methode des `Err`\-Objekts, um Laufzeitfehler zu generieren.  
  
 Wenn `errornumber` definiert ist, ruft die `Error`\-Anweisung den Fehlerhandler auf, nachdem den Eigenschaften des `Err`\-Objekts die folgenden Standardwerte zugewiesen wurden:  
  
|Property|Wert|  
|--------------|----------|  
|`Number`|Wert, der als Argument für die `Error`\-Anweisung angegeben wird.  Kann eine beliebige gültige Fehlernummer sein.|  
|`Source`|Name des aktuellen Visual Basic\-Projekts.|  
|`Description`|Zeichenfolgenausdruck, der dem Rückgabewert der `Error`\-Funktion für die angegebene `Number` entspricht, sofern diese Zeichenfolge vorhanden ist.  Wenn die Zeichenfolge nicht vorhanden ist, enthält `Description` eine Zeichenfolge der Länge 0 \(null, ""\).|  
|`HelpFile`|Der voll gekennzeichnete Laufwerks\-, Pfad\- und Dateiname der betreffenden Visual Basic\-Hilfedatei.|  
|`HelpContext`|Die betreffende Kontext\-ID in der Visual Basic\-Hilfedatei für den Fehler, der der `Number`\-Eigenschaft entspricht.|  
|`LastDLLError`|0|  
  
 Falls kein Fehlerhandler vorhanden oder aktiviert ist, wird aus den `Err`\-Objekteigenschaften eine Fehlermeldung erstellt und angezeigt.  
  
> [!NOTE]
>  Manche Visual Basic\-Hostanwendungen können keine Objekte erstellen.  Informationen dazu, ob die Hostanwendung Klassen und Objekte erstellen kann, finden Sie in der Dokumentation zu der Anwendung.  
  
## Beispiel  
 In diesem Beispiel wird mit der `Error`\-Anweisung Fehler Nummer 11 generiert.  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## Anforderungen  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Assembly:** Visual Basic\-Laufzeitbibliothek \(in Microsoft.VisualBasic.dll\)  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>   
 <xref:Microsoft.VisualBasic.Information.Err%2A>   
 <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>   
 [On Error Statement](../../../visual-basic/language-reference/statements/on-error-statement.md)   
 [Resume Statement](../../../visual-basic/language-reference/statements/resume-statement.md)   
 [Error Messages](../../../visual-basic/language-reference/error-messages/index.md)