---
title: -win32manifest
ms.date: 03/13/2018
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
ms.openlocfilehash: cef1e6c19e7fdd6fc9f42c8fc36008314ea80a80
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349128"
---
# <a name="-win32manifest-visual-basic"></a>-win32manifest (Visual Basic)
Identifiziert eine benutzerdefinierte Win32-Anwendungsmanifestdatei, die in die übertragbare ausführbare Datei (PE) eines Projekts eingebettet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`fileName`|Pfad der benutzerdefinierten Manifestdatei.|  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig bettet der Visual Basic-Compiler ein Anwendungsmanifest ein, das eine angeforderte Ausführungsebene als „asInvoker“ angibt. Er erstellt das Manifest in demselben Ordner, in dem die ausführbare Datei erstellt wird. Wenn Sie Visual Studio verwenden, ist dies in der Regel der Ordner „bin\Debug“ oder „bin\Release“. Wenn Sie ein benutzerdefiniertes Manifest bereitstellen möchten, z. B. um die angeforderte Ausführungsebene „highestAvailable“ oder „requireAdministrator“ anzugeben, verwenden Sie diese Option zur Angabe des Dateinamens.  
  
> [!NOTE]
> Diese Option und die Option [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) schließen sich gegenseitig aus. Wenn Sie versuchen, beide Optionen in derselben Befehlszeile zu verwenden, wird ein Buildfehler angezeigt.  
  
 Eine Anwendung ohne Anwendungsmanifest, das eine angeforderte Anwendungsebene angibt, unterliegt der Datei- und Registrierungsvirtualisierung unter der Benutzerkontensteuerung in Windows Vista. Weitere Informationen über Virtualisierung finden Sie unter [ClickOnce-Bereitstellung unter Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).  
  
 Die Anwendung unterliegt der Virtualisierung, wenn eine der folgenden Bedingungen erfüllt ist:  
  
1. Sie verwenden die Option `-nowin32manifest` und stellen in einem späteren Buildschritt oder als Teil einer Windows-Ressourcendatei (RES-Datei) kein Manifest bereit, indem Sie die Option `-win32resource` verwenden.  
  
2. Sie stellen ein benutzerdefiniertes Manifest bereit, das keine angeforderte Ausführungsebene angibt.  
  
 Visual Studio erstellt eine MANIFEST-Standarddatei und speichert sie zusammen mit der ausführbaren Datei in den Debug- oder Releaseverzeichnissen. Klicken Sie zum Anzeigen oder Bearbeiten der „app.manifest“-Standarddatei im Projekt-Designer auf der Registerkarte **Anwendung** auf **UAC-Einstellungen anzeigen**. Weitere Informationen finden Sie unter [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
 Sie können das Anwendungsmanifest als benutzerdefinierten Postbuildschritt oder als Teil einer Win32-Ressourcendatei bereitstellen, indem Sie die Option `-nowin32manifest` verwenden. Verwenden Sie dieselbe Option, wenn Ihre Anwendung der Datei- oder Registrierungsvirtualisierung unter Windows Vista unterliegen soll. Dadurch wird verhindert, dass der Compiler ein Standardmanifest in der PE-Datei erstellt und einbettet.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt das Standardmanifest, das der Visual Basic-Compiler in eine PE-Datei einfügt.  
  
> [!NOTE]
> Der Compiler fügt einen Standardanwendungsnamen („MyApplication.app“) in die XML-Manifestdatei ein. Mit dieser Problemumgehung können Anwendungen unter Windows Server 2003 Service Pack 3 ausgeführt werden.  
  
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

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
