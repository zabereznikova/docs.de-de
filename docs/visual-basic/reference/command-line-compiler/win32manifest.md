---
title: "/win32manifest (Visual Basic) | Microsoft Docs"
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
  - "/win32manifest compiler option [Visual Basic]"
  - "win32manifest compiler option [Visual Basic]"
  - "-win32manifest compiler option [Visual Basic]"
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# /win32manifest (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Identifiziert eine benutzerdefinierte Win32\-Anwendungsmanifestdatei, die in die übertragbare ausführbare Datei \(Portable Executable, PE\) eines Projekts eingebettet werden soll.  
  
## Syntax  
  
```  
/win32manifest: fileName  
```  
  
## Argumente  
  
|||  
|-|-|  
|Begriff|Definition|  
|`fileName`|Der Pfad der benutzerdefinierten Manifestdatei.|  
  
## Hinweise  
 Standardmäßig bettet der Visual Basic\-Compiler ein Anwendungsmanifest ein, das die angeforderte Ausführungsebene asInvoker angibt.  Das Manifest wird in dem Ordner erstellt, in dem die ausführbare Datei erstellt wird, bei Verwendung von Visual Studio üblicherweise im Ordner bin\\Debug oder bin\\Release.  Wenn Sie ein benutzerdefiniertes Manifest bereitstellen möchten \(z. B., um die angeforderte Ausführungsebene highestAvailable oder requireAdministrator anzugeben\), geben Sie den Namen der Datei mit dieser Option an.  
  
> [!NOTE]
>  Diese Option und die [\/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)\-Option schließen sich gegenseitig aus.  Wenn Sie in derselben Befehlszeile beide Optionen angeben, tritt ein Buildfehler auf.  
  
 Eine Anwendung ohne ein Anwendungsmanifest, das die angeforderte Ausführungsebene angibt, unterliegt der Datei\-\/Registrierungsvirtualisierung der Benutzerkontensteuerung von Windows Vista.  Weitere Informationen über Virtualisierung finden Sie unter [ClickOnce Deployment on Windows Vista](/visual-studio/deployment/clickonce-deployment-on-windows-vista).  
  
 Eine Anwendung unterliegt der Virtualisierung, wenn eine der folgenden Bedingungen erfüllt ist:  
  
1.  Sie verwenden die `/nowin32manifest`\-Option und Sie stellen in einem späteren Buildschritt oder als Teil einer RES \(Windows Resource\)\-Datei mit der `/win32resource`\-Option kein Manifest bereit.  
  
2.  Sie stellen ein benutzerdefiniertes Manifest bereit, das keine angeforderte Ausführungsebene angibt.  
  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] erstellt eine Standardmanifestdatei und speichert diese zusammen mit der ausführbaren Datei in den Debug\- und Releaseverzeichnissen.  Sie können die Standarddatei app.manifest anzeigen oder bearbeiten, indem Sie im Projekt\-Designer auf der Registerkarte **Anwendung** auf **Einstellungen für die Benutzerkontensteuerung anzeigen** klicken. Weitere Informationen finden Sie unter [Seite "Anwendung", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic).  
  
 Sie können das Anwendungsmanifest in einem benutzerdefinierten Postbuildschritt oder mit der `/nowin32manifest`\-Option als Teil einer Win32\-Ressourcendatei bereitstellen.  Verwenden Sie dieselbe Option, wenn Sie möchten, dass Ihre Anwendung auf Windows Vista der Datei\- oder Registrierungsvirtualisierung unterliegt.  Dadurch wird verhindert, dass der Compiler ein Standardmanifest erstellt und in die PE\-Datei einbettet.  
  
## Beispiel  
 Das folgende Beispiel enthält das Standardmanifest, das vom Visual Basic\-Compiler in eine PE eingefügt wird.  
  
> [!NOTE]
>  In das Manifest\-XML wird vom Compiler der Standardanwendungsname MyApplication.app eingefügt.  Dies ist eine Problemumgehung, damit Anwendungen auf Windows Server 2003, Service Pack 3 ausgeführt werden.  
  
```  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <assemblyIdentity version="1.0.0.0" name="MyApplication.app"/>  
  <trustInfo xmlns="urn:schemas-microsoft-com:asm.v2">  
    <security>  
      <requestedPrivileges xmlns="urn:schemas-microsoft-com:asm.v3">  
        <requestedExecutionLevel level="asInvoker"/>  
      </requestedPrivileges>  
    </security>  
  </trustInfo>  
</assembly>  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/nowin32manifest](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)