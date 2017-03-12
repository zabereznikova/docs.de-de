---
title: "/resource (Visual Basic) | Microsoft Docs"
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
  - "/resource compiler option [Visual Basic]"
  - "-resource compiler option [Visual Basic]"
  - "/res compiler option [Visual Basic]"
  - "res compiler option [Visual Basic]"
  - "-res compiler option [Visual Basic]"
  - "resource compiler option [Visual Basic]"
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# /resource (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Bettet eine verwaltete Ressource in eine Assembly ein.  
  
## Syntax  
  
```  
/resource:filename[,identifier[,public|private]]  
' -or-  
/res:filename[,identifier[,public|private]]  
```  
  
## Argumente  
  
|||  
|-|-|  
|Begriff|Definition|  
|`filename`|Erforderlich.  Der Name der Ressourcendatei, die in die Ausgabedatei eingebettet werden soll.  In der Standardeinstellung ist `filename` in der Assembly öffentlich.  Schließen Sie den Dateinamen in Anführungszeichen \(" "\) ein, wenn der Name ein Leerzeichen enthält.|  
|`identifier`|Optional.  Der logische Name der Ressource. Dieser wird zum Laden der Ressource verwendet.  Der Standardwert ist der Dateiname.  Sie können wahlweise angeben, ob die Ressource im Assemblymanifest öffentlich oder privat ist. Beispiel: `/res:``filename.res`, `myname.res`, `public`|  
  
## Hinweise  
 Verwenden Sie `/linkresource`, wenn Sie eine Ressource mit einer Assembly verknüpfen möchten und die Ressourcendatei nicht in der Ausgabedatei platziert werden soll.  
  
 Wenn `filename` eine [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Ressourcendatei ist, die beispielsweise durch den [Resgen.exe \(Resource File Generator\)](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md) oder in der Entwicklungsumgebung erstellt wurde, kann mit Membern im <xref:System.Resources>\-Namespace darauf zugegriffen werden \(weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager>\).  Um zur Laufzeit auf alle anderen Ressourcen zuzugreifen, verwenden Sie eine der folgenden Methoden: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A> oder <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.  
  
 `/res` ist die Kurzform von `/resource` .  
  
 Informationen über das `/resource` in der Visual Studio\-IDE finden Sie unter [Verwalten von Anwendungsressourcen \(.NET\)](/visual-studio/ide/managing-application-resources-dotnet).  
  
## Beispiel  
 Mit dem folgenden Code wird `In.vb` kompiliert und die Ressourcendatei `Rf.resource` angehängt.  
  
```  
vbc /res:rf.resource in.vb  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)   
 [\/linkresource](../../../visual-basic/reference/command-line-compiler/linkresource.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)