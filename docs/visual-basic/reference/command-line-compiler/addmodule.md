---
title: "/addmodule | Microsoft Docs"
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
  - "/addmodule compiler option [Visual Basic]"
  - "addmodule compiler option [Visual Basic]"
  - "-addmodule compiler option [Visual Basic]"
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# /addmodule
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Bewirkt, dass der Compiler dem Projekt, das Sie gerade kompilieren, sämtliche Typinformationen aus den angegebenen Dateien bereitstellt.  
  
## Syntax  
  
```  
/addmodule:fileList  
```  
  
## Argumente  
 `fileList`  
 Erforderlich.  Durch Komma getrennte Liste von Dateien, die Metadaten, aber keine Assemblymanifeste enthalten.  Dateinamen mit Leerzeichen müssen in Anführungszeichen \(""\) eingeschlossen werden.  
  
## Hinweise  
 Die vom `fileList`\-Parameter aufgeführten Dateien müssen mit der `/target:module`\-Option oder mit einer `/target:module`\-äquivalenten Option eines anderen Compilers erstellt werden.  
  
 Alle Module, die mit `/addmodule` hinzugefügt werden, müssen sich im selben Verzeichnis wie die Ausgabedatei zur Laufzeit befinden.  Das heißt, Sie können ein Modul in einem beliebigen Verzeichnis zur Kompilierungszeit angeben, aber das Modul muss sich zur Laufzeit im Anwendungsverzeichnis befinden.  Wenn dies nicht der Fall ist, wird ein <xref:System.TypeLoadException>\-Fehler ausgegeben.  
  
 Wenn Sie, implizit oder explizit, eine andere [\/target](../../../visual-basic/reference/command-line-compiler/target.md)\-Option als `/target:module` mit `/addmodule` angeben, werden die an `/addmodule` übergebenen Dateien zu einem Bestandteil der Assembly des Projekts.  Eine Assembly muss eine Ausgabedatei ausführen, zu der mindestens eine Datei mit `/addmodule` hinzugefügt wurde.  
  
 Importieren Sie mit [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md) Metadaten aus einer Datei, die eine Assembly enthält.  
  
> [!NOTE]
>  Die `/addmodule`\-Option ist innerhalb der Entwicklungsumgebung von Visual Studio nicht verfügbar, sondern nur bei der Kompilierung über die Befehlszeile.  
  
## Beispiel  
 Der folgende Code erstellt ein Modul.  
  
 [!code-vb[VbVbalrCompiler#47](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]  
  
 Der folgende Code importiert die Typen des Moduls.  
  
 [!code-vb[VbVbalrCompiler#48](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]  
  
 Wenn Sie `t1` ausführen, wird `802` ausgegeben.  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)