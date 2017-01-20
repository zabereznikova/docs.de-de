---
title: "/sdkpath | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sdkpath"
  - "/sdkpath"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "-sdkpath compiler option [Visual Basic]"
  - "/sdkpath compiler option [Visual Basic]"
  - "sdkpath compiler option [Visual Basic]"
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /sdkpath
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt das Verzeichnis für Mscorlib.dll und Microsoft.Visualbasic.dll an.  
  
## Syntax  
  
```  
/sdkpath:path  
```  
  
## Argumente  
 `path`  
 Das Verzeichnis, das die für die Kompilierung zu verwendenden Versionen von Mscorlib.dll und Microsoft.Visualbasic.dll enthält.  Dieser Pfad wird erst beim Laden überprüft.  Setzen Sie den Verzeichnisnamen in doppelte Anführungszeichen \(" "\), wenn er ein Leerzeichen enthält.  
  
## Hinweise  
 Diese Option weist den [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Compiler an, die Dateien Mscorlib.dll und Microsoft.Visualbasic.dll aus einem Verzeichnis zu laden, das kein Standardverzeichnis ist.  Die `/sdkpath` \-Option ist dafür vorgesehen, in Verbindung mit [\/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md) verwendet zu werden.  In [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)] werden andere Versionen dieser Unterstützungsbibliotheken verwendet, um die Verwendung von Typen und Sprachfeatures zu verhindern, die nicht auf den Geräten verfügbar sind.  
  
> [!NOTE]
>  Die `/sdkpath`\-Option ist innerhalb der Entwicklungsumgebung von Visual Studio nicht verfügbar, sondern nur bei der Kompilierung über die Befehlszeile.  Die `/sdkpath`\-Option wird festgelegt, wenn ein [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Geräteprojekt geladen wird.  
  
 Mithilfe der `/vbruntime`\-Compileroption können Sie festlegen, dass der Compiler ohne Verweis auf die Visual Basic Runtime Library kompilieren soll.  Weitere Informationen finden Sie unter [\/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).  
  
## Beispiel  
 Mit dem folgenden Code wird `Myfile.vb` mit [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)] kompiliert. Dabei werden die Versionen von Mscorlib.dll und Microsoft.VisualBasic.dll verwendet, die sich im Standardinstallationsverzeichnis von [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)] auf Laufwerk C befinden.  In der Regel verwenden Sie die neueste Version von [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)].  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [\/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)   
 [\/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)