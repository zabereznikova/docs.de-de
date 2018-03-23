---
title: -win32manifest (Visual Basic)
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79b51117197f28cec21671eea4dd7b7f2f1cc306
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="-win32manifest-visual-basic"></a>-win32manifest (Visual Basic)
Identifiziert eine benutzerdefinierte Win32-Anwendungsmanifestdatei, die in die übertragbare ausführbare Datei (PE) eines Projekts eingebettet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`fileName`|Der Pfad der benutzerdefinierten Manifestdatei.|  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig bettet der Visual Basic-Compiler ein Anwendungsmanifest, das eine angeforderte Ausführungsebene asInvoker angibt. Das Manifest erstellt in demselben Ordner, in dem die ausführbare Datei wird erstellt, in der Regel der Ordner "bin\Debug" oder "bin\Release" bei der Verwendung von Visual Studio. Verwenden Sie diese Option den Namen der Datei angeben, wenn Sie ein benutzerdefiniertes Manifest, z. B. zum Festlegen einer angeforderte Ausführungsebene HighestAvailable oder RequireAdministrator, angeben möchten.  
  
> [!NOTE]
>  Diese Option und die [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) Option schließen sich gegenseitig. Wenn Sie versuchen, die beide Optionen in derselben Befehlszeile verwenden, erhalten Sie einen Buildfehler.  
  
 Eine Anwendung ohne Anwendungsmanifest, das eine angeforderte Anwendungsebene angibt, unterliegt der Datei- und Registrierungsvirtualisierung unter der Benutzerkontensteuerung in Windows Vista. Weitere Informationen zur Netzwerkvirtualisierung finden Sie unter [ClickOnce-Bereitstellung unter Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).  
  
 Ihre Anwendung unterliegen Virtualisierung aus, wenn eine der folgenden Bedingungen zutrifft:  
  
1.  Verwenden Sie die `-nowin32manifest` Option, und Sie bieten kein Manifests in einem späteren Schritt der Erstellung oder als Teil einer Windows-Ressourcendatei (res) mithilfe der `-win32resource` Option.  
  
2.  Sie stellen ein benutzerdefiniertes Manifest bereit, das keine angeforderte Ausführungsebene angibt.  
  
 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] erstellt eine Standard MANIFEST-Datei und speichert sie zusammen mit der ausführbaren Datei in den Debug- oder Releaseverzeichnissen. Sie können anzeigen oder bearbeiten Sie die Datei "Standard" app.manifest "durch Klicken auf **UAC-Einstellungen anzeigen** auf die **Anwendung** Registerkarte im Projekt-Designer. Weitere Informationen finden Sie unter [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
 Sie können das Anwendungsmanifest als benutzerdefinierte Postbuildschritt oder als Teil einer Win32-Ressourcendatei bereitstellen, mit der `-nowin32manifest` Option. Verwenden Sie dieselbe Option, wenn Ihre Anwendung der Datei- oder Registrierungsvirtualisierung unter Windows Vista unterliegen soll. Dies verhindert, dass der Compiler erstellt und eine Standard-Manifest in die PE-Datei einbetten.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt dem Standard-Manifest, dass die Visual Basic-Compiler in eine PE-Datei eingefügt.  
  
> [!NOTE]
>  Der Compiler Fügt eine standardmäßige Anwendungsname MyApplication.app eingefügt, in das XML-Manifest. Mit dieser Problemumgehung können Anwendungen unter Windows Server 2003 Service Pack 3 ausgeführt werden.  
  
```xml  
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
 [-nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
