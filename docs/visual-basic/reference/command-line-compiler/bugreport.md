---
title: "/bugreport | Microsoft Docs"
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
  - "-bugreport compiler option [Visual Basic]"
  - "bugreport compiler option [Visual Basic]"
  - "/bugreport compiler option [Visual Basic]"
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# /bugreport
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Erstellt eine Datei, die Sie beim Einreichen eines Problemberichts verwenden können.  
  
## Syntax  
  
```  
/bugreport:file  
```  
  
## Argumente  
  
|||  
|-|-|  
|Begriff|Definition|  
|`file`|Erforderlich.  Der Name der Datei, die den Problembericht enthalten soll.  Schließen Sie den Dateinamen in Anführungszeichen \(""\) ein, wenn der Name ein Leerzeichen enthält.|  
  
## Hinweise  
 Die folgenden Informationen werden zu `file` hinzugefügt:  
  
-   Eine Kopie aller in der Kompilierung verwendeten Quellcodedateien.  
  
-   Eine Liste der bei der Kompilierung verwendeten Compileroptionen.  
  
-   Versionsinformationen zum Compiler, zur Common Language Runtime und zum Betriebssystem.  
  
-   Compilerausgabe, falls vorhanden.  
  
-   Eine Beschreibung des Problems. Sie werden aufgefordert, diese Beschreibung einzugeben.  
  
-   Eine Beschreibung Ihres Vorschlags zur Beseitigung des Problems. Sie werden aufgefordert, diese Beschreibung einzugeben.  
  
 Da Kopien aller Quellcodedateien in `file` gespeichert werden, empfiehlt es sich, den \(vermuteten\) Codefehler in einem möglichst kurzen Programm zu reproduzieren.  
  
> [!IMPORTANT]
>  Die `/bugreport`\-Option erstellt eine Datei, die möglicherweise vertrauliche Informationen enthält.  Dazu gehören die aktuelle Uhrzeit, Compilerversion, [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Version, Betriebssystemversion, Benutzername, die Befehlszeilenargumente, mit denen der Compiler ausgeführt wurde, der gesamte Quellcode und die binäre Form aller Assemblys, auf die verwiesen wird.  Auf diese Option kann durch Angabe von Befehlszeilenoptionen in der Datei Web.config für eine serverseitige Kompilierung einer [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)]\-Anwendung zugegriffen werden.  Um dies zu verhindern, ändern Sie die Datei Machine.config so, dass es Benutzern nicht erlaubt ist, auf dem Server zu kompilieren.  
  
 Wenn diese Option mit `/errorreport:prompt`, `/errorreport:queue` oder `/errorreport:send` verwendet wird und in der Anwendung ein interner Compilerfehler auftritt, werden die in `file` enthaltenen Informationen an die Microsoft Corporation gesendet.  Diese Informationen erleichtern es den Microsoft\-Technikern, die Fehlerursache zu identifizieren und die nächste Version von [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] in entsprechender Hinsicht zu verbessern.  Standardmäßig werden keine Informationen an Microsoft gesendet.  Wenn Sie eine Anwendung jedoch mit `/errorreport:queue` kompilieren \(standardmäßig aktiviert\), sammelt die Anwendung ihre Fehlerberichte.  Wenn sich dann der Administrator des Computers anmeldet, wird durch das Fehlerberichtssystem ein Popupfenster angezeigt, mit dem der Administrator alle seit der Anmeldung angefallenen Fehlerberichte an Microsoft weiterleiten kann.  
  
> [!NOTE]
>  Die `/bugreport`\-Option ist innerhalb der Entwicklungsumgebung von Visual Studio nicht verfügbar, sondern nur, wenn Sie in der Befehlszeile kompilieren.  
  
## Beispiel  
 Im folgenden Beispiel wird `T2.vb` kompiliert, und alle Informationen für den Problembericht werden in der Datei `Problem.txt` gespeichert.  
  
```  
vbc /bugreport:problem.txt t2.vb  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/debug](../../../visual-basic/reference/command-line-compiler/debug.md)   
 [\/errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [trustLevel\-Element für securityPolicy \(ASP.NET\-Einstellungsschema\)](http://msdn.microsoft.com/de-de/729ab04c-03da-4ee5-86b1-be9d08a09369)