---
title: /win32manifest (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b07d5816e5bb80a95e608fa7214a2db48ebac0dc
ms.lasthandoff: 03/13/2017

---
# <a name="win32manifest-visual-basic"></a>/win32manifest (Visual Basic)
Identifiziert eine benutzerdefinierte Win32-Anwendungsmanifestdatei, die in die übertragbare ausführbare Datei (PE) eines Projekts eingebettet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
/win32manifest: fileName  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`fileName`|Der Pfad der benutzerdefinierten Manifestdatei.|  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig bettet der Visual Basic-Compiler ein Anwendungsmanifest eine angeforderte Ausführungsebene "asInvoker" angibt. Das Manifest erstellt in demselben Ordner, in dem die ausführbare Datei erstellt wird, in der Regel Ordner Bin\Debug oder Bin\Release bei Verwendung von Visual Studio. Wenn Sie möchten ein benutzerdefiniertes Manifest, z. B. zum Festlegen einer angeforderten Ausführungsebene "highestAvailable" oder "requireAdministrator", verwenden Sie diese Option den Namen der Datei angeben.  
  
> [!NOTE]
>  Diese Option und die [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) Option schließen sich gegenseitig. Wenn Sie versuchen, in derselben Befehlszeile beide Optionen verwenden, erhalten Sie einen Buildfehler.  
  
 Eine Anwendung ohne Anwendungsmanifest gibt an, dass eine angeforderte Ausführungsebene unterliegen Datei-/Registrierungsvirtualisierung der Benutzerkontensteuerung in Windows Vista ist. Weitere Informationen zur Virtualisierung finden Sie unter [ClickOnce-Bereitstellung unter Windows Vista](https://docs.microsoft.com/visualstudio/deployment/clickonce-deployment-on-windows-vista).  
  
 Die Anwendung wird Virtualisierung sein, wenn eine der folgenden Situationen zutrifft:  
  
1.  Verwenden Sie die `/nowin32manifest` Option, und Sie bieten kein Manifest in einem späteren Buildschritt oder als Teil einer Windows-Ressource (res)-Datei mithilfe der `/win32resource` Option.  
  
2.  Sie geben ein benutzerdefiniertes Manifest, das keine angeforderte Ausführungsebene angibt.  
  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]erstellt eine Standardmanifestdatei und speichert sie in den Verzeichnissen Debug- und zusammen mit der ausführbaren Datei. Sie können anzeigen oder bearbeiten Sie die Standarddatei app.manifest durch Klicken auf **UAC-Anzeigeeinstellungen** auf der **Anwendung** Registerkarte im Projekt-Designer. Weitere Informationen finden Sie unter [Anwendungsseite, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
 Sie können das Anwendungsmanifest einer benutzerdefinierten Postbuildschritt oder als Teil einer Win32-Ressourcendatei bereitstellen, mit der `/nowin32manifest` Option. Verwenden Sie dieselbe Option, wenn Sie Ihre Anwendung unter Windows Vista der Datei- oder Registrierungsvirtualisierung unterliegen soll. Dies verhindert, dass der Compiler erstellt und eine Standard-Manifest in die PE-Datei einbetten.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel enthält dem Standardmanifest, Visual Basic-Compiler in eine PE eingefügt.  
  
> [!NOTE]
>  Der Compiler Fügt eine standardmäßige Anwendungsname MyApplication.app eingefügt, in das XML-Manifest. Dies ist eine Lösung zum Aktivieren von Anwendungen auf Windows Server 2003 Service Pack 3 ausgeführt.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/NoWin32Manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
