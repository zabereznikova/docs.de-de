---
title: "/recurse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
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
  - "/recurse compiler option [Visual Basic]"
  - "-recurse compiler option [Visual Basic]"
  - "recurse compiler option [Visual Basic]"
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /recurse
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Kompiliert Quellcodedateien in allen untergeordneten Verzeichnissen des angegebenen Verzeichnisses oder des Projektverzeichnisses.  
  
## Syntax  
  
```  
/recurse:[dir\]file  
```  
  
## Argumente  
 `dir`  
 Optional.  Das Verzeichnis, in dem die Suche beginnen soll.  Wird dieses nicht angegeben, beginnt die Suche im Projektverzeichnis.  
  
 `file`  
 Erforderlich.  Die zu suchende\(n\) Datei\(en\).  Platzhalterzeichen sind zulässig.  
  
## Hinweise  
 Sie können in einem Dateinamen Platzhalter verwenden, um alle entsprechenden Dateien im Projektverzeichnis zu kompilieren, ohne `/recurse` verwenden zu müssen.  Wenn Sie keinen Ausgabedateinamen angeben, legt der Compiler den Namen der ersten verarbeiteten Eingabedatei zugrunde.  Dies ist in der Regel die erste Datei in der alphabetischen Liste der kompilierten Dateien.  Es empfiehlt sich daher, mithilfe der `/out`\-Option einen Ausgabedateinamen anzugeben.  
  
> [!NOTE]
>  Die `/recurse`\-Option ist innerhalb der Entwicklungsumgebung von Visual Studio nicht verfügbar, sondern nur bei der Kompilierung über die Befehlszeile.  
  
## Beispiel  
 Mit dem folgenden Code werden alle [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Dateien im aktuellen Verzeichnis kompiliert.  
  
```  
vbc *.vb  
```  
  
 Mit dem folgenden Code werden alle [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Dateien im Verzeichnis `Test\ABC` und in allen darunter befindlichen Verzeichnissen kompiliert. Es wird die Datei `Test.ABC.dll` generiert.  
  
```  
vbc /target:library /out:Test.ABC.dll /recurse:Test\ABC\*.vb  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/out](../../../visual-basic/reference/command-line-compiler/out.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)