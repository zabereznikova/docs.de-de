---
title: "/keyfile | Microsoft Docs"
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
  - "/keyfile compiler option [Visual Basic]"
  - "keyfile compiler option [Visual Basic]"
  - "-keyfile compiler option [Visual Basic]"
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# /keyfile
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Gibt eine Datei mit einem Schlüssel oder Schlüsselpaar an, um einer Assembly einen starken Namen zuzuweisen.  
  
## Syntax  
  
```  
/keyfile:file  
```  
  
## Argumente  
 `file`  
 Erforderlich.  Die Datei, die den Schlüssel enthält.  Wenn der Dateiname ein Leerzeichen enthält, schließen Sie den Namen in Anführungszeichen \(" "\) ein.  
  
## Hinweise  
 Der Compiler fügt den öffentlichen Schlüssel in das Assemblymanifest ein und signiert dann die endgültige Assembly mit dem privaten Schlüssel.  Geben Sie `sn -k file` in der Befehlszeile ein, um eine Schlüsseldatei zu generieren.  Weitere Informationen finden Sie unter [Sn.exe \(Strong Name Tool\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md).  
  
 Wenn Sie mit `/target:module` kompilieren, wird der Name der Schlüsseldatei im Modul gespeichert und in die Assembly integriert, die beim Kompilieren einer Anwendung mit [\/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) erstellt wird.  
  
 Die Verschlüsselungsinformationen können auch mit [\/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) an den Compiler übergeben werden.  Verwenden Sie [\/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md), wenn die Assembly teilweise signiert werden soll.  
  
 Sie können diese Option auch als benutzerdefiniertes Attribut \(<xref:System.Reflection.AssemblyKeyFileAttribute>\) im Quellcode für ein beliebiges MSIL\-Modul \(Microsoft Intermediate Language\) angeben.  
  
 Wenn sowohl `/keyfile` als auch [\/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) \(entweder durch eine Befehlszeilenoption oder durch ein benutzerdefiniertes Attribut\) in derselben Kompilierung angegeben sind, verwendet der Compiler zuerst den Schlüsselcontainer.  Wenn dies erfolgreich ist, wird die Assembly mit den Informationen aus dem Schlüsselcontainer signiert.  Wenn der Compiler den Schlüsselcontainer nicht finden kann, wird die durch `/keyfile` angegebene Datei verwendet.  Wenn dies erfolgreich ist, wird die Assembly mit den Informationen aus der Schlüsseldatei signiert, und die Schlüsselinformationen werden im Schlüsselcontainer installiert \(vergleichbar mit `sn -i`\). Der Schlüsselcontainer ist somit bei der nächsten Kompilierung gültig.  
  
 Beachten Sie, dass eine Schlüsseldatei möglicherweise nur den öffentlichen Schlüssel enthält.  
  
 Weitere Informationen über das Signieren einer Assembly finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md).  
  
> [!NOTE]
>  Die `/keyfile`\-Option ist innerhalb der Entwicklungsumgebung von [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] nicht verfügbar, sondern nur bei der Kompilierung über die Befehlszeile.  
  
## Beispiel  
 Mit dem folgenden Code wird die Quelldatei `Input.vb` kompiliert und eine Schlüsseldatei angegeben.  
  
```  
vbc /keyfile:myfile.sn input.vb  
```  
  
## Siehe auch  
 [Assemblys und der globale Assemblycache](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)