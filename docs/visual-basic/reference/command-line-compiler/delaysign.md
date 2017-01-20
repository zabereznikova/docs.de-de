---
title: "/delaysign | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "delaysign compiler option [Visual Basic]"
  - "/delaysign compiler option [Visual Basic]"
  - "-delaysign compiler option [Visual Basic]"
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /delaysign
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt an, ob die Assembly vollständig oder teilweise signiert wird.  
  
## Syntax  
  
```  
/delaysign[+ | -]  
```  
  
## Argumente  
 `+` &#124; `-`  
 Optional.  Verwenden Sie `/delaysign-`, wenn die Assembly vollständig signiert werden soll.  Verwenden Sie `/delaysign+`, wenn Sie nur den öffentlichen Schlüssel in die Assembly einfügen und Speicherplatz für den signierten Hash reservieren möchten.  Der Standardwert ist `/delaysign-`.  
  
## Hinweise  
 Die `/delaysign`\-Option ist nur dann wirksam, wenn sie zusammen mit [\/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) oder [\/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) verwendet wird.  
  
 Wenn Sie eine vollständig signierte Assembly anfordern, hasht der Compiler die Datei, die das Manifest \(die Assemblymetadaten\) enthält und signiert dieses Hash mit dem privaten Schlüssel.  Die erhaltene digitale Signatur wird in der Datei mit dem Manifest gespeichert.  Wenn eine Assembly verzögert signiert wird, berechnet und speichert der Compiler die Signatur nicht, sondern reserviert Speicherplatz in der Datei, damit die Signatur später hinzugefügt werden kann.  
  
 Beispielsweise kann ein Entwickler in einer Organisation mithilfe von `/delaysign+` nicht signierte Testversionen einer Assembly verteilen, die Tester für den globalen Assemblycache registrieren und verwenden können.  Wenn die Arbeit an der Assembly abgeschlossen ist, kann die für den privaten Schlüssel der Organisation verantwortliche Person die Assembly vollständig signieren.  Durch diese Aufgabenteilung wird der private Schlüssel der Organisation vor Offenlegung geschützt, während alle Entwickler an den Assemblys arbeiten können.  
  
 Weitere Informationen über das Signieren einer Assembly finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md).  
  
### So legen Sie \/delaysign in der integrierten Entwicklungsumgebung von Visual Studio fest  
  
1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  Weitere Informationen finden Sie unter [Introduction to the Project Designer](http://msdn.microsoft.com/de-de/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Klicken Sie auf die Registerkarte **Signierung**.  
  
3.  Legen Sie den Wert im Feld **Nur verzögerte Signierung** fest.  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)   
 [\/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)