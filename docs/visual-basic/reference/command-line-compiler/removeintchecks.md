---
title: "/removeintchecks | Microsoft Docs"
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
  - "removeintchecks"
  - "/removeintchecks"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "removeintchecks compiler option [Visual Basic]"
  - "/removeintchecks compiler option [Visual Basic]"
  - "-removeintchecks compiler option [Visual Basic]"
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /removeintchecks
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Aktiviert bzw. deaktiviert Ganzzahlüberlauf\-Überprüfungen.  
  
## Syntax  
  
```  
/removeintchecks[+ | -]  
```  
  
## Argumente  
  
|||  
|-|-|  
|Begriff|Definition|  
|`+`  &#124; `-`|Optional.  Die `/removeintchecks-` Option bewirkt, dass der Compiler alle ganzzahligen Berechnungen für Sammel zu überprüfen.  Der Standardwert ist `/removeintchecks-`.<br /><br /> Wenn Sie `/removeintchecks` oder `/removeintchecks+` angeben, wird die Fehlerüberprüfung unterbunden. Berechnungen mit ganzen Zahlen werden dadurch schneller ausgeführt.  Bei deaktivierter Fehlerüberprüfung können jedoch falsche Ergebnisse gespeichert werden, ohne dass ein Fehler gemeldet wird, wenn die Datentypkapazitäten überschritten werden.|  
  
||  
|-|  
|So legen Sie \/removeintchecks in der integrierten Entwicklungsumgebung von Visual Studio fest|  
|1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  Weitere Informationen finden Sie unter [Introduction to the Project Designer](http://msdn.microsoft.com/de-de/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Klicken Sie auf die Schaltfläche **Erweitert**.<br />4.  Ändern Sie den Wert des Felds **Überprüfungen auf Ganzzahlüberlauf entfernen**.|  
  
## Beispiel  
 Im folgenden Code wird `Test.vb` kompiliert und die Ganzzahlüberlauf\-Überprüfung deaktiviert.  
  
```  
vbc /removeintchecks+ test.vb  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)