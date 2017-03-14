---
title: "/win32resource | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "/win32resource"
  - "win32resource"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/win32resource compiler option [Visual Basic]"
  - "-win32resource compiler option [Visual Basic]"
  - "win32resource compiler option [Visual Basic]"
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# /win32resource
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Fügt eine Win32‑Ressource in die Ausgabedatei ein.  
  
## Syntax  
  
```  
/win32resource:filename  
```  
  
## Argumente  
 `filename`  
 Der Name der Ressourcendatei, die der Ausgabedatei hinzugefügt werden soll.  Schließen Sie den Dateinamen in Anführungszeichen \(" "\) ein, wenn der Name ein Leerzeichen enthält.  
  
## Hinweise  
 Mit dem Microsoft Windows\-Ressourcencompiler \(RC\) können Sie eine Win32\-Ressourcendatei erstellen.  
  
 Eine Win32\-Ressource kann Release\- oder Bitmap\(Symbol\) Informationen enthalten, mit deren Hilfe die Anwendung in **Explorer** identifizieren.  Wenn Sie `/win32resource` nicht angeben, generiert der Compiler Versionsinformationen basierend auf der Assemblyversion.  Die `/win32resource`\-Option und die `/win32icon`\-Option schließen sich gegenseitig aus.  
  
 Siehe [\/linkresource](../../../visual-basic/reference/command-line-compiler/linkresource.md), wenn Sie auf eine [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]\-Ressourcendatei verweisen, oder [\/resource](../../../visual-basic/reference/command-line-compiler/resource.md), wenn Sie eine [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]\-Ressourcendatei anfügen möchten.  
  
> [!NOTE]
>  Die `/win32resource`\-Option ist innerhalb der Entwicklungsumgebung von Visual Studio nicht verfügbar, sondern nur bei der Kompilierung über die Befehlszeile.  
  
## Beispiel  
 Mit dem folgenden Code wird `In.vb` kompiliert und die Win32\-Ressourcendatei `Rf.res` angehängt:  
  
```  
vbc /win32resource:rf.res in.vb  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)