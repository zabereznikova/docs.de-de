---
title: "/linkresource (Visual Basic) | Microsoft Docs"
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
  - "/linkresource compiler option [Visual Basic]"
  - "-linkresource compiler option [Visual Basic]"
  - "linkresource compiler option [Visual Basic]"
  - "/linkres compiler option [Visual Basic]"
  - "linkres compiler option [Visual Basic]"
  - "-linkres compiler option [Visual Basic]"
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# /linkresource (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Erstellt einen Link zu einer verwalteten Ressource.  
  
## Syntax  
  
```  
/linkresource:filename[,identifier[,public|private]]  
' -or-  
/linkres:filename[,identifier[,public|private]]  
```  
  
## Argumente  
 `filename`  
 Erforderlich.  Die Ressourcendatei, die mit der Assembly verknüpft werden soll.  Wenn der Dateiname ein Leerzeichen enthält, schließen Sie den Namen in Anführungszeichen \(" "\) ein.  
  
 `identifier`  
 Optional.  Der logische Name für die Ressource.  Der Name, der zum Laden der Ressource verwendet wird.  Der Standardwert ist der Dateiname.  Sie können wahlweise angeben, ob die Datei im Assemblymanifest öffentlich oder privat ist. Beispiel: `/linkres:filename.res,myname.res,public`.  In der Standardeinstellung ist `filename` in der Assembly öffentlich.  
  
## Hinweise  
 Mit der `/linkresource`\-Option können Sie die Ressourcendatei nicht in der Ausgabedatei einbetten. Verwenden Sie dazu die `/resource`\-Option.  
  
 Die  `/linkresource`\-Option erfordert eine der `/target`\-Optionen, jedoch nicht `/target:module`.  
  
 Wenn `filename` einer [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Ressourcendatei entspricht, die beispielsweise durch den [Resgen.exe \(Resource File Generator\)](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md) oder in der Entwicklungsumgebung erstellt wurde, kann mit Membern im <xref:System.Resources>\-Namespace darauf zugegriffen werden.  \(Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager>.\) Mit den Methoden der <xref:System.Reflection.Assembly>\-Klasse, die mit `GetManifestResource` beginnen, greifen Sie zur Laufzeit auf alle anderen Ressourcen zu.  
  
 Der Dateiname kann jedes Dateiformat haben.  Sie können beispielsweise eine systemeigene DLL zum Bestandteil der Assembly machen, damit sie im globalen Assemblycache installiert und aus verwaltetem Code in der Assembly darauf zugegriffen werden kann.  
  
 Die Kurzform von `/linkresource` ist `/linkres`.  
  
> [!NOTE]
>  Die `/linkresource`\-Option ist innerhalb der Entwicklungsumgebung von Visual Studio nicht verfügbar, sondern nur, wenn Sie von der Befehlszeile aus kompilieren.  
  
## Beispiel  
 Mit dem folgenden Code wird `In.vb` kompiliert und mit der Ressourcendatei `Rf.resource` verknüpft.  
  
```  
vbc /linkresource:rf.resource in.vb  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [\/resource](../../../visual-basic/reference/command-line-compiler/resource.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)