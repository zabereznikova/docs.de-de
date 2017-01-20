---
title: "/win32icon | Microsoft Docs"
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
  - "win32icon compiler option [Visual Basic]"
  - "-win32icon compiler option [Visual Basic]"
  - "/win32icon compiler option [Visual Basic]"
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /win32icon
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Fügt eine ICO\-Datei in die Ausgabedatei ein.  Diese ICO\-Datei wird die Ausgabedatei in **Explorer** dar.  
  
## Syntax  
  
```  
/win32icon:filename  
```  
  
## Argumente  
  
|||  
|-|-|  
|Begriff|Definition|  
|`filename`|Die ICO‑Datei, die der Ausgabedatei hinzugefügt werden soll.  Schließen Sie den Dateinamen in Anführungszeichen \(" "\) ein, wenn der Name ein Leerzeichen enthält.|  
  
## Hinweise  
 Eine ICO\-Datei können Sie mit dem Ressourcencompiler \(RC\) von Microsoft Windows erstellen.  Der Ressourcencompiler wird gestartet, wenn Sie ein Visual C\+\+\-Programm kompilieren. Die ICO\-Datei wird anhand der RC\-Datei erstellt.  Die `/win32icon`\-Option und die `/win32resource`\-Option schließen sich gegenseitig aus.  
  
 Siehe [\/linkresource](../../../visual-basic/reference/command-line-compiler/linkresource.md), wenn Sie auf eine [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Ressourcendatei verweisen, oder [\/resource](../../../visual-basic/reference/command-line-compiler/resource.md), wenn Sie eine [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Ressourcendatei anfügen möchten.  Informationen zum Importieren einer RES\-Datei finden Sie unter [\/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md).  
  
||  
|-|  
|So legen Sie \/win32icon in der Visual Studio\-IDE fest|  
|1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  Weitere Informationen finden Sie unter [Introduction to the Project Designer](http://msdn.microsoft.com/de-de/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Klicken Sie auf die Registerkarte **Anwendung**.<br />3.  Ändern Sie den Wert im Feld **Symbol**.|  
  
## Beispiel  
 Mit dem folgenden Code wird `In.vb` kompiliert und die ICO\-Datei `Rf.ico` angehängt.  
  
```  
vbc /win32icon:rf.ico in.vb  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)