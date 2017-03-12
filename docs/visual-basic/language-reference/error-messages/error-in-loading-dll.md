---
title: "Error in loading DLL (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID48"
dev_langs: 
  - "VB"
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Error in loading DLL (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Eine Dynamic Link Library \(DLL\) ist eine Bibliothek, die in der `Lib`\-Klausel einer `Declare`\-Anweisung angegeben ist.  Dieser Fehler kann folgende Ursachen haben:  
  
-   Die Datei ist keine ausführbare DLL\-Datei.  
  
-   Die Datei ist keine Microsoft Windows DLL.  
  
-   Die DLL verweist auf eine andere DLL, die nicht vorhanden ist.  
  
-   Die DLL oder die Referenz\-DLL befindet sich nicht in einem im Pfad angegebenen Verzeichnis.  
  
### So beheben Sie diesen Fehler  
  
-   Wenn es sich bei der Datei um eine Quellcodedatei und daher nicht um eine ausführbare DLL handelt, muss sie kompiliert und mit einem ausführbaren DLL\-Formular verknüpft werden.  
  
-   Wenn die Datei keine Microsoft Windows DLL ist, verwenden Sie ein Microsoft Windows\-Äquivalent.  
  
-   Wenn die DLL auf eine andere DLL verweist, die nicht vorhanden ist, machen Sie die Referenz\-DLL verfügbar.  
  
-   Wenn sich die DLL oder die Referenz\-DLL nicht in einem durch den Pfad angegebenen Verzeichnis befindet, verschieben Sie die DLL in ein Verzeichnis, auf das verwiesen wird.  
  
## Siehe auch  
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)